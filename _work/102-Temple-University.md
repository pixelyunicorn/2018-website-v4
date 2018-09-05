---
title: Temple University
permalink: /temple

web: https://develop.cla.temple.edu/global-studies
web-display: CLA.Temple.edu

tagline: Solving XKCD 773!
description: Easy-to-navigate content structure for a major public university.
lead: <strong>Temple University’s College of Liberal Arts</strong> needed a way to quickly unify the content and design for their overall web presence. I created a simple development and editorial workflow as allowed a small team to launch 40 new websites in a year.

tags: [ design, dev, education, materialize, website, 2017 ]
deliverables: [ Backend, Frontend, CMS ]
technologies: [ Jekyll, Netlify, Sass, PHP, Ngninx, Travis CI ]
contributors: [ Temple University, Chris Hill, Camille Elliott ]

accent: "#E43043"
accent-light: "#FFDEE2"
header-text: white
pattern: hero-patterns/temple-05.svg
preview: temple/preview.png

stickers:
 - [ twemoji/ding.svg, ding bell ]
 - [ twemoji/golf.svg, golf ]
 - [ twemoji/drum.svg, drum ]

screenshots: true
screenshots-desktop: temple/homepage-d.png
screenshots-mobile: temple/homepage-m.png
---

{% include components/sticker.html sticker=0 float="right" top="-4em" %}

# A System of Legacy Systems

When I started on this project, there was a team of 5 copy writers and developers tasked with maintaing and updating content on all 60+ websites. Trying to keep up with different versions of Drupal, WordPress, SharePoint, DreamWeaver, DIY PHP, plain HTML, and more easily becomes a pain — not to mention the security nightmares and the difficulties of training people to use 50+ different content management systems.

<blockquote class="text-center">
	<grid grid column-count="2" phone-column-count="1">
		<a href="https://wayback.archive.org/web/20161021193725/http://www.cla.temple.edu/american_studies/" target="_blank" class=""><img src="{{ site.baseurl }}/media/temple/old-as.png" alt=""></a>
		<a href="https://wayback.archive.org/web/20161022020732/https://www.cla.temple.edu/cj/" target="_blank" class=""><img src="{{ site.baseurl }}/media/temple/old-cj.png" alt=""></a>
		<a href="https://wayback.archive.org/web/20161021212258/http://www.cla.temple.edu/womenstu/" target="_blank" class=""><img src="{{ site.baseurl }}/media/temple/old-gws.png" alt=""></a>
		<a href="https://wayback.archive.org/web/20161021212507/http://www.cla.temple.edu/neuroscience/" target="_blank" class=""><img src="{{ site.baseurl }}/media/temple/old-ns.png" alt=""></a>
	</grid>
</blockquote>

<!-- https://wayback.archive.org/web/20161021193725/http://www.cla.temple.edu/american_studies/

https://wayback.archive.org/web/20160405040658/http://www.cla.temple.edu:80/asian_studies/

https://wayback.archive.org/web/20161022020732/https://www.cla.temple.edu/cj/

https://wayback.archive.org/web/20161022022246/https://www.cla.temple.edu/economics/

https://wayback.archive.org/web/20161021212507/http://www.cla.temple.edu/neuroscience/

https://wayback.archive.org/web/20161021212258/http://www.cla.temple.edu/womenstu/ -->

Taking into account problems of the existing system, we set out to build a new system of sites that was secure, easy to maintain, and consistent. More imporantly, these new sites are designed to follow good readability and accessibility standards.

<blockquote class="text-center">
	<grid grid column-count="2" phone-column-count="1">
		<a href="https://www.cla.temple.edu/liberal-studies/" target="_blank" class=""><img src="{{ site.baseurl }}/media/temple/new-ls.png" alt=""></a>
		<a href="https://www.cla.temple.edu/pre-law/" target="_blank" class=""><img src="{{ site.baseurl }}/media/temple/new-pl.png" alt=""></a>
		<a href="https://develop.cla.temple.edu/psychology/graduate/" target="_blank" class=""><img src="{{ site.baseurl }}/media/temple/new-psy.png" alt=""></a>
		<a href="https://develop.cla.temple.edu/neuroscience/faculty/" target="_blank" class=""><img src="{{ site.baseurl }}/media/temple/new-ns.png" alt=""></a>
	</grid>
</blockquote>

{% include components/sticker.html sticker=1 float="right" top="-12vh" %}

# Less is More

Each of these sites can contain 100s of pages, many of which contain outdated, hard-to-find, or duplicated information that is up-to-date elsewhere. Additionally, we have found that the content of most of these sites were did not contain what people were looking for. There is actually a very relatable XKCD #773 comic about this that highlights the problems with many university websites:

![People go to the website because they can't wait for the next alumni magazine, right? What do you mean, you want a campus map? One of our students made one as a CS class project back in '01!  You can click to zoom and everything!](https://imgs.xkcd.com/comics/university_website.png)

We identified 8 areas of content that most programs had in common and used it as a starting point for pages: Homepage, Undergraduate Studies, Graduate Studies, Study Abroad, Research, Faculty Lists, and Resources/Next Stops. Information such as News, Events, and Media Mentions are more can be found in an external university-wide data source that is regularly maintained and listed on the homepage. This vastly reduced the average number of pages on each site, reduces information compexity for visitors, and makes it significantly easier for the copy writers to keep the site up-to-date.

<grid column-count="2" phone-column-count="1">
	<div class="brick accent-bg">
		<h2>20-300</h2>
		<p class="lead">Pages per site before redesign</p>
	</div>
	<div class="brick accent-bg">
		<h2>~5</h2>
		<p class="lead">Pages per site after redesign</p>
	</div>
</grid>

Relevant content about the University can be found in the footer:

> ![Webpage footer]({{ site.baseurl }}/media/temple/footer.png)

Additionally, we limited the customization options available to each site. The use of a limited set of editing tools and customization options allows for copy writers to very easily edit the site, but not go too overboard when it come to placing content.

The simplicity of the content structure has allowed a small team to for over 40 sites in a year - that’s nearly a new site going live every week!

{% include components/sticker.html sticker=2 float="right" %}

# Mantaining Sanity aka “The Stack”

:warning: _Warning: technical jargon ahead!_

I architected a backend solution that is transparent, extra secure, and low-cost to host/maintain. The sites consist of static content generated using Jekyll, and deployed to Amazon Web Services S3 buckets. A central Jekyll theme applied to each site ensures that all sites are consistent in appearence.

Thanks to the growing popularity of Jekyll, web copy writers have a choice between content management systems. The sites have been tested on and works on Prose.io, Siteleaf, Forestry, and Nelify CMS.

Each site has its content stored in GitHub in markdown files. The editorial workflow is as easy as creating a GitHub Issue or Pull Request (edit request), which allows teams to work on proposed changes before they go live.

> ![Image showing proposed content changes in a GitHub pull request]({{ site.baseurl }}/media/temple/pr.png)

# Open Source

The best part of this project is that everything is open source! In case you skimmed through the whole thing and missed it, the theme and individual sites are open source at :octocat: [GitHub.com/TULiberalArts](https://github.com/TULiberalArts). If you find a bug or want to improve a site, pull requests are always open!
