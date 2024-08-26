{% from "common/macros.njk" import get_date, embed_topic, show_as_tab, thumb, timing_badge with context %}
{% from "common/admin.njk" import show_admin_summary with context %}

{% call show_admin_summary() %}
1. Install Java {{ timing_badge("before the lecture") }}
1. Create a GitHub account
1. Submit the pre-course survey  {{ timing_badge("by " + get_date(date_w1_start, 4)) }}
1. Attend the lecture
1. Submit weekly exercises
{% endcall %}

#### {{ thumb(0) }} Learn about the course and the website

{{ embed_topic("../../admin/index-tic2002-fragment.md#course-info", "Admin " + icon_embedding + " About the course", "week1Admin-java", "1") }}
{{ embed_topic("../../admin/index-tic2002-fragment.md#website-info", "Admin " + icon_embedding + " Using the website", "week1Admin-java", "1") }}


#### {{ thumb(1) }} Install Java {{ timing_badge("before the lecture", "secondary") }}

* See the panel below:

{{ embed_topic("../../admin/index-tic2002-fragment.md#java", "Admin " + icon_embedding + " Programming Language", "week1Admin-java", "1") }}


#### {{ thumb(2) }} Create a GitHub account

* See the panel below:

{{ embed_topic("../../admin/index-tic2002-fragment.md#github-info", "Admin " + icon_embedding + " Tools → GitHub", "week1Admin-github", "1") }}


#### {{ thumb(3) }} Submit the pre-course survey  {{ timing_badge("by " + get_date(date_w1_start, 4), "secondary") }}

* Submit the pre-course survey, available on Canvas

#### {{ thumb(4) }} Attend the lecture
* There is no tutorial in this week. The lecture will start at 7.00pm.

{{ embed_topic("../../admin/index-tic2002-fragment.md#lectures-info", "Admin " + icon_embedding + " Lectures", "week1Admin-lectures", "1") }}


#### {{ thumb(5) }} Submit weekly exercises

* As you learn the weekly topics, submit Week 1 programming exercise on Coursemology. See the panel below for more info. More instructions about this will be provided during the lecture.


{{ embed_topic("../../admin/index-tic2002-fragment.md#exercises-info", "Admin " + icon_embedding + " Programming Exercises", "week1Admin-exercises", "1") }}
{{ embed_topic("../../admin/index-tic2002-fragment.md#coursemology-info", "Admin " + icon_embedding + " Tools → Coursemology", "week1Admin-repl", "1") }}
{{ embed_topic("../../admin/index-tic2002-fragment.md#help-info", "Admin " + icon_embedding + " Getting Help", "week1Admin-help", "1") }}
