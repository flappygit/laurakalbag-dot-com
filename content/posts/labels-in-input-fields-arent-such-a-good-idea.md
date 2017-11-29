---
title: "Labels in input fields aren’t such a good idea"
draft: true
colours: ["#2377a4", "#466e84", "#5A92B0", "#3a86ae", "#80afc9", "#235976", "#6ab1d7"]
date: 2011-05-27T17:52:37+00:00
categories: ["Design Issues", "Usability"]
tags: ["accessibility", "form", "form fields", "HTML5", "interface", "label", "placeholder attribute", "usability", "users"]
[params]
  body_classes = "blog"
---

There’s something that’s been bothering me lately. It seems to be some kind of form interface trend where the labels for text inputs are placed inside the fields themselves.

Example:

{{< figure class="size-full wp-image-422 alignleft" title="a form field where the label is shown inside the text input field" alt="a form field where the label is shown inside the text input field" src="/images/2011/05/Screen-shot-2011-05-27-at-16.48.49.png" width="226" height="54" >}}

## There might be some pros

Admittedly, this makes an interface slicker. It saves space where you’d usually have a label, then some padding, then the input field and probably a load of padding around the lot.

But what you’re gaining in a clean look, you’re completely losing through a total lack of usability.

## So, I’m an interface idiot

You know the lowest common denominator, idiot users that we design easy interfaces for? The ones that need to be led by the hand, step by step, across your design to get to the call-to-action?

That’s me, that is. I am an incredibly naïve user. I skim read, I’m forgetful, I barely pay attention and when I do I’m easily confused.

## This is what I see

Here’s an example from a site that is otherwise a shimmering beacon of awesomeness over the wasteland that is the web:

### Project Noah

As part of Project Noah, you upload photos of nature. The aim is to identify the creature or plant in your photo, and part of that is providing the relevant links to that species’ page on Wikipedia and the Encyclopedia of Life.

[{{< figure class="aligncenter size-full wp-image-423" title="Reference URLs on Project Noah, where the label is shown inside the text input" alt="Reference URLs on Project Noah, where the label is shown inside the text input" src="/images/2011/05/Screen-shot-2011-05-27-at-16.55.42.png" width="399" height="142" >}}](http://projectnoah.org)It’s a beautiful interface, but I have an issue. I’ll go and paste in a URL, then I’ll select the other text box:

{{< figure class="aligncenter size-full wp-image-424" title="Reference URL input on Project Noah, where one URL input is filled in and the other is focused but empty" alt="Reference URL input on Project Noah, where one URL input is filled in and the other is focused but empty" src="/images/2011/05/Screen-shot-2011-05-27-at-16.59.40.png" width="401" height="140" >}}
Then I have this thought:

> Did I put the URL in the right box? Is Encyclopedia of Life the top input or the bottom input? How do I find out?!

It seems pedantic, but I *genuinely do* get this sense of panic that I’m entering it wrong and there’s no way to check that I’m doing it right. I have to click back outside the input box, so it no longer has focus, to check what the label was again.

### WordPress

Another example from an interface that I use on a regular basis and generally love. In the 2.8 redesign of the WordPress admin, which is generally a huge amount better than before, the post editor title lost it’s label.

Before:

{{< figure class="aligncenter size-large wp-image-425" title="WordPress 2.7 post editor" alt="WordPress 2.7 post editor" src="/images/2011/05/Screen-shot-2011-05-27-at-1-960x617.png" width="640" height="411" >}}
After:

{{< figure class="aligncenter size-large wp-image-429" title="WordPress 3.1 post editor" alt="WordPress 3.1 post editor" src="/images/2011/05/Screen-shot-2011-05-27-at-17.19.17-960x624.png" width="640" height="416" >}}

The problem is that the first input box you’ll click into is the top title input. It actually auto-focuses, and some clever script means that it puts the label back in after the auto-focus, but then the second you start typing you’ve lost that label. If you start typing, then backspace because you made a mistake, you’ve lost that label:

<p style="text-align: center;">{{< figure class="aligncenter size-full wp-image-431" title="WordPress 3.1 post editor with no title label" alt="WordPress 3.1 post editor with no title label" src="/images/2011/05/Screen-shot-2011-05-27-at-17.18.48.png" width="636" height="460" caption="" >}}

#### Designers often make assumptions

It’s all very well to assume that the user will remember that the title belongs in that box, but what if it’s somebody has cognitive difficulties? What if it’s someone that’s just an idiot like me who clicks into boxes without paying attention to the label first?

### It started as an example

Originally we used pre-entered text in an input field as an example, to help users understand the input required. WordPress itself has a great example of this on the Writing Settings page in the WordPress admin:

{{< figure class="aligncenter size-full wp-image-433" title="WordPress Writing Settings uses text inside input boxes to help users understand the input required" alt="WordPress Writing Settings uses text inside input boxes to help users understand the input required" src="/images/2011/05/Screen-shot-2011-05-27-at-17.30.53.png" width="641" height="253" >}}

These fantastic triggers mean that users who aren’t necessary technically minded can see the type of input that’s required to set up post via email, match that to the information they have and easily enter it into the boxes.

When did these useful triggers become a way to hinder users, instead of help them?

## The rise of the HTML5 placeholder leaves room for abuse

HTML5 has a fantastic new form input attribute for adding placeholder information into the input boxes so that you can easily give your users cues without the need for JavaScript or CSS hacks:

{{< figure class="aligncenter size-full wp-image-434" title="HTML5 form snippet" alt="HTML5 form snippet" src="/images/2011/05/Screen-shot-2011-05-27-at-17.38.39.png" width="527" height="142" >}}

**Edit:** “*name*” should actually be “*id*” here in the text input, I always get those two mixed up! (Thanks [Mike](/labels-in-input-fields-arent-such-a-good-idea/#comment-2794), for the heads up)

{{< figure class="size-full wp-image-435 aligncenter" title="HTML5 form preview" alt="HTML5 form preview" src="/images/2011/05/Screen-shot-2011-05-27-at-17.39.00.png" width="215" height="101" caption="I’m concerned that people will misuse or misunderstand the placeholder attribute as a way to replace form labels" >}}

But it’s not the same thing!

A label tells you what a form input requires, a placeholder gives you an example of the input required.

I’m no accessibility expert, but I can imagine the loss of a label isn’t going to help with screen readers. Forgetful people and people with cognitive disabilities will also struggle.

## Please think of daft people like me

It might beautify your interface and make you look modern and cool, but a label isn’t the same as a prompt. We need to keep our forms as clear as possible and not let cool technology take over the understanding of basic user behaviour.

I don’t know if I’m alone in struggling with using these inputs, but I’d love to know everybody else’s opinions.

## 48 comments

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-200">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/2d65a81054bdc80fc05dc74f2740b4c9?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/2d65a81054bdc80fc05dc74f2740b4c9?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://dbushell.com' rel='external nofollow' class='url'>David Bushell</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-200"><time datetime="2011-05-27T18:06:33+00:00" pubdate class="published">
		 at <span class="hours">18:06pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Great post Laura! I’ve experimented with placeholders instead of labels but any aesthetic gain is totally lost in usability. I have exactly the same problems you’ve highlighted. If us web designers/developers can’t handle it –; what about everyone else? I say use both labels and placeholders.
	</div>
	<ul class="children">
		<li class="comment odd alt depth-2" id="li-comment-221">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/3394cf25ac096698c680916a3c6cf336?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/3394cf25ac096698c680916a3c6cf336?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://meteoracle.co.uk' rel='external nofollow' class='url'>Westley Knight</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-221"><time datetime="2012-12-14T10:16:05+00:00" pubdate class="published">
		 at <span class="hours">10:16am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		I agree that the use of both labels and placeholders is the way to go. If you are going to drop one, it should be the placeholder and the label should be more descriptive. But ALWAYS have a label. And don’t forget the ‘for’ attribute.
		</div>
	</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-201">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/f202503f0ea3118e596f40fdaf8fb3f8?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/f202503f0ea3118e596f40fdaf8fb3f8?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.cliffpro.com' rel='external nofollow' class='url'>Cliff Huizenga</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-201"><time datetime="2011-05-27T18:30:02+00:00" pubdate class="published">
		 at <span class="hours">18:30pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		I’m definitely on the camp of using both labels and placeholders, but not placeholders by themselves. I recently tried manipulating a search field on my blog to remove the search button and place the word “Search” as a label inside the field. While it looked clean, it was confusing as to what it was after you click inside the box, and it wasn’t obvious how to send the search query (mainly because…well, there was no longer a search button). 

Not everything is obvious to everyone. Even though the design *could* look nicer without labels, a true designer will find a way to make them work visually.
	</div>
</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-202">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/9be8367907d042cb538af6697549e47e?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/9be8367907d042cb538af6697549e47e?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://twitter.com/markedup' rel='external nofollow' class='url'>Pete Fairhurst</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-202"><time datetime="2011-05-27T21:05:18+00:00" pubdate class="published">
		 at <span class="hours">21:05pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		As an Interaction Designer, I’ve been tackling and retackling this very problem in my forms for a while now.

The current solution to the “activated, anonymous” problem involves standard HTML features, with a dash of jQuery to smarten things up.

<p>1. Layout your form with paired label and input combinations as normal.

2. Use a safe offscreening technique on your labels to maintain accessibility and satisfy your visual requirements.

3. Add the label text to each input as a ‘title’.

4. Add a class of “hint” to each input.

5. Use a bit of jQuery that, on load:

a) sets the “value” of all your “hint” inputs to their title text,

b) adds a class of “hinted” for that light grey text effect,

c) set the “focus” event to remove the “hinted” class and clear the “value” *if* it’s the same as the title on focus,

d) set the “blur” event to reinstate both the “hinted” class and the “title” as value *only* if the value is empty.</p>
It’s a little bit of faff, but I think it’s worth it for the experience benefits. If your user mouses over an input, they’ll get a tool tip (because of the title). And if they click out of the input without entering anything, they’ll get the hint back again.

And, for an added nicety, you could set a corresponding icon as a background on each input on focus, too –; particularly effective if you need to have several hinted fields close together.

Anyway, hope some of all that is of use. :)
	</div>
</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-203">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/9be8367907d042cb538af6697549e47e?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/9be8367907d042cb538af6697549e47e?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://twitter.com/markedup' rel='external nofollow' class='url'>Pete Fairhurst</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-203"><time datetime="2011-05-27T21:14:52+00:00" pubdate class="published">
		 at <span class="hours">21:14pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Oh, and one final step!

6. When your form submits, make sure you empty every “hint” input if its value matches its title; otherwise you may cock up any validation you might otherwise have on your form.
	</div>
	<ul class="children">
		<li class="comment byuser comment-author-laura bypostauthor odd alt depth-2" id="li-comment-205">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Laura</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-205"><time datetime="2011-05-27T22:21:05+00:00" pubdate class="published">
		 at <span class="hours">22:21pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Thanks Pete, that’s brilliant. Definitely something I’ll think of using in the future!
		</div>
	</li>
	<li class="comment even thread-even depth-1" id="li-comment-204">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/4279716d19699a421a5ad1d532fc9a08?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/4279716d19699a421a5ad1d532fc9a08?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://zed1.com' rel='external nofollow' class='url'>Mike Little</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-204"><time datetime="2011-05-27T22:15:42+00:00" pubdate class="published">
		 at <span class="hours">22:15pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Hi Laura,

I’m passionate about accessibility and usability, and I agree completely; this trend for ultra clean interfaces is causing problems for people who might struggle with this thing called the web.</p>
These days some of the newest users are those who have been reluctant to do this “internet thing” because it is “complicated and scary”. We shouldn’t be making it any harder than it is. There is huge value in keeping things familiar, especially when it requires non-trivial interaction from the user.

Thanks for raising the subject, it’s important not to forget the user in the pursuit for beauty!

Mike
	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-206">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/3785543bade130b2613346d12de80dfc?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/3785543bade130b2613346d12de80dfc?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.cvwdesign.co.uk' rel='external nofollow' class='url'>Clive Walker</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-206"><time datetime="2011-05-28T10:20:21+00:00" pubdate class="published">
		 at <span class="hours">10:20am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		In these cases, using the title attribute on input fields helps (in a small way) since that is seen on hover. Quite simple to do but not always done (I admit I forget sometimes!)
	</div>
	<ul class="children">
		<li class="comment even depth-2" id="li-comment-207">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://laurakalbag.wpengine.com' rel='external nofollow' class='url'>Laura</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-207"><time datetime="2011-06-01T17:12:58+00:00" pubdate class="published">
		 at <span class="hours">17:12pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		You’re right! I don’t think I ever knew that. Definitely helps the usability of the form if the user holds their mouse over for long enough.
	</div>
</li>
	<li class="comment odd alt depth-2" id="li-comment-209">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/4279716d19699a421a5ad1d532fc9a08?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/4279716d19699a421a5ad1d532fc9a08?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://zed1.com' rel='external nofollow' class='url'>Mike Little</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-209"><time datetime="2011-06-01T17:36:05+00:00" pubdate class="published">
		 at <span class="hours">17:36pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		It will also be read out for those using screen readers.
	</div>
	<ul class="children">
		<li class="comment even depth-3" id="li-comment-233">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/7aa2f48d088eb88d5c65e203cbc5f24c?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/7aa2f48d088eb88d5c65e203cbc5f24c?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://irresponsibleart.com' rel='external nofollow' class='url'>Jer Brand</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-233"><time datetime="2013-02-20T19:11:24+00:00" pubdate class="published">
		 at <span class="hours">19:11pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		I used to think this as well, however the guys at WebAIM schooled me: Reading of the title attribute is OPTIONAL and can be turned off entirely in most app’s settings. You can’t depend on it.
		</div>

		



</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-208">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/4279716d19699a421a5ad1d532fc9a08?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/4279716d19699a421a5ad1d532fc9a08?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://zed1.com' rel='external nofollow' class='url'>Mike Little</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-208"><time datetime="2011-06-01T17:34:28+00:00" pubdate class="published">
		 at <span class="hours">17:34pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		By the way, the HTML5 example has an error. 

The `for` attribute of the `label` can only take an `id` as a value. But the corresponding `input` doesn’t have an `id`. See the [HTML5 specification](http://www.w3.org/TR/html5/forms.html#attr-label-for" rel="nofollow).
	</div>
	<ul class="children">
		<li class="comment even depth-2" id="li-comment-210">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://laurakalbag.wpengine.com' rel='external nofollow' class='url'>Laura</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-210"><time datetime="2011-06-01T17:38:51+00:00" pubdate class="published">
		 at <span class="hours">17:38pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Yes! I realised this when I wrote out a massive form with every single input using `name=` instead of `id=`. Always get those two mixed up :s
	</div>
	<ul class="children">
		<li class="comment odd alt depth-3" id="li-comment-225">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/e6a042553edc475cda59f8f62df2a86c?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/e6a042553edc475cda59f8f62df2a86c?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">dotnetCarpenter</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-225"><time datetime="2012-12-18T02:49:23+00:00" pubdate class="published">
		 at <span class="hours">02:49am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Someone noted on some website that I forgot, but it’s pretty damn useful. Put your <b></b> inside your <b></b> and use don’t have to specify <b>for=”[id of input]”</b>. And never have to remember the difference between name and id. Except that the server guy receiving the form data will appreciate you and give you coffee if you have sane <b>name</b> properties.
		</div>

		



</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-211">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/ded01cdab114abe4ec13511e4c25b9bb?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/ded01cdab114abe4ec13511e4c25b9bb?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://andyhume.net' rel='external nofollow' class='url'>Andy Hume</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-211"><time datetime="2011-06-04T23:37:02+00:00" pubdate class="published">
		 at <span class="hours">23:37pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Good post –; and I agree! There’s a worrying trend of people conflating label and placeholder, and an even more worrying one of people thinking that having placeholder text is in any way a replacement for a label *element*.

I checked the WordPress example you mentioned, and they do include the input element which is good. In fact it looks like quite a clever implementation. The label element is actually absolutely positioned on top of the text input, rather than text written to the input’s value property. Then when you click on the label it focuses you into the input.

Having said that it looks like they handle the no JavaScript situation less well. The label element is hidden and there is no visual hint as to what the field is for at all. I tried it with Voice Over switched on and it does read the label for the title input which is good, but then there is no label at all associated with the textarea for the body of the post, and the screen reader is completely lost.
	</div>
</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-212">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/32e397a45f37a7102f5bd8c8eff54112?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/32e397a45f37a7102f5bd8c8eff54112?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Mats Svensson</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-212"><time datetime="2012-02-16T15:15:52+00:00" pubdate class="published">
		 at <span class="hours">15:15pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Putting help-texts or labels INSIDE the texfields,

either with HTML5 placeholder, or some hack,

 is F useless and should NEVER be used.</p>
I have never EVER ever seen it done in a way that doesn’t break when you fill a field by drag&amp;drop.

<p>Example:

The help text in the field says “Name”.

You select the text “Smith” somewhere and drag it and drop it in the field.

It now says “NaSmithme” or similar.</p>
I guess you could build something that makes the field transparent , puts the help-text under (lower z-index), and then hides the help-text  when the user start to fill it out.

<p>But NEVER actually put the help-text inside the field itself, like its always done now .

This madness must be stopped!</p>	</div>
</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-213">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/be750826c14d16592d7f44fa8f952990?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/be750826c14d16592d7f44fa8f952990?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.belron.com' rel='external nofollow' class='url'>Craig Sullivan</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-213"><time datetime="2012-03-19T07:38:39+00:00" pubdate class="published">
		 at <span class="hours">07:38am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Hi,

One other thing missing is the ‘affordance’ of the field –; during scanning behaviour.

For example, adding text into a search box simply makes it less visible on the screen so you’re hobbling your interface discoverability.   

We’ve found the best balance is out of field help text –; supporting but not interfering with people’s ability to evaluate the size, information required and type from the input box itself (seen in eye tracking + see [http://www.lukew.com](http://www.lukew.com" rel="nofollow) work).

I think that if you test this stuff, you’ll find all sorts of problems.  Visual clarity in the designers eyes does not translate to usability or conversion in a product –; this stuff often looks nice and clever but can suffer from interrupting already known patterns for using an interface that people look for (e.g. an empty bloody box, not something filled with text).

I had a similar discussion regarding phone formatting recently –; splitting it all into nice little boxes for USA phone numbers looks pretty but imposes work and friction on the viewer –; regardless of your design intentions.  In that case, lots of  clicks and eye focus work would have been imposed on the user, even though it looked ‘nice’.

C.
	</div>
</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-216">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/05a5dfd9e66b566bbb32091bb87ad202?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/05a5dfd9e66b566bbb32091bb87ad202?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://remy.bach.me.uk' rel='external nofollow' class='url'>Rémy</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-216"><time datetime="2012-04-12T18:35:17+00:00" pubdate class="published">
		 at <span class="hours">18:35pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		I totally agree with your POV here. It’s the whole reason I made this jQuery plugin! [https://github.com/remybach/jQuery.superLabels](https://github.com/remybach/jQuery.superLabels" rel="nofollow)
	</div>
</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-217">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/94434f1e43403f5c1bf620565f0027cb?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/94434f1e43403f5c1bf620565f0027cb?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.goodsignal.com' rel='external nofollow' class='url'>Blair Keen</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-217"><time datetime="2012-04-13T14:23:14+00:00" pubdate class="published">
		 at <span class="hours">14:23pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Hi Laura,

Great post.  I’d be interested to hear what your point of view would be regarding the use of tool tips to display the form label in the event that the placeholder label is either replaced with input text or removed as in your WordPress example?
	</div>
	<ul class="children">
		<li class="comment odd alt depth-2" id="li-comment-218">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/666570c00e7598fbf0090bf4f76f860e?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/666570c00e7598fbf0090bf4f76f860e?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Stomme poes</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-218"><time datetime="2012-04-14T09:21:38+00:00" pubdate class="published">
		 at <span class="hours">09:21am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Hi Blair,

you also mean this tooltip is available to keyboarders using CSS or JS (in the case of IE and similar)?</p>		</div>
	</li>
	<li class="comment even thread-even depth-1" id="li-comment-219">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/2366090ac3624ea0bbb7e9c04ae5b2da?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/2366090ac3624ea0bbb7e9c04ae5b2da?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://koenahn.com' rel='external nofollow' class='url'>Koen Ahn</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-219"><time datetime="2012-11-30T22:39:26+00:00" pubdate class="published">
		 at <span class="hours">22:39pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Excellent article!

Forms are always a struggle. I’ll keep this in mind when making one.

Thank you :)</p>	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-220">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/a1a15f489279744da38547e1a8d8ae19?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/a1a15f489279744da38547e1a8d8ae19?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://danmalarkey.com' rel='external nofollow' class='url'>Dan Malarkey</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-220"><time datetime="2012-12-13T17:30:19+00:00" pubdate class="published">
		 at <span class="hours">17:30pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Great article! “Web Form Design” by Luke Wroblewski goes over many of these exact examples!
	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-222">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/f85dd90f263cc1d9a86a727fb26c21dc?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/f85dd90f263cc1d9a86a727fb26c21dc?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.artsocket.com' rel='external nofollow' class='url'>Dmitri</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-222"><time datetime="2012-12-17T22:57:57+00:00" pubdate class="published">
		 at <span class="hours">22:57pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Sorry guys I just didn’t have time to read all the comments to post mine, so my apologies if it’s a repost of someone else’s idea.

<p>I think this is a review of unfinished or undersigned examples. Or they are just buggy, and those bugs are the problem, not the design. Here’s why:
* When I focus on the field, this should not make the label go away, the label should go away only when I start typing.

*After not entering any text in that field and removing the focus, the label would remain, according to the above. Thus confusion cleared.

*This design will obviously be not a good idea where all the fields look the same and there are plenty of them. It works best on login forms, where you can save some space and make people feel great about using your app.</p>
To sum it up, if the bugs are fixed and this concept is not over abused, it is a good idea :)
	</div>
	<ul class="children">
		<li class="comment odd alt depth-2" id="li-comment-234">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/87a9c125448afeb9108a8b8cf56fd658?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/87a9c125448afeb9108a8b8cf56fd658?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://jarment.com' rel='external nofollow' class='url'>Jim Arment</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-234"><time datetime="2013-02-26T19:07:30+00:00" pubdate class="published">
		 at <span class="hours">19:07pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		+1 on that.

Include labels for accessibility reason, but visibility of them isn’t necessary if you’re using the placeholder attribute. The placeholder text is preset on :focus, but hides after you start typing.
		</div>
	</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-223">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/a8c2ce39b271184ff4c10c9e971f8bc9?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/a8c2ce39b271184ff4c10c9e971f8bc9?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://jamiefarrelly.com' rel='external nofollow' class='url'>Jamie Farrelly</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-223"><time datetime="2012-12-17T23:14:15+00:00" pubdate class="published">
		 at <span class="hours">23:14pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Good read, I thought I was the only person who does things like this!

A few weeks ago something similar happened to me and I just had to refresh the page to double check that I knew what was going on.
	</div>
</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-224">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/0c734018957cef85042f5e4c58ceaadd?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/0c734018957cef85042f5e4c58ceaadd?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.timothywhalin.com' rel='external nofollow' class='url'>Timothy Whalin</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-224"><time datetime="2012-12-17T23:21:36+00:00" pubdate class="published">
		 at <span class="hours">23:21pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Hi Laura,

I agree with you 90%. The label is a much needed element that seems to be missing from a lot of web content. However, I would also like to comment that I think there are cases in which a label is not needed. For example, if a search field has a “search” placeholder and a search icon, a user will know what they’ve typed in there even once the placeholder text is gone. This would be similar to anytime a form contains icons.

Another example is when the fields are very straightforward. For example, the contact form on my site has name, email, message. Once a user types in their name, for example, they would remember and know that the field was their name.

I totally agree with the sentiment of your article that form labels are still needed and shouldn’t be removed just for aesthetics. Hope you don’t mind my devil’s advocate comment. :)
	</div>
</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-226">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/1ea75377e8f31300a35d459391be2373?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/1ea75377e8f31300a35d459391be2373?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.zivmeltzer.com' rel='external nofollow' class='url'>Ziv Meltzer</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-226"><time datetime="2012-12-18T14:44:59+00:00" pubdate class="published">
		 at <span class="hours">14:44pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Well, thank you! Finally, someone writes it down, as simple as it should be.

Win! :)</p>	</div>
</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-227">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/598b7b1a8f45f2a8ed4e3000fa955b14?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/598b7b1a8f45f2a8ed4e3000fa955b14?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://www.vasiljevski.com' rel='external nofollow' class='url'>Nikola Vasiljevski</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-227"><time datetime="2012-12-18T16:17:45+00:00" pubdate class="published">
		 at <span class="hours">16:17pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Nice point, people tend to forget that technology should help people :)
	</div>
</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-229">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/8486c9e4d3ef6024f449bf9de54b1330?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/8486c9e4d3ef6024f449bf9de54b1330?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://carlorizzante.com' rel='external nofollow' class='url'>Carlo Rizzante</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-229"><time datetime="2012-12-27T14:51:20+00:00" pubdate class="published">
		 at <span class="hours">14:51pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Nice article, Laura (and nice blog). It actually inspired me today while polishing a backend interface (in WordPress). You made me realize that it’s likely time to finally fix my own contact page ^__^ Thanks!
	</div>
</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-230">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/8486c9e4d3ef6024f449bf9de54b1330?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/8486c9e4d3ef6024f449bf9de54b1330?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://carlorizzante.com' rel='external nofollow' class='url'>Carlo Rizzante</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-230"><time datetime="2012-12-27T14:55:23+00:00" pubdate class="published">
		 at <span class="hours">14:55pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Nice article, Laura, thanks for sharing. It inspired me right today while polishing a backend interface I’m developing (in WordPress). And it made me realize that it may be finally time to rethink my contact page! :-o Cheers!
	</div>
</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-235">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/ad1368d5f36d84983fd58ebdbb90172d?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/ad1368d5f36d84983fd58ebdbb90172d?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Aaron</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-235"><time datetime="2013-02-27T06:24:52+00:00" pubdate class="published">
		 at <span class="hours">06:24am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		I agree with this post but always liked the clean look of using placeholders.

I wrote a jQuery plugin that I think largely solves this problem. It works by dropping the label down below the field after it has focus or a value so the label is still visible, while maintaing the clean look of placeholders before the form is used.

You can find it here along with a demo: <a href='http://jacware.github.com/fancyplaceholder/' rel="nofollow">http://jacware.github.com/fancyplaceholder/</a>

Let me know what you all think!
	</div>
</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-237">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/bf2b0d6a0f46d26d5cb5168285107816?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/bf2b0d6a0f46d26d5cb5168285107816?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://jfeliweb.com' rel='external nofollow' class='url'>Jeazy</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-237"><time datetime="2013-03-04T19:39:44+00:00" pubdate class="published">
		 at <span class="hours">19:39pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Great Article! This makes complete sense to me and you hit the points well. I can’t count how many times I forget what to put into a form.
	</div>
</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-239">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/92340eafa4400eae2b68798a47e077bf?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/92340eafa4400eae2b68798a47e077bf?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://kolor-designs.com' rel='external nofollow' class='url'>razvan</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-239"><time datetime="2013-05-25T05:08:00+00:00" pubdate class="published">
		 at <span class="hours">05:08am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		It always drives me crazy when a form only has placeholders that go away on focus. 

I really like the aesthetic of having the label inside the input field –; just don’t hide it on focus. Here’s an example of how I implemented it on one of the projects I worked on: goo.gl/pzdkg
	</div>
</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-240">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/ff5098abb715ee41beda5c4239a3f2f4?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/ff5098abb715ee41beda5c4239a3f2f4?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Spencer Edwards</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-240"><time datetime="2013-06-11T16:53:03+00:00" pubdate class="published">
		 at <span class="hours">16:53pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Excellent post!  I agree that this rising trend of only using placeholders as labels is actually knocking down the usability of a form.  I tend to use both as well, as one does accent the other.  There are ways to get a slick design while using both.
	</div>
</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-2780">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/55bb2acf65203dbb95c35a83e62e9ae6?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://laurakalbag.wpengine.com' rel='external nofollow' class='url'>Laura Kalbag</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-2780"><time datetime="2013-10-25T07:09:31+00:00" pubdate class="published">
		 at <span class="hours">07:09am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		A quick update on this subject: [Brad Frost has written up a great potential float label pattern (designed by Matt D Smith) on his website](http://bradfrostweb.com/blog/post/float-label-pattern/" rel="nofollow).
	</div>
</li>
	<li class="comment odd alt thread-even depth-1" id="li-comment-140588">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/000da50f19db5e37a65c29b87fd30956?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/000da50f19db5e37a65c29b87fd30956?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Ken Pierce</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-140588"><time datetime="2015-04-22T04:13:57+00:00" pubdate class="published">
		 at <span class="hours">04:13am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Some good ideas in the comments, but don’t forget that any solution that involves hovering the mouse literally does not exist for any user who lives on a smart phone rather then parked in front of a nice big monitor.
	</div>
</li>
	<li class="comment even thread-odd thread-alt depth-1" id="li-comment-145915">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/3d27a2811e4f7db144ee521ea05ebfcb?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/3d27a2811e4f7db144ee521ea05ebfcb?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">loeffel</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-145915"><time datetime="2016-03-17T10:03:29+00:00" pubdate class="published">
		 at <span class="hours">10:03am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		This can be done without using placeholder text with pure css. The markup needs to include the label after the input field then just position the label absolutely and resize and move it a few pixels up with something like `input-text:focus + label`. Add a transition and voilà –; no need for a jquery plugin.
	</div>
</li>
</ol>
