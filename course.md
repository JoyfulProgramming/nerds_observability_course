# Fix Bugs 20x Faster - From Zero to Incident Superhero Workshop

Learn how to diagnose and fix bugs 20x faster using modern observability techniques and a systematic approach to debugging.

## Tasks


### 1. Set Up Your Development Environment

[SCRIPT]
Hey there! Before we dive into debugging, we need to get our tools ready. In this section, I'll walk you through setting up three essential services:
- GitHub for version control
- Replit for our development environment
- And Dynatrace for observability

Don't worry if you're new to any of these - I'll guide you through each step. Let's get started!
[END SCRIPT]

**Introduction:** Before we can start debugging, we need to set up our development environment with all the necessary tools and services.

**Description:** To get started with this workshop, you'll need to set up three key services:

1. **GitHub Account Setup**
   - Go to [GitHub Signup](https://github.com/signup)
   - Complete the registration process

2. **Replit Account Setup**
   - Visit [Replit Signup](https://replit.com/signup)
   - Create your account
   - Navigate to the template: [Fix Bugs 20x Faster Template](https://replit.com/@johngallagher2/Fix-Bugs-20x-Faster)
   - Click 'Remix Template' to create your own copy

3. **Dynatrace Account Setup**
   - Go to [Dynatrace Signup](https://www.dynatrace.com/signup)
   - Sign up for the 15-day free trial
   - Enter your email and details
   - Wait for account setup confirmation

Once you have access to all three services, proceed to the next task.

**Acceptance Criteria:**
- GitHub account created and verified
- Replit account created and template remixed
- Dynatrace trial account activated
- All services are accessible and working

**Learning Materials:**
- [GitHub Signup](https://github.com/signup)
- [Replit Signup](https://replit.com/signup)
- [Dynatrace Signup](https://www.dynatrace.com/signup)

[SCRIPT]
Great! Let me show you what it looks like when everything is set up correctly:

First, here's my GitHub account - you can see I'm logged in and ready to go.

Next, in Replit, I've already remixed the template. Notice the unique URL showing it's my copy.

Finally, here's my Dynatrace dashboard. The trial is active and I can access all the monitoring features.

Perfect! Now you're ready to start debugging with all three services properly configured.
[END SCRIPT]


### 2. Understand the Cross-Stitch Pattern Preview Problem

[SCRIPT]
Let me show you the application we'll be debugging today. It's a cross-stitch pattern preview generator that helps designers showcase their work on Etsy.

In this lesson you'll upload one pattern that works and one that doesn't and watch the app go BANG!
[END SCRIPT]


**Introduction:** Now that we have our environment set up, let's understand the business problem we're trying to solve.

**Description:** You're working on a cross-stitch pattern business application that helps designers upload pattern previews to their Etsy shop. The application:

- Is built with Ruby on Rails
- Takes FCJSON files from FlossCross
- Renders preview images

To see the current functionality:

1. Press 'Run' in your Replit environment
2. Wait for the webview to open
3. Download the sample `MonaLisa.fcjson` file
4. Upload it to the application
5. Click 'Update Pattern'
6. Wait ~30 seconds to see the generated image

Next, try to reproduce the bug:

1. Go back to the home page
2. Download and upload the `Puffins.fcjson` file
3. Observe that the app hangs and no images are shown

This is the bug we'll be investigating and fixing throughout this workshop.


**Acceptance Criteria:**
- Successfully ran the application in Replit
- Successfully generated preview for MonaLisa pattern
- Reproduced the bug with Puffins pattern
- Understood the basic application workflow

[SCRIPT]
So here's what you should have seen.

I start the app.

Watch what happens when I upload this MonaLisa pattern... it works perfectly! The preview generates in about 30 seconds.

But now, let me show you the bug. I'll upload this Puffins pattern and... nothing happens. The app just hangs.

This is the mystery we'll solve together using modern debugging techniques. Let's get started!
[END SCRIPT]


### 3. Set Up Basic Error Tracking

**Introduction:** With the bug reproduced, we'll start implementing basic error tracking.

**Description:** To begin debugging, we need to see the errors that are occurring. Follow these steps:

1. In Replit, access the error logs using one of these methods:
   - Use the top menu dropdown and click the Play icon next to 'Show Errors'
   - OR press `Command Shift P`, type 'Shell', and run `bin/errors`

2. Examine the error output:
   - Look for the stack trace
   - Identify that the error is coming from `Pattern#add_border_to_preview`

3. Install the required logging gems:
```bash
bundle add semantic_logger rails_semantic_logger
```

4. Create a new file `lib/flat_json_formatter.rb` with the provided formatter code

5. Create `config/initializers/semantic_logger.rb` with the logging configuration

This setup will allow us to start gathering more detailed information about the errors occurring in our application.

**Acceptance Criteria:**
- Semantic Logger gems installed successfully
- Flat JSON formatter created and configured
- Semantic Logger initializer created
- Error logs are accessible and readable

### 4. Implement Detailed Error Logging

**Introduction:** With basic error tracking in place, we'll add more detailed logging to help identify the root cause.

**Description:** We need to add more context to our logs to understand what's happening when the error occurs. Modify the `Pattern#add_border_to_preview` method in `app/models/pattern.rb`:

1. Add the following logging context:
```ruby
def add_border_to_preview(size)
  SemanticLogger.tagged(
    "app.pattern.id" => id,
    "app.pattern.height" => height,
    "app.pattern.width" => width,
    "code.namespace" => "Pattern",
    "code.function.name" => "add_border_to_preview",
    "app.code.args.size" => size
  ) do
    # ... existing code ...
    Rails.logger.info(
      message: "Border added to preview",
      "event.name" => "app.pattern.border_added_to_preview"
    )
  rescue StandardError => e
    Rails.logger.error(
      message: "Error adding border to preview",
      "event.name" => "app.pattern.border_added_to_preview",
      exception: e
    )
    raise e
  end
end
```

This will give us crucial information about the pattern dimensions and operation status.

**Acceptance Criteria:**
- Added logging context to Pattern#add_border_to_preview
- Implemented success and error logging
- Logs include pattern dimensions
- Logs include operation status

### 5. Analyze Error Patterns Using Dynatrace

**Introduction:** Now that we have detailed logging, let's analyze the data to identify patterns in the errors.

**Description:** Use Dynatrace to analyze the error patterns:

1. Run the test script to generate more data:
   - Click the dropdown next to 'Stop'
   - Select 'Hammer' or run `bin/hammer` in the console

2. In Dynatrace:
   - Navigate to Logs
   - Filter for `event.name = "app.pattern.border_added_to_preview"`
   - Add columns for `error`, `app.pattern.height`, and `app.pattern.width`
   - Sort by the `error` column

3. Analyze the data to identify patterns:
   - Look for correlations between errors and pattern dimensions
   - Notice that errors occur when width is greater than height

This analysis suggests the issue might be related to image orientation.

**Acceptance Criteria:**
- Generated test data using the hammer script
- Set up appropriate filters in Dynatrace
- Identified correlation between errors and dimensions
- Recognized potential orientation-related issue

### 6. Add Orientation Tracking

**Introduction:** Having identified a potential orientation issue, let's add orientation tracking to confirm our hypothesis.

**Description:** To verify if orientation is the root cause, add orientation tracking to our logs:

1. Update the logging context in `Pattern#add_border_to_preview`:
```ruby
SemanticLogger.tagged(
  "app.pattern.id" => id,
  "app.pattern.height" => height,
  "app.pattern.width" => width,
  "code.namespace" => "Pattern",
  "code.function.name" => "add_border_to_preview",
  "app.code.args.size" => size,
  "app.pattern.orientation" => orientation
) do
```

2. In Dynatrace, create a new query to analyze orientation data:
```
fetch logs
| filter matchesValue(event.name, "app.pattern.border_added_to_preview")
| summarize count(), by: { error, app.pattern.orientation }
```

3. Analyze the results to confirm if all errors occur with landscape orientation.

**Acceptance Criteria:**
- Added orientation to logging context
- Created orientation analysis query in Dynatrace
- Confirmed correlation between errors and orientation
- Identified missing landscape configuration as root cause

### 7. Implement the Fix for Landscape Orientation

**Introduction:** Now that we've confirmed the root cause, let's implement the fix.

**Description:** The root cause has been identified: the `PREVIEW_WITH_BORDER_DIMENSIONS` hash is missing the `:landscape` configuration. To fix this:

1. Apply the fix using git:
```bash
git fetch
git stash
git cherry-pick e8d138ec16991d26b683c11a0ecdaa175ab3871c
git stash pop
```

2. Verify the fix:
   - Restart the server
   - Upload the Puffins.fcjson file again
   - Confirm that the preview images are generated successfully

3. Review the logs in Dynatrace to confirm no more orientation-related errors are occurring.

**Acceptance Criteria:**
- Applied the landscape orientation fix
- Successfully generated Puffins pattern preview
- Verified no new orientation-related errors
- Confirmed fix addresses root cause