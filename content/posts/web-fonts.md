---
title: "Web Fonts"
draft: false
colours: ["#3276D5", "#2095C3", "#7EBEEA", "#2b5794", "#bee2fb", "#264571", "#20afc3"]
date: 2010-07-02T18:12:16+00:00
categories: ["Design"]
tags: ["@font-face", "CSS", "Font Squirrel", "fonts", "Fonts.com", "Fontshop", "Google Web Fonts", "typekit"]
body_classes: "blog"
---

I’ve got a new infatuation; web fonts. Since the second I heard about [Typekit](http://typekit.com) (and [Fontdeck](http://fontdeck.com/)) last year I’ve been giddy with excitement about being able to use more fonts on the web. [Georgia](http://en.wikipedia.org/wiki/Georgia_font "Georgia on Wikipedia") just doesn’t cut it anymore. Even the introduction of ten new fonts to shake things up would have me flustered. Here’s a brief look at my experience of web fonts over the last year or so.

## @font-face and Font Squirrel

Before Typekit, the situation around the [CSS @font-face declaration](http://www.alistapart.com/articles/cssatten/) started getting more attention. There was good support across all major browsers (and some of the oldies like Internet Explorers 6 &amp; 7) for this cunning little declaration that allowed you to embed any font into your website. @font-face displayed fonts like we needed, displaying as real selectable text that remains accessible and index-able by search engines.

Despite being far easier to use, and more reliable, than the truly hideous (though handy at the time) Flash text-replacement methods like [sIFR](http://wiki.novemberborn.net/sifr3/) and [Cufón](http://cufon.shoqolate.com/generate/), @font-face is a bit of a pain to implement. The CSS declarations themselves are fairly simple, but the amount of different font formats you need to include is pretty insane. You need to include .eot, .woff, .ttf and .svg formats of each font face. Not to mention that there’s no piracy protection on these font faces so, not only do you have to find all those different font formats, but you had to make sure you had the rights to distribute them as well (’cause everybody knows that piracy is mean.)

Then came along [Font Squirrel](http://www.fontsquirrel.com/).

[{{<figure class="wp-caption aligncenter size-full wp-image-75 " title="Quicksand font at Font Squirrel" src="/images/2010/07/Screen-shot-2010-07-02-at-21.31.14.png" alt="Quicksand font at Font Squirrel" width="627" height="331" caption="Quicksand font at Font Squirrel">}}](/images/2010/07/Screen-shot-2010-07-02-at-21.31.14.png)

A wickedly cool site that shows you a huge array of fonts that are licensed for @font-face use, complete with @font-face kits containing the fonts, the license, a demo HTML file and the CSS you need to implement great-looking web fonts using @font-face.

[{{<figure class="wp-caption aligncenter size-full wp-image-76 " title="Font Squirrel @font-face kit download" src="/images/2010/07/Screen-shot-2010-07-02-at-21.32.52.png" alt="Font Squirrel @font-face kit download" width="572" height="276" caption="Font Squirrel @font-face kit download">}}](/images/2010/07/Screen-shot-2010-07-02-at-21.32.52.png)

[{{<figure class="wp-caption aligncenter size-full wp-image-77" title="All the files in the Font Squirrel @font-face kit" src="/images/2010/07/Screen-shot-2010-07-02-at-21.37.41.png" alt="All the files in the Font Squirrel @font-face kit" width="513" height="681" caption="All the files in the Font Squirrel @font-face kit">}}](/images/2010/07/Screen-shot-2010-07-02-at-21.37.41.png)

All you need to do is copy all the font files on to your site, and copy the CSS into your stylesheet:

```@font-face {

font-family: 'QuicksandBook';

src: url('Quicksand_Book-webfont.eot');

src: local('☺'), url('Quicksand_Book-webfont.woff') format('woff'), url('Quicksand_Book-webfont.ttf') format('truetype'), url('Quicksand_Book-webfont.svg#webfontozh2o7Cr') format('svg');

font-weight: normal;

font-style: normal;

}```

and put the font into your font-family font stack:

```h1 { font-family: 'QuicksandBook', Helvetica, Arial, sans-serif; }```

## Typekit

Font Squirrel was great but as most of the fonts are free, a large amount of the fonts are lacking a bit in quality. They just lack the care and attention a font gets from a very skilled type designer.

And that’s where Typekit makes things awesome.

I rarely buy fonts. I try to get away with system fonts, or free fonts, *a lot* of the time. As I mostly work on the web, it never made sense to use fonts that weren’t web-safe. I’d only indulge in paid fonts (and still pretty cheap ones) when I was doing logo or print design. I would have loved to use the beautiful, unusual and quality fonts from proper font foundries. I subscribed to [FontShop](http://www.fontshop.com/)‘s newsletters just so I could gaze longingly at the fonts that felt too good for me.

[{{<figure class="wp-caption aligncenter size-full wp-image-78" title="One of FontShop's lovely e-mail newsletters" src="/images/2010/07/Screen-shot-2010-07-02-at-21.43.02.png" alt="One of FontShop's lovely e-mail newsletters" width="629" height="522" caption="One of FontShop’s lovely e-mail newsletters">}}](/images/2010/07/Screen-shot-2010-07-02-at-21.43.02.png)

Typekit brings those to-die-for fonts from top quality foundries to the web with a teensy bit of javascript. Typekit showcases [some of the most stunning fonts](http://typekit.com/foundries/veer) I’ve ever seen and allows you to use them on your site in a way that is quick and easy, but still preserves the licensing and distribution control that the foundries and font designers need to keep them going.

[{{<figure class="wp-caption aligncenter size-full wp-image-79 " title="Proper nice fonts from Typekit" src="/images/2010/07/Screen-shot-2010-07-02-at-21.46.36.png" alt="Proper nice fonts from Typekit" width="708" height="338" caption="Proper nice fonts from Typekit">}}](/images/2010/07/Screen-shot-2010-07-02-at-21.46.36.png)

Since Typekit has launched, they have added loads more fonts, and they just keep getting better. The libraries are easy to browse, using tags and your own text samples, and you can even view browser samples of each font so you can see how bad it’s going to look in Windows’ browsers ;)

[{{<figure class="wp-caption aligncenter size-full wp-image-80 " title="Typekit preview of Atrament Web on Windows XP Internet Explorer 6" src="/images/2010/07/Screen-shot-2010-07-02-at-21.50.10.png" alt="Typekit preview of Atrament Web on Windows XP Internet Explorer 6" width="678" height="234" caption="Typekit preview of Atrament Web on Windows XP Internet Explorer 6">}}](/images/2010/07/Screen-shot-2010-07-02-at-21.50.10.png)

I use Typekit on my personal site, and this blog, and an increasing amount of client sites. The only downside is that, because the fonts are only licensed for the web, you can’t use them in Photoshop mockups or logo designs unless you buy the correct licensed version. However, if you’re like me, and trying to design in-browser more often, it’s absolutely perfect from start to finish.

## Google Web Fonts, Fontdeck and Fonts.com

There are other services around offering the same kind of solution as Typekit. One is [Google Web Fonts](http://code.google.com/webfonts), [who are working in collaboration](http://blog.typekit.com/2010/05/19/typekit-and-google/ "Typekit and Google Announce Open Source Collaboration") with Typekit, and another is Fontdeck. I haven’t got an invite to Fontdeck yet, so I reckon that one will remain a mystery for a while longer, and I took a quick look at Google Web Fonts, which only serves open source fonts, and it looks pretty similar to Typekit but only has a limited amount of fonts at the moment.

[{{<figure class="wp-caption aligncenter size-full wp-image-81 " title="Google Font Directory" src="/images/2010/07/Screen-shot-2010-07-02-at-21.55.27.png" alt="Google Font Directory" width="579" height="347" caption="Google Font Directory">}}](/images/2010/07/Screen-shot-2010-07-02-at-21.55.27.png)

I had a quick go on [Fonts.com web fonts](http://webfonts.fonts.com/), and whilst the site design is a bit much, the service seems reasonable. It was a very straight-forward process picking and publishing the font I’d chosen to a site. However, the rendering of the font (Century Gothic) looked awful on Windows, despite being a system font that usually looked pretty decent. I’m not assuming that this is the situation with all fonts on Fonts.com, but not being able to preview it cross-browser at a glance seems like a disadvantage after the excellent previews on Typekit.

[{{<figure class="wp-caption aligncenter size-large wp-image-82" title="Fonts.com Web Fonts using about a million fonts" src="/images/2010/07/Screen-shot-2010-07-02-at-21.57.05-960x459.png" alt="Fonts.com Web Fonts using about a million fonts" width="640" height="306" caption="Fonts.com Web Fonts using about a million fonts">}}](/images/2010/07/Screen-shot-2010-07-02-at-21.57.05.png)

Overall, my preferred web font solution is definitely Typekit. The exciting thing is that new solutions keep popping up all time, so I’m sure the best is yet to come. For now, I have to do a complicated mix of Typekit, @font-face and standard system fonts to cover all bases so I’m really looking forward to the day we have a robust solution that does it all for me!
