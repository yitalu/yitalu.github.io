---
layout: default
title: Teaching
---

I run real-time interactive experiments online using <a href ="https://www.otree.org">oTree</a>, a platform based on Python and Django. Traditional lab experiments that need subjects to interact strategically can be transformed and conducted remotely.

If you have good ideas or funding, we can collaborate.


{% for post in paginator.posts %}

	<article class="post">

		{% if post.external-url %}
			<h1>
				<a href="{{ post.external-url }}">{{ post.title }}</a>
				<a class="anchor" href="{{ post.url }}"><i class="icon-anchor"></i></a>
			</h1>
		{% else %}
			<h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
		{% endif %}

		<div class="post-content">{{ post.content }}</div>

	</article>

{% endfor %}

{% if paginator.total_pages > 1 %}
	<div class="postnavigation">

		{% if paginator.previous_page %}
			{% if paginator.page == 2 %}
				<a class="prev left" href="/">&larr; Newer</a>
			{% else %}
				<a class="prev left" href="/page{{paginator.previous_page}}/">&larr; Newer</a>
			{% endif %}
		{% else %}
			<span class="nope left">&larr; Newer</span>
		{% endif %}

		<span class="pages">Page {{ paginator.page }} of {{ paginator.total_pages }}</span>

		{% if paginator.next_page %}
			<a class="next right" href="/page{{paginator.next_page}}/">Older &rarr;</a>
		{% else %}
			<span class="nope right">Older &rarr;</span>
		{% endif %}

	</div>
{% endif %}