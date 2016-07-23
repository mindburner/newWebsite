+++
date = "2016-07-23T00:12:53-04:00"
title = "Instructions to Edit the Website File"
+++

- Each post on the blog can be created by creating a new file inside content/post.
  file just needs a date and a title and optional content
  <pre>
  <code>
    +++
    date = "2016-07-23T00:12:53-04:00"
    title = "Instructions to Edit the Website File"
    +++

    content then follows
  </code>
  </pre>
- The most important file is the config.toml file.
  This file has information that is used to create content throughout the website. Just give
  it a look. It's pretty intuitive and looks like this:

  <pre>
    <code>
    [params.about]
        headline    = "Change the following the text from config.toml"
        description = "Mayan EDMS is an ...."
        buttonText  = "Overview"
    </code>
  </pre>

We'll see how this will be used next.

- The information from config.toml file is used by html files inside content/layout/partials.
  Different sections of the website, like about, contact etc have their own html files. These html files
  can easily refer to information from config.toml file or even include new information like any html file.
  For example, the above snippet from the config file is used as:
  <pre><code>< h2 class="section-heading">{{ with .Site.Params.about.headline }}{{ . }}{{ end }} < /h2> </code></pre> to generate a heading inside about.html.
  One can also just add a new header like <pre><code> < h2 class="section-heading">Hello World!< /h2> </code></pre> without using anything from the config file.

- Next, all of the static contents like images, stylesheet files, fonts, etc are all inside content/static
  folder.
      - The main css file to change the style of the website is creative.css.
        After few mins of trial and error, it's relatively easy to figure out what section
        controls what.
      - The man image for the website is labeled header.png inside the content/static/img


- There is probably a lot to generating static websites with Hugo, but with limited time, this is all I got   done. I also didn't know what would go inside each section so I left a lot of files(html,css, and images) that could be useful or not useful based on the content. Sorry about that.

- I didn't look into parallax, but should be pretty straightforward to incorporate provided the website has
  an actual picture background. I believe content/static/js/creative.js would be a place to add that
  functionality.   
