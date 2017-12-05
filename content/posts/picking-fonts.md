---
title: "Picking Fonts"
draft: false
colours: ["#B57C37", "#976b3c", "#D6AF78", "#4E4741", "#BE9464", "#2d2b2a", "#43c1f2"]
date: 2010-07-05T19:23:32+00:00
categories: ["Design"]
tags: ["@font-face", "font-family", "fonts", "header", "mac", "paragraph", "sans-serif", "serif", "typekit", "windows"]
body_classes: "blog"
---

This little post is an extension of my post on Web Fonts.

Of late, some of the snobbier designers are whining that more fonts available will mean the web will get covered in horrible mis-use of fonts, unreadable body text and general ugliness.

I don’t think this is totally fair, but I’m sure some people might get confused by the variety of fonts that are around, so I thought I’d share a few things I try to keep in mind when choosing fonts:

### Use appropriate fonts

Easily said, I know, but some fonts are clearly more suitable for particular designs than others. For example, you wouldn’t use a font that looks like it’s dripping blood on a corporate site, and you’d not use a handwriting-style font on a site about computer programming.

[{{<figure class="wp-caption aligncenter size-full wp-image-92 " title="Firey font isn't really suitable for Daisy's Darling Cake shop" src="/images/2010/07/Screen-shot-2010-07-05-at-18.39.37.png" alt="Firey font isn't really suitable for Daisy's Darling Cake shop" width="610" height="70" caption="Firey font isn’t really suitable for Daisy’s Darling Cake shop">}}](/images/2010/07/Screen-shot-2010-07-05-at-18.39.37.png)

<p>If you’re aiming for clean and modern, go sans-serif. If you’re looking for a slightly more traditional feel, go serif.
 
### Don’t use more than two fonts

With all these cool fonts around, it’s easy to go over-the-top and try out loads at once. Unless you’re going for a Victorian poster style, I’d steer clear of the multi-font look.

[{{< figure class="aligncenter size-medium wp-image-97" title="Old Victorian circus poster, lots and lots of fonts" src="/images/2010/07/Circus_Montreal_9_March_1812-253x320.jpg" alt="Old Victorian circus poster, lots and lots of fonts" width="253" height="320" >}}](/images/2010/07/Circus_Montreal_9_March_1812.jpg)

It’s difficult to find two fonts that match each other well. You want to look for as similar shapes as possible, round fonts with other circle-based fonts, condensed fonts with other tall, thin fonts.

[{{< figure class="aligncenter size-full wp-image-93" title="Kaffeesatz as a header font with Droid Sans as the body font" src="/images/2010/07/Screen-shot-2010-07-05-at-18.48.50.png" alt="Kaffeesatz as a header font with Droid Sans as the body font" width="435" height="144" >}}](/images/2010/07/Screen-shot-2010-07-05-at-18.48.50.png)

If you’re really struggling to combine two, just use a different weight or style for the heading, like bold or all uppercase.

[{{< figure class="aligncenter size-full wp-image-94" title="Georgia as header and body font" src="/images/2010/07/Screen-shot-2010-07-05-at-18.51.45.png" alt="Georgia as header and body font" width="440" height="134" >}}](/images/2010/07/Screen-shot-2010-07-05-at-18.51.45.png)

<p>Mark Boulton covers these kinds of combinations in his fantastic book, A Practical Guide to Designing For The Web.

### Keep it in the family

The easiest way to find two fonts that suit each other is to take two from the same family. These are always designed around the same shapes so you know they’ll look good next to each other. This is particularly useful if you want to mix serif and sans-serif fonts. For example, the Museo family. Museo Sans, Museo Serif and Museo Slab all look great used in any combination.

[{{< figure class="size-full wp-image-95 aligncenter" title="The Museo Family" src="/images/2010/07/Screen-shot-2010-07-05-at-18.55.53.png" alt="The Museo Family" width="453" height="278" >}}](/images/2010/07/Screen-shot-2010-07-05-at-18.55.53.png)

### Use simple fonts for body text

Whatever you do, leave the fancy fonts for the headings. With body text (paragraph text,) you’re aiming for readability above all else. Using any kind of fancy, looping, scrawly, drippy, firey font here will make it hard to read and really distract the reader.

[{{< figure class="size-full wp-image-96 aligncenter" title="A paragraph in Papyrus" src="/images/2010/07/Screen-shot-2010-07-05-at-18.59.14.png" alt="A paragraph in Papyrus" width="458" height="283" >}}](/images/2010/07/Screen-shot-2010-07-05-at-18.59.14.png)

### Use lovely long font stacks

Bear in mind that, whatever fancy web font method you use, there will always be a user that can’t see that font. It might be because their browser doesn’t have javascript turned on, or doesn’t support @font-face or doesn’t have the system font you specified. Solve this problem by using as many similar fonts as possible in your font stack.

For example, I want to use Museo Sans as my body font on this page. My code would look like:

`body { font-family: "Museo Sans", "Perspective Sans", Helvetica, Arial, sans-serif; }`

* Typekit will provide Museo Sans for me, so I’ll put that first in my font stack.
* In case the user doesn’t have javascript enabled (or uses Opera!) I’ll specify an @font-face font I found on Font Squirrel, Perspective Sans.
* For the rare case that don’t support Typekit or @font-face, I’ll specify the system font Helvetica.
* Just in case a user doesn’t even have Helvetica, I’ll also specify the wildly popular system font, Arial.
* And for the user who for some reason has only weird fonts I’ve never heard of on their computer, I’ll specify sans-serif, so at least I know that they’re not being delivered a serif font when I really fancied sans.

Not much effort, maximum kindness to the user.

### Keep the poor Windows users in mind

Whichever fonts you choose, you want to make sure it looks good in as many browsers as possible. For us lucky mac users, the fonts tend to normally look smooth and light and lovely. Unfortunately many Windows users aren’t so lucky. Craggy, pixelly and oddly squashed-looking fonts are very common.

[{{<figure class="wp-caption aligncenter size-full wp-image-98" title="Typodermic's Bouffant font in Mac's Safari (top) and Windows' Internet Explorer 6 (bottom) " src="/images/2010/07/Screen-shot-2010-07-05-at-19.14.52.jpg" alt="Typodermic's Bouffant font in Mac's Safari (top) and Windows' Internet Explorer 6 (bottom) " width="232" height="104" caption="Typodermic’s Bouffant font in Mac’s Safari (top) and Windows’ Internet Explorer 6 (bottom)">}}](/images/2010/07/Screen-shot-2010-07-05-at-19.14.52.jpg)

Many Windows people aren’t as fussy as me, or just don’t notice, but it’s really worth checking that what the Windows’ users see is actually *legible*.

This quick little guide is just the beginning of all the things I try to consider when I’m choosing fonts to use on the web. A lot of it feels automatic, but when I really think about it, there’s all sorts of rules and theory I’m trying to apply to my choices. And that’s still not saying I always get it right. To a degree, it is still a subjective choice.

## 4 comments

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-4">
			<div class="comment-author vcard">
			<img alt='' src='http://2.gravatar.com/avatar/2ecdcad7eefa02963363be36460ccc7b?s=72&amp;d=mm&amp;r=g' srcset='http://2.gravatar.com/avatar/2ecdcad7eefa02963363be36460ccc7b?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' /><cite class="fn"><a href='http://ashinyworld.blogspot.com' rel='external nofollow' class='url'>Loulouk</a></cite>
				<aside class="comment-meta commentmetadata"><p><a href="#comment-4"><time datetime="2010-07-05T19:48:37+00:00" pubdate class="published">
		 at <span class="hours">19:48pm</span></time></a></p>
	</aside>
	</div>
	<div class="comment-entry">
		I’ve absolutely no clue about fonts and about to be thrown into a web dev job. To say this is helpful would be a small understatement but in lieu of gushing I’ll simply say thank you.
	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-5">
			<div class="comment-author vcard">
			<img alt='' src='http://2.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=72&amp;d=mm&amp;r=g' srcset='http://2.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' /><cite class="fn">Laura</cite>
				<aside class="comment-meta commentmetadata"><p><a href="#comment-5"><time datetime="2010-07-06T16:35:12+00:00" pubdate class="published">
		 at <span class="hours">16:35pm</span></time></a></p>
	</aside>
	</div>
	<div class="comment-entry">
		I’m so pleased you found it helpful! Your comment made my day :)
	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-6">
			<div class="comment-author vcard">
			<img alt='' src='http://0.gravatar.com/avatar/3785543bade130b2613346d12de80dfc?s=72&amp;d=mm&amp;r=g' srcset='http://0.gravatar.com/avatar/3785543bade130b2613346d12de80dfc?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' /><cite class="fn"><a href='http://www.cvwdesign.com/txp' rel='external nofollow' class='url'>Clive Walker</a></cite>
				<aside class="comment-meta commentmetadata"><p><a href="#comment-6"><time datetime="2010-07-13T12:27:26+00:00" pubdate class="published">
		 at <span class="hours">12:27pm</span></time></a></p>
	</aside>
	</div>
	<div class="comment-entry">
		The Windows font thing is a real bugbear of mine. I have seen lots of websites using ‘new’ fonts where the display on Windows is almost illegible. Perhaps this is because of Windows font rendering issues (ClearType vs non-ClearType vs Vista vs XP?) or perhaps the font chosen does not have very good hinting for the web, I don’t know. Either way, it seems like poor testing/implementation.

OK, rant over :-)
	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-7">
			<div class="comment-author vcard">
			<img alt='' src='http://0.gravatar.com/avatar/9a3a20b0ac41f570312843796cd8e53e?s=72&amp;d=mm&amp;r=g' srcset='http://0.gravatar.com/avatar/9a3a20b0ac41f570312843796cd8e53e?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' /><cite class="fn">Yulie</cite>
				<aside class="comment-meta commentmetadata"><p><a href="#comment-7"><time datetime="2010-07-17T23:29:38+00:00" pubdate class="published">
		 at <span class="hours">23:29pm</span></time></a></p>
	</aside>
	</div>
	<div class="comment-entry">
		Thanks Laura! Your tips are simple and to the point :)
	</div>
</li>
</ol>

	
