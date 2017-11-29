---
title: "Grid Frameworks and why I’m not keen on them…"
draft: true
colours: ["#7e2727", "#AF302F", "#c93534", "#4e4e4e", "#F8E2E2", "#303030", "#F5F6F8"]
date: 2013-01-01T19:01:59+00:00
categories: ["Markup"]
tags: ["accessibility", "clients", "control", "development", "frameworks", "grids"]
[params]
  body_classes = "blog"
---

I’ve written [a post for 12 Devs of Xmas on Grid Frameworks](http://12devsofxmas.co.uk/post/2013-01-01-day-7-grid-frameworks).

After spending months whining about grid frameworks, 960.gs and Bootstrap, I’ve finally backed up my tweet-sized complaints with some context and examples.

I knew it would be contentious and that some people would feel antagonised by my saying that developers who don’t consider accessibility shouldn’t be on the web. And possibly also that I suggest some developers lazily fail to customise frameworks to appropriately suit their needs. So far, the reasons behind these feelings seem to be a lack of control over their own work, blaming clients or bosses. I don’t know what to say to be helpful in these situations

Me, I would refuse to do a job that wouldn’t fit my idea of quality development. If there’s not enough time to make a site accessible (the idea of this still baffles me as I consider accessibility part of core development) then there’s not enough time to finish the project. It does feel rather unhelpful telling someone that, if their boss/client is forcing them to do things in the wrong way, they should quit their job, and I probably care about these things a lot harder than many, but honestly, that’s what I’d do.

Anyway, I’m sure I’ll be dealing with more accessibility-related issues in the future. It’s far too easy for me to go off on a rant and a ramble, I just want more people to care.

## 7 comments

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-435">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/3368e6126004d4fe7b1f7edfdbf7e5d6?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/3368e6126004d4fe7b1f7edfdbf7e5d6?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.craigmcpheat.co.uk' rel='external nofollow' class='url'>Craig McPheat</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-435"><time datetime="2013-01-02T15:26:53+00:00" pubdate class="published">
		 at <span class="hours">15:26pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		I appreciate and agree with your sentiment about semantic markup, and accessibility, but I think you may have jumped the gun in [Day 7: Grid Frameworks](http://12devsofxmas.co.uk/post/2013-01-01-day-7-grid-frameworks" rel="nofollow) by implying grid frameworks are inherently inaccessible.

I argue against front end frameworks in my day to day job. The reasons I cite are:

<p>1) developers need to learn the framework, not the underlying technology

2) our web standards require semantic markup, which frameworks often lack out the box

3) frameworks look like a framework –; sometimes as much work is required to theme it as there would be to build from scratch

4) frameworks often mean extra bytes –; superfluous markup contradicts my requirements for mobile first / every byte counts</p>
I get where you’re coming from and agree in most parts. I’m not saying I’ll never use a front end framework, but I do campaign for refining and building our own internal boilerplates.

It’s important to be careful when choosing arguments to protect accessibility. To say using a grid framework would introduce a risk to the accessibility of the site would be careless if not untrue, thus risking the importance of the accessibility argument. Like all things, the devil is in the detail. If those grids had semantic class names rather than grid_whatever they’d be no more accessible. You rightly point out some basic semantics required for a good accessible build –; lists, heading levels, good anchor text –; but these are separate from the structure provided by a grid framework. (Of course, all this goes without mention of landmark areas, aria, skip to main content etc)

(As an aside, is it terrible to use a grid as the structure and object orientate the theme with semantic classnames alongside the grid_whatevers?)

I agree accessibility and semantics are both important, but I think there’s a lot of detail missing to get from point A to point B in your post and subsequent comments, which is very dangerous when promoting the cause to senior stakeholders and those who need to understand the cold hard facts without emotion.
	</div>
	<ul class="children">
		<li class="comment byuser comment-author-laura bypostauthor odd alt depth-2" id="li-comment-436">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Laura</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-436"><time datetime="2013-01-02T17:06:57+00:00" pubdate class="published">
		 at <span class="hours">17:06pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Thanks Craig, there’s some great points in there, and I think you’re right in saying that I was making a bit of leap, here’s my explanation why:

I was really trying to create an argument around your point 2. “Our web standards require semantic markup, which frameworks often lack out of the box.” But then I came to ask myself: why do semantics matter? Why bother making anything semantic? I know that **I** think that semantics are important, but how do you explain it to someone who just thinks that semantics are about being fussy?

So I went one level deeper. Why are semantics so important to me? Chiefly, accessibility. Then reusability, maintenance etc. Thus my post became about these things, brushing over the semantics that people often disregard as purist.

I’m sorry if I didn’t convey the point well enough, and you’ve definitely given me some food for thought in terms of how I represent accessibility.
	</div>
	<ul class="children">
		<li class="comment even depth-3" id="li-comment-437">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/3368e6126004d4fe7b1f7edfdbf7e5d6?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/3368e6126004d4fe7b1f7edfdbf7e5d6?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.craigmcpheat.co.uk' rel='external nofollow' class='url'>Craig McPheat</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-437"><time datetime="2013-01-02T17:57:55+00:00" pubdate class="published">
		 at <span class="hours">17:57pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		No apology necessary Laura, any constructive discussion on accessibility is good discussion.

I too am incredibly passionate about semantic markup and accessibility, but the reason I need to be careful is there’s always someone ready with a counter; a supplier, external developers, project managers&#8230; I push back on poorly structured content all the time. As you mention, the basic but big ticket items like heading levels, form inputs, lists, good anchor text are all essential –; but would I push back on someone for using a grid framework? Probably not, as the site can be completely accessible whilst using a grid system, just as much as a more semantic site can be inaccessible.

If I’m honest, I would actually have to pay more attention if a supplier uses HTML5 sectioning elements to <b>structure the document “semantically”</b>, as these cause problems with the document outline when not implemented correctly:

[HTML5 sectioning elements, headings, and document outlines](http://www.456bereastreet.com/archive/201103/html5_sectioning_elements_headings_and_document_outlines/" rel="nofollow)

[HTML5 document outline revisited](http://www.456bereastreet.com/archive/201104/html5_document_outline_revisited/" rel="nofollow)
		</div>

		



</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-438">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/ed2eb293beec01de6d0081a2371fae06?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/ed2eb293beec01de6d0081a2371fae06?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Marc</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-438"><time datetime="2013-01-03T08:10:10+00:00" pubdate class="published">
		 at <span class="hours">08:10am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		I largely agree with your opinion on inaccessible, non-semantic grid systems. However, your post would have been more balanced if you had paid some attention to the existing alternatives. More semantic grid systems, such as [Susy](http://susy.oddbird.net/" rel="nofollow), [Singularity](http://singularity.gs/" rel="nofollow) and [Zen Grids](http://zengrids.com/" rel="nofollow) make it very easy to apply a custom grid to your own semantic HTML structure.
	</div>
	<ul class="children">
		<li class="comment byuser comment-author-laura bypostauthor even depth-2" id="li-comment-439">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Laura</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-439"><time datetime="2013-01-03T08:44:42+00:00" pubdate class="published">
		 at <span class="hours">08:44am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		I would if I were more familiar with the alternatives! That’s why I cautiously tweeted that Sass is probably the answer. And whilst I do use Sass, I still write all my grids from scratch. This might be foolish, or because I’m a creature of habit having done that with CSS since I started out……I’m not sure which!
	</div>
	<ul class="children">
		<li class="comment odd alt depth-3" id="li-comment-440">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/ed2eb293beec01de6d0081a2371fae06?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/ed2eb293beec01de6d0081a2371fae06?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Marc</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-440"><time datetime="2013-01-03T09:04:56+00:00" pubdate class="published">
		 at <span class="hours">09:04am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		OK, I didn’t see that tweet. I’d say just give Susy a try and keep an eye on [Susy Next](http://oddbird.net/2013/01/01/susy-next/" rel="nofollow)!
		</div>

		



</li>
</ol>
