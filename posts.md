---
layout: default
title: Posts
---



<h2 class="category-title">
  <a href="{{ '/posts/ai-shit/' | relative_url }}">
    AI SHIT
  </a>
</h2>
{% assign ai_posts = site.categories["ai-shit"] %}
{% include post-list.html posts=ai_posts %}

<h2 class="category-title">
  <a href="{{ '/posts/finance-shit/' | relative_url }}">
    FINANCE SHIT
  </a>
</h2>
{% assign fin_posts = site.categories["finance-shit"] %}
{% include post-list.html posts=fin_posts %}

<h2 class="category-title">
  <a href="{{ '/posts/basic-bitch-shit/' | relative_url }}">
    BASIC BITCH SHIT
  </a>
</h2>
{% assign basic_posts = site.categories["basic-bitch-shit"] %}
{% include post-list.html posts=basic_posts %}

<h2 class="category-title">
  <a href="{{ '/posts/other-crap/' | relative_url }}">OTHER CRAP</a>
</h2>
{% assign oth_posts = site.categories["other-crap"] %}
{% include post-list.html posts=oth_posts %}

<h3 id="words-that-make-you-sound-smarter-than-you-really-are" class="category-title">
  <a href="{{ '/posts/other-crap/words-that-make-you-sound-smarter-than-you-really-are/' | relative_url }}">
    WORDS THAT MAKE YOU SOUND SMARTER THAN YOU REALLY ARE
  </a>
</h3>
{% assign word_posts = site.categories["words-that-make-you-sound-smarter-than-you-really-are"] %}
{% include post-list.html posts=word_posts %}

<h3 id="kulture-klub" class="category-title">
  <a href="{{ '/posts/other-crap/le-kulture-klub/' | relative_url }}">LE KULTURE KLUB</a>
</h3>
{% assign lkk_posts = site.categories["le-kulture-klub"] %}
{% include post-list.html posts=lkk_posts %}



