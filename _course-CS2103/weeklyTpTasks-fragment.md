{% from "common/macros.njk" import get_date with context %}

{% set weekly_tp_tasks = {
week3: [
  {id: 'get_familiar_with_ab3', deadline: get_date(date_w3_start, 5, time="23:59")},
  {id: 'set_up_meeting_time', deadline: 'by the end of the tutorial'},
  {id: 'check_collective_ip_status', deadline: get_date(date_w4_start, 1, time="")}
],
week4: [
  {id: 'start_weekly_meetings'},
  {id: 'start_project_notes', deadline: 'before the tutorial'},
  {id: 'decide_project_direction', deadline: 'decide by tutorial, submit by Sat'}
],
week5: [
  {id: 'brainstorm_user_stories', deadline: 'before the tutorial'},
  {id: 'prioritize_user_stories', deadline: 'before/during the tutorial'}
],
week6: [
  {id: 'conceptualize_first_version'},
  {id: 'draft_the_ug'},
  {id: 'set_up_project_repo'},
  {id: 'get_familiar_with_the_code_base'}
],
week7: [
  {id: 'do_a_practice_iteration', deadline: get_date(date_w7_start, 10, time="23:59")},
  {id: 'update_website_aboutus_readme'},
  {id: 'update_the_ug'},
  {id: 'update_dg_user_stories_etc'},
  {id: 'plan_the_next_iteration'},
  {id: 'start_implementing_the_next_version'}
],
week8: [
  {id: 'ensure_you_know_tp_expectations'},
  {id: 'start_proper_milestone_management'},
  {id: 'add_first_functionality_increment'}
],
week9: [
  {id: 'deliver_first_version', deadline: get_date(date_w9_start, 3, time="23:59")},
  {id: 'start_updating_uml_diagrams'}
],
week10: [
  {id: 'do_a_postmortem'},
  {id: 'adjust_process_rigor'},
  {id: 'start_on_the_penultimate_version'},
  {id: 'update_dg_with_design_details'},
  {id: 'smoke_test_catcher', deadline: 'COMPULSORY', graded: true},
  {id: 'do_a_release'}
],
week11: [
  {id: 'deliver_the_feature'},
  {id: 'update_user_docs', deadline: get_date(date_w11_start, 3, time="23:59")},
  {id: 'release_as_a_jar_file', deadline: get_date(date_w11_start, 3, time="23:59")},
  {id: 'wrap_up_penultimate_version'},
  {id: 'demo_penultimate_version'},
  {id: 'get_ready_for_the_PED'}
],
week12: [
  {id: 'attend_the_PED', deadline: 'During the weekly briefing on ' + get_date(date_w12_start, time=""), graded: true},
  {id: 'start_fixing_PED_bugs', deadline: 'Before the tutorial'},
  {id: 'tweak_product_as_per_PED'},
  {id: 'draft_the_ppp'},
  {id: 'try_pdf_conversion_early'},
  {id: 'make_code_reposense_compatible'}
],
week13: [
  {id: 'do_final_tweaks'},
  {id: 'submit_final_deliverables', deadline: get_date(date_final_submission, time=time_final_submission)},
  {id: 'demo_the_product', deadline: get_date(date_final_submission, 2 if time_final_submission == "23:59" else 1)},
  {id: 'wrap_up_final_milestone', deadline: get_date(date_final_submission, 2 if time_final_submission == "23:59" else 1)},
  {id: 'prepare_for_PE'},
  {id: 'attend_the_PE', deadline: 'during the weekly briefing on ' + get_date(date_w13_start, 4, format=format_normal, time=""), deadline_type: 'warning'},
  {id: 'attend_the_makeup_PE', deadline: get_date(date_w13_start, 6, format=format_normal, time="1400-1600"), deadline_type: 'secondary'}
]
} %}

{% set weekly_tp_themes = {
  w3: {name: "Kickoff"},
  w4: {name: "Set direction"},
  w5: {name: "Gather requirements"},
  w6: {name: "Conceptualize the product"},
  w7: {name: "Do a practice iteration → " + version_practice, milestone: version_practice},
  w8: {name: "mid-" + version_first},
  w9: {name: version_first, milestone: version_first},
  w10: {name: "mid-" + version_penultimate},
  w11: {name: version_penultimate, milestone: version_penultimate},
  w12: {name: "mid-" + version_final},
  w13: {name: version_final, milestone: version_final}
} %}
