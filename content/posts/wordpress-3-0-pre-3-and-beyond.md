---
title: "WordPress 3.0 Part 1—Pre 3.0 and Beyond"
draft: true
colours: ["#dc7a1e", "#216F94", "#F7F7F7", "#D54E21", "#D7D7D7", "#B4411B", "#525252"]
date: 2010-07-16T21:49:42+00:00
categories: ["WordPress"]
tags: ["custom taxonomies", "featured images", "post thumbnails", "wordpress", "wordpress 2.8", "wordpress 2.9", "wordpress 3.0"]
body_classes: "blog"
---

This post has three parts. This is part one. Visit the other parts below:

* Part 2: [WordPress 3.0—Really WordPress 3.0](/wordpress-3-0-really-wordpress-3)
* Part 3: [WordPress 3.0—Theme Development and the Design](/wordpress-3-0-theme-development-and-the-design)

---

I’m a big fat WordPress fan. I love the [people behind it](http://automattic.com/ "Automattic, the people behind WordPress"), I love [the ethics](http://www.google.com/hostednews/afp/article/ALeqM5igVn4hcj6ZNWlawSvzLvgEMkZmkQ "AFP News--Blogging guru chips away at Great Firewall of China")and I love how it makes it easy for me to make cool sites that my clients can update themselves.

Not really being much of a PHP developer, I can still get by and can make fairly capable themes from-scratch for my clients. However, it was getting to the point where I couldn’t offer clients an easy way to input content that wasn’t a standard page or a standard blog post without getting a bit hacky with posts, categories and tags.

These solutions were OK, but really far too much of a workaround for clients who were only fairly basic computer users in the first.

Then along came the wondrous…

## WordPress 3.0

Actually, it started a bit before that with WordPress 2.9 with the infinitely useful post thumbnails.

### Featured Images

But I’ll carry on by calling ‘post thumbnails’ by their new name, ‘featured images’, as this is what they’ve become known as since WordPress 3.0.

Featured images were a selling point in many magazine-style themes for a long time. The ability to have an image that was a visual representation of a post was incredibly sought-after, especially if those images could also be shown in some kind of javascript carousel that rotated the images on the front page of the site. As a result, a huge amount of post-image carousel-type themes exist using all kinds of hacky ways to select a post’s image as the ‘featured’ one.

I used the excellent [Get The Image plugin](http://wordpress.org/extend/plugins/get-the-image/faq/ "Get The Image plugin in the WordPress plugin repository") by (the equally excellent) [Justin Tadlock](http://justintadlock.com/) when I wanted to use a featured image in a theme. Get The Image cycled through images linked to your post through custom fields, then through the attachments to the post, and even setting a default image, making it really easy to implement featured images in a way that all clients could understand. I still would recommend Get The Image if you want to pick images straight from your posts, rather than setting a specific featured image.

However, setting a specific featured image couldn’t be easier, and I see very few occasions where it wouldn’t be perfect for the job.

First, you’ll need to enable featured images in your functions.php file. This prevents a ‘Featured Image’ box appearing in themes which don’t support the use of featured images (which could cause a lot of confusion for users.) All this requires is a little:

<pre>add_theme_support( 'post-thumbnails' );</pre>
Then you can see the Featured Image box appear in your post and page editors.

[{{<figure class="wp-caption aligncenter size-full wp-image-121" title="Featured Image box in the Post editor" src="/images/2010/07/Screen-shot-2010-07-16-at-20.31.56.png" alt="Featured Image box in the WordPress Post editor" width="299" height="82" caption="Featured Image box in the Post editor">}}](/images/2010/07/Screen-shot-2010-07-16-at-20.31.56.png)

The image selection process is identical to that of adding standard images into the post. You can choose to select from your computer, from a URL or from the Media Library. All you need to make sure is that, instead of hitting the ‘Insert into Post’ button, you select ‘Use as featured image’.

[{{<figure class="wp-caption aligncenter size-full wp-image-123" title="Ensure you select 'Use as featured image'" src="/images/2010/07/Screen-shot-2010-07-16-at-20.33.23.png" alt="When adding a featured image to a WordPress post, ensure you select 'Use as featured image' when selecting an image" width="645" height="256" caption="Ensure you select ‘Use as featured image’">}}](/images/2010/07/Screen-shot-2010-07-16-at-20.33.23.png)

If you only want to allow Featured Images for posts in your theme, you can specify this through:

<pre>add_theme_support( 'post-thumbnails', array( 'post' ) );</pre>
Or for just pages:

<pre>add_theme_support( 'post-thumbnails', array( 'page' ) );</pre>
Then when it comes to including the Featured Image in your theme, you’ll just need to include:

<pre>&lt;?php the_post_thumbnail(); ?&gt;</pre>
Really nice and simple!

Even better, you can have more fine-grained control over the sizes of the images, and have different types of image sizes through a few more lines in your functions.php file:

<pre>set_post_thumbnail_size( 100, 100, true );
// Set the standard size for your featured images</pre>
<pre>add_image_size( 'magazine-column-image', 400, 300 );
//Specify a custom image size, you can do this as many
times as you want</pre>
This is great if you want to output small thumbnail images on your homepage template and large feature images on your article pages.

For more depth on featured images I recommend you read Mark Jaquith’s pro writeup [New in WordPress 2.9: Post Thumbnail images](http://markjaquith.wordpress.com/2009/12/23/new-in-wordpress-2-9-post-thumbnail-images/).

### Custom Taxonomies

As early as WordPress 2.8 also came custom taxonomies, a sneak peek into something beyond bloggy categories and bloggy tags. For those who blog on specialist subjects you can do without categories and have different hierarchical taxonomies (category trees to people like me), such as ‘genres’ for your film reviews.

If you wanted to tag your film reviews with different actors names, but still keep standard tags to describe your review, you can do this. If you still wanted to organise your fashion blog by different types of articles, using categories, but also wanted to choose from a list of  items of clothes to describe your article, you can do this as well.

These are a bit trickier to implement than post thumbnails. Not much, but there’s a bit more to explain in the functions.php file, so if you want to know more I’d recommend that you visit one (or all) of the fantastic resources that I use, below:

1.[Custom Taxonomies on the WordPress Codex](http://codex.wordpress.org/Custom_Taxonomies)
2. [Custom Taxonomies in WordPress 2.8 by Justin Tadlock](http://justintadlock.com/archives/2009/05/06/custom-taxonomies-in-wordpress-28)
3. [Creating a page template that lists all your custom taxonomies by Justin Tadlock](http://justintadlock.com/archives/2009/05/02/creating-a-page-template-that-lists-all-of-your-wordpress-taxonomies)
4. [Introducing WordPress 3 Custom Taxonomies on NetTuts](http://net.tutsplus.com/tutorials/wordpress/introducing-wordpress-3-custom-taxonomies/)

---

This post has three parts. This is part one. Visit the other parts below:

* Part 2: [WordPress 3.0—Really WordPress 3.0](/wordpress-3-0-really-wordpress-3)
* Part 3: [WordPress 3.0—Theme Development and the Design](/wordpress-3-0-theme-development-and-the-design)

## 2 comments

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-8">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">bookmeister</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-8"><time datetime="2010-07-16T21:13:07+00:00" pubdate class="published">
		 at <span class="hours">21:13pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		@laurakalbag good effort on the wordpress blog posts. You could write a book :-)
	</div>
	<ul class="children">
		<li class="comment odd alt depth-2" id="li-comment-9">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://twitoaster.com/laurakalbag/' rel='external nofollow' class='url'>laurakalbag</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-9"><time datetime="2010-07-16T21:17:26+00:00" pubdate class="published">
		 at <span class="hours">21:17pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		@bookmeister thanks but barely! You see how much the language plugin shouts at me. Apparently I can barely string a sentence together ;)
		</div>
	</li>
</ol>
