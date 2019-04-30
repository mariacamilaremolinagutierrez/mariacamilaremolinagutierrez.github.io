---
layout: post
section-type: post
title: Website Info and Setup
category: website
tags: [ 'tutorial' ]
---

## Config.yml

All features of { Personal } are controlled by setting values to variables that are defined in the
\_config.yml file. 

### Essential variables

<pre><code data-trim class="yaml">
# NB! Set your site's url, otherwise stuff will break :)

url: "https://mariacamilarg.github.io"

# If you're hosting your site at a Project repository on GitHub pages
# (https://yourusername.github.io/repository-name)
# and NOT your user repository (https://yourusername.github.io)
# then add in the baseurl here, like this: "/repository-name"
#
# NB! Without this *nothing* will work, because it's used in every path :)

baseurl: /personal-jekyll-theme
</code></pre>

The url and baseurl variables are essential, because they are used *everywhere* where an anchor is defined!

### Coloring

You can define the colors that you want in your { Personal } website by setting
the following variable sin the /_sass/_variables.scss file:

<pre><code data-trim class="scss">
// Main color
$primary-color: #000;

// Anchor color
$secondary-color: #00cdff;

// Font color
$font-color: #fff;
</code></pre>

### HTTPS

By default { Personal } will enforce https by javascript redirection.
HTTPS is important because it encrypts the data sent between the client and the server.
If you are hosting on GitHub Pages then it will just work, because your website
will be piggybacking GitHub's certificate.
If you are hosting your website in a server that doesn't have a certificate and
you don't want to issue one, then you can disable this feature by setting the following
variable to False:

<pre><code data-trim class="yaml">
force-https: True
</code></pre>

### HTML Head

<pre><code data-trim class="yaml">
lang: "en"
author: "John Smith"
title: "{ John Smith }"
description: "Blog and website of John Smith, blogging mainly for tech. Opinions expressed are mine."
keywords: "smith, jones, personal, jekyll, theme"
favicon: "/img/favicon.ico"
err-404-img: "/img/author.png"
</code></pre>

The values that you set, will be placed in the head section of every generated HTML page.

### Google Analytics

The Google tracking code will be placed in every generated page.
If you don't want Google analytics tracking your website's traffic, set the google-tracking-id to an empty string.

<pre><code data-trim class="yaml">
google-tracking-id: "UA-XXXXXXXX-X"
</code></pre>

### Serving { Personal }

Install the required dependencies:

<pre><code data-trim class="bash">
gem install jekyll jekyll-paginate jemoji html-proofer
</code></pre>

Serve the jekyll website:

<pre><code data-trim class="bash">
./scripts/serve-production
</code></pre>

Another option is following the [GitHub's Jekyll Help](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll)

<pre><code data-trim class="bash">
bundle exec jekyll serve
</code></pre>

Visit [http://127.0.0.1:4000](http://127.0.0.1:4000) and you are ready to start hacking around your { Personal } website! Note that every time you update the site configuration (\_config.yml), you will need to cancel the serving (*Ctr + C*) and serve the website again.


## Modifying the header

The intro part of the index page (Header) is consisted of four elements:

<ol>
  <li>A black favicon</li>
  <li>Background image</li>
  <li>Welcome text</li>
  <li>Your image</li>
</ol>

### Black favicon

The black favicon is an image on the left of the navigation bar.
Preferably it should be a black and white version of your favicon.

<pre><code data-trim class="yaml">
black-favicon: "/img/favicon.ico"
</code></pre>

### Background image

In order to set the background, set the path to following variable:

<pre><code data-trim class="yaml">
background-img: "../img/wallpaper-blurry.jpg"
</code></pre>

<small>NB! Keep the .. in the beginning of the background image path</small>

### Welcome text

The welcome text is controlled by the following (self-explanatory) variables:

<pre><code data-trim class="yaml">
dynamic-typing: True
shuffle: True # Shuffle the lines.
loop: True
loop-count: False # Set False for infinite loop, or set any number for finite loop.
type-speed: 10 # Default 10
start-delay: 200 # Default 200
delete-delay: 5000 # Default 5000
lines: # You can add HTML Tags in the Text
  - text: "The lower you fall, the higher you'll fly."
  - text: "Where’s your will to be weird?"
</code></pre>

### Your image

You can set your image from the following variable:

<pre><code data-trim class="yaml">
me-img: "/img/author.png"
</code></pre>

If you want to connect your Facebook profile image then you can use the following.                 
Replace `user_id` with your facebook user id. Facebook user id can be found by clicking
on your profile pic and the large number in the end of the url just before '&type' is your user id.           
Note: fbid is not the same as user id and user id only contains numbers.

<pre><code data-trim class="yaml">
me-img: "https://graph.facebook.com/user_id/picture?type=large&width=500&height=500"
</code></pre>

If you want to connect your Github profile image then you can use the following.              
Replace `user_name` with your Github user name.

<pre><code data-trim class="yaml">
me-img: "https://github.com/user_name.png?size=500"
</code></pre>

If you want to connect your Gravatar profile image then you can use the following.              
Replace `email_hash` with your Gravatar profile email hash.                      
You can create the email hash by using an online tool like [md5hashgenerator](http://www.md5hashgenerator.com/),
just enter your email and it will generate the hash.

<pre><code data-trim class="yaml">
me-img: "https://www.gravatar.com/avatar/email_hash?s=500"
</code></pre>



## Web App Mode

You can make your website behave like a native web app in iOS and Android devices
by providing links for the icons for each resolution:

<pre><code data-trim class="yaml">
web-app-mode: True

# Icons for Web App mode

icon-36p: "/img/web-app/icon-36p.png"
icon-48p: "/img/web-app/icon-48p.png"
icon-72p: "/img/web-app/icon-72p.png"
icon-96p: "/img/web-app/icon-96p.png"
icon-144p: "/img/web-app/icon-144p.png"
icon-192p: "/img/web-app/icon-192p.png"
</code></pre>

<small>If you want to disable this feature, simply set the web-app-mode variable to False</small>

This is how your website will look when added to the homescreen:

![iOS](https://dl.dropboxusercontent.com/u/8522559/personal-jekyll-theme/ios.jpg)

![Android](https://dl.dropboxusercontent.com/u/8522559/personal-jekyll-theme/pinned.jpg)

And when the user opens it (note that it renders in fullscreen):

![Web App](https://dl.dropboxusercontent.com/u/8522559/personal-jekyll-theme/web-app.jpg)



## Browser status bar customization

You can color the browser status bar when in mobile mode, by setting it to a color.

The color is define in the site config with the following variables

<pre><code data-trim class="yaml">
##############################
# Color the browser elements #
##############################
color-browser: "#000000"
apple-status-bar-style: "black"
</code></pre>


## Blog

A website is truly personal if it hosts your blog as well, this place of the internet
where you can place your thoughts about anything!

### Archive

A blog is expected to host many posts, so you will need an archive with pagination,
which in a nutshell it's a grouping of your posts in pages, in reverse chronological
order. You can define the number of posts that are displayed per page by changing:

<pre><code data-trim class="yaml">
paginate: 5
</code></pre>

The archive is available in {website-url}/blog.

### Share buttons

Many share buttons are available and can be enabled or disabled by setting the following:

<pre><code data-trim class="yaml">
email-share: True
fb-share: True
twitter-share: True
linkedin-share: True
reddit-share: True
google-plus-share: True
tumblr-share: True
pinterest-share: True
pocket-share: True
vkontakte-share: True
</code></pre>

### RSS feed

The RSS feed is automatically generated and placed in /feed.xml.

### Sitemap

The Sitemap is automatically generated and placed in /sitemap.xml



## Writing Posts

### Creating a new post

Run the ./scripts/newpost script with the file name of the post as an argument:

<pre><code data-trim class="bash">
cd <your { Personal } repo>
./scripts/newpost hello-world
</code></pre>

A a new post template with name YYYY-MM-DD-hello-world.md will be created under ./\_posts, with the current date. In the created post, just replace the Title, Category and tags and you can
start writing your post in markdown right bellow the end of the post header. 

Every file with the format <i>YYYY-MM-DD-post-title.md</i> will be processed as a
post, with publication date <i>YYYY-MM-DD</i>. The content starts with:

<pre><code data-trim class="yaml">
---
layout: post
section-type: post
title: Title
category: Category
tags: [ 'tag1', 'tag2' ]
---
</code></pre>

The *layout* and *section-type* variables are used by the theme and you shouldn't remove them.

### Hashtags

Jekyll generates a static pages.
As a result we have to create the tag pages before building and publishing the site.
In order to generate the tag pages, simply run the *generate-tags* script from the repo's root directory:

<pre><code data-trim class="bash">
./scripts/generate-tags
</code></pre>

The script will parse all your posts, and generate the tag pages for the newly added tags.

<small>If you are not using GitHub Pages, you can automate the execution of this script during build time.</small>

### Categories

You can organize your posts under categories. Categories are behaving like hashtags,
they have to be generated offline, by running the ./scripts/generate-categories script.

The category of the post is specified in the yaml header, in the Category variable.

NB! Only one category can be defined per post.

### Syntax highlighting

If you want to demonstrate source code in your posts, syntax highlighting is provided.
If you want to see how to render your code with the highlight, simply check the source
code of this tutorial post :smile:

<pre><code data-trim class="c">
{% raw %}
int main()
{
  printf("Hello, world of syntax highlighting!");

  return 0;
}
{% endraw %}
</code></pre>

<small>If you don't need syntax highlight in your website you can disable it by setting the syntax-highlight variable to False</small>

### Emoji support

You can add emojis to your posts by simply typing their [emoji code](http://www.emoji-cheat-sheet.com/) :wink:

### Author Blurb

You can add a short description of yourself bellow your posts, by setting the next two variables in the site config

<pre><code data-trim class="yaml">
################
# Author Blurb #
################

# The author blurb goes underneath blog posts.
# This works best when your author blurb image has a transparent background, or matches your site background color.

# if the author_blurb is not set, then this feature is skipped
author_blurb: "John Smith is an awesome person. He lives in Flatland, where he works on two-dimensional engineering projects. In his spare time, John likes to eat cotton candy."
author_blurb_image: "/img/author.jpg"
</code></pre>




## Adding a life event in the timeline

One of the coolest features of { Personal } is that enables you to tell your life's story in
the form of a timeline of photos, dates and text descriptions. The Timeline is controlled by the following variables:

<pre><code data-trim class="yaml">
events:
  - image: "/img/timeline/spidertocat.png"
    date: "September 2013 - Today"
    description: "Saving the neighborhood!"
  - image: "/img/timeline/baracktocat.jpg"
    date: "September 2007 - August 2013"
    description: "Started coding"

# First image of the Timeline

timeline-img: "/img/timeline/default.png"
</code></pre>

For each event of your life, add a tuple of image, date and description to the events,
and the timeline will be automatically generated!

The timeline-img path variable is the image that you want to show up in the beginning of your Timeline, be creative!

<small>Square images are recommended 😉</small>




## Social Buttons

Social buttons (rendered above the footer) are great for having a small hub with all your social footprint. You can edit them with the following variables:

<pre><code data-trim class="yaml">
social:
  - title: "facebook"
    url: "https://facebook.com/"
  - title: "twitter"
    url: "https://twitter.com/"
  - title: "github"
    url: "https://github.com/PanosSakkos/personal-jekyll-theme"
  - title: "bitcoin"
    url: "https://blockchain.info/address/1LHuKC9Em3KA5yoZaf7nngnNdf9K7s2gSi"
  - title: "rss"
    url: "/feed.xml"
</code></pre>

The title selects the desired [Font Awesome](https://fortawesome.github.io/Font-Awesome/icons/)
icon and it shouldn't include the "fa-" prefix.




## Contact tutorial

The contact part of the index page is consisted of two elements:

<ol>
  <li>Text</li>
  <li>Your email address</li>
</ol>

You can modify the Contact text from the /contact.html file and set the email in the site config:

<pre><code data-trim class="yaml">
email: "your@email.here"
</code></pre>

Don't be afraid of email harvesting, write your email properly and the page will perform javascript obfuscation.



## Thanks to

Theme credits to: <a href="https://github.com/PanosSakkos/personal-jekyll-theme" target="\_blank">PanosSakkos</a>. THANK YOU!