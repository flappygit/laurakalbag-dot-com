---
title: "WordPress 3.0 Part 2—Really WordPress 3.0"
draft: true
colours: ["#dc7a1e", "#216F94", "#F7F7F7", "#D54E21", "#D7D7D7", "#B4411B", "#525252"]
date: 2010-07-16T21:50:50+00:00
categories: ["WordPress"]
tags: ["custom post types", "template parts", "wordpress", "wordpress 3.0", "wordpress loop", "wordpress templates"]
---

This post has three parts. This is part two. Visit the other parts below:

* Part 1: [WordPress 3.0—Pre 3.0 and Beyond](/wordpress-3-0-pre-3-and-beyond)
* Part 3: [WordPress 3.0—Theme Development and the Design](/wordpress-3-0-theme-development-and-the-design)

---

## Really WordPress 3.0

### Custom Post Types

Custom Post Types are my new best friends. I have used new post types on every client project since the beta of WordPress 3.0. That’s how valuable I think they are.

For any content that you need to act like a post, but not *actually* **be** a post, custom post types are there for you. If you already have a news section that uses posts, but also want an articles section separate from your posts, custom post types are what you need.

One of my latest site designs, stuartclayton.com, I used no fewer than four different custom post types:

[{{<figure class="wp-caption aligncenter size-full wp-image-124 " title="Custom post types in the WordPress admin" src="/images/2010/07/Screen-shot-2010-07-16-at-20.36.02.png" alt="Custom post types in the WordPress admin" width="164" height="366" caption="Custom post types menus in use in the WordPress admin">}}](/images/2010/07/Screen-shot-2010-07-16-at-20.36.02.png)

1. #### Discography

It’s pretty self-explanatory, I used the custom post types to list a new CD in each post.

2. #### Books

Each one of Stuart’s books has its own post in the ‘Books’ post type.

3. #### Features

This is a bit less obvious. In the sidebar or footer on every page is a feature that shows a latest book, video or audio track.

For this I used a custom post type of ‘Feature’ with a featured image to show the image and using the title and text content (even though it’s very little text) as standard. The ‘Buy Now’ button is created by entering a URL and button text into a [custom write panel](http://www.deluxeblogtips.com/2010/04/how-to-create-meta-box-wordpress-post.html) (also known as [meta boxes](http://codex.wordpress.org/Function_Reference/add_meta_box).)

4. #### Gear

The gear is pretty special as I made use of a ‘Gear’ custom post type with a ‘Type of gear’ custom taxonomy. You certainly couldn’t do that a few versions ago!

[{{<figure class="wp-caption aligncenter size-full wp-image-125" title="Types of gear custom taxonomy panel" src="/images/2010/07/Screen-shot-2010-07-16-at-20.37.20.png" alt="Types of gear custom taxonomy panel in the WordPress editor" width="296" height="331" caption="Types of gear custom taxonomy panel">}}](/images/2010/07/Screen-shot-2010-07-16-at-20.37.20.png)

Each item of musical gear that Stuart has is (or will be) listed under the ‘Gear’ section. Then to group the different gear by whether it’s a bass, an amp, strings or effects, a category-style custom taxonomy is used. This helps dictate how the pages are laid out.

I struggled a bit with custom post types at first. I think it It was probably because the developers hadn’t quite ironed out all the quirks and I was too keen on trying out everything during the beta. I could create custom post types that showed up in the admin with no problem, but had issues with choosing which features showed in the editors.

If you, like me, get a bit confused with the huge amount of options for custom post types in the functions.php file, I really would recommend you give [Custom Post Type UI](http://wordpress.org/extend/plugins/custom-post-type-ui/?compatibility%5Bversion%5D=3.0&amp;compatibility%5Btopic_version%5D=0.5.2&amp;compatibility%5Bcompatible%5D=1) by [WebDevStudios](http://webdevstudios.com/) a go. This excellent plugin does just what you would do in your functions.php file but gives it a friendly checkbox and text input interface in your WordPress admin so you needn’t write any code.

[{{<figure class="wp-caption aligncenter size-large wp-image-126" title="Custom Post Types UI in action" src="/images/2010/07/Screen-shot-2010-07-16-at-19.27.32-960x433.png" alt="Custom Post Types UI in action" width="640" height="288" caption="Custom Post Types UI in action">}}](/images/2010/07/Screen-shot-2010-07-16-at-19.27.32.png)

For those that more confident, these are the best resources I’ve found on creating custom post types straight into your themes (or plugins):

* [Custom Post Types in WordPress by Justin Tadlock](http://justintadlock.com/archives/2010/04/29/custom-post-types-in-wordpress) (I know, I’m a fan!)
* [Custom Post Types on the WordPress Codex](http://codex.wordpress.org/Custom_Post_Types)
* [How to add a custom icon to your custom post type by Ptah Dunbar](http://wpdevel.wordpress.com/2010/04/03/how-to-add-a-custom-icon-to-your-custom-post-type/)

### loop.php and other Template Parts

A change in WordPress 3.0 that I’m a bit confused about is the template parts, which separates the WordPress loop into its own file, loop.php. It is certainly not necessary to do this in order to make your WordPress theme work, and the idea behind doing this is that you can now easily separate repeatable parts of your templates into different files and call them when you need them, thus preventing you repeating yourself many times in one file and needing to edit the same repeated line of code multiple times just because you want to change a few characters.

However, the implementation of this in the new default TwentyTen theme seems to contradict this non-repetitive, breaking up into digestible chunks, sensibility. Apologies for the huge amount of code that follows:

```
<pre class="brush:php">can be overridden in child themes with loop.php or
 * loop-template.php, where 'template' is the loop context
 * requested by a template. For example, loop-index.php would
 * be used if it exists and we ask for the loop with:
 * <code>get_template_part( 'loop', 'index' );</code>*
 * @package WordPress
 * @subpackage Twenty_Ten
 * @since Twenty Ten 1.0
 */
?&gt;

max_num_pages &gt; 1 ) : ?&gt;</pre>
<div id="nav-above" class="navigation">
<div class="nav-previous">← Older posts’, ‘twentyten’ ) ); ?&gt;</div>
<div class="nav-next">→’, ‘twentyten’ ) ); ?&gt;</div>
</div>
<pre class="brush:php">
<div id="post-0" class="post error404 not-found">
<pre class="brush:php">
<div id="post-&lt;?php the_ID(); ?&gt;">&gt;</p>
<h2 class="entry-title"></h2>
<p>


<div class="gallery-thumb">$post-&gt;ID, ‘post_type’ =&gt; ‘attachment’, ‘post_mime_type’ =&gt; ‘image’, ‘orderby’ =&gt; ‘menu_order’, ‘order’ =&gt; ‘ASC’, ‘numberposts’ =&gt; 999 ) ); $total_images = count( $images ); $image = array_shift( $images ); $image_img_tag = wp_get_attachment_image( $image-&gt;ID, ‘thumbnail’ ); ?&gt;</div>
<p>
<p>
<div class="entry-utility"><span class="meta-sep">|</span> <span class="comments-link"> </span> | <span class="edit-link">‘, ‘</span>‘ ); ?&gt;</div>
<p>
<pre class="brush:php">
<div id="post-&lt;?php the_ID(); ?&gt;">&gt; 

→’, ‘twentyten’ ) ); ?&gt;</div>
<p>
<div class="entry-utility"><span class="meta-sep">|</span> <span class="comments-link"> </span> | <span class="edit-link">‘, ‘</span>‘ ); ?&gt;</div>
<p>
<pre class="brush:php">
<div id="post-&lt;?php the_ID(); ?&gt;">&gt;</p>
<h2 class="entry-title"></h2>
<p>

→’, ‘twentyten’ ) ); ?&gt; ‘</p>
<div class="page-link">‘ . __( ‘Pages:’, ‘twentyten’ ), ‘after’ =&gt; ‘</div>
‘ ) ); ?&gt;
</div>
<p>
<div class="entry-utility"><span class="cat-links"> Posted in</span> %2$s’, ‘twentyten’ ), ‘entry-utility-prep entry-utility-prep-cat-links’, get_the_category_list( ‘, ‘ ) ); ?&gt; <span class="meta-sep">|</span> <span class="tag-links"> Tagged</span> %2$s’, ‘twentyten’ ), ‘entry-utility-prep entry-utility-prep-tag-links’, $tags_list ); ?&gt; <span class="meta-sep">|</span> <span class="comments-link"> </span> | <span class="edit-link">‘, ‘</span>‘ ); ?&gt;</div>
<p>
<pre class="brush:php">
<div id="nav-below" class="navigation">
<div class="nav-previous">← Older posts’, ‘twentyten’ ) ); ?&gt;</div>
<div class="nav-next">→’, ‘twentyten’ ) ); ?&gt;</div>
</div>
<pre class="brush:php">```

If you wade through the code above, you might notice that the loop is cycling through special displays for a gallery category, an asides category, the archives and search, and then all other posts.

This seems utterly bizarre to me. Why, in an exercise that is aimed at splitting the code into manageable chunks are they lumping all of these different outputs into one new file? According to the [Template Hierarchy](http://codex.wordpress.org/Template_Hierarchy#Category_display), you could have separate template files for

* a category named ‘gallery’ (category-gallery.php)
* a category named ‘asides’ (category-asides.php)
* an archive page (archive.php)
* and search results (search.php.)

Leaving all other posts happily served by index.php. This would keep your templates separate and easy to read as well as stopping WordPress having to cycle through all of those conditional options by just hitting the relevant template first.

As I’ve said before, I’m no PHP developer, but if somebody could explain the logic of this particular loop.php file to me, it’d make me feel a lot happier!

---

This post has three parts. This is part two. Visit the other parts below:

* Part 1: [WordPress 3.0—Pre 3.0 and Beyond](/wordpress-3-0-pre-3-and-beyond)
* Part 3: [WordPress 3.0—Theme Development and the Design](/wordpress-3-0-theme-development-and-the-design)

## 6 comments

<ol class="commentlist">
	<li class="comment even thread-even depth-1" id="li-comment-19">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">benmckenna</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-19"><time datetime="2010-07-16T21:02:38+00:00" pubdate class="published">
		 at <span class="hours">21:02pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		@laurakalbag 3 is great isn’t it? First real play this week and it’s so much less hacky it’s unreal. Now for the arduous client upgrades :-/
	</div>
	<ul class="children">
		<li class="comment odd alt depth-2" id="li-comment-20">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://twitoaster.com/laurakalbag/' rel='external nofollow' class='url'>laurakalbag</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-20"><time datetime="2010-07-16T21:09:38+00:00" pubdate class="published">
		 at <span class="hours">21:09pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		@benmckenna it’s really cool. Shouldn’t be too troublesome with auto-upgrades and backwards compatibility.
	</div>
	<ul class="children">
		<li class="comment even depth-3" id="li-comment-21">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">benmckenna</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-21"><time datetime="2010-07-16T21:11:09+00:00" pubdate class="published">
		 at <span class="hours">21:11pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		@laurakalbag yep, just trying to leave a sensible period for plug-ins. I went a bit plug-in crazy one one in particular
		</div>

		



</li>
	<li class="comment odd alt thread-odd thread-alt depth-1" id="li-comment-22">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">nevillestclair</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-22"><time datetime="2010-07-16T21:08:04+00:00" pubdate class="published">
		 at <span class="hours">21:08pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		@laurakalbag Nice little précis of 3.0 stuff there. Ta for that. &lt;3 custom posts.
	</div>
	<ul class="children">
		<li class="comment even depth-2" id="li-comment-23">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn"><a href='http://twitoaster.com/laurakalbag/' rel='external nofollow' class='url'>laurakalbag</a></cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-23"><time datetime="2010-07-16T21:10:33+00:00" pubdate class="published">
		 at <span class="hours">21:10pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		@nevillestclair ooh, posh words. Thanks :) Custom posts are &lt;3 &lt;3 &lt;3
	</div>
	<ul class="children">
		<li class="comment odd alt depth-3" id="li-comment-24">
			<div class="comment-author vcard">
			<img alt='' src='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=72&amp;d=mm&amp;r=g' srcset='https://secure.gravatar.com/avatar/d281a23b55db2b3d1d6b0be43791bf6b?s=144&amp;d=mm&amp;r=g 2x' class='avatar avatar-72 photo' height='72' width='72' />
### <cite class="fn">nevillestclair</cite>
		</div>
		<aside class="comment-meta commentmetadata"><p><a href="#comment-24"><time datetime="2010-07-16T21:16:12+00:00" pubdate class="published">
		 at <span class="hours">21:16pm</span></time></a></p>
	</aside>
	<div class="comment-entry">
		@laurakalbag Any excuse to do diacritical marks on letters :p
		</div>

		



</li>
</ol>
