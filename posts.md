---
layout: default
title: Posts
---

## AI Shit
{% assign ai_posts = site.categories["AI Shit"] %}
{% include post-list.html posts=ai_posts %}

## Finance Shit
{% assign fin_posts = site.categories["Finance Shit"] %}
{% include post-list.html posts=fin_posts %}

## Basic Bitch Shit
{% assign basic_posts = site.categories["Basic Bitch Shit"] %}
{% include post-list.html posts=basic_posts %}

## Other Crap
{% assign oth_posts = site.categories["Other Crap"] %}
{% include post-list.html posts=oth_posts %}
