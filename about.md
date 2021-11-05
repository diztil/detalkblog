---
layout: page
title: About
permalink: /about/
published: true
---

<div class="page" markdown="1">

{% capture page_subtitle %}
<img
    class="me"
    alt="{{ author.name }}"
    src="{{ site.author.photo | relative_url }}"
    srcset="{{ site.author.photo2x | relative_url }} 2x"
/>
{% endcapture %}

{% include page/title.html title=page.title subtitle=page_subtitle %}

## What is DeTalk? 

Just some minimalistic blog site that tries to archive, summarize and host any kind of text the author has chosen to publish.

## Who's behind DeTalk?
Me. Dewan M.I. Mukto. Just me, myself and my knowledge.

## Like the theme?
Thank [**Marcin C.**](https://github.com/melangue/dactl) for creating this theme. Thank [**Jekyll**](https://jekyllrb.com/) and [**Github Pages**](https://pages.github.com/) for the implementation and hosting. Thank [**MuxSites**](https://www.muxsites.com) and [**MuxWorks**](https://www.muxworks.com) (the company behind MuxSites) for the domain and overall support.

</div>
