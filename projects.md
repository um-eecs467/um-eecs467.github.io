---
layout: page
title: Final Projects
---

{%for term in site.data.projects%}
- [{{term.term}}](#{{term.term}})
{%endfor%}

{%for term in site.data.projects%}
<h2 id="{{term.term}}"> {{term.term}} </h2>
{%for project in term.projects%}
### Group {{project.group_num}}
**{{project.name}}**

*{{project.people}}*

{{project.iframe}}
{%endfor%}
{%endfor%}