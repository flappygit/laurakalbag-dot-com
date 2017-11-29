---
title: "SMACSS –; Scalable and Modular Architecture for CSS"
draft: true
colours: ["#4595a1", "#45587B", "#3c88af", "#496d7e", "#94C7E1", "#374850", "#60A7C9"]
date: 2012-10-31T08:45:52+00:00
categories: ["Reviews"]
tags: ["CSS", "HTML", "preprocessors", "Sass", "semantics", "structure"]
body_classes: "blog"
---

I bought [Jonathan Snook’s Scalable and Modular Architecture for CSS](http://smacss.com/) five months ago and, embarrassingly, I’ve only just read it. As a “flexible guide to developing sites small and large”, it’s fantastic.

{{< figure class="aligncenter  wp-image-1252" title="SMACSS book cover" src="/images/2012/10/IMG_5259.jpg" alt="SMACSS book cover" width="925" height="890" >}}</p>
Last month I was lucky enough to see Jonathan speak about [State-Based Design](http://2012.fromthefront.it/) (a concept which he covers in SMACSS) at the[ FromTheFront conference](http://2012.fromthefront.it/) and it reminded me to put the book at the top of my to-read pile. It’s not a long book, it’s about the same easy-to-digest length as [the A Book Apart series](http://www.abookapart.com/), which meant I got through it (whilst taking notes) in a couple of hours. I also love that there’s a [mailing list](http://smacss.com/) that keeps you updated with the latest methods and other relevant news.

## I’m an HTML and CSS girl

As a front-end developer, I’ve long been obsessed about writing really good clean and semantic HTML and CSS. Frameworks and boilerplates tend to make me cringe. Accessibility and [progressive enhancement](http://www.alistapart.com/articles/understandingprogressiveenhancement/) are what I value the most. It was lovely to read a book about CSS that was from a practical point of view but still held those ideals. The SMACSS core goals are:

1. Increase the semantic value of a section of HTML and content
2. Decrease the expectation of a specific HTML structure

Jonathan walks you through the way that he lays out his stylesheets, informs you the reasons behind his decisions and backs these up with solid examples. There’s no “you must do this” or “you’re not standards-based if you don’t do that.” Jonathan reiterates throughout that his way isn’t the only way, but it works for him.

**This is the exact opposite of what frameworks do**. [Frameworks](http://en.wikipedia.org/wiki/CSS_frameworks) tend to do the thinking for you, and encourage lazy blanket usage (perhaps not intentionally, but that’s what they tend to result in.) Jonathan teaches you the background that you need in order to make your own informed decisions.

Throughout the book, Jonathan also refers to how this structuring of CSS affects older browsers, and how it works with [newer development techniques such as those using media queries](http://www.alistapart.com/articles/responsive-web-design/).

## Really thinking about your CSS

One thing that really stood out for me in SMACSS is the importance of process when structuring your CSS:

> With a module-based system, it is important to consider state-based design as applied to each of the modules. When you actively ask yourself “what us the default state,” then you’ll find yourself thinking proactively about progressive enhancement. It also can have you approaching issues slightly differently.

This systems-based way of thinking really appeals to me as I’ve been thinking a lot about design systems as part of [responsive design](http://www.alistapart.com/articles/responsive-web-design/). It’s great to read about the usefulness of patterns in both development and design, making our planning a lot smarter and considering future use to create *maintainable* stylesheets.

## Starting from the beginning

The structure of the book works really well and should help someone fairly new to CSS as well as more advanced masters of markup. It starts with the basics of structuring (ordering) your CSS, then moves on to more advanced details with selectors and performance. After the main SMACSS principles are covered, Jonathan goes on to explain the role of [pre-processors](http://www.vanseodesign.com/css/css-preprocessors/) and how they could work with the SMACSS principles. His explanation of [Sass](http://sass-lang.com/) actually helped me understand how to use it more efficiently (and I already use Sass on all my projects) and would do well as a primer for someone who is completely new to pre-processors.

## Finding the balance

Whilst reading SMACSS I’ve managed to pinpoint the biggest problem in my CSS; I have a tendency to use overly qualified selectors (such as `body.home div#content h3.entry-title`.) I’m not sure why I do it, though I suspect it’s because it looks more visually balanced than `.entry-title`. And also I’m an idiot.

Jonathan points out that structuring your selectors in this way is tying your CSS behaviour to your HTML structure (and hierarchy.) Of course, as someone obsessed with semantics and hell-bent on avoiding ‘classitis,’ I’ve tended to rely heavily on the structure of my HTML (and the unique nature of HTML5 elements) to hook my CSS but it does not make for modular or scalable CSS.

I’ve learnt a great deal from SMACSS and I believe that writing good CSS is about finding that balance between writing clean, reusable HTML (written independently of CSS) and clean, reusable CSS (making use of HTML element classnames.) I feel like this book has made me understand a lot more about CSS and I really recommend it if you’re striving to be more efficient. I don’t often collaborate on markup, but I can imagine that SMACSS could help make team projects considerably easier.

## 9 comments

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-341">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/3fe9db0e9123cc01797b65a8564f9e27?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/3fe9db0e9123cc01797b65a8564f9e27?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Abbaty Kori</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-341"><time datetime="2012-10-31T09:40:26+00:00" pubdate class="published">
		 at <span class="hours">09:40am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Great! :D Sounds like what I’ve been looking for&#8230;

I’m definitely getting a copy soon :)</p>	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-342">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/579562979b2f9229f1c8c5d300c72676?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/579562979b2f9229f1c8c5d300c72676?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://dannybaggs.com' rel='external nofollow' class='url'>Danny Baggs</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-342"><time datetime="2012-10-31T09:55:24+00:00" pubdate class="published">
		 at <span class="hours">09:55am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Thanks for the reminder&#8230; just bought for my train ride.

Nice review.</p>	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-343">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/18592fc8bad8f92136390f52303ee29c?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/18592fc8bad8f92136390f52303ee29c?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://mrgwebdev.com' rel='external nofollow' class='url'>Mark Glover</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-343"><time datetime="2012-10-31T09:58:24+00:00" pubdate class="published">
		 at <span class="hours">09:58am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Hey Laura,

Thanks for posting this great review. There are a lot of CSS books out there and I’m not often tempted to buy one, but your writeup has pushed all my CSS buttons, so now I might have to&#8230;

Cheers</p>	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-344">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/8972424a01b25a343b664d5b8ff75a45?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/8972424a01b25a343b664d5b8ff75a45?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://pankajparashar.com/' rel='external nofollow' class='url'>Pankaj Parashar</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-344"><time datetime="2012-10-31T09:58:51+00:00" pubdate class="published">
		 at <span class="hours">09:58am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Wow! Even i tend to use overly qualified selectors most of the time, but never realized that I am actually making my css dependent on the HTML structure.

Thanks for this article!</p>	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-345">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/8f858a4d2a149894dd30c4d1a72833ac?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/8f858a4d2a149894dd30c4d1a72833ac?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://michaelwoodruff.com' rel='external nofollow' class='url'>Michael Woodruff</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-345"><time datetime="2012-10-31T12:56:58+00:00" pubdate class="published">
		 at <span class="hours">12:56pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		“I have a tendency to use overly qualified selectors (such as body.home div#content h3.entry-title.) I’m not sure why I do it, though I suspect it’s because it looks more visually balanced than .entry-title.”

My exact feeling as well.
	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-346">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/174df6d4445633cb5698e2c046ff7961?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/174df6d4445633cb5698e2c046ff7961?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.rachil.li' rel='external nofollow' class='url'>Rachel</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-346"><time datetime="2012-10-31T13:15:57+00:00" pubdate class="published">
		 at <span class="hours">13:15pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Like you, I’ve had SMACSS for quite a while now but have never got around to reading it. Reading this really just tells me that I need to *make* the time and get reading it. I’m sure it’ll help my process with CSS massively. Thanks :)
	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-347">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/6db663240610773f134b9711193a607c?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/6db663240610773f134b9711193a607c?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">hannes</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-347"><time datetime="2012-11-01T09:42:27+00:00" pubdate class="published">
		 at <span class="hours">09:42am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>‘And also I’m an idiot.’ :D

no, you’re not! great shoptalkshop btw. keep it up!</p>	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-348">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/a875214ef52a0868ff836df077af2ebe?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/a875214ef52a0868ff836df077af2ebe?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://tempertemper.net' rel='external nofollow' class='url'>Martin Underhill</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-348"><time datetime="2012-11-01T22:31:08+00:00" pubdate class="published">
		 at <span class="hours">22:31pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Great article! I’ve just gone to Mr. Snook’s site and bought the ebook– now to get stuck in! Thanks :)
	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-349">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/7bc4c5263bd87380a775d22aa165b9f1?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/7bc4c5263bd87380a775d22aa165b9f1?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://cupofvoodoo.com' rel='external nofollow' class='url'>Dan Robert</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-349"><time datetime="2012-11-02T23:16:22+00:00" pubdate class="published">
		 at <span class="hours">23:16pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Great review! I’ve also purchased the book quite a while back and still haven’t read it. This post prompted me to put it next on my list! :)
	</div>
</li>
</ol>
