---
layout: page
title: Projects | 
description: "This is a selection of projects (digital artifacts, interactive installations, etc.) that I have worked on during my academic career."
---

## Projects

This is a selection of projects (digital artifacts, interactive installations, etc.) that I have worked on during my academic career. Each project has a unique contexts, motivations and objectives, however, they all contribute with concepts, methods and empirical data towards the design of novel human-computer interactions.

{% for project in site.data.projects.main %}

<div class="project">
	<h3>{{ project.title }} ({{ project.year }})</h3>
	<img src="{{ project.image }}">
	<p class="author"><small><i class="fas fa-user-friends"></i> {{ project.authors }} </small></p>
	<p>{{ project.notes | markdownify }}</p>
	<p>Main publications:</p>
	<ul>
		{% for publication in project.publications limit:3 %}
			<li>{% bibliography --group_by none --query @*[key={{ publication }}] %}</li>
		{% endfor %}
	</ul>
</div>

{% endfor %}