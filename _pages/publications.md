---
layout: page
permalink: /publications/
title: publications
description: Peer-reviewed articles, chapters, talks, and conference abstracts, in reverse chronological order.
nav: true
nav_order: 1
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

<h2 class="bibliography">Journal articles</h2>

{% bibliography --query @article %}

<h2 class="bibliography">Books and book chapters</h2>

{% bibliography --query @incollection %}

<h2 class="bibliography">Manuscripts in preparation</h2>

{% bibliography --query @unpublished %}

<h2 class="bibliography">Thesis</h2>

{% bibliography --query @phdthesis %}

<h2 class="bibliography">Invited and conference talks</h2>

{% bibliography --query @misc %}

<h2 class="bibliography">Selected conference abstracts</h2>

{% bibliography --query @inproceedings %}

</div>
