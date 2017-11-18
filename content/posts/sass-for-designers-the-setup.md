---
title: "Sass for Designers — The Setup"
draft: true
colours: ["#b047b6", "#404040", "#bb1e88", "#783b7b", "#d39ed6", "#652a5e", "#d7d7d7"]
date: 2012-12-28T17:51:36+00:00
categories: ["Markup"]
tags: ["Codekit", "CSS", "preprocessors", "Sass"]
---

{{< oldpost >}}

As an accompaniment to my post on [Sass for Designers](http://laurakalbag.wpengine.com/sass-for-designers/ "Sass for Designers") (why and how you should use Sass) I thought I’d better include a quick writeup on my setup for working with Sass in the hope that it’ll help you get started. I’m afraid I work on a OS X, so my instructions will only be good for Macs.

Of course, all of this can be done with the command line and other terrifying tools. I’m very impressed by those who can remember all the commands and quickly get everything working silently in the background. I don’t find this very easy, and prefer to use apps to help me out.

## Codekit

[Codekit](http://incident57.com/codekit/) does all the processing for you. It takes your Sass and spits it out into fully-working CSS. It does loads of other clever things too, but I mostly just use it for Sass. [Go download it](http://incident57.com/codekit/) and give it a go. I think you’ll find it’s definitely worth paying for.

[{{< figure class="aligncenter size-full wp-image-1417" alt="screenshot of the Codekit website" src="/images/2012/12/codekit.png" width="921" height="658" >}}](http://incident57.com/codekit/)

In order to get started with Codekit and Sass, you’ll need a /sass folder in your project where you keep all your Sass files. Sass files can contain plain old CSS or Sass-style CSS but they must have the extension .scss.

[{{< figure class="aligncenter size-full wp-image-1425" alt="screenshot showing .scss file in the /sass folder" src="/images/2012/12/sass-folder.png" width="850" height="385" >}}](/images/2012/12/sass-folder.png)

Next you open Codekit and add your project folder in the Files section.

[{{< figure class="aligncenter size-full wp-image-1433" alt="screenshot of adding a new project to the Files pane in Codekit" src="/images/2012/12/codekit-new1.png" width="500" height="635" >}}](/images/2012/12/codekit-new1.png)

After you’ve added your project folder, Codekit will automatically find the Sass file inside your project.

[{{< figure class="aligncenter size-full wp-image-1437" alt="screenshot of a project in Codekit" src="/images/2012/12/project-in-codekit.png" width="900" height="605" >}}](/images/2012/12/project-in-codekit.png)

If you then go into your .scss file and add some Sass, as soon as you save that file, Codekit will compile it into CSS for you.

[{{< figure class="aligncenter size-full wp-image-1441" alt="screenshot of basic Sass being written into a .scss file" src="/images/2012/12/new-sass.png" width="510" height="360" >}}](/images/2012/12/new-sass.png)

If you go to the Log tab in Codekit, you can see that your Sass was successfully compiled into CSS.

[{{< figure class="aligncenter size-full wp-image-1449" alt="screenshot of the Log in Codekit showing a file successfully compiled" src="/images/2012/12/codekit-log1.png" width="900" height="245" >}}](/images/2012/12/codekit-log1.png)

If you then go back to look in your project folder, you can see where Codekit has compiled your CSS into a /css folder containing a .css file. It’s this file that you will reference in your HTML, not the .scss file.

[{{< figure class="aligncenter size-full wp-image-1453" alt="screenshot showing the /css folder created by Codekit" src="/images/2012/12/css-folder.png" width="530" height="350" >}}](/images/2012/12/css-folder.png)

Codekit is very smart. If you write invalid Sass, it will give you an error. This can be really helpful if you’re new to writing Sass. For example, here I’ve used a `#` hash symbol instead of a `$` dollar sign when creating a variable.

[{{< figure class="aligncenter size-full wp-image-1457" alt="screenshot of invalid Sass using # instead of $" src="/images/2012/12/bad-sass.png" width="530" height="370" >}}](/images/2012/12/bad-sass.png)

As with all validators, it’s not always easy to understand what the validation error message means (!) but it can be helpful to be pointed towards the line where the error occurs.

[{{< figure class="aligncenter size-full wp-image-1461" alt="screenshot of Codekit showing an error in the Sass" src="/images/2012/12/codekit-error.png" width="900" height="310" >}}](/images/2012/12/codekit-error.png)

## And you’re done

Those are the very basics you need when getting started with Sass. If anyone has any further suggestions for Sass tools, particularly on other OSes, please let me know!

## One comment

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-426">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/30237178832faefa2a7e79998d46648d?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/30237178832faefa2a7e79998d46648d?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">Dave Rutter</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-426"><time datetime="2013-01-07T22:33:09+00:00" pubdate class="published">
		 at <span class="hours">22:33pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		Hi Laura

You may have seen this already since writing this post but Hammer app looks very interesting ([http://hammerformac.com/](http://hammerformac.com/" rel="nofollow)). OSX only again I’m afraid. The in development mixture.io may also be of interest, especially for multi-device testing.

I’ve just come across your site and really enjoyed digging around. Keep up the good work.
	</div>
</li>
</ol>
