# The Complete Conversion Rate Optimization Course by Ruben de Boer

## Introduction to Conversion Rate Optimization
### Hierarchy of Evidence
	
Better Evidence the higher up the pyramid you are of the Hierarchy of Evidence

					Level 1: Meta-analysis (combines the results of multiple A/B tests)
				Level 2: Randomized Controlled Trial (or A/B Test)
			Level 3: Data & Science
		Level 4: User Research
	Level 5: Expert Opinion, Best Practices, & Competitors

An individual A/B test is prone to some degree of error, a meta-analysis aims to derive at an estimate closest to the truth


Introduction to the Case
- Using the Google Merchandise Store site as a case study


## Conversion Rate Optimization data research

### Conversion Rate Optimization Research
Better input for your A/B testing plan come from User Research, Data & Science

Data will tell you exactly what happens where on your website and gives you a great indication of where you should improve

Document where you should improve


### Know your company goals and KPIs
If you optimize for increasing the number of transactions, and the rest of the company wants to increase the average order value, you are optimizing for the wrong thing. And these could result in much different CRO tests

Also take micro-goals into account, like getting people to sign up for a newsletter

For our example on the Google Merchandise Store, our goal will be to increase the number of transactions.


### Web Analytics for CRO
Use your website's analytics account to find opportunites to test.

What to check for:
- Check if everything is being measured correctly
- Check some basic general numbers
- Set up funnels from the customer journeys on your website
- Check for on-page interactions


### Intro to GA4
An Engaged Session is a session lasting longer than 10secs, one that had at least 1 conversion event, or one that had at least two page views

- DAU - Daily Active Users
- WAU - Weekly Active Users
- MAU - Monthly Active Users


### Make sure everything is tracked
The more data is tracked, the more insights you will get


#### Enhanced Measurement
Admin > Data Streams > Turn on "Enhanced Measurement" so all events are tracked. Also hit the gear icon and check that all of the applicable events for your website are being tracked. 

#### Exclude Traffic from Your Office or from Agencies you Work With
Admin > Data Streams > Configure Tag Settings

Hit "Show all" and then scroll down and click on "Define Internal Traffic". Here is where you will want to create rules to exclude traffic from your office and agencies working on your website. Do this by setting up new Internal Traffic Rules indicating these internal traffic sources by IP address.

Then, we just need to tell Google Analytics to remove these items from the data. To do this:

Admin > Data Settings > Data Filters

Create a new filter excluding all data under the "internal" type.

These filters also have a "Filter State" of "Testing","Active", or "Inactive". The "Testing" state means you can evaluate your filter, but it is not applied to the data yet.

#### Google Signals
Data Settings > Data Collection > Enable Google Signals

#### Make sure Conversions are Measured
Admin > Events

Make sure that the most important events are marked as Conversion Events (or Key Events, now)


### General Data in GA4
Before you start with an in-depth analysis, start with some general Data across Google Analytics topics and serve as starting points for your data analysis.

First looks in the Tech > Tech Overview category to see if any browsers or types of devices are having any overt issues. He notices that, though the users on Desktop and Mobile are fairly similar (30k on desktop as compared to 27k on mobile), the engagement rate and converions are very low on mobile as compared to Desktop (Desktop has 839 conversions as compared to Mobile's 63 conversions.)
	- This might indicate a problem on mobile or that that side of the equation needs some A/B testing to increase that number.


Acquisition > Traffic Acquisition
	- He sees most purchases come from Direct and Organic Search Traffic
	- When choosing "Landing Page" as secondary dimension, he finds that the "Paid Shopping" channel that directs users to the Accessories page has a very low engagement rate and there are no purchases made from this page
		- This might be an opportunity to see a problem with an Ad or with the underlying page.

Engagement > Pages and Screens
	- Find your most used pages on yoru site and their average engagement time

There's also a "Landing Page" screen that's also fertile ground to dig around.


### GA4 Explore
The author says the GA4 Explore tab is where you will spend most of your time in GA4

Author is starting from a Blank Template. 
- Adds Dimensions landing page, and device category
- Add Metrics entrances, engaged sessions, avg engagement time per session, add-to-carts, purchases, purchase revenue and engagement rate

Can have up to 10 tabs in one Explore report

He drags "Landing Page" to the "Rows" tab setting, and all the metrics to the "Values" tab setting.

He notices right away that the second top landing page actually has the lowest engagement rate of any other page and the engagement time is really low too. Also, there have been barely any purchases on this page as opposed to the other pages in the report.

He then duplicates the tab to categorize by device type and sets "Device Category" as a column. This allows you to see each page broken down by device type. He then drags it over to rows, which shows the same data in another view.

He sees that the homepage on mobile has a really low engagement time and very low conversions as compared to on Desktop.

Adds "Bounce Rate" and "Exits" to the "Metrics" and then to the Values

Bounce Rate is opposite of engagement Rate. Bounce_Rate + Engagement_Rate = 100%

Exits are the number of sessions that ended on a page or stream. He sets up another tab to see where users are "Exit"-ing the most. The top 2 pages turn out to be on the homepage and the basket page


### Funnel Analysis in GA4
Dimensions - Device Category, Medium

Cannot Add Metrics in a Funnel Analysis

Set "Technique" to "Funnel Exploration"

Difference between Open and Closed Funnel - An open funnel means users can enter the funnel at any point within the funnel. In a closed funnel, users can only enter the funnel at Step 1.

Open is helpful to get a complete picture of what happens with each step with all users.

Closed helps analyze the funnel as a whole.

Edit the "Steps" by hitting the pencil.
- For an ecommerce site, he would typically start at the most important landing page or all category pages. But, he's going to use this funnel for add-to-cart events.

His Steps are:
	- Add to cart
	- View Cart
	- Sign In
	- Hit the "Your Info" page
	- Pay for the Item
	- Finalize the purchase.

He notices that only 10% proceed from the Add to Cart to viewing the Cart page. This could be a fertile ground to run A/B tests on.

Author isn't a big fan of Benchmarks (because he thinks that every situation is different), but for those who are, he says that he typically sees around 50% go from Cart to Checkout and 80% to 95% from there complete the checkout from there and purchasing the items. So these numbers are very very low.

He also breaks down this same report by device category and medium.

### Path Exploration in GA4
If you wonder what happens on page with a high abandonment rate, you can use the path exploration option.

Technique > Path Exploration

Drag "Page Title and Screen" into "Starting Point" and you can start to see where people go from the Shopping Cart page.

You can click on each branch of the path exploration to see what happens on that branch and the breakdown of page views, events, etc... there.

People on this site often go to the shopping cart, the sign in page, and (instead of going to the checkout page), they often go back to the homepage. This might also be a useful thing to test to see why people are basically bouncing from the sign in page.


### Segmentation in GA4
To get more insights, you can use segments of your users. A segment is a subset of your data; users on a mobile device, users who visited the cart, users from the US or India, etc...

You can sometimes create a segment by right clicking a row in your data and selecting "Exclude Selection" or "Include only Selection". GA4 will automatically apply a Filter under "Filters" that you can edit as you like.

You can also build a new segment by clicking the plus button under "Segments" on the left sidebar.
	- User Segment - Subsets of users who engaged with your site or app; users who have previously purchased a product from your or added something to their cart.
	- Session Segment - Subsets of the sessions that occured on your website or app; like sessions originating from a specific campaign.
	- Event Segment - Subsets of events that were triggered on your site or app.

There are also suggested segments you can use.

He uses a "Session Segment" to create a session that originates from a paid search campaign.

Once you hit "Save and Apply", the segment will be automatically applied to your report, and will filter all of the numbers on the final report to be only those from that segment.

You can also add a second segment; He adds a Session Segment of "Organic Search Traffic". 

Then you can compare those segments side-by-side.

Also, you can use this to check if a specific browser or device category has a very low conversion rate, which could indicate an error in your funnel process. 
	- Creates another Session Segment where Device Category is mobile and the browser is Safari

If there is an error on a specific step on your website, you'll see a very low completion rate and high abandonment rate on that step. You can then talk to your developers and get it fixed.

He does another segmentation (2 User segments) of users that are in the US and Canada, to be able to compare sales from those two countries.


### Non e-commerce websites, comparisons, & filters
CRO works across all kinds of sites and works the same for every site. Different sites, in the end, just have different goals.

If you have a non-ecommerce website, you might want to look at some other data in GA4.

For a non-ecommerce site, you still want to know your most visited pages.


#### Adding Filters
Add a filter -> up at the top underneath the title 
	- Sets "page path and screen class" as the condition and the "Google Redesign Stationery" slug as the Dimension value.

Now you will see all the events that happened on that page alone.

Track everything you can on a webpage so that you can take actions if you start seeing issues with users on key pages.


#### Comparing Filters
In any report, you can compare filters by clicking the "Edit Comparisons" icon and add a new comparison in the window that comes up. This could allow you to show differences between desktop and mobile traffic, for instance.


#### Compare Preceding Period
You can also go ahead and compare table values from the same values you had on the same day last year by choosing "Preceding Period (match day of week)" or "Same Period Last Year (match day of week)"


### Web Interaction Analysis
Next up, is the Web Interaction Analysis, where you mainly use heatmaps to see your data. You can see where a visitor clicks, scrolls, or moves their mouse.

Author suggests NOT using a mouse movement heatmap, as there has never been a coorelation between where people move their mouse and where they look. In other words, these heatmaps don't tell you a thing.

Checking out Three Tools; HotJar, Clarity, and Mouse Flow

Hotjar is fantastic, but has increased it's prices since it was purchased by ContentSquare in 2021. Clarity is free at the time of recording; works good for heatmaps and recordings, but lacks other functionalities. MouseFlow is affordable with a free trial and has some nice features. All tools user friendly and easy to setup.

Hotjar grabs all heatmaps from your website, and the user is looking at click heatmaps

Heatmaps shouldn't be off of a few hundred sessions; preferably the heatmaps are from a few thousand sessions.

On scroll maps, typically only a few percent of people make it all the way down to the bottom of the page. On his site, he has a form at the top and the bottom of the page, but he sees that only 40% of users get to the bottom form. If you see a form on your site that gets that low engagement, you might want to look at moving it up your page.

If you see a big drop in your scroll maps, it's possible that you have found a conversion killing piece of the page. So you might try moving that content to the bottom of the page.

MouseFlow has a Forms section that shows where users might drop off on form fields, indicating that a certain field causes them to bounce. It also has an "attention" heatmap, indicating what areas users linger on while scrolling, which isn't included in other tools.

Click Maps - Check elements that don't get clicked or get clicked often. Remove elements that don't get clicked much or make them more prominent. Elements that shouldn't be clicked should be made less prominent or removed.

Scroll Maps - See what elements get seen by what percentage of visitors. If so.mething is important, but barely anyone sees it, place it towards the top of hte page. If lots of users scroll down to the bottom of the page, they may be looking for more information. And if you see a big drop off at a certain part of the page, the material right before the drop might be a "converison killer".

Combine click maps and scroll maps to see what gets relatively a lot of clicks.


### Form Analysis
A thorough form analysis is impossible via Google Analytics, but you can use tools like MouseFlow and Zuko to do some detailed form analysis.

In MouseFlow, you can find information like how many users interact with each field, how long they spend on that field, and how many users drop off on each field. This helps you figure out what fields you should optimize

Zuko is a more in-depth form analysis tool. Contains a completion path which breaks down how many users view the form but don't submit it, etc...

Field Data breaks down between Abandons, Time Spent, and "Field Returns". Field returns are the number of times a user enters data in a particular field, moves on, and then comes back to it. You obviously want this as low as possible, because more field returns means that more users are having trouble filling out the form.

Some General Best Practices for Improving Forms:
 - Simplify the Form - Reduce the number of fields
 - Clear Field Labels - Ensure each field is clearly labeled, so users know exactly what information to enter
 - Use Placeholder Text - Placeholder text can provide hints or examples, but make sure it's not confusing
 - Logical Order - Arrange fields in a logical sequence
 - Visually Distinct and Clear CTA's - Make your submission button stand out and manage expectations for what users can expect
 - Progress Indicator for Multi-Step forms
 - Inline Validation - Provide real-time feedback if a user enters correct or invalid information while they are on the field instead of when they try to submit
 - Optimize field length - The length of your input fields should match the expected length of the answer
 - Enable auto-fill - So users don't have to type everything
 - Make it as easy as possible - Don't make your users think; allow for a wide range of inputs. Phone number fields should, for example, allow for spaces, dashes, and none of those.


### Page speed and mobile friendliness

To increase your conversion rates, you will also want to check out your page speed and mobile friendliness.

Page speed is getting more important as humans get more impatient. If your website takes a long time to load, your visitor will get impatient and will leave.

By Google
	- If page load time increases from 1s to 3s, bounce probability increases 32%
	- If page load time increases from 1s to 5s, bounce probability increases 90%
	- If page load time increases from 1s to 6s, bounce probability increases 106%
	- If page load time increases from 1s to 10s, bounce probability increases 123%

We also use our mobile phones more and more often. In most markets, Conversion Specialists need a mobile-first mindset.

Tools to help increase your speed and mobile friendliness
	- Pagespeed Insights (by Google)   - pagespeed.web.dev
	- PageSpeed Compare                - pagespeed.compare
		- Also can compare your website against your competitors
	- Web Page Test                    - webpagetest.org
	- Mobile Friendly Test (by Google) - search.google.com/test/mobile-friendly/


### Document findings

Document all insights and findings in one place.

Possible Tools:
- You could use Excel or Google Sheets, but as you do more complex experiments and research, you will quickly run into these programs' limitations
- Effective Experiments is another tool for this, and works quite well, but it comes at a significant price
- Airtable is the author's favorite tool. It's fully customizable, has a free version, and has everything we need to properly document our process and insights. It is a database, project management tool, and dashboarding all in one and is user friendly to boot.

Shows one method Google Sheets
- Table with Research Source, Research Finding, Device, Page, Text/Fix, who found it, and the status

Shows another method with Airtable to document findings


## Conversion Rate Optimization User Research and Science

### Intro to User research and Science

If you are asking questions of your users, do the following
- Never ask leading questions
- Don't ask double-barreled questions; like asking two questions in one
- Use Clear Language
- Avoid Absolutes ("always", "never", etc...)


### Polls, Surveys, & Feedback Tool

Survey
	- A questionnaire with questions you can have visitors fill out; display in a popup or through a link
Poll  
	- Like a mini survey, in a "pop-over" at the bottom of the screen. 
	- Typically asks only 1 or 2 questions. 
	- Three great locations: When someone lands on your website, when a visitor is about to leave your website, and when someone converts.
	- Aim for 100 to 200 useful responses
	- You can ask an open-ended question first and use the first answers you get to create a new multiple-choice question

You can also use a little feedback button on the side or bottom of your webpage, but only if you get sufficient valuable insights. Otherwise, it could distract your visitors from completing the most desired action.

Can setup most of these in HotJar or other tools. Sadly MS Clarity doesn't have poll and survey functions. Mouseflow has a Poll option under "Feedback", but no survey or feedback button options.


### Recordings

Another way is to get an insight into your user's behavior is through Recordings, where you can get a screen recording of your website visitor interacting with your website.

Author encourages you to not watch every recording from beginning to end, but instead to look at the dropoff points in your data and see what happens there inside the recording

Based on these recordings, you can find valuable insight for future experiments


### Usability Test

During a test like this, you will go through teh website with an actual person; someone from your target audience or a real customer. You give them an assignment or a set of assignments and see how they perform them on your website. You can see and hear what this person does, how they behave, and where they get stuck. And what they like or don't like about your website

The ideal setup is a fancy usability lab with one room with the user and the inteviewer, along with a camera, and another room with stakeholders who can watch whatever the user does on the website. But if you don't have a fancy lab like this, that's also okay; start off simple. Find someone from your target audience or a customer, and perform a usability test with them on a Desktop or Mobile device.

How to be a good moderator
- Look at what the participant does - Not so much what they are saying
- Make the assignments personal - Don't make them too specific. Like ask the participant to find a shirt for themselves, or if they mention they have a wedding coming up, to find clothes for said wedding. Author typically starts with a personal assignment and then a more specific assignment
- Shut up! Let the participant do the speaking
- Don't steer and don't judge
- The participant can not do something wrong - Tell them this
- Be Relaxed


Questions to avoid as a moderator
- Do you like this?
- What do you think about this?
- Would you use our website more often if we added... ?


Typical Situations
Participant Asks: How Does this Work?
- Ask the participant what they would do at home or what do they think they would have to do.

Participant looks confused
- Ask the participant if this is what they expected to happen.

Participant thinks he/she did something wrong.
- Tell them that they can't do anything wrong and that it's the website that's wrong

How many people you need to do a good usability test?
- You actually only need around 6 people. If you interview more people, you'll be hearing the same thing over and over again. 

Do usability test, fix the issues, and then do another 3 or 6 months down the line.

Author suggests one every 3 to 6 months.

There are also Remote Usability Tests. These have the advantage of making sure the participant doesn't get biased by coming to your office. But the disadvantage is that a usability test on mobile becomes pretty hard and that you can't see the full body language of the participant.

You can also use paid tools for remote usability tests:
- HotJar
- UserTesting
- UserFeel
- Lyssna


### Web Accessibility
A significant group of users that are overlooked are impaired users; those with visual, auditory, motor control, or cognitive disabilities.

Conduct user research to understand these users.

You can

### Experience it yourself 
Various chrome extensions that simulate how people with disabilities navigate the web 

Chrome Extension "Web Disability Simulator": https://chromewebstore.google.com/detail/olioanlbgbpmdlgjnnampnnlohigkjla. 

To experience a hearing disability, you can turn your device sound off and watch videos on your website that way. 

To emulate visitors that have visual or physical impairments and don't use a mouse or trackpad, you can browse the website with only your keyboard.

### Conduct a usability test or interview your users that have an impairment
See the previous section, but find disabled users and ask them about your website and where they get stuck

### Some General Rules
- Have a well structured content and a clear navigation
- Have a contrast ratio of 4.5 to 1
- Use a font size of at least 14px, but preferably 16px or larger
- Use captions in your videos
- Use alt text in your images

There are many people with an impairment, so don't forget these users when doing user research and optimizing your website.


### Customer Service and User Feedback

A very useful source for feedback from your customers is your customer service, team. They communicate with website visitors every day, and get all questions, concerns, complaints, and praises. This is fertile ground for test ideas

Sit with customer service and gather the information they get, not once, but every quarter or every 6 months. HAve a monthly meeting with the Customer Service Manager to discuss frequently asked questions. Or you can receive a monthly email with the top 5 questions, complaints, and praises.

Other Useful Resources for Customer Feedback
- Group Discussions
- Interviews
- Social Media Channels
- Reviews of your business

Gather these insights, along with the tone of voice of your customer and document them in your documentation tool.


### Other forms of user research

### Science

### User Research and Science Wrap-Up
