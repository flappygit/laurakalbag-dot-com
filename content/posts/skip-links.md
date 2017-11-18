---
title: "Do your skip links work with keyboard navigation?"
draft: true
colours: ["#1168c9", "#565656", "#2189f2", "#353535", "#9b9b9b", "#0a0a0a", "#474747"]
date: 2015-01-14T14:59:26+00:00
categories: ["Accessibility"]
tags: ["keyboard navigation", "skip links"]
---

{{< oldpost >}}

Recently I’ve been doing a lot of research in web accessibility, and it’s lead me to testing web pages more thoroughly. I’ve been testing keyboard-only navigation a lot. Keyboard-only input is how most screen reader users interact with the web, as well as many alternative input and mouse-less users.

This afternoon I was testing a new feature I want to add to [Ind.ie’s accessible video player](https://ind.ie/blog/accessible-video-player), and started moving down our [style guide (work in progress!) page](https://ind.ie/style-guide/), tabbing through the links. Our style guide is really long, so I’ve added skip links at the top of the page, allowing you to jump to the relevant section without having to scroll such a long way. Skip links are very common as an accessibility feature to skip past lengthy navigation to get straight to the page content. They’ve also become a common form of navigation used on one-page sites that have a lot of content on one page.

[{{< figure class="aligncenter size-full wp-image-4588" src="/images/2015/01/skip-links.jpg" alt="Contents list of links on the Ind.ie style guide" width="510" height="470" >}}](/images/2015/01/skip-links.jpg)

The code usually looks something like:

```&lt;a href="#main-content"&gt;Skip to content&lt;/a&gt;
    ...
&lt;div id="#main-content"&gt;
    ...
&lt;/div&gt;```

## What’s the problem?

Some browsers don’t support skip links in this way. After some very quick tests, I found both Safari and Chrome don’t change the keyboard focus to the visual focus area when a user follows a skip link. This means you might be looking at the section on branding, but the keyboard focus is still on the navigation at the top of the page. If you tab to the next item, your visual focus will scroll right back to the top of the page. A few web searches later and I find this isn’t a new problem at all.

The difference between visual and actual focus could be an irritation to any sighted users, but for screen readers users, it makes skip links utterly useless. They’re not actually skipping at all.

## How can we fix this?

Having a read through this [Webkit bug report](https://bugs.webkit.org/show_bug.cgi?id=17450), there’s seems to be cross-platform issues and implications. There’s no web standard for skip links, so there’s no guidance for browsers to follow.

But after some searching, I found [a JavaScript snippet](http://www.nczonline.net/blog/2013/01/15/fixing-skip-to-content-links/) that seems to solve the problem. Relying on JavaScript is less than ideal, but I think right now it’s the best we can do.

Without consistent behaviour for focus on skip links, they’re little value to the wider audience on the web.

Other sites posting on this issue:

* [WebAIM keyboard accessibility](http://webaim.org/techniques/keyboard/) (October, 2013)
* [Fixing “Skip to content” links](http://www.nczonline.net/blog/2013/01/15/fixing-skip-to-content-links/) (January, 2013)
* [Skip links and other in page links in WebKit browsers](http://www.456bereastreet.com/archive/201203/skip_links_and_other_in_page_links_in_webkit_browsers/) (March, 2012)
* [Keyboard Navigation in Mac Browsers](http://www.weba11y.com/blog/2014/07/07/keyboard-navigation-in-mac-browsers/) (useful for knowing how to test)

## 4 comments

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-137909">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/47d083708ad8d06202d50d5e567f3eaf?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/47d083708ad8d06202d50d5e567f3eaf?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://github.com/svinkle' rel='external nofollow' class='url'>@svinkle</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-137909"><time datetime="2015-01-14T15:09:03+00:00" pubdate class="published">
		 at <span class="hours">15:09pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>This is how I’ve been approaching this:

```&lt;a href=&quot;#main&quot; class=&quot;visuallyhidden focusable&quot;&gt;Skip to content&lt;/a&gt;```

CSS classes there are from HTML5 Boilerplate CSS.

I then have this for my main element:

`&lt;main id=&quot;main&quot; tabindex=&quot;-1&quot;&gt; ... &lt;/main&gt;`

Using tabindex=”-1" like this allows the main element to programmatically receive focus. When the user hits tab again, it will move focus away from main to the next focusable element.
	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-137910">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/2e7291b36e6344f7c6d2cb1b56aff1c9?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/2e7291b36e6344f7c6d2cb1b56aff1c9?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.pixeldiva.co.uk' rel='external nofollow' class='url'>pixeldiva</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-137910"><time datetime="2015-01-14T15:09:53+00:00" pubdate class="published">
		 at <span class="hours">15:09pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Another minor thing, to make things better (once the above problem is fixed)… having the link text be Skip to Main Content gives a screen reader a bit more context so the pronunciation will be correct as *Con*tent, rather than Con*tent*.
	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-137914">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/5375b1b830a01f1b6a894eea985ce7b8?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/5375b1b830a01f1b6a894eea985ce7b8?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">goetsu</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-137914"><time datetime="2015-01-14T16:11:58+00:00" pubdate class="published">
		 at <span class="hours">16:11pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Yes after 8 years of waiting for this bug to be fixed after I create it now it can work but the target of you links must be focusable (a link, a button, a form element or anything with a tabindex).

So, in your case the most easy thing I presume is to add a tabindex=”-1" to you hx</p>	</div>
</li>
</ol>
