---
title: "Sass for Designers"
draft: true
colours: ["#b047b6", "#404040", "#bb1e88", "#783b7b", "#d39ed6", "#652a5e", "#ffffff"]
date: 2012-12-28T17:51:04+00:00
categories: ["Markup"]
tags: ["CSS", "markup", "preprocessors", "Sass"]
body_classes: "blog"
---

Despite saying that I wanted to avoid writing post about development, I wanted to write something about [Sass](http://sass-lang.com/).

### Excuse me, what is Sass?

Sass is a CSS pre-processing language; it’s a slightly different way of writing CSS which can then be processed by a tool that spits out fully-working CSS. It’s like a kind of [short-hand](http://en.wikipedia.org/wiki/Short_Hand) that adds in some handy features that aren’t available in CSS. If you want to know how to use Sass in your workflow, try [my post on Sass for Designers — The Setup](/sass-for-designers-the-setup/ "Sass for Designers — The Setup").

### Why am I writing this?

Sass still isn’t particularly easy for designers to pick up straight away. The [documentation isn’t easy to understand](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html), The way it’s written is really aimed at those more familiar with programming. [The tutorial](http://sass-lang.com/tutorial.html) isn’t too bad, but it doesn’t tell you about the advantages from a designer’s point of view.

I want to just cover a few simple principles. I’m no Sass expert, I use mostly it in its simplest form, but I’ve found it incredibly useful.

So what are these advantages? It’s all about efficiency. It makes your markup quicker to write, less repetitive and easier to maintain. That might sound a bit performance-related, but I promise that it’s something that designers (we who use markup to support our design work, rather than being super-programmers) can use to make development much more straight-forward.

## Variables

The best and most basic example is variables. We tend to use the same colours throughout the document. This result in us writing the same hex code or RGB value over and over again. If we want to change that colour, we need to do a [Find-and-Replace](http://en.wikipedia.org/wiki/Find_and_replace) to pick through all of our markup, making sure we don’t accidentally change the wrong value. You might have a few rules that each need your dark red brand colour:

```
a {
  color: #822733;
}

.summary {
  color: #822733;
}

.copyright {
  color: #822733;
}
```

Using variables, we can give that particular red hex colour a variable name of `$brand-colour` at the beginning of our stylesheet, and then just use that variable throughout the stylesheet where we’d usually use the hex colour. Then, if you suddenly decide that the shade of red isn’t quite right, you just need to change where you declared `$brand-colour: #822733;` at the top, and it will be changed for every rule that uses the variable throughout the whole stylesheet.

```
// My Sass colour library

$brand-colour: #822733;

a {
  color: $brand-colour;
}

.summary {
  color: $brand-colour;
}

.copyright {
  color: $brand-colour;
}
```

### Numbers as variables

Variables don’t just have to be strings of text, they can also be numbers which you can manipulate. If you use some kind of baseline grid idea, modular scale, or just a pattern of numbers to keep your design proportional, chances are you’re frequently repeating the same values throughout your stylesheet. If you were using 10px measurements all over the place, you might create ‘unit variable’ with `$unit = 10;`. This unit could then be repeated:

```
$unit = 10px;

h1, h2, h3 {
  margin-bottom: $unit;
}

p {
  margin-bottom: $unit;
}
```

But how about when you want that unit to be doubled? You want *exactly* twice the margin on another element, because then it will still keep the rhythm in your design. With Sass, you can add simple maths (+, -, \*, /, %) to do this very simply:

```
$unit = 10px;

h1, h2, h3 {
  margin-bottom: $unit;
}

p {
  margin-bottom: $unit;
}

aside {
  margin-bottom: $unit*2; /* 20px */
}

footer {
  margin-top: $unit*4; /* 40px */
}
```

Then if you decide, one day, that multiples of 10px aren’t big enough for your design (need MOAR WHITESPACE) then you can just change your `$unit` variable to something bigger, such as `$unit = 15;` and all of your measurements will be changed accordingly, preserving those proportions throughout your stylesheet.

## Mixins

Mixins are reusable collections of rules. These are perfect for design patterns that you might use throughout the site. These also stop you repeating yourself in your CSS but in a way that’s more [semantic](http://en.wikipedia.org/wiki/Semantic_HTML) than using the same class name on every HTML element.

For example, you might have particular divider style that you use all over your site. You use it below all sorts of elements; `&lt;article&gt;`s, `&lt;header&gt;`s and even the odd `&lt;p&gt;`. It’s got a certain amount of padding between the border line and the content above, and a certain margin below. It’s just a grey border but it has a fancy shadow on it.

{{< figure class="attachment_1353 wp-caption aligncenter size-full wp-image-1353" alt="a grey border line with a subtle grey box-shadow" src="/images/2012/12/divider.jpg" width="280" height="50" caption="an example of what your divider with a subtle border might look like" >}}

Then you might apply the following CSS class of `.shadow-border` to any HTML element you want to have the divider. It’s not very semantic, but it does the job:

```
.shadow-border {
  border-bottom: 1px solid #a4a4a4; 
  
  -webkit-box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);
  box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);

  padding-bottom: 20px;
  margin-bottom: 40px;
}
```

If you wanted to be more semantic, you might go applying all those rules to all the relevant HTML elements, but this can make for an awkwardly-organised stylesheet.

```
header, article, p.intro {
  border-bottom: 1px solid #a4a4a4;
  -webkit-box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);
  box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);

  padding-bottom: 20px;
  margin-bottom: 40px;
}
```

With mixins, you can give this collection a name using `@mixin`. This name doesn’t have to relate in any way to your HTML:

```
@mixin shadow-border {
  border-bottom: 1px solid #a4a4a4; 
  
  -webkit-box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);
  box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);

  padding-bottom: 20px;
  margin-bottom: 40px;
}
```

Then, to apply that mixin to any element, you just include its name `@include shadow-border;` like you would any other rule in CSS.

```
@mixin shadow-border {
  border-bottom: 1px solid #a4a4a4; 
  
  -webkit-box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);
  box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);

  padding-bottom: 20px;
  margin-bottom: 40px;
}

article {
  @include shadow-border;
}

header {
  @include shadow-border;
}

p.intro {
  @include shadow-border;
}
```

Doesn’t that look neat and tidy?!

### Nesting mixins

Even better, you can nest your mixins inside other mixins. We might want to apply that same type of shadow to lots of elements, so that our design appears to have a consistent light source throughout the site. So we then make a mixin especially for that shadow too. This has the added bonus of keeping all the prefixed CSS (`-webkit, -moz, -o, -ms` etc.) tucked away in one place too.

```
// A few variables thrown in for good measure
$border-colour: #a4a4a4;
$unit: 10px;

@mixin subtle-shadow {
  -webkit-box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);
  box-shadow: 0px 2px 5px 0px rgba(200, 200, 200, 0.6);
}

@mixin shadow-border {
  @include subtle-shadow;
  border-bottom: $unit/10 solid $border-colour; /* Base unit divided by 10 = 1px */

  padding-bottom: $unit*2; /* Base unit multipled by 2 = 20px */ 
  margin-bottom: $unit*4; /* Base unit multipled by 4 = 40px */
}

article {
  @include shadow-border;
}

header {
  @include shadow-border;
}

p.intro {
  @include shadow-border;
}
```

## Nesting

Mixins aren’t the only thing you can nest in Sass. You could nest tags within each other if you wanted, which makes your CSS less repetitive and easier to read as you can see which selectors are related:

```
/* written in plain old CSS */

.module h3 {
  font-weight: bold;
}

.module p {
  padding-bottom: 10px;
}

/* written in Sass */

.module {
  
  h3 {
    font-weight: bold;
  }

  p {
    padding-bottom: 10px;
  }

}
```

But let’s face it, that’s getting really nit-picky about the neatness of your CSS.

### Nesting @media

Where nesting becomes incredibly useful is with media queries.

If you follow [SMACSS](/smacss-scalable-and-modular-architecture-for-css/ "SMACSS – Scalable and Modular Architecture for CSS") or any other school of thinking where you’re trying to base your media queries around the optimum display of your content, rather than the viewport width of various popular devices, then chances are your stylesheets are filled with different media queries trying to keep your site looking tidy at every possible width.

Nesting media queries can help with this. Where previous you may have felt like you needed to keep all your media queries in separate files (one for 320px and up, one for 768px and up and so on…) Group all selectors using the same media query width together or list all your media queries relevant to a selector one after the other. Sass allows you to nest your media queries within the selector so you can easily spot where those breaking points are and where they need to be changed.

For example, I have an article which has a changing `width`, `line-height` and `font-size` depending on the width of the viewport. I want the text of my article to be as legible as possible across all devices. In CSS, this might look like this:

```
/* initial rule for all viewports, including browsers that don't support @media */
article {
  font-size: 14px;
  line-height: 25px;
}

article h2 {
  font-size: 18px;
  padding-bottom: 15px;
}

/* for 300px viewports and wider (mobile first) */
@media only screen and (min-width: 300px) {
  article {
    line-height: 20px;
    width: 90%;
  }

  article h2 {
    padding-bottom: 10px; 
  }
}

/* for 600px viewports and wider */
@media only screen and (min-width: 600px) {
  article {
    line-height: 25px;
    width: 80%;
  }

  article h2 {
    padding-bottom: 15px; 
  }
}

/* for 900px viewports and wider */
@media only screen and (min-width: 900px) {
  article {
    width: 60%;
  }
}

/* for 1200px viewports and wider */
@media only screen and (min-width: 1200px) {
  article {
    font-size: 16px;
    line-height: 30px;
    width: 50%;
  }

  article h2 {
    font-size: 21px;
    line-height: 35px;
    padding-bottom: 20px; 
  }
}
```

When you can include the media query *within* the selector, it suddenly becomes a lot easier to find those rules that you’re so likely to tweak in the future.

```
article {
  font-size: 14px;
  line-height: 25px;

  h2 {
    font-size: 18px;
    padding-bottom: 15px;
  }
  
  @media only screen and (min-width: 300px) {
    line-height: 20px;
    width: 90%;
  
    h2 {
      padding-bottom: 10px; 
    }
  }

  @media only screen and (min-width: 600px) {
    line-height: 25px;
    width: 80%;

    h2 {
      padding-bottom: 15px; 
    }
  }

  @media only screen and (min-width: 900px) {
    width: 60%;
  }

  @media only screen and (min-width: 1200px) {
    font-size: 16px;
    line-height: 30px;
    width: 50%;

    h2 {
      font-size: 21px;
      line-height: 35px;
      padding-bottom: 20px; 
    }
  }
}
```

## Give it a go?

There are so many clever, time-saving, efficient things you can do with Sass, and I certainly don’t know them all. The benefit of writing Sass is that you can just write everything in plain old CSS, and just use Sass on the few selectors that could really benefit from it. That’s how I got started, and on every new project I work on, I learn another handy tip and make my CSS that much quicker to write.

If you’ve got any tips, please let me know in the comments as I find it really hard to discover what might be useful when you’re writing markup with a designer’s perspective!

## 9 comments

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-408">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/221a26d0593f7c89c378fc32ae401397?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/221a26d0593f7c89c378fc32ae401397?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://forrest-tanaka.com' rel='external nofollow' class='url'>Forrest Tanaka</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-408"><time datetime="2012-12-28T22:38:47+00:00" pubdate class="published">
		 at <span class="hours">22:38pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Nested media queries just about brought me to tears… Hey, you have `$unit = 10;` That should be `$unit: 10`? I couldn’t find anything in Sass nor SCSS that looks quite like that.
	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-409">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/476f698fd710deaab3b0c3c8b0623c21?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/476f698fd710deaab3b0c3c8b0623c21?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">John Harrington</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-409"><time datetime="2012-12-28T22:45:14+00:00" pubdate class="published">
		 at <span class="hours">22:45pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		<p>Nice article, but I don’t like that use of mixins very much, that style is just being duplicated everywhere and I really think you’d be better with a class for it, to reduce the bloat in CSS.

Mixins are best used when you need to calculate things, for instance I use this little mixin to quickly set font sizes and line heights:

```

=fontsize($size)

	font-size: $size + em

	@if ($size &gt;= 2)

		line-height: 1.5em

		@media screen and (min-width: 30em)

			line-height: 3em

	@else

		line-height: 1.5em

```

(also, I use the Sass syntax, rather than SCSS, because I love the whitespace)
	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-410">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/476f698fd710deaab3b0c3c8b0623c21?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/476f698fd710deaab3b0c3c8b0623c21?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">John Harrington</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-410"><time datetime="2012-12-28T23:33:51+00:00" pubdate class="published">
		 at <span class="hours">23:33pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		For mixins you would actually be better off doing the example where the CSS was badly organised because Sass won’t recognise that the same styles are being applied on each, so your CSS will end up bloated.
	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-411">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/830ba17ff6c951f84f7b97084133b163?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/830ba17ff6c951f84f7b97084133b163?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://yatil.net' rel='external nofollow' class='url'>Eric Eggert</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-411"><time datetime="2012-12-29T00:56:34+00:00" pubdate class="published">
		 at <span class="hours">00:56am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Funny enough, it was this article by Nathan Smith with the same name as this article here that convinced me about using SASS in the first place: [http://sonspring.com/journal/sass-for-designers](http://sonspring.com/journal/sass-for-designers" rel="nofollow)

(And I have a programming background :-)
	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-412">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/ec8560921f8715605bfa731058c012a7?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/ec8560921f8715605bfa731058c012a7?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://thomaspark.me' rel='external nofollow' class='url'>Thomas Park</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-412"><time datetime="2012-12-29T21:43:56+00:00" pubdate class="published">
		 at <span class="hours">21:43pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		A useful complement to `@include` is `@extend`. While `@include` duplicates the mixin rules for each class, `@extend` has the classes share a single instance of the rules. This helps with the CSS bloat that John mentions.
	</div>
</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-413">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/ec8560921f8715605bfa731058c012a7?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/ec8560921f8715605bfa731058c012a7?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://thomaspark.me' rel='external nofollow' class='url'>Thomas Park</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-413"><time datetime="2012-12-30T17:44:53+00:00" pubdate class="published">
		 at <span class="hours">17:44pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		A useful complement to `@include` is `@extend`. While `@include` duplicates the rules for each class, `@extend` causes them to share the rules they have in common. Helps with the CSS bloat.
	</div>
</li>
	<li class="comment even thread-even depth-1" id="li-comment-415">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/f09e13b2647166e6d0c5bd4722b0ba71?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/f09e13b2647166e6d0c5bd4722b0ba71?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">dtgreen</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-415"><time datetime="2013-01-11T00:10:46+00:00" pubdate class="published">
		 at <span class="hours">00:10am</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Brilliant read Laura. I’ve been trying to find the time to jump into SASS lately, and this article has pretty much made up my mind: I’m going to dive in this weekend! :)
	</div>
</li>
</ol>
