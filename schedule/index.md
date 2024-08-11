<frontmatter>
layout: schedule-layout.md
title: "Schedule"
pageNav: 1
</frontmatter>

{% import "common/topics.njk" as topics with context %}
{% from "admin/admin-tasks-fragment.md" import show_weekly_admin_tasks with context %}
{% from "common/macros.njk" import get_week_start_date, show_as_tab with context %}
{% from "_course-" + course + "/weeklyTextbookTopics-fragment.md" import weekly_textbook_topics, weeks_with_no_topics with context %}
{% from "_course-" + course + "/weeklyTpTasks-fragment.md" import weekly_tp_themes with context %}

{#
-1: site not ready, lands in the course intro page
0: site ready but semester hasn't started, lands in the course intro page
14: exam period, lands in the course intro page
15: site no longer used, lands in the course intro page
1..13: site is active, lands in the week's schedule page
#}


{% macro show_week_pagetop(week_num, category) %}

{% if tic2002 %}
  {% set categories = {
    notices: {name: "Summary", file: "index", icon: icon_tab_summary, pagenav: 4},
    topics: {name: "Topics", file: "topics", icon: icon_tab_topics, pagenav: 3},
    admin: {name: "Tasks", file: "admin", icon: icon_tab_tasks, pagenav: 4}
  } %}
{% elseif tee3201 %}
  {% set categories = {
    notices: {name: "Summary", file: "index", icon: icon_tab_summary, pagenav: 1},
    topics_py: {name: "Programming Topics", file: "topics-py", icon: icon_tab_programming_topics, pagenav: 4},
    topics: {name: "SE Topics", file: "topics", icon: icon_tab_topics, pagenav: 3},
    admin: {name: "Tasks", file: "admin", icon: icon_tab_tasks, pagenav: 4}
  } %}
{% else %}
  {% set categories = {
    notices: {name: "Summary", file: "index", icon: icon_tab_summary, pagenav: 4},
    admin: {name: "Admin", file: "admin", icon: icon_tab_admin_info, pagenav: 4},
    topics: {name: "Topics", file: "topics", icon: icon_tab_topics, pagenav: 3},
    project: {name: "Project", file: "project", icon: icon_tab_project, pagenav: 4},
    tutorial: {name: "Tutorial", file: "tutorial", icon: icon_tab_tutorial, pagenav: 4}
  } %}
{% endif %}

<frontmatter>
title: "Week {{ week_num }} - {{ categories[category].name }}"
layout: schedule-layout.md
pageNav: {{ categories[category].pagenav }}
</frontmatter>

<nav>
<ul class="pagination mt-2">
{%- set previous_status = " disabled" if week_num == 1 else "" -%}
{%- set next_status = " disabled" if week_num == 13 else "" -%}
<li class="page-item{{ previous_status }}"><a class="page-link" href="../week{{ 1 if week_num == 1 else (week_num - 1) }}/index.html"><md>:glyphicon-chevron-left: **Prev. Week**</md></a></li>
<li class="page-item">&nbsp;&nbsp;&nbsp;</li>
{% for c,v in categories %}
  {%- set is_active = " active" if categories[category] == v else "" -%}
  <li class="page-item{{ is_active }}"><a class="page-link" href="{{v.file}}.html"><md>{{ v.icon }}</md> {{v.name}}</a></li>
</li>
{% endfor %}
<li class="page-item">&nbsp;&nbsp;&nbsp;</li><li class="page-item{{ next_status }}"><a class="page-link" href="../week{{ 13 if week_num == 13 else (week_num + 1) }}/index.html"><md>**Next Week** :glyphicon-chevron-right:</md></a></li>
</ul>
</nav>

<p/>

# Week {{ week_num }} <small><small>%%[{{ get_week_start_date(week_num | int, format_normal) }}]%% - {{ categories[category].name }}</small></small>

{% endmacro %}


{% macro show_week_summary(week_num) %}

{% if course == "TIC2002" %}
<span id="summary">
<div class="container">
  <div class="row">
  <div class="col-sm border-right">
{% if week_num + "" in weeks_with_no_topics %}
* %%No topics allocated to this week.%%
{% else %}
<md>**{{ icon_book }} Topics Summary:**</md>

{{ topics.show_week_schedule_main(week_num, weekly_textbook_topics, "", is_toc=true, is_flat=true) }}

<panel type="seamless" header="%%Full ToC%%">
  <include src="topics.md#toc" optional />
</panel>
{% endif %}
  </div>
  <div class="col-sm">

<md>**{{ icon_todo }} Tasks Summary:**</md>
<include src="admin-{{ course | lower }}-fragment.md#summary" optional/>

  </div>
  </div>
</div>
</span>
<br>

{% elseif course == "TEE3201" %} {#--------------------------------------------------------------------------------#}

<span id="summary">
<div class="container">
  <div class="row">
  <div class="col-sm" style="border-right: 1px dotted lightgrey">

#### <a href="topics-py.html" class="badge bg-light text-dark">:fas-code: Programming Topics</a>
<include src="../programming-topics-fragment.md#week{{ week_num  }}-toc" optional />

  </div>
  <div class="col-sm">

#### <a href="topics.html" class="badge bg-light text-dark">{{ icon_book }} SE Topics</a>
{{ topics.show_week_schedule_main(week_num, weekly_textbook_topics, "", is_toc=true, is_flat=true) }}

<panel type="seamless" header="%%Full ToC%%">
  <include src="topics.md#toc" optional />
</panel>

  </div>
  </div>
  <div class="row" style="border-top: 1px dotted lightgrey">
  <div class="col-sm">

#### <a href="admin.html" class="badge bg-light text-dark mt-2">:fas-tasks: Tasks</a>
<include src="admin-{{ course | lower }}-fragment.md#summary" optional/>
  </div>
  </div>
</div>
</span>
<br>

{% else %} {#---------------------------------------------------------------------------------------#}

<span id="summary">
<div class="container">
  <div class="row">
  <div class="col-sm border-right">

**Topics:**
{% if week_num + "" in weeks_with_no_topics %}
* %%No topics allocated to this week.%%
{% else %}
{{ topics.show_week_schedule_main(week_num, weekly_textbook_topics, "", is_toc=true, is_flat=true) }}

<panel type="seamless" header="%%Full ToC%%">
  <include src="topics.md#toc" optional />
</panel>
{% endif %}

  </div>
  <div class="col-sm">

**Admin:**
<include src="admin.md#summary" optional/>
<include src="project.md#summary" optional/>

  </div>
  </div>
</div>
</span>
<br>
{% endif %}
{% endmacro %}


{% macro show_week_index_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "notices") }}

<include src="notices-{{ course | lower }}-fragment.md" optional />

{{ show_week_summary(week_num) }}
</div>
{% endmacro %}


{% macro show_week_admin_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "admin") }}

{% if week_num == "1" %}
<box type="info">

**This is the <span class="text-primary">{{ show_as_tab('Admin', icon_tab_admin) }}</span> tab** of this week. It contains admin info relevant to this week.

A label with the {{ icon_deadline }} icon indicates the deadline for that task %%(e.g., <span class="badge bg-secondary text-light">{{ icon_deadline }} Friday 2359</span>)%%.
</box>
{% endif %}

{% if course in ["TIC2002", "TEE3201"] %}
<include src="admin-{{ course | lower }}-fragment.md" optional />
{% else %}
{{ show_weekly_admin_tasks(week_num) }}
{% endif %}
</div>
{% endmacro %}


{% macro show_week_topics_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "topics") }}

{% if week_num == "1" %}
<box type="info">

**This is the <span class="text-primary">{{ show_as_tab('Topics', icon_tab_topics) }}</span> tab** of this week. It contains topics allocated to this week.
</box>
{% endif %}
<include src="topics.md#notices" optional />
{{ topics.show_week_schedule(week_num, weekly_textbook_topics) }}
</div>
{% endmacro %}


{% macro show_week_tutorial_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "tutorial") }}

{% if week_num == "1" %}
<box type="info">

**This is the <span class="text-primary">{{ show_as_tab('Tutorial', icon_tab_tutorial) }}</span> tab** of this week. It contains information relevant to the week's tutorial (if any).
</box>
{% endif %}
<include src="tutorial-{{ course | lower }}-fragment.md" optional />
</div>
{% endmacro %}


{% macro show_week_project_page_details(week_num) %}

{% set ip = week_num <= (ip_last_week | int) and week_num >= (ip_first_week | int) %}
{% set tp = week_num >= (tp_first_week | int) %}
{% if tp %}
  {% set theme = weekly_tp_themes["w" + week_num] %}
{% endif %}

<div id="summary" class="lead border-left ml-3 mb-3 pl-2" style="color: purple;">

{% if ip %}
**iP:**
<include src="../../admin/{{ "ip-w" + week_num + ".md" }}#summary" />
{% endif %}
{% if tp %}
**tP:** {% if theme.milestone %}<span class="border rounded text-success border-success pe-1 ps-1">:fas-tag: **{{ theme.milestone }}**</span>{% endif %}
<include src="../../admin/{{ "tp-w" + week_num + ".md" }}#summary" />
{% endif %}
</div>

{% if ip %}

<h2 class="d-block text-white bg-dark p-1 mb-4 mt-4">{{ icon_individual }} iP</h2>

<include src="../../admin/ip-w{{ week_num }}.md#body" />

{% endif %}
{% if tp %}

<h2 class="d-block text-white bg-dark p-1 mb-4 mt-4">{{ icon_team }} tP: {{ theme.name }} {% if theme.milestone %}<small><span style="float: right;" class="text-warning p-1"> → <md>{{ theme.milestone }}</md></span></small>{% endif %}</h2>

<include src="../../admin/tp-w{{ week_num }}.md#body" />
{% endif %}
{% if not ip and not tp %}
**There are no project activities allocated for this week.**
{% endif %}
{% endmacro %}


{% macro show_week_project_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "project") }}

{% if week_num == 1 %}
<box type="info">

**This is the <span class="text-primary">{{ show_as_tab('Project', icon_tab_project) }}</span> tab** of this week. It contains project-related information relevant to this week.
</box>
{% endif %}
{{ show_week_project_page_details(week_num) }}
</div>
{% endmacro %}

{% macro show_programming_topics_page(week_num) %}
<div class="website-content">
{{ show_week_pagetop(week_num, "topics_py") }}

{% if week_num == "1" %}
<box type="info">

Programming topics allocated to the week will appear in this tab.
</box>
{% endif %}
<include src="../programming-topics-fragment.md#week{{ week_num }}" optional />
</div>
</div>
{% endmacro %}


<!-- ============================= page content ============================================ -->

{% set week_to_show = "1" if current_week in ["-1", "0", "14", "15"] else current_week %}
<include src="week{{ week_to_show }}/index.md" />
