---
title: "Browser windows and responsive language"
draft: true
colours: ["#3643a6", "#28406c", "#4344a8", "#142648", "#523bb5", "#111e40", "#7343a8"]
date: 2013-08-08T18:59:17+00:00
categories: ["Design", "Design Issues", "Development"]
tags: ["browser windows", "clients", "communication", "language", "responsive design", "screen sizes"]
---

{{< oldpost >}}

In the same way that we continually evolve the processes we use when working with clients, I’ve now found myself evolving and refining the language I use with clients when discussing responsive web design.

## “Devices”

It started out with talking about devices. “This design will use X on a mobile phone, Y on a tablet and Z on a desktop computer.” Then it seemed that, as a web community, we realised that the lines between these devices were fairly blurry. There’s no way of telling which device is being used without testing for user agents, and then [it’s likely that the user agent string is lying to us anyway](http://farukat.es/journal/2011/02/499-lest-we-forget-or-how-i-learned-whats-so-bad-about-browser-sniffing).

## “Screen sizes”

Next, many of us started talking about device-agnostic “screen sizes”. Being device-agnostic meant we’d hopefully stop trying to make assumptions about user behaviour based on the particular type of device they were using. Mobile phone users could be “mobile” but it wouldn’t make a difference to use because we were basing our designs on screen sizes and using the knowledge that some people could possibly be “mobile” to improve usability and performance for all our users.

But then we still keep hanging on to those devices.

We know that smart phones tend to start at around 320px, tablets possibly around 760px and then we often count anything upward of 900px as if it’s a desktop computer. If we talk about screen sizes like this, they still correspond to the screens on particular types of devices.

## “Browser windows”

Nowadays I talk about “browser windows”. Yeah, these are often non-resizable fullscreen apps on the screens of various portable devices, but on desktop operating systems, a browser window could be *any* size.

If I check out my own site’s analytics, there are visitors from 24 different browser window widths upward of 800px. And my responsive media queries are responding to those browser window sizes. Not the device, not the size of the screen, but the width of the browser window.

And that’s only counting browser sizes at 800px and above. Who’s to say that a user doesn’t resize their browser window so that it’s narrower than 800px? They might be using two windows side-by-side. This would mean that they’re viewing a narrow version of a site, responding to media queries we may have designed with mobile phones in mind…

## Trying to be clear

Whilst we’re explaining what we’re doing as designers working on responsive sites, speaking in terms of “browser windows” helps clients (bosses, stakeholders, coworkers, whatever…) understand what we’re really doing. It helps them understand what we can and can’t detect, what we do and do not have control over and help us collectively truly embrace a responsive device-agnostic approach. We need to take care with the language we use, and choose accuracy, even if it means we sometimes have to educate others, over the dumbing-down which inevitably results in expectations we can’t, and don’t want to, meet.

## One comment

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-567">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/980339c2fa3195876f7389fa0db3ed3e?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/980339c2fa3195876f7389fa0db3ed3e?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://kruegerdesigns.com' rel='external nofollow' class='url'>Adam Krueger</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-567"><time datetime="2013-08-08T19:23:43+00:00" pubdate class="published">
		 at <span class="hours">19:23pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Hi Laura,

Great post, referring to the browser when talking about RWD makes a lot of sense. I’ve heard “mobile-first” miss used a lot at my office. This post should help clear up some confusion.
		</div>
	</li>
</ol>
