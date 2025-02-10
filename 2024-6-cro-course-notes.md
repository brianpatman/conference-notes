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

DAU - Daily Active Users
WAU - Weekly Active Users
MAU - Monthly Active Users


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
There are several test types that are also useful. For these tests, author recommends platform called Lyssna.

- Prototype test - Sync your Figma prototype design and have participants complete tasks
- First Click - Show your participants a screenshot of a webpage and ask them where they would click first, given a certain task
- Questions - A survey
- Preference Test - Respondent will see several designs and they pick the one they prefer.
- Card Sort - Ask participants to sort cards into categories; good for figuring out how to structure navigation (30 participants or more)
- Navigation Test - Analyze how users navigate your website given a specific tasks by clicking through a series of screens.
- Five Second Test - (Author's Favorite) - Show a screenshot of your website for 5 seconds and ask your respondents a couple of questions. You get information of your users' first impression.

Lyssna gives you the option to recruit from their panel of users, which will cost you a small amount, but you can also go ahead and send the link to users in your own database through whatever method you want. 

For a 5-second test, you need 20-50 participants to get the most accurate results.

You can setup even Figma designs to be A/B tested before it gets sent to developers to create and then A/B test that way.

### Science
With every assumption you make and every test hypothesis you have, it's likely that it's already been researched by someone else. This is often overlooked by those doing CRO.

You can find these scientific papers via Google Scholar (https://scholar.google.com/) and/or Semantic Scholar (https://www.semanticscholar.org/) to search for scientific papers. You can learn about your target audience, market, and product.

You could search for:
- Reasons to buy product/service x (online)
- Habits related to purchasing or using your products
- Motivations to buy product X
- Behavioral model for buying X
- Why do people buy expensive/cheap X
- Decision-making in buying

If you spend some time on this, you can find some very interesting insights.

If you can only find the Abstract of a paper and you want the full PDF without having to dish out a large sum of money, you can try:
- Google "PDF [TITLE OF RESEARCH PAPER]" and try to find a website with a free copy of the paper
- Another tip he got from a student is a website that lists almost all research papers freely accessible. (https://sci-hub.se/)

Looking for papers, he found some great research articles that he found some insights for merchandise stores:
- For online merchandise stores, the product information, assortment on the website, and price is of influence if someone will purchase or not
- Identification with the brand heavily influences buying behavior, including the amount of money spend
- Buying branded clothes results in feelings of belonging to a group
- Fans of brands desire to publicly show their affiliation with teh brand and express their support for the org
- Participants in this study attached symbolic meanings to their merchandise, emphasizing social relationships and connectedness as well as elements of personal history

We can add these insights to our documentation tool and use them to come up with new A/B tests.

In Summary, use scientific articles. These articles will teach you a lot about the needs, motivations, and behaviors of your target audience and your potential customer.


> My Note at 1:49
> On your comment about finding full scientific research papers.

> I've heard another tip where, if your other searches online turn up nothing, you can also **very politely** reach out via your personal email to the researcher(s) who performed the study and request the full research paper.

> Sometimes this may not work and they may be bound by rules restricting them from sharing it. But often, they will be happy to supply a copy, as most of the money made by these publishing houses doesn't make it's way back to the actual researcher.

> I would always, of course, try your best to find it online or pursue whatever other resources you have access to before you do. These researchers are likely very busy and emails can be missed. But this can also be a nice option in a pinch.


## Expert review, psychology basics, & competitor analysis
The last "research" part of the course

Expert Review - Analysis of the website based on your experience as a conversion specialist and best practices.

Though an expert review has a low hierarchy of proof, it may be good in cases where you don't have very much data

### Clarity
Is the content or offer on this page as clear as possible?
- Clear Value Proposition
- Clear Visual Hierarchy
- Visuals supporting the content
- Clear next steps
- Use of conventions

Value proposition *very important*. Matches your website vistors' needs and differentiates you from the competitor.

Clear visual hierarchy - should be clear what content is important and what belongs to what.

Visuals should strengthen the value proposition and match with your target audience (don't show photos of adults on a website marketing to teenagers, for example).

A clear next step on every page makes visitors convert

As we are all used to conventions, it will make it easier to navigate a website and find what we are looking for.
- Navigation should be at the top of the website
- Search should be on top with an icon of a magnifying glass
- Cart icon top right
- Company logo top left or middle
- Clicking on logo takes you to the homepage
- Category pages should have filters on left or top
- There should be a footer at the bottom of the page


##### Google Merchandise Store Expert Review
Do an expert review on Desktop, Mobile, and Tablet

There's not a clear value proposition on the homepage, which can be problematic. Some famous brands don't need a value proposition, as people already have strong brand associations. However, clothing isn't Google's core business, so they could try to experiment with adding a value proposition.

The store also has a double navigation; a short one below the header and one behind a hamburger menu. This can also confuse users, as we don't see this on other websites.

Showing most important categories on homepage or landing page is always a good idea, but author wonders if these categories (Drinkware, YouTube Collection, Kids, & Bike Collection) are actually the most important ones.

But the cart and search buttons are whre you would expect them to be.

On the Product Listing Page, there are some filters, but not a whole lot of them. Extra filters like color and available size would be nice too.

Also, there is no sizing or color information on the Product Listing page and you cannot add items to your wishlist on this page.

Onto the Individual Product Page

A model wearing the shirt might be nice to see what it looks like on a person. As well, while it shows the sizes here, that would be good information on the category page.

Selecting the Quantity is quite unusual. Usually you have the size in a dropdown and the quantity in a small input. So users might have to think about this too much.

To the cart

Estimated Shipping & Tax are left blank. Could be better if they gave you a message that this will appear after you enter your address.

To the checkout

Not immediately clear that the form fields are form fields, and why you need 2 addresses. So this makes people think.

The important thing with Clarity is to make people not have to think. Everything should be as clear to the user as possible.

### Relevancy
Does your webpage meet the visitor's expectation?

Visitors land on your website with certain expectations. If your message on your landing page is consistent with that expectation, visitors will stay on your website.

For example, if you run a facebook ad that displays "free whitepaper to download". Then when the user clicks through the ad and hits your website, they should see a similar message at the very top of the page indicating they can download the whitepaper right there.

First result on Google for "Google merchandise hoodies" is for the Mens/Unisex apparel, which would not appeal to women. But this course is over CRO and not SEO.

Sadly, when you click through, you see some hoodies, but some clothing like polos and jackets that are not applicable to the "hoodies" search.

As well, the header is on the right hand side, which is quite unusual. Moving this to the center or to the left would be the absolute best. But this would be more of a CLARITY issue.

Search for "Google shirt Female" and click the first link. In this case, we get much more relevant content, of just T-Shirts from Google.

Your landing pages should match teh expectations of your website visitors, which can guarantee they progress on your website.

When going to one page to another on your website, make sure the content on that other page matches your visitor's expectations.

### Friction
What is causing doubts, hesitations, and uncertanties?
- Form field too long
- Difficult field to fill out (Like a zip code field that requires letters, spaces, etc...)
- Bugs and errors (404 pages, filters that are not working, bad search results, etc...)
- Slow websites

Site search is VERY important and has to display the right results. If your search does not show the right results, it's a big source of friction and a conversion killer.


Several friction issues on Google Merchandise Store
- Can't filter to show only hoodies
- Many sizes are not available for many clothes AND you can only see this on the product details page
- On the cart page the Coupon field needs you to be logged in to enter a gift code, but there is no associated login button on the page
- Cannot use an incognito browser with this store, because you can't ever get past the login step.
- Finally, on the checkout, there are 2 proiminent warning messages at the top, one in Red. These can make users hesitant and cause them to drop off 

### Focus

Is there focus on the right elements?
- Convey one message
- Remove distracting/irrelevant content
- Have one call-to-action stand out

If a piece of content does not add to the motivation of your website visitor or it does not strengthen the value proposition, remove it!

You can have multiple CTAs, but one CTA should stand out.  Other CTAs that do not take visitors deeper into the funnel towards the final conversion should be removed or be made less prominent on the page.

Focus issues on the Google Merchandise Store
- The homepage slider, which is getting all the attention even though users may want to go navigate to a certain clothing category.
- In the cart, there's a lot of focus on the gift code block. For most users that don't have a gift code, this part gets way too much attention and removes focus from the Continue to Checkout button. Can trigger the feeling that hte user doesn't have a good deal or causes them to leave to get a coupon code.
- In checkout, the messages at the top also attract a ton of attention. This is bringing focus away from the form, where you actually want the user to proceed with

Bottom Line: for focus, remove everything that draws the website visitors attention away from completing the most desired action.


### Motivation and Psychology

Motivation
- Are the motivators persuasive, at the right, and believable
- Do they match the needs and motivations of your website visitors
- The best motivators are benefits matching the needs and motivations of your visitors, displayed at the right time

Especially important on Landing Pages

You can't make someone want to buy from you. Instead, we need to align with the user's motivations and show that our products/services match their needs.

In your user research, data, and science, you can discover what drives your website visitors. With psychology, you can strengthen these benefits.

Uses the 6 principles of Cialdini:
- Reciprocity
- Commitment & Consistency
- Social Proof
- Authority
- Likability
- Scarcity

Align your motivators first and then align them with the 6 principles

### Reciprocity
Our tendency to return a favor and not feel indebted.

Online, you can give something of value away for free or at a Low introductory price. In the latter, you should make it apparent to your customer that they get way more value than they paid for. Only then will reciprocity  kick in.

The intention is that the user will feel indebted due to the free/cheap item and soon convert fully.

For the Google Merchandise Store, they could find something that would be appealing to their fans. For instance:
- People could sign up for a newsletter and be the first to try new Google products for free
- Host a community event

By giving something away for free, or for very low introductory price, people will feel indebted and so will have a higher likelihood of converting in the future.

### Commitment and Consistency

As humans, we have the need and tendency to be consistent with a made decision. When we start something, we want to finish it. So when you are part of the way along the process of checking out on an online store, you are more likely to finish rather than bounce.

Need to be consistent 

Online
	- Steps in checkout process
	- Consistency in buttons
		- If a visitor comes to your website from an ad and clicked a green button to get there, you need those green buttons in your funnel. That way the visitor stays consistent with the behavior of clicking on that green button
	- Break up a long form
		- Break it up into multiple steps, so after completing a few fields, users will be more invested and more likely to complete the steps on the following pages
		- However, the author says to definitely experiment with this part, as he's seen mixed evidence
	- Wishlist
		- When users add products to a wishlist, they have a tendency to eventually buy them


Google Merchandise Store does show consistency with buttons, as they are all blue buttons. The "Add to Wishlist" is also a smaller link with no background color.

They could experiment with displaying the wishlist on the category page as well.

When you get to checkout, you can see a progressbar at the top of the page, to help users see how far along they are. However, it's very unclear that it is a progressbar, so Author suggests Google show the individual steps the user needs to take and make the progress bar stand out more.

### Social Proof
Humans have the tendency to do what others do (especially when uncertain)

We like to think we are individual creatures, but we often want to be accepted as part of the crowd.

Online
	- Reviews
	- Ratings
	- Customer Stories
	- Client Logos
	- Etc...

Make social proof as trustworthy as possible

A good customer story with first name, surname, and picture is worth way more than just some boxed review text with a First Name.

As well, some negative reviews actually make it look more real for your visitors, instead of merely displaying 5-star reviews. So make it as trustworthy as possible

For the Merchandise Store Example
- Very Simple; show reviews and ratings of the products and display an overall rating

### Authority
We have a tendency to obey figures of authority. We attribute accuracy to their opinion and can be influenced by it.

The Authority principle is also triggered if you are told something by a psychologist or your doctor.

Online
- Media Icons
- Awards your company has won
- Number of years in business
- Images or videos of you or your boss on stage; or perhaps start a blog with articles to show off your expertise

For the Merchandise Store Example:
	- Benefits from Google's Authority position
	- "Become part of the global Google community with 30,000 fans"

### Liking
People we like are more trustworthy

Online
	- Pictures of your staff - Users will see the face behind the website
	- Show you are the same as your visitor - Someone in your team could tell a story about your product or service
	- Show you understand your website visitors - Show you understand their pains, problems, and needs and mention how your product could help them.

For the Merchandise Store
- Display images of their staff
- A picture of the merchandise team (all wearing Google merch, of course)
- Emphasize the need to belong to a community as Google fans

### Scarcity
We value something that is scarce, therefore we want it more

Online
- Time-related scarcity
- Quantity-related scarcity

On the Google Merchandise Store
- Place more focus on the number of items in stock
- Add copy that you should order fast before the item becomes unavailable
- However, never lie and be honest; this is illegal and backfires by destroying trust

### Landing page and product page best practices
It's important that Landing pages and product pages have a large conversion rate, as often money is spent on ads to send users to these pages

- Have a big, relevant, and benefit-driven header support by high-quality visuals
- Start with benefits before features
- Use Social proof and make it as real as possible
- Single and clear CTA - preferably display at top of page and bottom
- Be as clear as possible - What will users get when they convert? Make sure your visitors have sufficient information so they can make a decision.

In general, besides these tips:
- Limit distraction
- Make it as easy as possible for the user to convert
- Create Urgency when Possible
- Show indicators of Safety and Authority.

### Checkout best practices

In checkout, you've already convinced the user to do business with you, so it's very different from a product page or landing page

3 best practices for checkout
- Limit distraction - You want the complete focus on your website visitor to go through every checkout step and finally convert
- Remove all forms of friction - Make it very easy for your visitor to fill out all the fields in your checkout and pay; also, remove all unnecessary form fields. The more fields you have, the more likely your visitor drops off
- Show the steps needed to convert, and show the visitor when they completed the step - This gives your visitor the feeling that they've started something and, therefore, will want to finish it!


### Copywriting best practices

Having the right copy on your website is also of great importance.

- Match your tone of voice with the voice of your customers - omit all forms of jargon and complex words; write how you would speak to your customer. 

	Dont say 
		"provide your details to proceed". 
	Use 
		"tell us about yourself"

- Be consistent in your copy - Use same terms for the same thing across your website
- Apply focus - Remove unnecessary words and keep things concise
- Make your text easy to scan - Descriptive headers, bullet points, and for long texts, you can use bold sentences
- Make it about the user - Show them how they can benefit from your offer; use the word "you"
- Write in an active voice - Makes it easier and more appealing to read. Good way to see if you are slipping into passive voice is finding if you are omitting the person or thing responsible for actions from your sentences. 

	Example of Active vs Passive Voice

		Passive - ~~ The house will be cleaned every Saturday ~~
		Active - I will clean the house every Saturday

- Omit words with negative connotations and change them to their positive connotations unless you stress a negative statement

	~~Don't use negative statements~~
	Use Positive Statements

	~~Don't make your text a hassle to read~~
	Make your text easy to read

- Write compelling benefits before clear and precise features; Why before the what
- Create emotional-centric copy

	To get the best copy, use the following formula
		Feature + Benefit = emotional-centric copy

	Make sure to know your customer pains and product to develop the best copy

	"Never wait around for the dev team again! Build any page (in less time than it takes to run a meeting about the page) on your own"

	"The simplest way to transform your posture"

	So, add emotional benefits to your copy by presenting benefits over features and by telling your customers' story.

### Competitor Analysis
The websites of your competitors can be another valuable source for your optimization.

- Analyze your Biggest Competitors
- Check what results come up in Google and analyze those websites as well
- Ask your customers


When you analyze the website of your competitors
- Highlights: Aspects where the competitor does better
- Noticeable Differences: Aspects that the competitor does completely differently.


Also check Reviews and Socail Medica Channels for Complaints, Questions and Praises. If a competitor gets many complaints or praises, you can use those things to make your website better.

Even your biggest competitors might not have a conversion specialist like you. They might not run A/B tests or do CRO tests. Then, when you find insights, add it to your testing plan and test it

A far more interesting way to analyze your competitor's website is to conduct a usability test

	- Direct Comparison Test: Complete a task on your website and your competitor's website
	- Isolated Test: Have participants complete a task on one website

This will give you a way to see where your competitor does better on the customer journey.

## Combine Insights, Prioritization, and Hypotheses

### Behavioral Hypotheses
Time to bring everything together.

When you do actual research for your site, you want to spend many hours, days, or even weeks. The more and better research you do, the better insights you arrive at, and better A/B tests you can before.

In this lesson, we will begin with Meta-analysis. To begin with this, we have to create behavioral hypothesis

In science, a meta-analysis is an analysis that combines the results of multiple studies. A single study (or A/B test) can be prone to errors, so a meta analysis aims to derive a pooled estimate closest to the truth.

For instance, for the merchandise store, we might think that adding social proof is the way to increase conversions. If we added it right above the categories and below the slider, and it resulted in a win, we might be tempted to call our hypothesis true. But, it's very possible that the social proof was not the real reason for the gain but, rather, the pushing down of those categories that users might see as irrelevant.

So a single A/B test can be prone to errors. Therefore, we conduct a meta-analysis to get closest to the truth as to what drives your visitors, and further understand what A/B tests are the best to run.

To conduct a meta-analysis, we need behavioral hypotheses
- General hypothesis stating something about your visitor's behavior, needs, and motivations
- Cluster research insights that belong together


For example, on the merchandise store:
- People buy merchandise becuase they love the brand (several sources)
- People want to be part of the Google community (several sources)
- People identify themselves with a brand (science)
- People are a fan of Google (poll)
- Customers use many Google products (interviews)

A good hypothesis on this is "When we elaborate on the brand and community feelings, sales increase"

In quantitative data, we have found:
- Visitors click back a lot (data)
- Many questions about shipping, delivery dates, and return policies (customer service)
- People seek information regarding the product itself and shipping (usability test)

A good hypothesis on this is "By providing clarity, sales increase"


These are just two, but when you do your optimization research:
- Aim for 4-10 behavioral hypotheses
- Use A/B Tests to verify or reject them (meta-analysis)
- Run several A/B tests related to one hypothesis

For the need for clarity, maybe we do the following:
- Test 1: Add product information
- Test 2: Add shipping information to the cart
- Test 3: Make return policy stand out on the checkout


Once you find an A/B test winner, which verifies a behavioral hypothesis, you could have learned something very valuable. 

When you find many winners for one behavioral hypothesis, you know you are on the right track.

CRO to increase conversions and **do research**

Everyone in the company can benefit from your insights!


### Combine Insights
Now that we have created our behavioral hypotheses, we need to come up with A/B tests to test these hypotheses. First, we need to decide whether to test something or fix something right away.

Author suggests to immediately fix Bugs, errors, and page speed issues. And to test everything else.

Craft the insights from our research into test ideas.

Our ideas for the merchandise store:
- Provide an estimated delivery date above the fold on the product detail page (for Clarity)
- State the return policy on the cart page (for Clarity)
- Provide the available sizes on the category pages (for Clarity)
- Add a value proposition on the Homepage (for elaborating on the brand)
- Display the mesage to thank for choosing Google on checkout (for elaborating on the brand)

Ideally you want many tests based on your beahvioral hypotheses, but if you have others that you'd like to try out, go ahead and do so! 
