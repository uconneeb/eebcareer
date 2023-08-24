# eebcareer
EEB-5100 (Planning for a career in EEB) course web site

## Markdown editing guide

### How do I edit a page?

Click on the markdown page you want to edit and then click on the pencil icon in the upper right (just to the left of the trashcan icon). If no edit (pencil) icon is present, it means that you do not yet have permission to edit anything (you are not yet a "collaborator").

### What are those lines at the top between lines of hyphens?

Under the hood, Github Pages web sites depend on [Jekyll](https://jekyllrb.com), and these first few lines (the "frontmatter") tell Jekyll what page layout to use, what title should be displayed, and what permalink should be used to access the page.

### How do I add a heading

Headings in markdown are indicated by starting a line with several hash characters. One hash (#) produces a level 1 heading, two hashes (##) represent a level 2 heading, three hashes (###) produce a level-3 heading, etc.

### How do I add a link to an email address?

Either of the constructs below would make a link to Paul's email address, with the only difference being that the second would show _Paul O. Lewis_ to the user rather than the actual email address:
~~~~~~
[paul.lewis@uconn.edu](mailto:paul.lewis@uconn.edu)
[Paul O. Lewis](mailto:paul.lewis@uconn.edu)
~~~~~~

### How do I add a link to an external site?

The following would add a link to the [University of Connecticut EEB Department](https://eeb.uconn.edu/) to  page. The 
part in square brackets is the link text (what the viewer of the web page sees):
~~~~~~
[University of Connecticut EEB Department](https://eeb.uconn.edu/)
~~~~~~

### How do I add a link to another page within this web site?

This would produce a link to the schedule [schedule](/schedule/):
~~~~~~
[schedule](/schedule/)
~~~~~~

If that doesn't work for some reason, try this:
~~~~~~
[schedule]({{ site.baseurl }}/schedule/)
~~~~~~
The `{{ site.baseurl }}` construct is known as a _liquid tag_, which are a kind of macro that expands to something and, in this case, it expands to the base part of the url (i.e. `https://uconneeb.github.io/`.

### How do I add an image?

The simplest way to add an image is to start a normal link with an exclamation point:
~~~~~~
![EEB Logo]('assets/img/eeb-logo-square-512x512.png')
~~~~~~
This would show the image at its actual size (which might be much to large or much too small) and  place the caption _Moi_ below it. I have created a custom [Liquid Tag](https://jekyllrb.com/docs/liquid/tags/) to make it easier to place images on your personal page that are sized correctly. 

To use the custom Liquid tag, add something like this:
~~~~~~
{% include figure.html description="EEB Logo" url="/assets/img/eeb-logo-square-512x512.png" height="300px" css="image-right" %}
~~~~~~
The initial part `{% include figure.html` should not be modified. You can change the 
description, url, height, and css attributes however to suit your purposes. 

**Important:**
* Note that the only options for `css` are `image-left`, `image-center` and `image-right`.
* Note that the url provided must be the actual path from the root of the web site 
to the image file (don't be tempted to use the permalink specified in the frontmatter
of your personal page as part of this url)\

### How do I create a simple table?

Tables couldn't be simpler to create in markdown:
~~~~~~
| What          | Information |
| :------------ | :---------------------------------------------- |
| **Presenter** | [Paul Lewis](https://phylogeny.uconn.edu/) |
| **Topic**     | Communicating your work: web sites |
| **Resources** | |
| **Notes**     | Homework: ... |
~~~~~~

The vertical bar (created using pipe `|` characters) is the boundary between columns, and
the horizontal bar (created using hyphen `-` characters) is the boundary between the header line and the ordinary table lines. You can justify particular columns using colons in  the line of hyphens defining the boudary separating header and table. For example, this would cause the "What" column to be right-justified rather than left-justified:
~~~~~~
| What          | Information |
| ------------: | :---------------------------------------------- |
| **Presenter** | [Paul Lewis](https://phylogeny.uconn.edu/) |
| **Topic**     | Communicating your work: web sites |
| **Resources** | |
| **Notes**     | Homework: ... |
~~~~~~

The spacing is irrelevant: you do not need to be tidy as long as you get a vertical bar
between your columns. Also, the number of hyphens in each column of the header separator
does not matter (but you do need at least 3). Finally, you need not have a header row at all: this would produce a table without headers but with justification information:
~~~~~~
| :------------ | :---------------------------------------------- |
| **Presenter** | [Paul Lewis](https://phylogeny.uconn.edu/) |
| **Topic**     | Communicating your work: web sites |
| **Resources** | |
| **Notes**     | Homework: ... |
~~~~~~

You may desire to have more control over your tables (e.g. want a particular column to be
wider or narrower), but markdown only allows pretty simple tables.

### Is there a limit to the size of files I can upload?

Short answer, yes! If we don't want to pay for hosting our site on GitHub Pages (and we don't), then we need to be frugal with respect to content. Scroll down to the Usage Limits section of the [About GitHub Pages](https://help.github.com/en/github/working-with-github-pages/about-github-pages) 
section for the details, but the bottom line is that there must be less than 1 GB of 
content in the published site. Thus, please try to **reduce the size** of any PDF file 
you add (ask for help with this if you don't know how to do this) and pre-shrink your image files to reasonable sizes (e.g. 500 pixels in width/height) and specifying screen resolution (72 dpi).
