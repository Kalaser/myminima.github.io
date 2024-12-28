---
layout: page
title: Categories
permalink: /categories/

---

<div class="categories-list">   <h1>{{ page.title }}</h1>   <p>以下是本站的所有分类，点击分类名查看相关内容：</p>      <ul>     {%- assign sorted_categories = site.categories | sort -%}     {%- for category in sorted_categories -%}       <li>         <a href="{{ site.baseurl }}/categories/{{ category[0] | slugify }}/">           {{ category[0] }}         </a>         <span>（{{ category[1].size }} 篇文章）</span>       </li>     {%- endfor -%}   </ul> </div>





