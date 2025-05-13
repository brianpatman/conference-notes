# WPEngine Decode Notes

## What is my content strategy in a world of AI agents?

B2A - Business to Agent; business is interacting with an automonous AI agent
C2A - Customers talk to AI agents
A2A - AI Agents talk to each other


AI Agents
- Automonous software systems that can perceive their environment, make decisions, and take actions to achieve specific goals, often with the ability to learn and adapt over time.

Basic Attributes
- Accesses and adds to memory
- Self-determines a plan of action
- Verification and Permissioned
- Completes Sophisticated Actions
- Self improvement, learns


Examples
- Home: plan, order, pay for delivery/cooked meals
- Comms: organize emails & messages; responds
- Work: gather, analyze, present data for EOM reports
- Physical: fully automonous self-driving cars (Waymo)


Advanced form of AI agents can also recruit other AI agents

### Thesis #1: AI Agents means the information comes to you

Today: Humans traverse hundreds of websites, apps, enterprise apps, which can be slow and painful

Tomorrow: AI agents will bring information to humans faster and easier

### Thesis #2: The data will reassemble in the interface that you want: voice, images, text, virtual, multimodal (often without ads), and when you want


### Examples

- Salesforce AgentForce
- Hubspot Agent.ai Agent Marketplace, suite integration\
- Crew AI: Open Source Enterprise AI Agents
- Skyfire: The AI Agent Payment Protocol


Agents will often be doing microtransactions. IT doesn't make sense for them to use credit cards; fees are too high. So they'll like use crypto or something like that.

Purchase premium versions of content for a few cents per user

Google unveiled Project Mariner - AI Agent extension on Chrome that can click through websites and complete tasks

The theory is that, in the future, the most common visitor to a website will be an AI rather than a human.

OpenAI launched AI Agent Operator

### 2025 AI Agent Ecosystem

In Data Layer
- AI Agents accessing data from Exclusive/Private Data
- AI Agents accessing Open Data from public sources, data providers, scraping services, etc...
- Unified APIs - Fast info or transactions; no imitating click path

In Management Layer
- Agent Permissions/Security - Agent authentication (KYA- know your agent), tiered credentials, and agent capabilities
- Management - Determine how agents collaborate or work together, (Arbitration) which agent gets priority in network, (Payments) agents to tech (Skyfire), agent to human (Payman), human to agent

In Applicaiton LAyer
- Agent Apps - The largest sector; multimodal input/sensors, knowledge data, output. No code agents
- Agent Platforms - Enable developers to build agents

Ecosystem Layer
- AI Agent Marketplaces


Gartner predicts Search Engine Volum with drop 25% by 2026, due to AI chatbots and other virtual agents


Five Insights and Predictions
- AI agents bring info to humans - They will centralize information, handling tasks, and purchases. Content delivered in a multi-modal format humans choose. Prior content needs to be cleansed and updated
- Media and revenue models shift dramatically - Ads will be embedded into foundational models/Perplexity. Ecommerce integrations into FMs, and AI agents centralize commerce.
- Traditional companies (big tech/corporate) respond to power loss: New company-side AI agent API's emerge, and company AI agents launch to broker with the human-agents
- Opportunity for Personalized Content at Scale - Content producers can now provide personalized content, in the way customers want, at scale, with AI
- AI agents form a new type of economy and social norms - AI Agents will interact autonomously (trading buying and selling) and evolve (learning and growing)

## AI Without Fear: Shaping your Future in an Automated World

What do we talk about when we talk about AI?

"Technosolutionism" - the belief that humanity is the problem and techology will save us

### Future of Work

No AI system has ever showed any intention behind what it's doing.

There's no future where an AI system will say "I want to put Laywer/Teachers out of a job" and not one  where they will automatically SEO optimize a website.

### The "Simple" Macroeconomics of AI
- "Nontrivial, but modest" impact on total factor productivity over the next decade - 0.66% to 0.53% increase in productivity globally
- Empirically, AI advances are unlikely to increase inequality as much as previous automation technologies, because their impact is more equally distributed across demographic groups, but there is also no evidence that AI will reduce labor income inequality
- AI is predicted to widen the gap between capital and labor income
- Need to account for negative social value (such as design of algorithms for online manipulation)


### Automation or Augmentation? The Future of Work

Which jobs are truly at risk?

"Our findings indicate that approximately 80% of the US workforce could have at least 10% of their work tasks affected by the introduction of GPTs, while around 19% of workers may see at least 50% of their tasks impacted. The influence spans all wage levels, with higher-income jobs potentially facing greater exposure"

Earlier technologies tended to automate away lower paying jobs, while this is more removing high level knowledge jobs.

**Perplexity**

There will be disparate impact across professions.

Think about how you communicated before email; in person meetings, mailings, conference calls, etc...

For most people, their job wasn't taken away due to the ability to send emails.

### In the Workplace

Human + AI is way better than using AI Alone OR Human without AI

Research paper where they split people into groups like:
- Working alone,
- Working alone with AI
- Working in teams
- Working in teams with AI


Working Alone - Control
Team with No AI - 0.2 Quality improvement over control
Individual + AI - 0.38 Quality improvement over control
Team with AI    - 0.39 Quality improvement over control; but the improvement is very marginal, so it may be more of a toss up between Team+AI and Invididual+AI


AI can help augment your individual contributors, but also your teams

People can amplify their level of skill and ability quite high with an AI

Study between the previous groups split into two; people who are experts in that field and people who are not

The most gains come from giving an expert in a field an AI system, because they perform SIGNIFICANTLY BETTER. Team+AI and Individual+AI.

Both Individual and Teams that are not experts have a large gain over not having an AI, but DO NOT PERFORM BETTER THAN AN EXPERT WITH OR WITHOUT AI.

Under Time Saved, Teams with No AI took longer, while Alone+AI saved around 8-9 minutes. Team+AI saved around 6-7 minutes

Top 10% solutions - Most came from Team+AI

### What's Next?
It's worth your time to invest in understanding AI
- It's a productivity tool, plain and simple; treat it as one
- Consider what your pain points are and what AI is good at doing; where do they intersect?

Another thing is that you can interate with AI 

> Chat: her TED Talk: https://www.ted.com/talks/rumman_chowdhury_your_right_to_repair_ai_systems?subtitle=en


## WPEngine Product Showcase
> Gary A in the Chat: "The part we need to be careful about when consuming AI is that it delivers the what minimizes the how but can take away the why"

80% of AI projects fail - Mostly due to poor definitions, organizational roadblocks, bad starting point, etc...

When WPEngine started looking into integrating AI, it was more like "What great things can we do with the data you already have?"

So they started with an AI Smart Search
- Pull everything from the WordPress Database
- Goes through a multi-step processing pipeline
- Machine learning to do fuzzing or learn that "honey" is associated with "natural sweetner", etc...
- You're not just getting a list of results, you're getting them ranked by their relevance. 



Wordpress's exact search isn't the best. It just looks for exact words. But people expect search to just WORK like it does on ChatGPT or Google.

It returns better results than the existing search behavior.

"Bean Mill" search can bring up results for "Coffee Grinders"

The vector database for the search is hosted on it's own server so it doesn't affect your existing site bandwidth.

AI Smart Search is built specifically for wordpress and automatically stays updated.

Recommendations for users is usually not great, but WPEngine is making their own Recommendation software that is AI powered. It also is generated server side, so it gets that nice SEO boost

> Fran A in Chat: "If I am not mistaken you can query via GraphQL against the vector DB spun up by WPE smart search without any extra config. It just works."

As part of AI Toolkit, WPengine is giving access to the vector database that powers the AI Search and Recommendations.

WPE also have a chatbot template, bare bones for you to further augment.

Reach out to WPE account team if you are interested in some of these beta features.

> Max L: "what is the name of the related posts block?"
> Luke P (Mod): 'Smart Search Recommendations" and its in Beta today for all of our Smart Search customers!'

AI Toolkit

Common to see 30-50 plugins on ecommerce sites


> Sarah W: "Time = $ for eCommerce. So any bloat literally is costing you (and your clients) money"

Slow Query Monitor and Dynamic Plugin Loading

"Smart Plugin Loading" - dramatically reduces page size and increasing efficiency

Tools available exclusively for E-Commerce plans where they will do the most good, but some of them will be eventually extended out to other sites.

**Nitropack**
Powerful all-in-one loading solution for WordPress. Already running on 300k+ wordpress sites.

Automatically handles caching, imge opt, and code minification. Code based SaaS tool.

Nitropack number one tool for increasing speed.
90% Nitropack sites loading in under 3 seconds.

**PageSpeedBoost**

New Features
- Lighthouse monitoring within NitroPack
- Account-level Lighthouse scores
- Performance Insights
- Reporting (coming soon!)

> Luke P (Mod): "Come join the AI Toolkit Beta!"

> Bitt D (Mod): "Thanks to everyone who's helped shape our roadmap thus far!
> 
> Want to help shape our future roadmap? Join our User Research Group! wpeng.in/decode25"


## Vetting AI in '25: What’s hype? What’s help?

> Justin Castilla -  @Gary we have a multilingual e5 model that can work in multiple languages
> https://www.elastic.co/search-labs/blog/multilingual-vector-search-e5-embedding-model


RAG - Retrieval Augmented Generation; run vectored search on your own data and then send it to an LLM as a chatbot

> Fran Agulto (Mod): Kellen Mace wrote about RAG with headless WP!
> 
> https://wpengine.com/builders/supercharge-headless-wordpress-development-with-ai-retrieval-augmented-generation-rag/

Person with thousands of legislative PDFs responsible for compliance. Basically pass the burden onto LLMs to find the very nuanced answers to your questions.

Hallucinations - with a properly built RAG, if you give it the proper information, hallucinations aren't going to be really a thing. You can help this by using the most up-to-date LLM, giving it the proper amount of data, and using proper prompt engineering.

"If you do not know the answer to my question, that's okay. Don't make anything up. Just say you don't know."

> Justin Castilla - "Knowledge is power, so the more RAG knows, the better the response."


Vector Database - See shared interactions between "power users"; they both commented on this post, etc...

> Me: "@Justin Castilla - What kinds of tools are used for RAG? Versions of Gemini or ChatGPT that you throw in all this data to or are there other tools that are more suitable for this purpose?"
>Justin Castilla: "Gemini, OpenAI, Anthropic and are all great bets. I personally use OpenAI for my prototypes and one-off scripts."
> Jeff Zallschl: "You need an embeddings model to generate vector embeddings, a place to store the embedding to efficiently search through"
> Justin Castilla: "The model doesn't necessarily have to be the above three, also. Huggingface has a ton of smaller models that just embed."
> Justin Castilla: "Data -> embedding model -> vector store -> <- LLM -> user interaction"


## From chaos to control with ACF: Taming the block editor for efficiency & design integrity

Headless WordPress App Discord Server -> wpeng.in/devrel-discord

### Building Sites Better

Most sites are really just a colleciton of rows. So they created a post type of "rows", where you can maintain a collection of all typs of rows (like a "subscribe" block)

- Adds New Custom Post Type
- Post Object field
- Custom Block registration through functions.php


> Brandon T: 'Lots of great videos and guides here: https://www.youtube.com/@WPEngineBuilders/videos '

**Check about REST API enable/disable**

ACF Local JSON Feature -> https://www.advancedcustomfields.com/resources/local-json/

ACF Blocks - Ability to register ACF blocks in the UI

The ability to edit fields inline in new versions of ACF, coming out soon!


## SEO and AI: did AI just eat my search traffic?

Inspiration from travel blog where author felt that Google and AI were killing her blog business.

"What time is the best to visit Scotland" used to send users to blogs with that information, but a lot of users are now only using the AI overview Google generates.

"While traffic may be going down, Leads may be going up, because more focused traffic can be bought in" - James Gibbons

"How do we make sure that the content we create is driving leads? And what kind of content do I want to add there?" - Miranda Gahrmann

"The quality of traffic, in certain cases, is way better along with conversions" - Jack

Google is now experimenting with "AI mode", where you don't even see the search results anymore, but just are listed as a source.

SEO used to be seen as a pure black box, but with AI overview, it's forcing the agency to learn the mechanisms of how Google parses out content from your text. Brands can use this to measure and see if their content is even relevant for these queries.

"IF you are cited in an AI overview, what text was used in the citation? AND what was the final text displayed in the AI overview and how was it modified, if at all?" - James Gibbons

### Is AI search a complement to traditional search or does it shift away from traditional searches?

Miranda Gahrmann - "Shifting away from traditional searches. Optimize for more of a conversational component."

Information is going to be presented by search in more of a conversational approach.

### AI Agents. How should companies strategically approach content generation for AI agents?

"What is your top SEO content currently that is driving traffic? Pull some of your keywords (including branded keywords) and add that into ChatGPT and see what comes back" - James Gibbons

Strategic spray and pray method of deploying content.

"Time to restructure, but strategically. Treat every month or quarter like an experiment and figure out what works from quarter to quarter or month to month."

> Zach B: "Every business owner should ask themselves. If I ask AI about my company does the right info come up? If I give AI my domain does it understand the product/service we're trying to sell?"
> Craig K: "What is [XYZ] known for?"


> Micah M: "what was the tool just mentioned to measure how likely it content is to get used by ai answers"
> James Gibbons: "I was mentioning Quattr the company I work for, you can start a free trial to optimize here https://www.quattr.com/content-ai "


"Google is the best crawler, hands down" - James Gibbons

External links can trigger crawls from Google/LLMs, but internal linking can also help. AI Agents also need to make the decisions to crawl content or not.

Make sure your brand is being mentioned at other websites.

Start putting together that Gemini/ChatGPT will be crawling your site just like Googlebot was and you're gonna start seeing a whole bunch of crawlers that you weren't seeing before. So make sure they don't get confused by your analytics to be human traffic.

Check for UserAgents of AIs and make sure they aren't getting blocked by any of your bot protections, because that could be problematic on getting your content into search

It's a great time to rethink and it's important to get all the data assembled. If you haven't been using GSC, now is the time. Now you've assembled every keyword the brand has appeared for. Also connected GA4 and Google Ads for further data.

Now we've begun to assemble data that links keywords that are linked to conversions.

Compare article publication date and the first date it popped up in Google, and start understanding the life cycle of your content

> Brandon T - "If you have search on your site, it may also help to log and view your top searches or no-result searches. This paired with google-analytic data can help shape the big picture."


### How do you define search visibility in our evolving environment?

It really does begin to shift us towards a "brand impressions" when we are talking about AI Overviews. Visbility used to mean potential for traffic, but it's now more on that brand recognition.

We may see more Direct traffic in this new "brand impressions" environment.


### Any other traditional ranking signals that matter as much as backlinks or should we be consdiering something else?

Fundamentals of SEO haven't changed. Creating good content, ensuring strong internal linking, EEAT, authorship policies, etc...

All built into "can this content be trusted?"

Deep coverage of topics in your industry instead of keeping things broad.

## The case for selling accessibility as a service

> Brandon Vreeman - "For those of you that want to find a navigation that is really well coded when it comes to accessibility, go to Chris' company's website. The navigation is very well built with accessibility in mind - https://equalizedigital.com/ "

> Chris H - https://equalizedigital.com/anatomy-of-an-accessible-navigation-steve-jones/

"We're sitting at the precipice of 'want to have' and 'need to have' and it's going to flip into the 'need to have' side of the scale very soon, with certain laws coming down."

Building an accessible website is not just checking a few boxes. It's about designing for real people, removing barriers, and creating experiences that are truly usable and welcoming.

What people think of with accessibility, mostly people think of blind and low vision. But there are those that are deaf or hard of hearing. Or those with cognitive issues or colorblindness.

Also motor impairment where certain people might only be able to use a keyboard or a "sip and puff" device.

Accessibility affects a wide swath of people.

"Another thing to appreciate is; None of us are locked at this fixed point of ability/disability. we can break our arm, go in for eye surgery, have a horrific car accident. There's a ton of things that can happen that can temporarily or permanently put us in this subset of disabled people."

The WHO indicates that up to 20% of your audience may be affected by this disability.

If 1,000 people are watching this session, 200 people may not be able to see the video or see the screen.

Accessibility isn't just a legal requirement There's a business case too, as it improves UX, increases conversions, and can even boost SEO. 

On a recent project where Chris and his team just tackled accessibility issues. No redesign or anything; just fixing accessibility things. But from this, the community college in question :
- Unique user visits to their website increased YoY by over 15%
- Aggregate time on site increased by over 1 minute
- Conversions on the site went up by ~2% for new student registrations

"Oh, people who are deaf/blind/cognitively disabled aren't part of my audience"

If you can eliminate minor and major inconveniences, and blockers to your users, you are making it way easier for the whole spectrum of disabled/non-disabled users to use your site.

On Redesign + Heavy Accessibility Priority:
- Increased overall YoY traffic by 200%+
- Page views went up by over 300%+
- Bounce Rates drop by 20%
- Session Duration Increased by 40%

"Accessibility is **Quality**"

### Common Objections from Clients and How to Overcome Them

#### "It's too expensive to add this to the project scope"

Tie it to lost revenue.

One client, got quarter of a million hits a monthon their website, but their conversion rate was 1.5%. "So, what if this just got you to 2%? That would pay for this multiple times over!" And it did!

Then you can tie it instead of to a carrot, you can tie it to a stick. Like the averge cost of an accessibility lawsuit, which is $25,000, but you're asking them for $3-4k. When you compare/contrast those numbers, it's easy to see the benefit there.


#### "Well, they're not our audience"
Like a backpacking company might react this way.

But this is totally not true! There are groups out there who are blind/low-vision who go spend tons of time hiking and camping! You don't know what you don't know.

In this instance, share some of these statistics about all people and that it's a spectrum of conditions.

Also, if you can find a competitor whose site is really accessible and highly dialed in, that's also a really good motivator.

It's really helpful to get ahead of objections in your sales presentation. You don't have to be like "100% accessible out of the gate", but you can build what you are comfortable with into the price.

If you can, get some case studies together for them.



You also need to work the client's goals and walk that back to accessibility. 

A 100 score via Google Page Speed or any automated tool does not mean that your website is fully accessible. It's one of many indicators but is not a yes/no flag for if your website is accessible or not.

The next step is to reach out to an accessibility professional and test your site manually with a screen reader and keyboard

You have to manually test.


### Practical Ways to Get Started
Start by running an automated accessibility scan of your own site's homepage.

Once you have a feel for fixing those automated issues (what Chris H calls the "low-hanging fruit of accessibility", you can start rolling that into your Agency Care Plan). If all agencies were just doing this as it stands, the web would be so much more accessible.

95% of the top 1 million website has easily detectable issues (by automated tools!) on their homepage! 

If your website doesn't come up with any accessibility issues using automated tools, congratulations! You're, sadly, in the top 5%!


> Kevin H: "Here's a nice resource for how a site could look with different visual imparements: https://www.whocanuse.com/"

> Brian G: "Here's a link to my color contrast checker of choice: https://webaim.org/resources/contrastchecker/"

> Adam Blodgett: "Accessibility is good for everyone. Even people without wheelchairs use ramps."

> Katarina Danks: "This is a recent topic for me and a client. Been reading a lot about overlays and how widget apps are not an AIO solution. https://overlayfactsheet.com/en/ "
> Kevin Hanselman: "Widgets are an accessibility lawsuit target now"
> Kevin Hanselman https://www.accessibility.works/blog/avoid-accessibility-overlay-tools-toolbar-plugins/

> Katarina Danks: another good link https://usablenet.com/
> Chris Hinds: They also have really, really good reports on the state of accessibility litigation in the USA. I'll see if I can dig up a link to that.
> Katarina Danks: This one? https://3280432.fs1.hubspotusercontent-na1.net/hubfs/3280432/UsableNet-2024-Year-End-ADA-Web-Lawsuit-Report.pdf

> David Lawless: Is there a consensus on what WCAG audit tool to use?
> Teisha Wegner: aXe (by deque), ARC Toolkit, WAVE and then manual testing

> Jess R: Do you guys have a website link that you can enter your url into that would audit the site? I'm bookmarking all the links, so I may have missed one
> Chris H: https://equalizedigital.com We put out a ton of free resources and tools. More on that later in the presentation too.
> Chris H: If you're using WordPress, we have a free plugin that will allow you to do that
> Chris H: Also the WAVE browser extension is great.

> Brian Gardner(Mod): If you're interested in accessibility, this is a must attend event. And it's 💯 free!
https://wpaccessibility.day/
> Chris H: If anyone here wants to have a judgement free conversation shoot me an email about where you are with accessibility. chris@equalizedigital.com


WordPress Accessibility Meetup - 2 times a month; recordings posted on EqualizeDigital's website