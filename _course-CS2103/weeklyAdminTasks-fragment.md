{% from "common/macros.njk" import get_date with context %}

{% set weekly_admin_tasks = {
week1: [
  {id: 'submit_pre_course_survey', deadline: get_date(date_w1_start, 4), graded: true},
  {id: 'learn_about_the_course'},
  {id: 'submit_pre_lecture_quiz', deadline: get_date(date_w1_start, 7), graded: true},
  {id: 'set_up_tools', deadline: get_date(date_w1_start, 4, time="") },
  {id: 'follow_the_git_learning_trail'}
],
week2: [
  {id: 'submit_first_post_lecture_quiz', deadline: get_date(date_w2_start, 4, time=time_lecture_start), graded: true},
  {id: 'get_connect_with_comm_channels'}
],
week3: [
  {id: 'submit_post_lecture_quiz', graded: true},
  {id: 'form_teams'}
],
week4: [
  {id: 'accept_github_invitations', graded: true},
  {id: 'submit_post_lecture_quiz', graded: true}
],
week5: [
  {id: 'submit_post_lecture_quiz', graded: true},
  {id: 'practice_peer_evaluations_on_TEAMMATES', deadline: get_date(date_w5_start, 3), graded: true}
] if semester == 'AY2425S2' else [
  {id: 'submit_post_lecture_quiz', graded: true},
  {id: 'submit_midterm_feedback_for_the_course', deadline: get_date(date_w5_start, 5), deadline_type: 'info'},
  {id: 'practice_peer_evaluations_on_TEAMMATES', deadline: get_date(date_w5_start, 3), graded: true}
],
week6: [
  {id: 'submit_midterm_feedback_for_the_course', deadline: get_date(date_w6_start, 5), deadline_type: 'info'},
  {id: 'submit_post_lecture_quiz', graded: true}
] if semester == 'AY2425S2' else [
  {id: 'submit_post_lecture_quiz', graded: true}
],
week7: [
  {id: 'submit_post_lecture_quiz', graded: true}
],
week8: [
  {id: 'submit_post_lecture_quiz', graded: true},
  {id: 'submit_midterm_peer_evaluations', deadline: get_date(date_w8_start, 6), graded: true}
],
week9: [
  {id: 'submit_post_lecture_quiz', graded: true}
],
week10: [
  {id: 'submit_post_lecture_quiz', graded: true},
  {id: 'join_catcher_load_testing', graded: true, deadline: "during the briefing on " + get_date(date_w10_start, 4, format="MMM Do", time=""), deadline_type: 'danger'}
],
week11: [
  {id: 'submit_post_lecture_quiz', graded: true}
] if pe_schedule_late else [
  {id: 'submit_post_lecture_quiz', graded: true},
  {id: 'submit_pe_mode_selection', deadline: "COMPULSORY | " + get_date(date_w11_start, 5), deadline_type: 'danger'}
],
week12: [
  {id: 'submit_reuse_declaration', deadline: "COMPULSORY | " + get_date(date_w13_start, 1), deadline_type: 'danger', graded: true},
  {id: 'submit_pe_mode_selection', deadline: "COMPULSORY | " + get_date(date_w12_start, 5), deadline_type: 'danger'},
  {id: 'submit_feedback_for_tutors'}
] if pe_schedule_late else [
  {id: 'submit_reuse_declaration', deadline: "COMPULSORY | " + get_date(date_w13_start, 1), deadline_type: 'danger', graded: true},
  {id: 'submit_feedback_for_tutors'},
  {id: 'submit_final_peer_evaluations', deadline: get_date(date_w12_start, 3), graded: true},
  {id: 'submit_pe_readiness_quiz', deadline: "before the PE", deadline_type: 'danger', graded: true}
],
week13: [
  {id: 'submit_final_peer_evaluations', deadline: get_date(date_w13_start, 3), graded: true},
  {id: 'submit_pe_readiness_quiz', deadline: "before the PE", deadline_type: 'danger', graded: true}
] if pe_schedule_late else []
} %}
