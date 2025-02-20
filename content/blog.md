---
layout: base.njk
title: Blog
description: Update from my blog post
pagination:
  data: collections.posts
  size: 6
  reverse: true
testdata:
 - item1
 - item2
 - item3
 - item4
permalink: "blog/{% if pagination.pageNumber > 0 %}page-{{ pagination.pageNumber + 1 }}/{% endif %}index.html"
---

    <section class="bg-primary">
      <div class="px-8 2xl:max-w-7xl mx-auto py-6">
        <div class="mt-6 space-y-2">
          <div class="h-0.5 bg-secondary"></div>
          <h3 class="text-secondary text-base font-medium">
            <span class="font-bold">{{title}}</span>
          </h3>
        </div>
        <div class="flex flex-col text-secondary pt-2 mt-2 gap-12 lg:gap-32">
            {%- for post in pagination.items %}
          <div data-aos="fade-up" data-aos-duration="1500" class="grid grid-cols-1 lg:items-end lg:grid-cols-4 py-4 gap-4">
            <p class="text-3xl leading-6 lg:col-span-3 lg:text-5xl lg:leading-9 indent-32 lg:indent-32"> <a href="{{post.url}}">{{post.data.description}}</a></p>
            <p class="italic text-xs block "> {{post.data.title}} </p>
          </div>{% endfor %}
<div class="flex gap-8 items-center">
{% if pagination.href.previous %}  <p class="text-3xl leading-6 lg:col-span-3 lg:text-5xl lg:leading-9 indent-32 lg:indent-32">  <a href="{{ pagination.href.previous }}">← Previous</a></p>{% endif %}
{% if pagination.href.next %}  <p class="text-3xl leading-6 lg:col-span-3 lg:text-5xl lg:leading-9 indent-32 lg:indent-32"> 
<a href="{{ pagination.href.next }}">Next →</a></p>{% endif %}
</div>
        </div>
          </div>
       </div>

      </div>
    </section>
