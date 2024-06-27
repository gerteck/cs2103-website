<frontmatter>
title: "Timeline"
layout: schedule-layout.md
pageNav: 3
</frontmatter>

{% import "common/topics.njk" as topics with context %}
{% from "common/macros.njk" import embed_topic, get_week_start_date with context %}

<div class="website-content">

# Summary of the Course Timeline
<div tags="m--cs2103 m--cs2113">
{{ embed_topic("../admin/weeklySchedule.md#deadline-definition", "Admin " + icon_embedding + " Weekly schedule → Deadline for weekly tasks", "1") }}
</div>
<div tags="m--tic2002">
{{ embed_topic("../admin/index-tic2002-fragment.md#deadlines-info", "Admin " + icon_embedding + " Policies → **Deadlines, Plagiarism**", "dummy") }}
</div>

<p/>
<hr>

{% macro show_link(week_num, icon, page) -%}<small><small><a href="week{{ week_num }}/{{ page }}" class="badge bg-light text-dark mr-1">%%{{ icon }}%%</a></small></small>{%- endmacro %}


{% for week_num in range(1, 14) %}
{% set start_day = get_week_start_date(week_num, format_normal) %}

<div tags="m--cs2103 m--cs2113">

### <a href="week{{ week_num }}/" class="badge rounded-pill bg-dark"><small>**Week {{ week_num }}** <small>- {{ start_day }}</small></small></a> {{ show_link(week_num, icon_book, "topics.html") }}{{ show_link(week_num, icon_project, "project.html") }}{{ show_link(week_num, icon_tutorial, "tutorial.html") }}{{ show_link(week_num, icon_info, "admin.html") }}

</div>
<div tags="m--tic2002">

### <a href="week{{ week_num }}/" class="badge rounded-pill bg-dark"><small>**Week {{ week_num }}** <small>- {{ start_day }}</small></small></a> {{ show_link(week_num, icon_book, "topics.html") }}{{ show_link(week_num, icon_todo, "admin.html") }}

</div>
<div tags="m--tee3201">

### <a href="week{{ week_num }}/" class="badge rounded-pill bg-dark"><small>**Week {{ week_num }}** <small>- {{ start_day }}</small></small></a>

</div>
<div class="indented-level2">

<include src="week{{ week_num }}/index.md#summary" optional />
</div>
{{ line_double }}

{% endfor %}

</div>
