Improvements

* Pattern class - what is this? Why are we using it? More explanations.



# Fix Bugs 20x Faster - From Zero to Incident Superhero - Dynatrace Edition



# Task 1 - Sign Up To Services

[SCRIPT]

Hey there! Before we dive into debugging, we need to get our tools ready. We'll be using Replit, Dynatrace and Github. I'll see you on the other side!

[ENDSCRIPT]

**Introduction:** Before we can start debugging, we need to set up our development environment with all the necessary tools and services.

**Description:**

1. Sign up to Github: [https://github.com/signup](https://github.com/signup)
2. Sign up to Replit: [https://replit.com/signup](https://replit.com/signup) 
3. Sign up to Dynatrace: https://www.dynatrace.com/signup/
    1. Sign up for 15 day free trial
    2. Enter your email and details
    3. Wait for account to be set up
    
    ![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image.png)

**Acceptance Criteria:**
- GitHub account created and verified
- Replit account created and template remixed
- Dynatrace trial account activated
- All services are accessible and working
    
**Solution:**

[SCRIPT]
Great! Let me show you what it looks like when everything is set up correctly:

First, here's my GitHub account - you can see I'm logged in and ready to go.

Next, in Replit, I've already remixed the template. Notice the unique URL showing it's my copy.

Finally, here's my Dynatrace dashboard. The trial is active and I can access all the monitoring features.

Next we'll create our Rails app.
[ENDSCRIPT]



# Task 2 - Create the App

[SCRIPT]
I've built a Rails app ready to go for you with a mystery defect embedded inside.

In this lesson you'll create the Rails app and get it running inside Replit.
[ENDSCRIPT]


**Introduction:**

Before we can start debugging, we need to set up our development environment with the Rails app that contains our mystery bug.


**Description:**

1. Sign in to Replit
2. Go to the template: [https://replit.com/@johngallagher2/Fix-Bugs-20x-Faster](https://replit.com/@johngallagher2/Fix-Bugs-20x-Faster)
3. Click “Remix Template”:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%201.png)

4. Click `Use Template`:
    
![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%202.png)

5. You’ll see the main screen of the app with the [`README.md`](http://README.md) to the right:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%203.png)

6. Click `Run` to run the app:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%204.png)

7. Wait a few seconds for the server to start up. It’ll auto open a browser with the app:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%205.png)

You’re all set up!

**Acceptance Criteria:**

* App running in Replit
* Home page "Upload Pattern" is showing

**Solution:**

[SCRIPT]

You can see here the app running in Replit.  Let's move on to seeing the defect.

[ENDSCRIPT]



# Task 3 - See The Defect

[SCRIPT]

The Rails app has a real life defect. I'll show you what the customer would see and how it would break for them.

[ENDSCRIPT]

**Introduction:**

Now that we have our development environment set up, let's explore a real bug in our cross-stitch pattern preview generator.

We'll see how the app behaves differently with two test patterns - one that works and one that fails. This will give us our first clue about what might be going wrong.


**Description:**

Log into Replit.

Press “Run” at the top of the screen.

You should see a new Webview open:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%206.png)

Download the `MonaLisa.fcjson` below, then upload into the app.

[MonaLisa.fcjson](https://drive.google.com/uc?export=download&id=1ptlLDeszOVkGmvwgH6K9SL0riqIYcLKf)

Press “Update Pattern”.

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%207.png)

Wait for ~30 seconds.

You’ll see one generated image:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%208.png)

### The Defect

Press Back twice to get back to the home page.

Now try uploading `Puffins.fcjson`:

[Puffins.fcjson](https://drive.google.com/uc?export=download&id=15MwbJ1gPnE9gz---EGS0PuWdW1TcQzVE)

Upload this pattern.

Wait… and wait… the app hangs and no images are shown.

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%209.png)

**Acceptance Criteria:**
- Successfully ran the application in Replit
- Successfully generated preview for MonaLisa pattern
- Reproduced the bug with Puffins pattern


**Solution:**

[SCRIPT]

Everything works normally with the MonaLisa pattern.

Try the Puffins pattern and the app hangs.

What's the solution every team has for this?

The error tracker - Sentry, Airbrake, New Relic.

[ENDSCRIPT]



# Task - Show Errors

[SCRIPT]

A defect - no worries - we've got an error tracker installed.

We'll look at the defect in the error tracker and we can figure out what's going wrong.

[ENDSCRIPT]

**Introduction:**

Let's see the error in our error tracker.

We'll be using a simple open source error tracker called Solid Errors by Stephen Margheim. Thanks Stephen!

**Description:**

Let's open a new terminal. Click search icon at the top right.

Type `Shell` and choose Shell:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2011.png)

Then run `bin/errors` 

## See the errors

This will show the error in a new tab:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2012.png)

Open up the error and see the stack trace:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2013.png)

We can see that the error is coming from `Pattern#add_border_to_preview`.

Any ideas why? Give yourself a strict timebox of 1 minute.

**Acceptance Criteria:**

* Open defect in error tracker
* Give yourself 60 seconds to come up with any ideas

**Solution:**

[SCRIPT]

What ideas did you come up with?

It's a bit of a trick question. The correct answer is... "I have no ideas".

This is where I find most teams get stuck.

Error tracking tools are OK, but they're nowhere near enough in today's market.

[ENDSCRIPT]



# Task - Five Steps to Observable Software

[SCRIPT]

I've wasted hundreds of hours looking at stack traces in error tracking tools, guessing what might be happening.

I started to see this was a huge waste of time.

Observability is often talked about in vague hand wavey terms.

Instead, I've created a 5 step process you can follow.

I call it The Five Steps To Observable Software or SOS.

[ENDSCRIPT]

**Introduction:**

When faced with a bug, most developers dive straight into the code trying to find the issue.

This often leads to hours of frustration and wasted time.

Instead, we need a systematic approach to make our software observable and debuggable.

Let's explore the Five Steps to Observable Software (SOS) - a proven methodology that will help you find and fix bugs up to 20x faster.


**Description:**

Introducing the five steps to observable software.

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2014.png)


## 1. Question

What's the question we want to answer?

## 2. Decide Data

What data do we need to answer our question?

The second step is to identify what data we need to collect to answer our questions and test our hypotheses. This could be logs, metrics, traces, or any other telemetry that will give us insight into the system's behavior.

## 3. Build Instrumentation

How do we get that data into our system?

This step involves adding the necessary code and tools to collect the data we identified. This might mean adding logging statements, metrics collection, tracing capabilities, or other monitoring instrumentation.

## 4. Use Logs or Graphs

How do we visualize the data to answer our question?

Once we have the data, we need to analyze it effectively. This could involve creating dashboards, analyzing log patterns, or building visualizations that help us understand what's happening in our system.

## 5. Improve

How can we make this easier next time?

The final step is continuous improvement.

We look at what we learned and how we can make future debugging easier.

We can go back to any of the previous steps. Maybe we don't need to improve anything and a different question is needed. Maybe we need to decide on different data. Maybe we need better instrumentation.

Let's run through this process.

**Acceptance Criteria:**

* Understood all stages of the Steps To Observable Software

**Solution**

[SCRIPT]

Great! Now you understand the theory, let's apply this process to our problem.

[ENDSCRIPT]



# Task - 1a. Question - Form Hypotheses

[SCRIPT]

In order to ask any question that can be tested with data, we need a hypothesis.

Hypotheses are just guesses about why the software might be erroring out.

This is the hardest task so far, so bring your best thinking!

[ENDSCRIPT]

**Introduction:**

The question stage has two steps:

1. Creating a testable hypothesis
2. Writing a specific question that can test this hypothesis

In this task we'll focus on creating a hypothesis.

**Description:**

We can't form a question directly without creating a few hypotheses as to why the app might be going wrong.

Hypotheses are just guesses why the app might be erroring.

First we go wide - a bit of brainstorming and lateral thinking is needed.

List out 3 guesses. Don't be too precious about this.

Don't worry about the quality of the guesses or how wild they might be.

After you've got 3 guesses, rank them by likelihood.

Most likely at the top, least likely at the bottom.

**Acceptance Criteria:**

* 3 hypotheses created
* Rank the hypotheses from most likely to least likely


**Solution:**

[SCRIPT]

This is probably the hardest challenge so far.

The good news is as you practice this "guessing" game more, you'll get more of a feel for it.

Here were mine:

Hypotheses

* Incorrect image format
* ImageMagick is installed incorrectly
* Pattern is too small or too big

Ordering by likelihood we get:

1. Pattern is too small or too big
2. Incorrect image format
3. ImageMagick is installed incorrectly

So the top hypothesis we chose and the most likely guess is that the pattern is too small or big.

Let's turn this guess into a specific question.

[ENDSCRIPT]



# Task - 1. Question - Convert Hypothesis into Question

[SCRIPT]

We think the pattern is too small or big.

Now we convert this into a specific question we can answer with data.

[ENDSCRIPT]

**Introduction:**

Now that we have a hypothesis that the pattern size may be causing issues, we need to turn this into a specific, data-driven question that we can investigate.

A good question should be concrete and measurable, helping us validate or invalidate our hypothesis about size-related problems.

**Description:**

Hypothesis - Pattern is too small or too big

Focus on this hypothesis. What’s a specific question you could ask?

A specific question has a specific answer - it's a data point we can gather.

Think like this - if the pattern is too small, or too big and that's what causes the issue, what's a specific question you could ask?

Example questions:

- What's the average response time for the /checkout endpoint over the last 24 hours?
- Which users are experiencing the most 500 errors?
- What percentage of image uploads fail vs succeed?
- Are errors more common during peak traffic times?
- What's the 95th percentile latency for database queries?
- Which 3 API endpoints have the highest error rates?
- How many unique users are affected by this bug?
- What's the memory usage pattern before crashes?
- What's the distribution of image sizes being processed?

They must have a concrete answer. The answer could be a yes or no. It could be a value or a number.

Think up just one question you could ask that might determine if this hypothesis about size is correct.

**Acceptance Criteria:**

* Created one specific question that can be answered with data


**Solution**

[SCRIPT]

This was a tough task.

Here's the question we'll ask:

Do the errors only happen on just one size of image?

We don't know exactly how to answer this question yet.

Next step is to decide which data can answer this question.

[ENDSCRIPT]


# Task - Decide Data

[SCRIPT]

To answer the question "Do the errors only happen on just one size of image?" we need to determine what data to collect to validate this theory.

Converting the question into data can be challenging too.

Thinking in events can really help. I'll show you how.

[ENDSCRIPT]

**Introduction:**

We'll use a structured approach to decide what attributes to instrument, similar to how we would structure a database query.

**Description:**

Let's look at how to decide what data to gather by using a different example:

Say we had a hypothesis "The checkout process is slow during peak hours".

A question might be "Which hour is the checkout process the slowest?".

To investigate this, we would need to decide:

1. Event - What action do we want to track? For checkout speed, we'd track the `checkout.completed` event.

2. Filter by - Do we want to narrow down the data? In this case we don't need to filter down the events further.

3. Group by - How should we group the data? For checkout times, we might group by hour of day to see peak patterns.

4. Attributes - What specific data points do we need? For checkout speed, we'd want:
   - Timestamp
   - P95 of Duration

## Think in SQL

Sometimes it's helpful to think in terms of SQL.

Most of the time when we're asking questions we're really doing a query on events.

```sql
SELECT timestamp, P95(duration)
FROM events 
WHERE event_name = 'checkout.completed'
GROUP BY HOUR(timestamp)
ORDER BY timestamp;
```

## Challenge

As a reminder, we want to answer the question:

>  Do the errors only happen on just one size of image?

Using the framework above (Event, Filter By, Group By, Attributes), answer what goes in each category.

Note - sometimes the answer in a category might be "None" or "Not relevant".

Also, please write the SQL version of this query.

**Acceptance Criteria:**

* Event to show filled in
* Filter by filled in
* Group by filled in
* Attributes listed
* SQL version of query

**Solution:**

[SCRIPT]

Here's what I came up with. You won't have this exact thing.

**1. Event**: `Pattern#add_border_to_preview` called

**2. Filter by**: None

**3. Group by**: None

**4. Attributes**: Width, Height, Error

In SQL this would be:

```
SELECT width, height, has_error
FROM events
WHERE event.name == 'Pattern#add_border_to_preview called'
```

Now we've decided which data to collect, we can move on to building the instrumenation to collect this data.

[ENDSCRIPT]


# Task - 3a. Build - Install Structured Logging

[SCRIPT]

In this task we're limiting ourselves to using logging.

Traces can be more powerful, but logging is more familiar and easier to get started with.

However, plain text logs aren't enough. We need structured logging.

Rails doesn't have structured logging by default, so we'll add it using a gem.

[ENDSCRIPT]

**Introduction:**

Now that we've identified what data we need to gather, let's set up the instrumentation to actually collect it.

We'll install and configure Semantic Logger, which will help us generate structured logs in a format that Dynatrace can understand.

**Description:**

We'll use Semantic Logger with OpenTelemetry formatting to send our metrics to Dynatrace.

First, we'll install the required gems and create a custom formatter to properly structure our logs. Then we'll add the instrumentation code to track our pattern size metrics.

👨‍💻 We’re using Dynatrace. This technique applies to all observability tools.

## Stop server

Press `Stop` at the top:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2015.png)

## Open Console

Click on the `+` tab:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2016.png)

It’ll come up with a command dropdown:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2017.png)

Type `Shell` and hit enter on the Shell option:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2018.png)

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2019.png)

## Install Semantic Logger

Add to the bundle:

```bash
bundle add semantic_logger rails_semantic_logger
```

Do a `git diff` to make sure the `Gemfile` and `Gemfile.lock` are altered correctly:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2020.png)


**Acceptance Criteria:**

* Semantic Logger gem installed

**Solution:**

[SCRIPT]

You'll see here I've got Semantic Logger installed.

Here's the diff. Not much else to show.

We need some standardisation of log attributes though - something OpenTelemetry can help with.

Let's look at that next.

[ENDSCRIPT]



# Task - 3b. Build - Create an OpenTelemetry formatter

[SCRIPT]

For a long time in observability there's been no standards which has increased vendor lock in.

OpenTelemetry can help here with keeping a consistent structure and format for our logs.

We'll add a formatter to do this.

[ENDSCRIPT]

**Introduction:**

OpenTelemetry helps us to keep our logs in a consistent structure and format.

We can do this in Semantic Logger by creating a formatter.

**Description:**

Using OpenTelemetry has a few advantages:

* Consistent format across all services makes logs easier to search and analyze
* Standard fields like service name, HTTP details, and error status make debugging simpler
* Better integration with observability tools and platforms
* Easier to correlate logs across different parts of the system
* Future-proof as more tools adopt OpenTelemetry as a standard

One misconception is that to get value out of OpenTelemetry engineers must install the Otel libraries.

There's a simpler, lower friction way to get started - use their semantic conventions.

This allows us to slowly opt in to OpenTelemetry in a low risk way without installing another dependency.

This formatter will transform our log entries into a flattened JSON structure that includes service name, HTTP details, and error status.

Open the files sidebar:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/903745e3-b573-440a-85d7-d2f4faf2bd93.png)

Find the `lib` folder and click on the three dots:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2021.png)

Click on it and `Add file`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2022.png)

Call it `flat_json_formatter.rb`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2023.png)

Copy and paste this code into the formatter:

```ruby
# lib/flat_json_formatter.rb

class FlatJsonFormatter < SemanticLogger::Formatters::Raw
  def initialize(time_format: :iso_8601, time_key: :timestamp, **args)
    super(time_format: time_format, time_key: time_key, **args)
  end

  def call(log, logger)
    log = super(log, logger)
    log.deep_merge!(log.delete(:payload) || {})
    log.deep_merge!(log.delete(:named_tags) || {})
    log.merge!(
      "service.name" => "minicrossstitching",
      "http.host" => log.delete(:host),
      "http.route" => log.delete(:path),
      "http.method" => log.delete(:method),
      "http.status_code" => log.delete(:status),
      "code.namespace" => log.delete(:controller),
      "code.action" => log.delete(:action),
      "error" => (log[:level].to_s == "error")
    )
    log.to_json
  end
end
```

**Acceptance Criteria:**

* Understand the benefits of OpenTelemetry
* Create an OpenTelemetry formatter for Semantic Logger

**Solution:**

[SCRIPT]

Not much to see here - I've got this appender in the right path.

Next step - we'll send the logs off to Dynatrace using this formatter.

[ENDSCRIPT]



# Task - 3c. Build - Create Dynatrace Appender

[SCRIPT]

To send logs from our Rails app to Dynatrace, we must write our own appender.

Semantic Logger has a nice design where you can send logs to multiple destinations using appenders.

Let's write the appender.

[ENDSCRIPT]

**Introduction:**

Now that we have our formatter set up, we need to create an appender that will send our logs to Dynatrace. The appender will use HTTP to send formatted logs to Dynatrace's API endpoint.

We'll configure Semantic Logger with a custom HTTP appender that:
- Formats logs using our FlatJsonFormatter
- Sends them to the Dynatrace logs ingest API
- Includes proper authentication headers

**Description:**

Create a new file in `config/initializers/semantic_logger.rb` :

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2024.png)

Paste in the following code:

```ruby
# config/initializers/semantic_logger.rb

require "semantic_logger"
require_relative "../../lib/flat_json_formatter"

SemanticLogger.add_appender(
  appender: :http,
  url: "https://#{ENV.fetch("DYNATRACE_APP_ID")}.live.dynatrace.com/api/v2/logs/ingest",
  formatter: FlatJsonFormatter.new,
  header: {
    "Content-Type" => "application/json",
    "Authorization" => "Api-Token #{ENV.fetch("DYNATRACE_API_TOKEN")}"
  }
)
```

This will send the logs to Dynatrace.

Next to set up the Dynatrace secrets.


**Acceptance Criteria:**

* Appender code written

**Solution:**

[SCRIPT]

Here's the appender in the codebase.

Next up we'll configure the Dynatrace secrets.

[ENDSCRIPT]



# Task - 3d. Build - Generate Dynatrace Secrets

[SCRIPT]

We'll generate secrets in Dynatrace first.

This will allow us to authenticate with Dynatrace from our app.

[ENDSCRIPT]


**Introduction:**

In this task, we'll generate API tokens in Dynatrace that will allow our application to authenticate and send logs.

**Description:**

Open Dynatrace.

Hit `Command K` or press `Search` at the top left:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2025.png)

Type `Logs` and select `Logs` :

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2026.png)

Click “Add Logs”:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2027.png)

Choose “Log Ingestion API”, then “Next”:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2028.png)

Press “Generate” to create a token.

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2029.png)

Press “Copy” button to put API token into the clipboard:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2030.png)


**Acceptance Criteria:**

* API token created and copied into clipboard.

**Solution:**

[SCRIPT]

You'll have the API tokens in your clipboard.

Let's add those to our Replit app.

[ENDSCRIPT]


# Task - 3e. Build - Add Dynatrace Secrets To Replit

[SCRIPT]

We'll add your Dynatrace API tokens into our Replit app.

This is fiddly and annoying but we're nearly ready to see our logs in Dynatrace.

Keep going!

[ENDSCRIPT]

**Introduction:**

Now that we have generated API tokens in Dynatrace, we need to securely store them in our Replit environment as secrets.

This will allow our application to authenticate and send logs to Dynatrace while keeping the credentials secure.

**Description:**

Now switch back to Replit.

Open the command palette:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2031.png)

Type `Secrets` :

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2032.png)

Press `Enter` and the `Secrets` panel will open:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2033.png)

Press `New Secret`, add `DYNATRACE_API_TOKEN`

Paste in the token from Dynatrace and click `Add Secret`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2034.png)

Go back to Dynatrace.

Get the Dynatrace App ID - it’ll be the part before `.apps.dynatrace` in your URL. Copy this:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2035.png)

Add a new secret in Replit called `DYNATRACE_APP_ID`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2036.png)


**Acceptance Criteria:**

* `DYNATRACE_API_TOKEN` set up in Replit secrets
* `DYNATRACE_APP_ID` set up in Replit secrets

**Solution:**

[SCRIPT]

As you can see I've got these two secrets stored in the secrets tab.

Finally, we're ready to fire up the app and check that the logs are in Dynatrace.

[ENDSCRIPT]


# Task - 3f. Build - Check Dynatrace Logs

[SCRIPT]

Semantic Logger can now, hopefully, talk to Dynatrace and send logs.

Let's check it's working.

[ENDSCRIPT]

**Introduction:**

We'll verify that logs are being properly sent and received in Dynatrace.

This will confirm our instrumentation is working correctly before we start collecting metrics about our bug.

**Description:**

Hit `Run` at the top of the screen again.

Wait until the `Preview` window has opened:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2037.png)

- 🆘 **Help!** I don’t see the `Preview` window…
    
Try looking inside the console tab:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2038.png)

When I’d forgotten to paste in the `FlatJsonFormatter` contents, here’s what I saw:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2039.png)


## Check For Logs In Dynatrace

Switch back to Dynatrace. Hit “Next”.

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2040.png)

Wait 30 seconds or so and hit “Refresh”.

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2041.png)

You should see logs start to roll in. Press `Done`.

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2042.png)

Refresh the page, then press `Run Query`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2043.png)

You’ll see logs:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2044.png)

**Acceptance Criteria:**

* App is running
* Logs are showing in Dynatrace

**Solution:**

[SCRIPT]

Here are what my logs look like.

Yours may differ in how many or what they appear.

Now we can see the logs, we'll simulate some load on the app.

[ENDSCRIPT]



# Task - 3g. Build - Simulate Users

[SCRIPT]

Now that we have our logging infrastructure set up, we need to generate some test traffic to trigger the errors.

In a real production system this step wouldn't be necessary!

[ENDSCRIPT]

**Introduction:**

We'll simulate multiple users interacting with our application to gather meaningful data about the pattern size issue.

**Description:**

Switch back to Replit.

**Option 1** **- GUI**. Click dropdown next to the `Stop` button and hit the play next to `Hammer`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2045.png)

**Option 2 - Console**. Click new tab and type `Shell` and hit return:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2046.png)

Then run `bin/hammer` :

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2047.png)

This will simulate our app being used by a variety of users.

Wait for the script to complete. If you’ve run it via the GUI you’ll need to switch the `Console` tab.

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2048.png)

After the script has completed, you'll need to wait for 2 minutes as the Dynatrace ingest API can be a bit slow.


**Acceptance Criteria:**

* Run `bin/hammer` to simulate users hammering the app
* Wait for the script to finish
* Wait for another 2 minutes

**Solution:**

[SCRIPT]

Here's what my Dynatrace looks like.

You can see lots of logs flowing in.

Next we’ll use the logs and graphs to answer our question!

[ENDSCRIPT]



# Task - 4a. Use - Find Errors in the Logs

[SCRIPT]

Now we've got logging all set up, we should be very close to answering our question!

First, let's find all the errors in the logs.

[ENDSCRIPT]

**Introduction:**

We'll analyze logs in Dynatrace to look for patterns in the errors.

**Description:**

Keep hitting `Run Query` until you get an `ERROR` shown at the right:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2049.png)

Hover over the “ERROR” to the right of the graph:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/cb7da703-1ea8-44e7-8602-adf6337fe261.png)

Alongside the error you’ll see three dots:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2050.png)

Click it and press “Run query for selection”:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2051.png)

This shows the errors:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2052.png)

Click on an error.

Scroll up and down. Can you figure out the root cause of the error with this?

No, nor can I.

**We don’t have enough data.**

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2053.png)

- **⚠️  Common anti-pattern - not enough data!**
    
Teams I’ve worked with are often held back by one simple limitation:

**They haven’t enough data to reason about their app.**

I see teams trying to debug issues with what you see above.

This is a waste of time. The minimal data above is utterly useless.

So what do I see engineers do? They guess.

> The defect might be in `pattern.rb`? Let’s take a look at the code… hmmm… that looks OK… let’s see… maybe the error is in the controller?

Engineers go round in circles, endlessly guessing, never figuring out what’s really going on.

The results? Wasted time, effort, demotivated engineers and learned helplessness.

**Observability is answering interesting questions that allow you to reason about your app.**

Without relevant data, that’s simply impossible.

The good news - once you break this “let’s guess” mentality and start instrumenting your app to gather data and answer questions, it’s a virtuous cycle.

Observability isn’t a check box in an endless list of “non functional requirements”.

It’s a force multiplier for you and your team. 🚀
    
**Acceptance Criteria:**

* Searched for `ERROR`
* Opened up an error log to see inadequate data

**Solution:**

[SCRIPT]

Scrolling up and down here, I can see this doesn't contain anything interesting.

So, instead of trying to guess what might be happening, we need to gather more data.

So we go back to the build step.

[ENDSCRIPT]



## Task - 3. Build - Add Data Needed

[SCRIPT]

If we can't answer questions, we're not gathering the right data.

This is the part I see few teams spending time on!

We can improve observability by instrumenting our code with extra attributes.

Let's do that now.

[ENDSCRIPT]

**Introduction:**

We need to add structured logging to gather data about pattern dimensions and errors. This will help us determine if errors only happen with certain image sizes.

**Description:**

We already decided which data to gather - we've spent this long just getting *any* logs into the system.

As a reminder:

**1. Event**: `Pattern#add_border_to_preview` called
**2. Filter by**: None
**3. Group by**: None
**4. Attributes**: Pattern Width, Pattern Height, Error

Let’s build code to collect this data.

Stop the server first:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2054.png)

Now click on the search icon:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2055.png)

Type in `models/patter` :

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2056.png)

This will open up the code.

Click in the editor, `Command F` to find and type in `add_border_to_preview`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2057.png)

## Add logging to `#add_border_to_preview`

Let’s add some logging to this.

Add the added lines indicated below:

```diff
  def add_border_to_preview(size)
+   SemanticLogger.tagged(
+     "app.pattern.id" => id,
+     "app.pattern.height" => height,
+     "app.pattern.width" => width,
+     "code.namespace" => "Pattern",
+     "code.function.name" => "add_border_to_preview",
+     "app.code.args.size" => size
+   ) do

      preview_image = MiniMagick::Image.read(preview.download)
      preview_image_width = preview_image.data.dig("geometry", "width")
      ... snip ...
      temp_file.close
      temp_file.unlink

+     Rails.logger.info(
+       message: "Border added to preview",
+       "event.name" => "app.pattern.border_added_to_preview",
+     )
+   rescue StandardError => e
+     Rails.logger.error(
+       message: "Error adding border to preview",
+       "event.name" => "app.pattern.border_added_to_preview",
+       exception: e,
+     )
+     raise e
+   end
  end
```

⚠️ **Make sure the** **`do`**  **`end`** **s all match up!**

- A few things here:
    - `SemanticLogger.tagged` - this adds context for any log that’s triggered inside the block
    - This means we can add these shared attributes whether the event is successful or not
    - The blocks at the bottom - these are logging success and error respectively.
    - Note the event - `app.pattern.border_added_to_preview` is namespaced and in the past tense
    - Note how clumsy the logging is and how much code is needed. There are nicer ways to organise our code, but they’re out of scope for this workshop.


**Acceptance Criteria:**

* `#add_border_to_preview` has been instrumented
* All `do` `end`s match up with no syntax errors

**Solution:**

[SCRIPT]

Here's the instrumentation in my editor.

Now for the cool part - time to see these extra attributes in the logs.

[ENDSCRIPT]


## Task - 4b. Use - See Extra Attributes In Logs

**Introduction:**
Now that we've added instrumentation to track pattern sizes and errors, let's examine the logs in Dynatrace to see if we can identify any patterns in the failures.

We'll look specifically at the width and height attributes we added to determine if errors correlate with specific image dimensions.

**Description:**

Restart the server (Hit “Stop” then “Run”).

Hammer the server again using `bin/hammer`.

Wait for ~2 minutes.

Now we’ll see our new logs in Dynatrace.

Click `Run query` again:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2058.png)

You’ll see the new errors from the new code:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2059.png)

There are two different kinds of logs here:

1. Generic `Error performing CreatePreviewFromPatternJob ...`
2. Log we added: `Error adding border to preview` 

Click on the specific `Error adding border to preview` 

You’ll see the extra data:

- `app.pattern.height`  - Pattern height
- `app.pattern.width` - Pattern width
- `error` - has the operation failed or not
- [`event.name`](http://event.name) - the event name we can search for

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2060.png)


**Acceptance Criteria:**

* App restarted
* Users simulated with `bin/hammer`
* After 2 minutes, Dynatrace errors visible
* Extra attributes examined

**Solution:**

[SCRIPT]

Great! We've got the data into the logs.

The biggest remaining hurdle is using Dynatrace to search for what we need to answer the question.

[ENDSCRIPT]


## Task - 4c. Use - Show Attributes As Columns


**Introduction:**

Now that we have our logs in Dynatrace, we'll learn how to filter and display the specific attributes we need to analyze the pattern size issue.

We'll use Dynatrace's query interface to show width, height and error status for each pattern, similar to how we would write a SQL query to analyze this data.

**Description:**

Reminder of the question we're trying to answer:

## **Question: Do the errors only happen on just one size of image?**

The query we want in SQL format:

```sql
SELECT app.pattern.width, app.pattern.height, error
FROM events
WHERE name = 'app.pattern.border_added_to_preview'
```

Click on a specific error - `Error adding border to preview`

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2061.png)

## Filter for `app.pattern.border_added_to_preview`

We’ll implement the `WHERE` section of the SQL first.

In the sidebar, scroll down to  `event.name` , click three dots alongside it, select “Filter by…”

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2062.png)

A new filter is added in the query bar.

Now press `Run query`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2063.png)

This filters out all the crappy generic errors:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2064.png)

## Show the correct attributes

Now we’ll work on the `SELECT` part of the query.

Click the “xx columns hidden”:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2065.png)

Now select the columns - `error`, `app.pattern.height`, `app.pattern.width` then hit `Apply` :

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2066.png)

You’ll see the attributes we care about:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2067.png)


**Acceptance Criteria:**

* Filtered by event in Dynatrace
* Attributes shown as columns

**Solution:**

[SCRIPT]

This is what my view looks like in Dynatrace.

You can see the attributes in columns, nice and neat.

We're one step away from answering our question.

[ENDSCRIPT]



## Task - 4d. Use - Show All Logs

[SCRIPT]

Filtering by just errors doesn't allow us to see patterns between errors and successes.

So we'll show all logs - both successes and errors.

[ENDSCRIPT]

**Introduction:**

Now that we have our logs filtered and formatted properly, we need to look at all logs, not just errors, to understand the pattern of failures.

This will help us identify any correlations between pattern dimensions and errors.

**Description:**

Click the cross next to `status = ERROR`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2068.png)

Hit `Run Query`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2069.png)

## Sort by error

Click on the `error` column to sort by error:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2070.png)

You’ll see the logs sorted by error:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2071.png)

## Challenge

Take a moment to look at this.

Are there any patterns you can see in the height and the width?

Write down any observations you have.


**Acceptance Criteria:**

* One observation about patterns you see written down

**Solution:**
    
[SCRIPT]

Looking through these logs in Dynatrace.

Seems like for most the errors, the width is more than the height. Interesting…

Unexpected facts like this can cause us to reassess our direction.

[ENDSCRIPT]

    
# Task - 1 - Question - Form New Hypothesis

[SCRIPT]

Often I see engineers become wedded to a specific theory.

They pursue it doggedly, despite clues being given to them repeatedly that they're not moving in the right direction.

When to keep asking questions around the same hypothesis and when to switch is a skill.

It always helps to be curious and be open to new directions.

Let's explore another hypothesis.

[ENDSCRIPT]

**Introduction:**

After analyzing the logs, we discovered a potential pattern.

We'll explore this pattern to see if we need a new hypothesis.

**Description:**

Based on what we've learned, let's form a new question.

So… if the width is greater than the height…

…could it be something to do with landscape vs square vs portrait?

**Surely this is off track?**
    
Might seem like we’re getting distracted here.

We want to keep our original question as a north star… but we can’t be too inflexible.

In the flow of exploring, we’ll learn new things.

So old hypotheses may become less important.

In this case, orientation is related to the height and weight, so we’ll pursue this line of reasoning for now.

**Challenge**
    
Can you think of a hypothesis related to orientation?

And can you think of a question that you can answer definitively that will lead to that hypothesis being proven as right or wrong?
    
**Acceptance Criteria:**

* Understand the benefit of staying curious and open to changing hypothesis
* Create a new hypothesis related to orientation

**Solution:**

[SCRIPT]

This was another hard task. Don't worry if your hypothesis doesn't look like mine.

This is a skill that takes lots of practice to hone.

That said:

**Hypothesis:** Specific orientations cause the errors.

**Question:** Do all errors happen with a specific orientation?

OK, so what data do we need to answer this question?

[ENDSCRIPT]


# Task - 2 - Define Data - Explore Group By

[SCRIPT]

We need to decide what data to collect to answer our question about orientation.

This is a perfect case for grouping our data.

But which attributes should we group by?

[ENDSCRIPT]

**Introduction:**

Explore how grouping by an attribute can help discover correlations.

**Description:**

Here's our question:

**Question:** Do all errors happen with a specific orientation?

Let's think about what we need:

1. We need to know if there was an error
2. We need to know the orientation
3. We need to know how many times each combination occurred

Can you think of a few attributes we can group by to explore this question?

And then can you write a SQL statement that reflects this?

**Acceptance Criteria:**

* List attributes we can group by to discover correlations
* SQL statement we had previously has been amended to include the GROUP BY clause

**Solution**

[SCRIPT]

We want to see how errors and orientation are correlated.

So we group by **Error** and **Orientation**.

**Event**: `app.pattern.border_added_to_preview` called

**Filter by**: None

**Group by**: Error, Orientation

**Attributes**: Width, Height, Error

In SQL, it’d be:

```
SELECT error, app.pattern.orientation, COUNT(*)
FROM events
WHERE event.name = 'app.border_added_to_preview'
GROUP BY error, app.pattern.orientation
```

What data are we missing? The orientation of the pattern.

[ENDSCRIPT]



# Task - 3 - Build - Add Orientation

[SCRIPT]

Thankfully the orientation is already in the database.

All we need to do is add it into the attributes that are logged.

[ENDSCRIPT]

**Introduction:**

We'll add orientation as an attribute to our logging and analyze the results in Dynatrace to see if certain orientations are more prone to errors than others.

**Description:**
We’re missing orientation in Dynatrace.

Open `app/models/pattern.rb` again and go to `#add_border_to_preview`

Add the **code in bold green**.

**⚠️ Don’t forget to add the trailing comma after `size`!**

This gets the `orientation` attribute from the `Pattern` model and adds it into the logs.

```diff
  def add_border_to_preview(size)
    SemanticLogger.tagged(
      "app.pattern.id" => id,
      "app.pattern.height" => height,
      "app.pattern.width" => width,
      "code.namespace" => "Pattern",
      "code.function.name" => "add_border_to_preview",
-     "app.code.args.size" => size
+     "app.code.args.size" => size,
+     "app.pattern.orientation" => orientation
    ) do
      preview_image = MiniMagick::Image.read(preview.download)
```

`app.pattern.orientation`  is added for **every log statement in the block** so it’ll be added for both the error **and** the success logs.

`Stop` the server, `Run` it then run `Hammer` again, either through the GUI or console.

Wait for a few minutes for the logs to come through into Dynatrace.

**Acceptance Criteria:**

* Orientation added as an extra attribute
* Server restarted
* `bin/hammer` ran again

**Solution**

[SCRIPT]

You can see the extra instrumentation in this code I'm showing.

Next we'll explore this in Dynatrace.

[ENDSCRIPT]


# Task - 4. Use - Explore In Dynatrace

[SCRIPT]

Now that we've added orientation to our logs, we can analyze them in Dynatrace to see if there's any correlation between orientation and errors.

Using the instrumentation we've added is one of my favourite parts to understanding what my app is doing.

We're about to see something interesting.

[ENDSCRIPT]

**Introduction:**

Now that we have added orientation as an attribute to our logs, we'll explore the data in Dynatrace to see if there's a correlation between image orientation and errors.

We'll group the logs by error status and orientation to identify any patterns.

**Description:**
Go back to the query in Dynatrace.

Set the time range back to `30 minutes` to see the most recent logs:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2072.png)

⚠️  **Wait until you see `ERROR` logs.**

Now let’s group by `error` and `app.pattern.orientation`.

To group in Dynatrace, we need a query in DDL - their query language.

Click `Edit DDL Query`:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2073.png)

Shows the filter in DDL format:

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2074.png)

Now change the DDL query to group by `error` and `app.pattern.orientation`:

```
fetch logs
| filter matchesValue(event.name, "app.pattern.border_added_to_preview")
| summarize count(), by: { error, app.pattern.orientation }
```

This is the equivalent of the SQL query we saw earlier.

Press `Run query` and list out all the combinations you find.

What's the answer to our question?

**Acceptance Criteria:**

* Group by error and orientation in the logs
* List out all the combinations
* Write down an answer to the question

**Solution:**


[SCRIPT]

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2075.png)

See how there is only three combinations?

Square and portrait images **always** work and landscape **always** errors.

## **Answer: Every error is in landscape format**.

[ENDSCRIPT]



# Task - 4b. Use - Reason About Answer

[SCRIPT]

Now we've gathered data, we're ready to read some code and reason about what's going wrong.

[ENDSCRIPT]


**Introduction:**

Now that we have data showing all errors occur with landscape orientation, let's analyze what this means and how it relates to the code.


**Description:**
Do we have enough data to fix the issue?

With this new data, let’s read some code.

What uses the `orientation`?

```
  def add_border_to_preview(size)
    tracer = OpenTelemetry.tracer_provider.tracer("minicrossstitching")
    tracer.in_span("Pattern#add_border_to_preview") do |span|
      # ...
      **w, h = PREVIEW_WITH_BORDER_DIMENSIONS.dig(orientation.to_sym, size)**
      MiniMagick.convert do |c|
        c.size "#{w}x#{h}"
        # ...
      end
```

Let’s look at that **`PREVIEW_WITH_BORDER_DIMENSIONS`**  hash:

```
  PREVIEW_WITH_BORDER_DIMENSIONS = {
    portrait: {
      small: [ 40 * STITCH_WIDTH, 55 * STITCH_WIDTH ],
      small_wide: [ 40 * STITCH_WIDTH, 57 * STITCH_WIDTH ],
      medium: [ 55 * STITCH_WIDTH, 75 * STITCH_WIDTH ],
      medium_large: [ 65 * STITCH_WIDTH, 87 * STITCH_WIDTH ],
      medium_tall: [ 55 * STITCH_WIDTH, 75 * STITCH_WIDTH ],
      large: [ 75 * STITCH_WIDTH, 100 * STITCH_WIDTH ],
      large_tall: [ 65 * STITCH_WIDTH, 85 * STITCH_WIDTH ]
    },
    square: {
      small: [ 43 * STITCH_WIDTH, 43 * STITCH_WIDTH ],
      small_wide: [ 55 * STITCH_WIDTH, 43 * STITCH_WIDTH ],
      medium: [ 55 * STITCH_WIDTH, 55 * STITCH_WIDTH ],
      medium_large: [ 65 * STITCH_WIDTH, 65 * STITCH_WIDTH ],
      medium_tall: [ 55 * STITCH_WIDTH, 75 * STITCH_WIDTH ],
      large: [ 75 * STITCH_WIDTH, 75 * STITCH_WIDTH ],
      large_tall: [ 65 * STITCH_WIDTH, 85 * STITCH_WIDTH ]
    }
  }
```

What might be going wrong here? How might we fix the code?

When you've got an idea, move on.

**Acceptance Criteria:**

* Code has been read
* Reason for error found

**Solution:**

[SCRIPT]

Aha! **Missing** **`:landscape`** **key.**

This will result in `width_with_border` and `height_with_border` being `nil`.

## Problem found: missing `:landscape` configuration

The app doesn’t support landscape configuration.

To fix this, we’ll add a few lines to **`PREVIEW_WITH_BORDER_DIMENSIONS`:**

[NOSCRIPT]



## Task - Fix Defect

[SCRIPT]

OK! Finally, we're ready to fix the defect.

Let's do this!

[ENDSCRIPT]


**Introduction:**

Now that we've found the bug, let's apply a fix and verify it works.

We'll use git commands to apply a pre-made fix that adds the missing landscape configuration.

After applying the fix, we'll test it by uploading the Puffins pattern again to confirm the images generate correctly.

**Description:**

I’ve created a fix you can just apply:

```bash
git fetch

# See the fix - adds landscape orientation
git show e8d138ec16991d26b683c11a0ecdaa175ab3871c

# Apply the fix
git stash
git cherry-pick e8d138ec16991d26b683c11a0ecdaa175ab3871c
git stash pop
```

Run the server, upload Puffins.fcjson again:

[Puffins.fcjson](https://drive.google.com/uc?export=download&id=15MwbJ1gPnE9gz---EGS0PuWdW1TcQzVE)

# Resources

Cheat Sheet: [https://joyfulprogramming.notion.site/fix-bugs-20x-faster-cheat-sheet](https://joyfulprogramming.notion.site/fix-bugs-20x-faster-cheat-sheet)


**Acceptance Criteria:**

* Fix applied from Git
* Fix verified by running app

**Solution:**

[SCRIPT]

You’ll see the images are generated! Hurrah!

![image.png](Fix%20Bugs%2020x%20Faster%20-%20From%20Zero%20to%20Incident%20Superh%2096bbcf8408f04df9968ebe583824919e/image%2076.png)

[ENDSCRIPT]


# Task - Wrap Up

**Introduction:**

Let's reflect on what we've learned in this course about debugging and observability.

**Description:**

You've completed this course. Great!

Here are the things we've covered:

1. Forming testable hypotheses and questions
2. Deciding what data we need
3. Building proper instrumentation 
4. Using logs and visualization tools effectively
5. Making continuous improvements

Through hands-on practice with a real bug, we saw how structured logging and data-driven debugging can help us find and fix issues much faster than traditional debugging methods.

Now to reflect on what you've learned.

- What's the biggest problem for your company that could be helped by the techniques you learned today?
- What's the tiniest improvement you could make to help this?
- How do you feel unprepared?
- What do you need? Resources? Knowledge? Skill? Safety?
- How can you get those resources?

## Want More?

Explore the next segment of the course, coming soon!
