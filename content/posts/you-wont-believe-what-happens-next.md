---
title: "Digital Assistants, Facebook Quizzes, And Fake News! You Won’t Believe What Happens Next"
draft: true
colours: ["#aa2222", "#595959", "#c42e27", "#343434", "#ffffff", "#0a0a0a", "#ffffff"]
date: 2017-04-10T12:58:22+00:00
categories: ["ind.ie"]
tags: ["Better", "better.fyi", "Ind.ie", "slides", "speaking", "talks"]
---

{{< oldpost >}}

This is the talk I gave at DIBI Conference in Edinburgh in March 2017. Many people asked me for my slides, but I wanted to include them in context, with accessible links. This is roughly how it went:

[{{< figure class="aligncenter size-large wp-image-4862" src="/images/2017/04/001-1024x576.jpg" alt="Digital Assistants, Facebook Quizzes, And Fake News! You Won’t Believe What Happens Next @laurakalbag @indie @betterbyindie https://ind.ie https://better.fyi" width="1024" height="576" >}}](/images/2017/04/001.jpg)

## Performance!

Nowadays performance seems to be the hot topic of the web industry. So let’s have a look at how we might improve the speed of a web page.

[{{<figure class="wp-caption aligncenter size-large wp-image-4863" src="/images/2017/04/006-1024x576.jpg" alt="Screenshot of the Onion homepage" width="1024" height="576" caption="theonion.com">}}](/images/2017/04/006.jpg)
Looking at [the Onion homepage](http://www.theonion.com), you can see it’s loading lots of images and a few videos. It’s mostly images and text content. There’s a big sticky ad at the bottom of the viewport that takes a while to load.

[{{< figure class="aligncenter size-large wp-image-4864" src="/images/2017/04/009-1024x576.jpg" alt="Safari Web Inspector for The Onion: 384 resources, 8MB, 15.24 seconds, 205 errors, 8 warnings" width="1024" height="576" >}}](/images/2017/04/009.jpg)

If you look at what’s loading behind the scenes, you can see a the layout being rendered, loading in all the content first, then more and more requests as new stuff is being loaded in. All in all, they’re loading 384 resources, coming in at 8MB, taking 15.24 seconds minimum to load. (There’s also 205 errors which may well be impacting that load time.)

If we look at Safari’s Network Requests tab, we can see a little more of what’s being loaded in. If we look at the requests by size:

[{{< figure class="aligncenter size-large wp-image-4865" src="/images/2017/04/011-1024x576.jpg" alt="Screenshot of Safari web inspector’s resources. Showing the files listed below" width="1024" height="576" >}}](/images/2017/04/011.jpg)

* **.html** the primary HTML document is only the 19th largest file being loaded
* The largest file is **.js**, a biggish javascript file, that’s fairly standard
* The next **.js** file is a lightbox script, there’s an external <abbr title="Content Delivery Network">CDN</abbr> for fast loading, that’s fine.
* **.css** is CSS, which is very important!
* **.js** is jQuery, fine if you must…
* **.jpg** is a big picture of houses

But then there is also…

* **addthis.com** AddThis social buttons
* **addthis.com** more AddThis
* **perfectmarket.com** Perfect Market
* **taboola.com** Taboola
* **taboola.com** Taboola again
* **doubleclick.net** Google DoubleClick
* **krxd.net** Krux
* **moatads.com** Moat Ads
* **googlesyndication.com** Google Syndication
* **googlesyndication.com** Google Syndication again
* **optimizely.com** Optimizely
* **googleadservices.com** Google Ad Services
* **2mdn.net** which I know is another domain for Google DoubleClick.

I could go on for other 408 requests but I’d be here for a week. These are all scripts for tracking people in one way or another.

What would happen if we just load the main page without any third party tracking scripts? Let’s look again at that timeline, but this time with those third party tracking scripts blocked:

[{{< figure class="aligncenter size-large wp-image-4866" src="/images/2017/04/034-1024x576.jpg" alt="Safari Web Inspector for The Onion: 115 resources, 2.95MB, 2.27 seconds, 1 error, 9 warnings" width="1024" height="576" >}}](/images/2017/04/034.jpg)

The Onion now has 115 requests, coming in at 2.95MB, loading in just 2.27 seconds.

Comparing the before and after, that’s 269 requests, 5.11MB and 12.97 seconds caused by third party trackers.

[{{< figure class="aligncenter size-large wp-image-4898" src="/images/2017/04/Digital-Assitants-etc.041-1024x576.jpeg" alt="Your web performance effort means nothing" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.041.jpeg)

You know what that means? Your web performance effort counts for little to nothing if your organisation’s business model requires a gazillion tracking scripts to make money.

## Facebook

[{{<figure class="wp-caption aligncenter size-large wp-image-4867" src="/images/2017/04/044-1024x576.jpg" alt="Screenshot of my Facebook profile" width="1024" height="576" caption="Me on Facebook">}}](/images/2017/04/044.jpg)
Let’s look at this phenomenon from the perspective of the people browsing the web. We feel like we know Facebook’s game. They show us adverts, and we get to socialise for free. Simple as that?

I don’t give Facebook much info, I get ads for the average 30 year old woman: washing liquid, shampoo, makeup, dresses, more dresses, and sometimes a wild card ad for pregnancy tests. But what happens when Facebook gets a bit more information?

[{{< figure class="aligncenter size-large wp-image-4868" src="/images/2017/04/051-1024x576.jpg" alt="Ads I’ve seen on Facebook for washing liquid, shampoo, makeup, dresses, more dresses, and a pregnancy test" width="1024" height="576" >}}](/images/2017/04/051.jpg)

Nearly two years ago, my mother died. We didn’t want any of our friends and family finding out from a poorly thought-out tweet or Facebook post… so we didn’t post anything on social media. We rang people to let them know. And then Facebook suggested I might be interested in… Goodwill Family Funeral Directors.

[{{< figure class="aligncenter size-large wp-image-4869" src="/images/2017/04/056-1024x576.jpg" alt="Facebook ad for Goodwill Family Funeral Directors" width="1024" height="576" >}}](/images/2017/04/056.jpg)

Surely just a coincidence?

So I asked my sisters and brother if any of them had posted something on Facebook…

[{{< figure class="aligncenter size-large wp-image-4929" src="/images/2017/04/Digital-Assitants-etc.058-1024x576.jpeg" alt="Me asking: Did any of you tell your friends on Facebook? Facebook has started showing me creepy funeral director ads…" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.058.jpeg) [{{< figure class="aligncenter wp-image-4930 size-large" src="/images/2017/04/Digital-Assitants-etc.060-1024x576.jpeg" alt="Jess replied: Not me! Might just be coincidence… Hmm" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.060.jpeg)

[{{< figure class="aligncenter size-large wp-image-4931" src="/images/2017/04/Digital-Assitants-etc.061-1024x576.jpeg" alt="Nini says: “Sorry, that was me I think - I face booked Madds cos she's in Australia now xxx”" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.061.jpeg)

Well it might just be a strange coincidence, but maybe too close to be a coincidence. My sister *had* told her friend via private message. She’d used some key words in a Facebook message to her friend Maddy, Facebook may have made the connection that I’m her sister, figured out that I might want a Funeral Director and stuck that ad in my feed. It just goes to show how much Facebook knows, and how much complexity it can grasp, despite my not telling it anything.

[{{< figure class="aligncenter size-large wp-image-4870" src="/images/2017/04/068-1024x576.jpg" alt="Diagram showing my sister talking to her friend on Facebook, Facebook knowing I’m her sister, and the funeral director ad I got in my Facebook feed" width="1024" height="576" >}}](/images/2017/04/068.jpg)

### How do they know?

But how else could Facebook have known?

[{{< figure class="aligncenter size-large wp-image-4871" src="/images/2017/04/074-1024x576.jpg" alt="Screenshot of CBS news article on Facebook buttons violating privacy" width="1024" height="576" >}}](http://www.sbs.com.au/news/article/2016/03/10/facebook-button-violates-privacy)

If I was browsing funeral-related sites, maybe Facebook would have that information if those sites had Facebook Share Buttons or Facebook login. As [this article in SBS News](http://www.sbs.com.au/news/article/2016/03/10/facebook-button-violates-privacy) points out, those Facebook buttons track you across the web, violating your privacy. (Also note the hypocrisy of this news site using multiple Facebook buttons on this article.)

You can find out some of the things Facebook knows about you in your Ad Preferences.

[{{< figure class="aligncenter size-large wp-image-4872" src="/images/2017/04/079-1024x576.jpg" alt="More of my Facebook ad preferences including Away from Family, Expat (UK), iPhone 7, Frequent International Travellers, All iOS Devices" width="1024" height="576" >}}](/images/2017/04/079-1024x576.jpg)

But as ProPublica point out, Facebook doesn’t tell its users everything it really knows about them:

> “What the [Facebook ads] page doesn’t say is that those sources include detailed dossiers obtained from commercial data brokers about users’ online lives. Nor does Facebook show users any of the often remarkably detailed information it gets from those brokers.”—[Julia Angwin, Terry Parris Jr.and Surya Mattu, December 2016](https://www.propublica.org/article/facebook-doesnt-tell-users-everything-it-really-knows-about-them)

I’ll come back to data brokers later.

> “The fundamental purpose of most people at Facebook working on data is to influence and alter people’s moods and behaviour.They are doing it all the time to make you like stories more, to click on more ads, to spend more time on the site.” [A data scientist who previously worked at Facebook](http://andrewledvina.com/code/2014/07/04/10-ways-facebook-is-the-devil.html)

If your first thought is “but isn’t that what we’re all trying to do”, you need to watch some sci-fi. The Nosedive episode from Black Mirror series 3 may seem far-fetched, but we are already participating in this ranking. It’s just not visible to us.

[{{< figure class="aligncenter size-large wp-image-4873" src="/images/2017/04/082-1024x576.jpg" alt="Still from Black Mirror’s Nosedive episode showing the main character with her online rating" width="1024" height="576" >}}](/images/2017/04/082-1024x576.jpg)

“But you don’t have to be on Facebook!” We hear this all the time from people who have never joined Facebook, have no intention of leaving Facebook, who don’t socialise, or who are generally pedantic and tedious. My answer is: NOPE.

### You can’t just leave Facebook

You can’t just leave Facebook. First of all, you’d end up severing social ties, miss out on events and other social interactions that people limit to Facebook. But even if you do leave, or if you never joined, [Facebook has a shadow profile on you](http://www.zdnet.com/article/firm-facebooks-shadow-profiles-are-frightening-dossiers-on-everyone/).

If a friend or acquaintance has used the Find Friends functionality, or used Facebook Messenger on their phone, they gave Facebook access to their Contacts. Facebook uses those names, email addresses, and phone numbers to build their shadow profiles.

[{{< figure class="aligncenter size-large wp-image-4875" src="/images/2017/04/088-1024x576.jpg" alt="Screenshot of all the different input forms for Facebook’s Find Friends, including email addresses and passwords" width="1024" height="576" >}}](/images/2017/04/088-1024x576.jpg)

The following quote is nearly four years old:

> “Right now commenters across the Internet will be saying, Don’t join Facebook or Delete your account. But it appears that we’re subject to Facebook’s shadow profiles whether or not we choose to participate.

> I feel like we’re only beginning to understand why Facebook’s data is so very valuable to advertisers, governments, app makers and malicious entities.”—[Violet Blue, Zero Day. June 2013](http://www.zdnet.com/article/firm-facebooks-shadow-profiles-are-frightening-dossiers-on-everyone/)

### Facebook isn’t alone

Facebook isn’t the only place this happens. If I go to the Spotify website, just to download Spotify, using Firefox and their [Lightbeam extension](https://mozilla.org/lightbeam). (Lightbeam is a Firefox add-on. It shows you who is tracking you via third-party scripts.) Lightbeam shows me that Spotify sends my data to 25 sites.

[{{< figure class="aligncenter size-large wp-image-4876" src="/images/2017/04/097-1024x576.jpg" alt="The Lightbeam interface on Firefox, showing 25 sites that Spotify passes my data on to" width="1024" height="576" >}}](/images/2017/04/097.jpg)

Let’s have a closer look at these sites… there are a few that are familiar to developers…

* **Google Analytics**, we know that’s analytics
* **Twitter and Facebook**, possibly some kind of sharing buttons (but also possibly not)

But that leaves 21 more mysterious scripts… Let’s have a close look at one of those sites…

[{{< figure class="aligncenter size-large wp-image-4877" src="/images/2017/04/109-1024x576.jpg" alt="The Lightbeam interface highlighting adsrvr.org" width="1024" height="576" >}}](/images/2017/04/109.jpg)

## What is adsrvr.org?

[{{< figure class="aligncenter size-large wp-image-4878" src="/images/2017/04/110-1024x576.jpg" alt="Screenshot of adsrvr.org" width="1024" height="576" >}}](/images/2017/04/110.jpg)

A quick search of adsrvr.org brings me to an opt-out page which shows me this site belongs to the The Trade Desk. The Trade Desk is apparently: “true buying power” and “omnichannel buying capabilities and industry –; leading tech” Whatever that means.

[{{< figure class="aligncenter size-large wp-image-4879" src="/images/2017/04/111-1024x576.jpg" alt="Screenshot of The Trade Desk’s homepage saying they have “True Buying Power”" width="1024" height="576" >}}](/images/2017/04/111.jpg)

At [Ind.ie](https://ind.ie), we’ve been doing a lot of research into trackers lately, and here’s a top tip: always check out the privacy policy. Most tracking companies are the clearest about their agendas in their privacy policies.

> “The Trade Desk Technology allows our Clients to buy ad space on websites for online advertising and allows for the use of proprietary and third party data in the purchase of that media.”—[The Trade Desk Privacy Policy](http://thetradedesk.com/general/privacy-policy)

> “Our Technology collects Non-Personally Identifiable Information(“Non-PII”) that may include, but is not limited to…

> * Your IP host address,
> * the date and time of the ad request,
> * pages viewed,
> * browser type,
> * the referring URL,
> * Internet Service Provider,
> * and your computer’s operating system,”

> [The Trade Desk Privacy Policy](http://thetradedesk.com/general/privacy-policy)

That’s a lot of your information going into the cloud. But did you notice the caveat? Non-personally identifiable information.

### Non-personally identifiable information

> “Such as your IP host address, age, gender, income, education, interests and usage activity…”[The Trade Desk Privacy Policy](http://thetradedesk.com/general/privacy-policy)

Take my IP address where I work in Malmö… it can pinpoint me to exactly where I am 25% of the time. And then if you add in my age, gender and education (which is all easily available on Facebook, Linkedin, etc)… How many 30 year old women who studied in Somerset in the UK are working in that building in Malmö 800 miles away? It’s definitely this idiot.

[{{< figure class="aligncenter size-large wp-image-4880" src="/images/2017/04/146-1024x576.jpg" alt="My IP address, age, gender and education overlayed on a map of Malmö, where I work" width="1024" height="576" >}}](/images/2017/04/146.jpg)

But they “don’t share it.” “It’s non-personally identifiable information.” But how true is that really? In [‘Why “Anonymous” Data Sometimes Isn’t’](http://archive.wired.com/politics/security/commentary/securitymatters/2007/12/securitymatters_1213), Bruce Schneier, a cryptographer, computer security and privacy expert says:

> “it takes only a small named database for someone to pry the anonymity off a much larger anonymous database”— [ Bruce Schneier](http://archive.wired.com/politics/security/commentary/securitymatters/2007/12/securitymatters_1213).

With more than one dataset, and the right algorithm, nearly any dataset can be de-anonymised. An example of these databases could be Sweden’s hitta.se, or the UK’s electoral roll. With these publicly-available databases, any or all of this data could be connected to me as a person.

[{{< figure class="aligncenter wp-image-4899 size-large" src="/images/2017/04/Digital-Assitants-etc.156-1024x576.jpeg" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.156.jpeg)

This means many of these third parties can work out a lot more about me and my habits, but surely they don’t know me as…a person?

> “Facebook knows you better than your members of your own family”—[Sarah Knapton, Science Editor, Daily Telegraph.January 2015](http://www.telegraph.co.uk/news/science/science-news/11340166/Facebook-knows-you-better-than-your-members-of-your-own-family.html)

Psychologists and a Computer Scientist from the Universities of Cambridge and Stanford discovered that [computer-based personality judgments are more accurate than those made by humans](http://www.pnas.org/content/112/4/1036.abstract).

> “The team found that their software was able to predict a study participant’s personality more accurately than a work colleague by analysing just 10 ‘Likes’.”—[Sarah Knapton, Science Editor, Daily Telegraph. January 2015](http://www.telegraph.co.uk/news/science/science-news/11340166/Facebook-knows-you-better-than-your-members-of-your-own-family.html)

> “Inputting 70 ‘Likes’ allowed it to obtain a truer picture of someone’s character than a friend or room-mate, while 150 ‘Likes’ outperformed a parent, sibling or partners.”—[Sarah Knapton, Science Editor, Daily Telegraph. January 2015](http://www.telegraph.co.uk/news/science/science-news/11340166/Facebook-knows-you-better-than-your-members-of-your-own-family.html)

[{{< figure class="aligncenter size-large wp-image-4881" src="/images/2017/04/161-1024x576.jpg" alt="Diagram showing the correlation between how many likes on Facebook and how well the algorithm knows you" width="1024" height="576" >}}](http://www.pnas.org/content/112/4/1036/F2.large.jpg)

> “It took 300 ‘Likes’ before the programme was able to judge character better than a spouse.”—[Sarah Knapton, Science Editor, Daily Telegraph. January 2015](http://www.telegraph.co.uk/news/science/science-news/11340166/Facebook-knows-you-better-than-your-members-of-your-own-family.html)

With the introduction of Facebook reactions, there’s even more Facebook can know about you because they have more specific data. [Police in Belgium have even warned people about using Facebook reactions](http://www.independent.co.uk/life-style/gadgets-and-tech/news/facebook-reactions-%20belgian-police-warn-citizens-not-to-react-to-posts-on-social-media-a7027786.html)…

> “Belgian police now says that the site [Facebook] is using them as a way of collecting information about people and deciding how best to advertise to them. As such, it has warned people that they should avoid using the buttons if they want to preserve their privacy.”—[The Independent](http://www.independent.co.uk/life-style/gadgets-and-tech/news/facebook-reactions-%20belgian-police-warn-citizens-not-to-react-to-posts-on-social-media-a7027786.html)

[{{< figure class="aligncenter size-large wp-image-4882" src="/images/2017/04/163-1024x576.jpg" alt="Facebook reactions: Like, Love, Haha, Wow, Sad, Angry" width="1024" height="576" >}}](/images/2017/04/163.jpg)

> “By limiting the number of icons to six, Facebook is counting on you to express your thoughts more easily so that the algorithms that run in the background are more effective,” the post continues. “By mouse clicks you can let them know what makes you happy.”—[The Independent](http://www.independent.co.uk/life-style/gadgets-and-tech/news/facebook-reactions-%20belgian-police-warn-citizens-not-to-react-to-posts-on-social-media-a7027786.html)

That is real information from the Belgian police. How many things have you liked on Facebook? Do you use the other reactions too?

## Welcome to the world of the Data Broker

And this is why data brokers exist. They are corporations whose business it is to collect and combine data sets:

[{{< figure class="aligncenter size-large wp-image-4883" src="/images/2017/04/170-1024x576.jpg" alt="LexisNexis homepage" width="1024" height="576" >}}](/images/2017/04/170.jpg)

> “LexisNexis helps uncover the information that commercial organizations, government agencies and nonprofits need to get a complete picture of individuals, businesses and assets…”

[{{< figure class="aligncenter size-large wp-image-4884" src="/images/2017/04/172-1024x576.jpg" alt="Acxiom homepage" width="1024" height="576" >}}](/images/2017/04/172.jpg)

> “Only Acxiom connects people across channels, time and name change at scale by linking our vast repository of offline data to the online environment”

It’s a big money business, and the different ways to monetise you are endless. For example, a couple of years ago, Facebook was granted a patent:

[{{< figure class="aligncenter size-large wp-image-4885" src="/images/2017/04/176-1024x576.jpg" alt="Facebook’s patent" width="1024" height="576" >}}](/images/2017/04/176.jpg)

> “When an individual applies for a loan, the lender ” examines the credit ratings of members of the individual’s social network who are connected to the individual through authorized nodes. If the average credit rating of these members is at least a minimum credit score, the lender continues to process the loan application. Otherwise, the loan application is rejected.”

Yes, that means what you think it does. It means they want to approve loans based on the financial records of your Facebook friends. And would that make you think about your friends in a different light? What about when your friend unfriends you on Facebook because you’re too poor?

## Governments and corporations

[{{< figure class="aligncenter size-large wp-image-4886" src="/images/2017/04/182-1024x576.jpg" alt="Donald Trump meeting with tech leaders from Silicon Valley" width="1024" height="576" >}}](/images/2017/04/182.jpg)

Privacy advocates have long worried about the data that is collected by corporations getting into the hands of unfriendly governments. With the political situation we find ourselves in now, those privacy advocates are unfortunately being proved right:

[Border controls across the world using social media to discriminate against travellers](http://www.theverge.com/2017/1/30/14438280/trump-border-agents-search-social-media-instagram), even demanding those under scrutiny enter their password to allow authorities access to their accounts. Of course, this disproportionately affects people of colour and other victims of bigoted profiling. [People arrested during protests on Trump’s Inauguration Day had investigators requesting their data from Facebook to help incriminate them](https://www.engadget.com/2017/02/10/inauguration-protest-arrests-lead-to-facebook-data-prosecution/). And [anti-choice groups have used behavioural advertising on phones to target women in healthcare clinics](https://rewire.news/article/2016/05/25/anti-choice-groups-deploy-smartphone-surveillance-target-abortion-minded-women-clinic-visits/). Erin Kissane put it best in her post on how to “Be More Careful on Facebook” when she said:

> “If you believe Facebook will keep your data safe and never let it be used against you or your most vulnerable contacts, by governmental or private entities, you’re putting your faith in an entity that has demonstrated bad faith for years.”—[Erin Kissane, Be More Careful on Facebook, February 2017](http://incisive.nu/2017/facebook/)

## Data grabbing is the dominant business model of mainstream technology

[{{< figure class="aligncenter size-large wp-image-4900" src="/images/2017/04/Digital-Assitants-etc.190-1024x576.jpeg" alt="Data grabbing is the dominant business model of mainstream technology" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.190.jpeg)

I may be spending an unequal amount of time focusing on Facebook when, grabbing your data is really the dominant business model of mainstream technology. I thought I’d insert here a list of products and services that collect your information without really needing it, but I realised it’d be unending. Instead, I’ve made a list of products whose information on you would probably make you a little uncomfortable…

* **Google Nest**, home security that [will have a good look around your home](https://www.theguardian.com/technology/2015/jun/18/googles-nest-cam-always-watching-live-streaming-video)
* **Hello Barbie**, a doll who your kids can talk to, [recording all their responses, and sending it back to a multinational corporation](http://europe.newsweek.com/privacy-advocates-want-take-wifi-connected-hello-barbie-o%20ine-313432)
* [**Smart pacifier**](https://www.pacif-i.io), in case you wanted to put a chip in your baby.
* **Your medical records.** [Because it’s fine if Google has those, right?](https://www.digitalhealth.net/2017/03/deepmind-health-is-in-conversation-with-nhs-trusts-across-the-country/)
* [**Looncup**](https://www.kickstarter.com/projects/700989404/looncup-the-worlds-first-smart-menstrual-cup), a smart menstrual cup! It’s one of many smart things that women can put inside themselves. (Note that most of the internet of things companies in this genre are run by men…)
* **We Connect’s smart dildo**, which was [found to be tracking its users’ habits](http://www.vocativ.com/358530/smart-dildo-company-sued-for-tracking-users-habits/)

And have you ever wondered how many calories you’re burning during intercourse? How many thrusts? Speed of your thrusts? The duration of your sessions? Frequency? How many different positions you use in the period of a week, month or year? Then you want the [iCondom](http://britishcondoms.uk/i-con-smart-condom.html).

[{{< figure class="aligncenter size-large wp-image-4887" src="/images/2017/04/211-1024x576.jpg" alt="iCondom packaging" width="1024" height="576" >}}](/images/2017/04/211.jpg)

That’s assuming you want all that information shared with advertisers, insurers, your government, and whoever else wants to buy it…

Needless to say, beware the *Internet Of Things That Spy On You*.

[{{< figure class="aligncenter size-large wp-image-4901" src="/images/2017/04/Digital-Assitants-etc.212-1024x576.jpeg" alt="Beware the Internet Of Things That Spy On You" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.212.jpeg)

## Learning about yourself ≠ corporations learning about you

Some of these products are really cool. I was an early adopter of fitness trackers. I love to know data about myself, and use that to encourage better habits. Learning about yourself does not have to mean that corporations learn about you too. None of these Internet Of Things products *need* to share your data back to their various clouds, or with any other parties, to be convenient to you. These are physical products. They have a clear option for a business model, they can be sold for money.

[{{< figure class="aligncenter size-large wp-image-4903" src="/images/2017/04/Digital-Assitants-etc.213-1024x576.jpeg" alt="Learning about yourself is not equal to corporations learning about you" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.213.jpeg)

Not to mention, collecting information about people can be dangerous. Any organisation collecting data has to be able to keep it secure and safe from malicious parties. Glow, a pregnancy app, [was discovered to have vulnerabilities](http://www.consumerreports.org/mobile-security-software/glow-pregnancy-app-exposed-women-to-privacy-threats/) making it easy for stalkers, online bullies, or identity thieves to use the information they gathered to harm Glow’s users.

### Chilling Effect

Even if you’re aware that these products are spying on you, and you continue to use them, they can still affect you in adverse ways. They can create a “chilling effect.” A chilling effect is where a person may behave differently from how they would naturally, because of the legal and social implications of their actions.

From the other side, products with information about you are far more able to manipulate you. Products like digital assistants such as Amazon’s Alexa or Google Now…

> “As the digital butler expands its role in our daily lives, it can alter our worldview. By crafting notes for us, and suggesting “likes” for other posts it wrote for other people, our personal assistant can e ectively manipulate us through this stimulation.—[Maurice E. Stucke and Ariel Ezrachi, The Subtle Ways Your Digital Assistant Might Manipulate You, November 2016](https://www.wired.com/2016/11/subtle-ways-digital-assistant-might-manipulate/)

## Fake News!

[{{< figure class="aligncenter size-large wp-image-4904" src="/images/2017/04/Digital-Assitants-etc.220-1024x576.jpeg" alt="Fake News!" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.220.jpeg)

I’ve got fake news in the title of this talk, but what does all of this have to do with fake news?

First of all we have to look at what constitutes fake news. Fake news is content presented as a news story but with no grounding in reality, let alone journalistic rigour. Fake news roughly fits into three categories:


1.Real issues exaggerated to distract you, such as issues that are exaggerated to distract the public.
2. Propaganda, weaponised speech delivered to achieve a political aim –; a mixture of truth, exaggeration and deception.
3. [“Disinformatzya,”](http://www.dw.com/en/fake-news-is-a-red-herring/a-37269377) false content deliberately created to muddy the waters of informed public opinion, to make you distrust everything in the news

### Adtech!

[{{< figure class="aligncenter size-large wp-image-4905" src="/images/2017/04/Digital-Assitants-etc.226-1024x576.jpeg" alt="Adtech!" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.226.jpeg)

We have to ask why have all of these forms of not-news dressed up as news become popular? The answer is adtech:

> “This form of digital advertising [adtech] has turned into a massive industry, driven by an assumption that the best advertising is also the most targeted, the most real-time, the most data-driven, the most personal”—[Doc Searls, Brands need to fire adtech, March 2017](https://artplusmarketing.com/brands-need-to-fire-adtech-f9d18edd2f9a)

The problem is that adtech powers the ads that show alongside everything. Adtech is behind the pay-per-click ads that show you things that are relevant to the article or to you.

[{{< figure class="aligncenter size-large wp-image-4888" src="/images/2017/04/228-1024x576.jpg" alt="Facebook ad alongside Facebook feed" width="1024" height="576" >}}](/images/2017/04/228.jpg)

Adtech is the ads that follow you around the web.

[{{< figure class="aligncenter size-large wp-image-4889" src="/images/2017/04/229-1024x576.jpg" alt="Amazon ads for things you’ve browsed following you around the web" width="1024" height="576" >}}](/images/2017/04/229.jpg)

Adtech is the clickbait of intriguing stories that are sometimes dressed up as “Other articles you might like”, “Promoted links,” or “Sponsored content.”

[{{< figure class="aligncenter size-large wp-image-4890" src="/images/2017/04/230-1024x576.jpg" alt="Outbrain “promoted links from around the web” on The Guardian" width="1024" height="576" >}}](/images/2017/04/230.jpg)

> 1. “1. It’s adtech that spies on people and violates their privacy.
> 2. It’s adtech that’s full of fraud and a vector for malware.
> 3. It’s adtech that incentivizes publications to prioritize “content generation” over journalism.
> 4. It’s adtech that gives fake news a business model, because the fake is easier to produce than the real, and it pays just as well.

> —[Doc Searls, Brands need to fire adtech, March 2017](https://artplusmarketing.com/brands-need-to-fire-adtech-f9d18edd2f9a)

[Wired talked to a Macedonian teenager about his lucrative business posting disinformatyza](https://www.wired.com/2017/02/veles-macedonia-fake-news/):

> “He posted the link on Facebook, seeding it within various groups devoted to American politics; to his astonish­ment, it was shared around 800 times. That month—February 2016—Boris made more than $150 off the Google ads on his website. Considering this to be the best possible use of his time, he stopped going to high school.”

And on top of that, as Evgeny Morozov said in the Guardian:

> “The problem is not fake news but the speed and ease of its dissemination, and it exists primarily because today’s digital capitalism makes it extremely profitable – look at Google and Facebook – to produce and circulate false but click-worthy narratives.”—[Evgeny Morozov, Moral panic over fake news hides the real enemy – the digital giants, January 2017](https://www.theguardian.com/commentisfree/2017/jan/08/blaming-fake-news-not-the-answer-democracy-crisis)

But how do we solve this problem that is now at the core of journalism?

> “Solving the problem of sensationalistic, click-driven journalism likely requires a new business model for news that focuses on its civic importance above profitability.”—[Ethan Zuckerman, Fake news is a red herring, January 2017](http://www.dw.com/en/fake-news-is-a-red-herring/a-37269377)

Not-news is causing problems for the advertisers too, with [some advertisers stopping using adtech platforms after their products appeared alongside undesirable and extreme content](https://www.theguardian.com/technology/2017/mar/19/google-braces-for-questions-as-more-big-name-firms-pull-adverts). But I’m not so sure this will make much of a difference to the pockets of the adtech makers. I wonder is this adtech business model too lucrative to change?

## What can we do to block clickbait and fake news from our lives?

We need to think about what can we do *now* to block the clickbait and fake news from our lives? Assuming our friends aren’t forcing us on to it via social media…

### Ad Blockers?

Could ad blockers be the answer? Many people have started blocking trackers using ad blockers. The key issue with this is that **ads are not the problem. Trackers are the problem.** The third-party tracking scripts are the problem.

At [Ind.ie](https://ind.ie), we’ve been doing [research into trackers](https://better.fyi), and we found some of the most used third-party scripts on the web:

* google-analytics.com—64.1% of sites researched
* doubleclick.net—54.4% of sites researched
* google.com—41.9% of sites researched
* gstatic.com—32.8% of sites researched
* googleadservices.com—32.3% of sites researched
* facebook.com—29.0% of sites researched
* googlesyndication.com—26.9% of sites researched
* facebook.net—26.4% of sites researched
* google.se—23.0% of sites researched

So far, we’ve found around 78.5% of trackers from the top 10,000 sites come from Google. All of these sites set third-party cookies and/or tracking pixels.

Cookies themselves aren’t inherently problematic. First-party cookies can be useful in storing your username at logins or remembering your preferred language on a site. But we don’t want or need the bad third-party cookies that are just sitting there following us around and spying on everything we do.

### Surveillance Capitalism

This is what Shoshana Zuboff coined as “Surveillance capitalism.” Also know as “corporate surveillance” or more simply, “people farming.”

[{{< figure class="aligncenter size-large wp-image-4891" src="/images/2017/04/260-1024x576.jpg" alt="Horrible clickbait on LifeBuzz such as “Mirror cakes are the new food porn and they WILL excite you”" width="1024" height="576" >}}](/images/2017/04/260.jpg)

Some people recognising this problem have started using ad blockers to block ads and third party scripts. As consumers of the web, we often use ad blockers, but as web builders, they can inconvenience us if they block what we’ve created.

When it comes to ad blockers, it bears repeating: ads are not the problem. Trackers are the problem. There are some horrifying ads and clickbait out there, but many of these blockers are not doing exactly what you think they are. For example, [Adblock Plus](https://adblockplus.org/en/acceptable-ads" rel="nofollow) has a whitelist called Acceptable Ads which are ads and trackers that they just let through:

> “we share a vision with the majority of our users that not all ads are equally annoying”—[Acceptable Ads criteria](https://adblockplus.org/en/acceptable-ads#criteria" rel="nofollow)

Acceptable ads are largely included under the criteria that they’re not too dominant or annoying. But as I said before, annoying ads are not the problem. Trackers are the problem. And there’s nothing in the Acceptable Ads criteria about ads tracking you.

> “we are being paid by some larger properties that serve non-intrusive advertisements that want to participate in the Acceptable Ads initiative”—[Acceptable Ads Agreements](https://adblockplus.org/acceptable-ads-agreements" rel="nofollow)

What’s worse is that larger companies are paying for their ads to be shown. Including Google’s ads (and trackers). And we know how wide Google’s trackers reach… Worse still, [now AdBlock Plus is even selling ads to replace the ones it blocks](http://boingboing.net/2016/09/13/adblock-now-selling-ads.html).

The anti-annoying-ad argument is distracting us from the real problems. Ad networks aren’t inherently bad. For example, [The Deck](http://decknetwork.net) (now sadly closed) was an ad network which targeted its audience by only being used on specialist sites. And [they were fine with knowing nothing](http://decknetwork.net/privacy/) about the individuals who viewed those ads:

> “We don’t track our readers in any way or allow any other behind-the-scenes shenanigans. We just serve useful, relevant ads in a simple, unobtrusive way to support independent publishers.”—[The Deck Privacy Policy](http://decknetwork.net/privacy/)

### Can we still have behavioural ads?

[{{< figure class="aligncenter size-large wp-image-4906" src="/images/2017/04/Digital-Assitants-etc.281-1024x576.jpeg" alt="Advertising does not need to phone home to the cloud" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.281.jpeg)

The benefit of The Deck was that it showed static ads to a niche audience, but what about behavioural ads? We could still show relevant ads based on behaviour. Advertising does not need to phone home to the cloud. You could still have behavioural advertising that keeps your information private by doing all the behavioural analysis and decision-making on the device itself. So it could work in theory, but who is going to use these systems when your personal information is so lucrative?

[{{< figure class="aligncenter size-large wp-image-4892" src="/images/2017/04/275-1024x576.jpg" alt="The Deck’s privacy policy which said “We’re fine with knowing nothing”" width="1024" height="576" >}}](/images/2017/04/275.jpg)

### Analytics

There’s one third-party script that almost all of us put on our sites… analytics. Considering everything we’ve looked at so far, how can we use analytics more ethically?

Remember that stat from before, that 64.1% of the top 10,000 sites are using Google Analytics? How many of those sites do you visit? What has that told Google about you? How does that make you feel about using analytics on your own sites? Is it ethical or necessary to track visitors to our site? This isn’t a problem with a yes or no answer, but we need to consider these questions.

## Ethics in technology

All of these issues I’ve discussed fall under the bracket of ethics. Ethics are defined as “a set of moral principles, especially ones relating to or affirming a specified group, field, or form of conduct.” So how do they relate to our everyday work in the web and technology industries?

### We build the new everyday things

[{{< figure class="aligncenter size-large wp-image-4907" src="/images/2017/04/Digital-Assitants-etc.290-1024x576.jpeg" alt="We build the new everyday things" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.290.jpeg)

Us people building the web are building the new everyday things. We’re building the new infrastructure that powers our society. Much like other systems we use every day that we might pay taxes for: roads, clean water, waste removal, police, fire and rescue services.

How much time do you spend using a road every day? On the average day, I’ll cycle to the office, walk to the supermarket, that’s around 90 minutes using roads and paths. When [the average person spends 2 hours 51 minutes of time per day on the internet](https://www.iabuk.net/about/press/archive/definitive-time-people-spend-online-2hrs-51-mins-a-day), it becomes clear how much impact our work can have. And that’s why we need to take responsibility.

[{{< figure class="aligncenter size-large wp-image-4908" src="/images/2017/04/Digital-Assitants-etc.295-1024x576.jpeg" alt="We need to take responsibility" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.295.jpeg)

We need to take care of people using the new infrastructure we’re building. Having responsibility isn’t usually fun, but it is necessary. And this is why we need ethics, a kind of code of conduct for the people in our position of power of building the web. Mike Monteiro points out how hypocritical we can be…

> “[W]hen other industries behave unethically we get upset. Yet, many of us seem to have no problem behaving unethically ourselves. We design databases for collecting information, without giving a second thought what that information will be used for.

> As a community have we fallen to the level of debating the importance of ethics that’s usually reserved for politicians, bankers, hedge fund managers, pimps, and bookies?—[Mike Monteiro, Ethics can’t be a side hustle, March 2017](https://deardesignstudent.com/ethics-cant-be-a-side-hustle-b9e78c090aee)

## Use your powers for good

We need designers and developers to use their powers for good.

[{{< figure class="aligncenter size-large wp-image-4909" src="/images/2017/04/Digital-Assitants-etc.298-1024x576.jpeg" alt="Use your powers for good" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.298.jpeg)

This come with the understanding that code is not neutral, that whatever we build comes with our biases. We all have biases. And that code is political. I’m not saying that your code is politically aligned to a particular party, you do not need to have the same political affiliations as me to believe that your world outlook has an impact on the things you create.

[{{< figure class="aligncenter size-large wp-image-4911" src="/images/2017/04/Digital-Assitants-etc.302-1024x576.jpeg" alt="Your world outlook has an impact on the things you create" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.302.jpeg)

What happens when [someone only tests their algorithms on the other white people around them](http://www.theverge.com/2015/7/1/8880363/google-apologizes-photos-app-tags-two-%20black-people-gorillas)? Or [when a programmer makes a security system that assumes there are no women doctors](http://www.cambridge-news.co.uk/cambridge-paediatrician-8217-s-outrage-pure-gym/%20story-26188693-detail/story.html)?

We’re not just building cool stuff for fun, we’re building things that affect other peoples’ lives.

## The Ethical Design Manifesto

At Ind.ie, we decided we need an [Ethical Design Manifesto](https://ind.ie/ethical-design) for the things we use every day:

[{{< figure class="aligncenter size-large wp-image-4913" src="/images/2017/04/Digital-Assitants-etc.371-1024x576.jpeg" alt="The 3 Rs of Ethical Design" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.371.jpeg)
We need to build products that are decentralised, private, open, interoperable, accessible, secure and sustainable. Because that means a product will respect human rights.

### Decentralised

Decentralisation is something we talk about as developers as being a good thing because we don’t like to rely on centralised systems. It’s why we don’t hotlink all our images and scripts from other sites, and why nobody gets any work done when Github is down. We understand that if it’s not on our computers or servers, it’s not under our control. But for some reason we’re happy to give *corporations* control over all of our data.

[{{< figure class="aligncenter size-large wp-image-4894" src="/images/2017/04/317-1024x576.jpg" alt="GitHub’s timeout status page" width="1024" height="576" >}}](/images/2017/04/317.jpg)

With control over data comes power. After the Snowden revelations, people were rightly outraged by how much access our governments had to our browsing information, but not so many people were angry with the corporations who were collecting that information, and handing it right over to the governments. As Bruce Schneier said:

> ‘The NSA woke up and said “Corporations are spying on the Internet, let’s get ourselves a copy”’—[Bruce Schneier](https://www.schneier.com/news/archives/2014/04/surveillance_is_the.html)

### Private

We need to build products that are private. Privacy can come as a result of decentralisation: if your data is only on your device, it’s private to you.

### Open

We need to build open products. “Free and open” or “open source” mean that anyone with sufficient technical knowledge can take the code from some software and make their own version. For free. When a product is free and open, it means you can trust it to some degree, because if one version goes in a direction you don’t like, you can use a different version. Though it’s worth noting that developers are much more of a position to do this than most people who use computers.

### Interoperable

We need to build products that are interoperable. Back in the day, we had phones where you enter all your contacts in manually. It took ages, and then when you got a new phone, you’d have to enter your contacts in all over again. It was a frustrating experience. But using a SIM card to transfer the contacts across made it much easier because SIM cards are interoperable.

Another example of where we don’t have interoperability is in “walled gardens.” It is very common for corporations to want to lock you into their own beautiful ecosystem. That’s what can make it a nightmare switching between Apple and Android.

### Accessible

<p>We need to build products that are accessible. Accessibility is making something available to as many people as possible. To make our products more accessible we need to consider diversity, cost, and

catering to a variety of needs that aren’t necessarily the same as our own. We must never stop looking for ways to make our work more accessible.</p>
### Secure

We need to build products that are secure. In the age of https on everything, we’re more clued up about security. However, security is also confused and conflated with privacy. For example, Google encrypted email and said “yay! all your stuff is now safe and private from hackers!” But that email is not encrypted and private *from Google*, it just protects your information in transit between you and Google.

### Sustainable

We need to build products that are economically, environmentally and culturally sustainable. When a product is sustainable, you know it’s worth putting your time into using it. The product isn’t going to disappear tomorrow with all your information and hard work down the drain.

One of the key elements of sustainability is that a product has a viable long-term business model. (That doesn’t rely on selling your data!) If a startup has been given a huge amount of venture capital without having a business model, chances are they’re not sustainable, and it’s highly likely they’re going to rely on selling your data for profit.

### Functional, convenient and reliable

When we’ve ensured our product respects human rights, we can work on making it functional, convenient and reliable. Doing so respects human effort, and these are generally the goals most of us are reaching for when we’re building things.

When a product is functional, convenient and reliable, it actually does the thing, it does the thing in a way that doesn’t get in your way, and it does that thing reliably again and again.

### Delightful

Once our product respects human rights and human effort, we can layer the delight on top, to make our product delightful, respecting human experience.

Delightful isn’t just making products fun and fluffy. It’s about creating a genuinely great experience, which is reinforced because it’s built upon the strong foundation of respecting your effort and rights. Basecamp is a good example of this, where they have little touches of delight.

[{{<figure class="wp-caption aligncenter size-large wp-image-4912" src="/images/2017/04/Digital-Assitants-etc.368-1024x576.jpeg" alt="Screenshot of Basecamp schedule with a cute pen drawing of a Basecamp icon toasting marshmallows over a campfire" width="1024" height="576" caption="The Basecamp schedule when you haven’t had any past events yet">}}](/images/2017/04/Digital-Assitants-etc.368.jpeg)
Basecamp can only get away with whimsical details because they already respect your human rights and effort. As [Sara Wachter-Boettcher wrote in a fabulous article](https://medium.com/@sara_ann_marie/dear-tech-you-suck-at-delight-86382d101575) last year:

> “Quit painting a thin layer of cuteness over fundamentally broken interfaces.”—[Dear Tech, You Suck at Delight, Sara Wachter-Boettcher](https://medium.com/@sara_ann_marie/dear-tech-you-suck-at-delight-86382d101575)

Layering cuteness on top it is not a solution to a badly-built product, it’s just a way to make ourselves feel better about the problem.

At Ind.ie, we call Respecting human rights, Respecting human effort, and Respecting human experience the 3 Rs of Ethical Design.

[{{< figure class="aligncenter size-large wp-image-4913" src="/images/2017/04/Digital-Assitants-etc.371-1024x576.jpeg" alt="The 3 Rs of Ethical Design" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.371.jpeg)

Many modern products don’t respect our human rights. Instead they’re built on the backs of the humans that use them. These (often-Silicon Valley) products may respect human experience and human effort, but they take advantage of their users. They don’t give them privacy or security, interoperability or open technologies. Very rarely are their products accessible or sustainable.

But as an industry, we hail these products. We call them the “disruptors.” In the dictionary, “to disrupt” means “to interrupt (an event, activity, or process) by causing a disturbance or problem.” People making these products call themselves disruptors because they “disrupt” a market. They take down existing sustainable businesses and kill them off. They monopolise and they dump. We need to disrupt the disruptors. We need to disrupt their disruption.

[{{< figure class="aligncenter size-large wp-image-4895" src="/images/2017/04/375-1024x576.jpg" alt="Silicon Valley landscape" width="1024" height="576" >}}](/images/2017/04/375.jpg)

## We need to ask ourselves these questions

We need to ask ourselves these questions about what we build. Because we are the gatekeepers of what we create. We don’t have to add tracking to everything, it’s already gotten out of our control.

[{{< figure class="aligncenter size-large wp-image-4914" src="/images/2017/04/Digital-Assitants-etc.379-1024x576.jpeg" alt="We are the gatekeepers of what we create" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.379.jpeg)

The business model of the organisations we work for is our business. If what we are building is harming people, we can’t blame someone else for that. We can’t defer responsibility for the products we build, that’s how bad things happen.

[{{< figure class="aligncenter size-large wp-image-4915" src="/images/2017/04/Digital-Assitants-etc.381-1024x576.jpeg" alt="We can’t defer responsibility" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.381.jpeg)

Some people say to me “but if I don’t like what Google/Facebook/Other Corporations are doing, *surely* *I* don’t have to use their services…?”

Nope. As I said before, social networks are part of society now. Email, booking services, ecommerce are our new everyday things. If I stopped using every site that is sharing my data with Google, I’d be using less than 25% of the web. And I couldn’t use email. We deserve to be able to take part in society, and use everyday things without our privacy being compromised.

[{{< figure class="aligncenter size-large wp-image-4916" src="/images/2017/04/Digital-Assitants-etc.386-1024x576.jpeg" alt="We deserve to be able to take part in society, and use everyday things, without our privacy being compromised" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.386.jpeg)

Another thing I often hear is “what if *I* trust Google/Facebook/Other Corporation with my data?” Seriously people, Google isn’t your lover, you shouldn’t *have* to trust them. Why are we so loyal to faceless corporations?

[{{< figure class="aligncenter size-large wp-image-4917" src="/images/2017/04/Digital-Assitants-etc.390-1024x576.jpeg" alt="We need to design and build systems that don’t need to be trusted" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.390.jpeg)

We need to design and build systems that don’t need to be trusted. If it fits with the Ethical Design Manifesto, you don’t need to trust it, you own your own data, and you can easily go elsewhere if you’re no longer satisfied.

[{{< figure class="aligncenter size-large wp-image-4918" src="/images/2017/04/Digital-Assitants-etc.393-1024x576.jpeg" alt="Not worrying about your data is privilege" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.393.jpeg)

It’s important to realise that not worrying about your data is privilege. If you don’t worry about corporations (and by extension, governments) having access to your data, you are privileged. And quite possibly just foolish. What if you lived in a country where your sexual preference is illegal? What if you lived in a country that wants to deport people with your ethnic background? What if you lived in a country where your religious beliefs can get you killed? What if you needed a loan and your friends were considered too poor? What if you needed medical treatment but your medical insurance considered your habits made you too high risk?

Look at the world around us, any of these things could happen tomorrow. If you want to think about it in terms of how trackers affect you, you need to fear for your future self.

[{{< figure class="aligncenter size-large wp-image-4919" src="/images/2017/04/Digital-Assitants-etc.396-1024x576.jpeg" alt="You’re not just making these decisions for yourself" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.396.jpeg)

You also need to bear in mind that you’re not making these decisions for yourself. If you use Gmail, you are swapping free email for the data of everyone you exchange emails with. If you support your business with tracking, you are making that decision for your visitors. It’s invisible, and it’s opt-in by default. Is that fair?

[{{< figure class="aligncenter size-large wp-image-4920" src="/images/2017/04/Digital-Assitants-etc.397-1024x576.jpeg" alt="If you support your business with tracking, you are making that decision for your visitors" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.397.jpeg)

As creators we need to make wise decisions on behalf of our visitors. We can be the gatekeepers of harmful decisions. If making these decisions becomes a battle you have to fight with the top of your organisation, there might just be something wrong with the business model. An organisation that makes its money by tracking people, whether they’re doing it themselves, or getting something in exchange for adding scripts to their site, is not going to want to change. They may even find it impossible to change.

As people become more aware of these issues, we need to be careful that if an organisation does appear to change, it’s not just superficial, that they’re not misdirecting us, or telling us something is better when it’s just bad in a different way. Like [when WhatsApp switched on end-to-end encryption for hundreds of millions of users](https://www.wired.com/2014/11/whatsapp-encrypted-messaging/). So many people said “Yay! They’re the good guys!” But as [Rick Falkvinge said on his blog…](https://www.privateinternetaccess.com/blog/2014/11/whatsapp-encryption-shows-value-of-metadata/)

> “Would Facebook really allow WhatsApp to throw away the business value in a 19-billion acquisition? Of course it wouldn’t. This demonstrates that the snoop value was in the metadata all along: the knowledge of who talks to whom, when, how, and how often. Not in the actual words communicated.”—[Rick Falkvinge](https://www.privateinternetaccess.com/blog/2014/11/whatsapp-encryption-shows-value-of-metadata/)

And surprise! [WhatsApp is now sharing user data with Facebook](http://www.theverge.com/2016/8/25/12638698/whatsapp-to-start-sharing-user-data-with-facebook).

And remember [when Google’s Allo was heralded for its privacy features?](http://www.theverge.com/2016/5/18/11701030/google-io-2016-keynote-highlights-announcements-recap) Turns out, [that was just a bit of announcement <abbr title="public relations">PR</abbr>](http://www.theverge.com/2016/9/21/12994362/allo-privacy-message-logs-google).

You can learn about the value of metadata by watching the fantastic documentary, [A Good American](http://agoodamerican.org). In this film, Bill Binney, working on surveillance for the US, says that meta information is the most valuable information that the <abbr title="National Security Agency of the US">NSA</abbr> can collect. Without meta data, surveilling people is like looking for a needle in a haystack. (I also recommend the recent Oliver Stone [Snowden](https://snowdenfilm.com) film for learning about how corporate surveillance and government surveillance come together.)

[{{< figure class="aligncenter wp-image-4921 size-large" src="/images/2017/04/Digital-Assitants-etc.418-1024x576.jpeg" alt="Screenshot of the Better.fyi spotlight" width="1024" height="576" >}}](https://better.fyi/spotlight/)

As we become more aware of the problems, the people behind the trackers are getting defensive. Massive German publisher [Axel Springer says their “core business is delivering ads to its visitors. Journalistic content is just a vehicle to get readers to view the ads”](https://better.fyi/spotlight). According to Lindsay Rowntree, who writes for a marketing and advertising blog…

> “The web, as it is today, exists because of an implicit understanding that ads pay for the content consumers love and, therefore, need to be seen.”

> —[Lindsay Rowntree, Why Three’s Partnership with Shine…, May 2016](https://www.exchangewire.com/blog/2016/05/18/why-threes-partnership-with-%20shine-makes-publishers-more-vulnerable-than-ever/)

Again. No. This is just not true. Ads are the most common business model, but not the only one. Do you want to get all your news from people who just want your eyeballs? And remember, ads are still not the problem. Trackers are the problem.

[{{< figure class="aligncenter size-large wp-image-4922" src="/images/2017/04/Digital-Assitants-etc.424-1024x576.jpeg" alt="Corporations need to stop treating us like we’re greedy lab rats" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.424.jpeg)

Corporations need to stop treating us like we’re greedy lab rats, making outrageous demands just by asking “please don’t experiment on us.”

We must question and challenge these unethical practices. And we need to learn to see past the <abbr title="Public Relations">PR</abbr>. We certainly shouldn’t engage in this PR ourselves. We need to make real things that have meaning, rather than the illusion of having meaning. Don’t be the person shaving a few kilobytes off an image file when someone else is adding 5MB of trackers.

[{{< figure class="aligncenter size-large wp-image-4923" src="/images/2017/04/Digital-Assitants-etc.428-1024x576.jpeg" alt="Save our jobs" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.428.jpeg)

We should also be selfish. Building ethical alternatives to centralised technologies will save our jobs. [The average Facebook user spends 50 minutes on Facebook a day](http://www.nytimes.com/2016/05/06/business/facebook-bends-the-rules-of-audience-engagement-to-its-advantage.html). Facebook’s functionality has replaced status updates, photo sharing, company sites, news, and chat, to name just a few.

[{{< figure class="aligncenter size-large wp-image-4896" src="/images/2017/04/435-1024x576.jpg" alt="Status updates, Instagram, Facebook Messenger, Facebook Pages" width="1024" height="576" >}}](/images/2017/04/435.jpg)

When it comes to our business use, what Facebook hasn’t got covered, Google has a product for you. If we want jobs that aren’t at Facebook or Google, we’re going to need to make sure the rest of the web actually exists.

[{{< figure class="aligncenter size-large wp-image-4897" src="/images/2017/04/436-1024x576.jpg" alt="All the Google products" width="1024" height="576" >}}](/images/2017/04/436.jpg)

## Build and support alternatives

We need to build alternatives, giving ourselves the choice to choose a different way, as both the consumers and the builders of the web. And when we find alternatives, we must support them.

[{{< figure class="aligncenter size-large wp-image-4924" src="/images/2017/04/Digital-Assitants-etc.438-1024x576.jpeg" alt="Build and support alternatives" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.438.jpeg)

When you’re looking for replacements for Facebook and Google products, don’t just look for another behemoth. You can’t replace Google in its entirety, but you can use individual products/services to replace different parts of its functionality. Perhaps DuckDuckGo for search, OpenStreetMap for maps, WordPress for blogging, Fastmail for email. The benefit of using individual products is that no one organisation has all your information.

[{{< figure class="aligncenter size-large wp-image-4925" src="/images/2017/04/Digital-Assitants-etc.441-1024x576.jpeg" alt="Look for traditional business models" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.441.jpeg)

It’s also worth looking for organisations that have traditional business models. Business models where you pay for a product or service in small one-off or recurring fees. With larger organisations, that’s no guarantee that they won’t track you, but small-to-medium businesses are less likely to take your money and track you too.

[{{< figure class="aligncenter size-large wp-image-4926" src="/images/2017/04/Digital-Assitants-etc.442-1024x576.jpeg" alt="Call out bad behaviour" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.442.jpeg)

It’s also vitally important that we call out bad behaviour and make tracking socially unacceptable. Call out businesses you see tracking you, *especially* if you also pay them.

### Work for more ethical companies

We can’t all just quit our jobs to go work somewhere more ethical, but maybe next time you’re looking for work, do your research on their business models. Help make a difference by putting your valuable knowledge and skills into building the alternatives, and help us build these bridges from the mainstream technology to the future we want to see.

[{{< figure class="aligncenter size-large wp-image-4927" src="/images/2017/04/Digital-Assitants-etc.445-1024x576.jpeg" alt="Build the world you want to live in" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.445.jpeg)

Build the world you want to live in.

[{{< figure class="aligncenter size-large wp-image-4928" src="/images/2017/04/Digital-Assitants-etc.446-1024x576.jpeg" alt="Thanks for reading!" width="1024" height="576" >}}](/images/2017/04/Digital-Assitants-etc.446.jpeg)

## 3 comments

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-160272">
			<div class="comment-author vcard">
			<img alt='' src='http://1.gravatar.com/avatar/a1212e71e1f99cd5b98bb673dca73580?s=72&amp;d=mm&amp;r=g' srcset='http://1.gravatar.com/avatar/a1212e71e1f99cd5b98bb673dca73580?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://eyedeastudio.london' rel='external nofollow' class='url'>Prisca</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-160272"><time datetime="2017-04-13T09:45:22+00:00" pubdate class="published">
		 at <span class="hours">09:45am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Laura, thanks for posting this — must have been an excellent talk, going by this brilliant write-up. Thank you :)
	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-160273">
			<div class="comment-author vcard">
			<img alt='' src='http://2.gravatar.com/avatar/8e942d1ef483b3486d3d8498e1d93454?s=72&amp;d=mm&amp;r=g' srcset='http://2.gravatar.com/avatar/8e942d1ef483b3486d3d8498e1d93454?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.darnelldigitalink.com' rel='external nofollow' class='url'>Wayne Darnell</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-160273"><time datetime="2017-04-22T20:52:07+00:00" pubdate class="published">
		 at <span class="hours">20:52pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Excellent&#8230;. You hit on some fantastic points that more people need to be aware of.  It’s definitely an uphill battle making changes and developing or finding products that can adhere to an ethical business model (I’m changing gears in my company to spend a lot more time working on solutions) but it must be done.  To continue along the path that the large corporations have laid out for us “users” will eventually end with no privacy, control, or ownership of our information and ultimately our identities&#8230;  The writing is on the wall for anyone who takes the time to look, it’s up to us to erase that writing.
	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-160274">
			<div class="comment-author vcard">
			<img alt='' src='http://0.gravatar.com/avatar/37f8e32692c57724169c062d09547d2f?s=72&amp;d=mm&amp;r=g' srcset='http://0.gravatar.com/avatar/37f8e32692c57724169c062d09547d2f?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='https://lifesimply.rocks' rel='external nofollow' class='url'>Alina &amp; Deian</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-160274"><time datetime="2017-04-23T12:21:58+00:00" pubdate class="published">
		 at <span class="hours">12:21pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Dear Laura,

wonderful article with a lot of information. We’ve been following you closely and even use Better on our Macs. When we started developing our Travel/Digital Nomad blog last year, we thought hard about how to make it sustainable without handing data over to big corporations. Google Analytics was never an option so we did some research and found stetic, a German alternative, that is not free. Still, we bought a one year license, eating up the costs and protecting our visitors while still getting useful data to improve our website.

What that shows is, that you have to invest — nothing is for free these days. Sadly, most people prefer a free service over a paid one.
	</div>
</li>
</ol>