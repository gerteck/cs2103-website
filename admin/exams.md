{% from "common/admin.njk" import show_admin_page with context %}
{% from "common/topics.njk" import panopto with context %}
{% from "common/macros.njk" import show_faq with context %}

{% call show_admin_page("exams") %}
<div id="main">


<p class="lead">There is no midterm exam. Information about the final exam (which counts for {{ marks_exam }}% of the final grade) is given below.</p>

{% if (current_week | int) < 8 %}
<box type="important">

Instructions below are from the previous semester. Will be updated closer to the exam.
</box>
{% endif %}


<div tags="m--cs2113">

* We will use Examplify for the final exam.
* The exam is **closed-book** (i.e., secure exam).
* However, the course textbook (pdf version) and UML reference sheet will be made available to you via the exam attachment.
* Permitted materials:<br>
  1 A4 sized cheat sheet.<br>
  NUS-approved calculator.

## Exam structure

The exam duration is 90 minutes.

The final exam has two types of questions:
1. MCQ questions - includes True/False like concept questions and some multiple choice/response questions
2. Short-answer questions

<br>

* All questions will be displayed at once as Examplify doesn't allow creating sections
* Based on the question you are answering, you need to manage your time appropriately
* Weightage of the questions will be displayed to help you with time management


## Exam briefing, mock exam, practice exam paper

* Please watch the [Examplify briefing video here](https://mediaweb.ap.panopto.com/Panopto/Pages/Viewer.aspx?id=48df9509-7daf-41f4-9ee8-ae22008a7383)
* [Examplify briefing slides](https://nus.atlassian.net/wiki/spaces/DAstudent/pages/22511667/Examplify+Student+Briefing+Slides); look for In-Person Assessment
* You will be given a practice exam paper (smaller than the full paper) to help you practice timing. That practice paper will be released at least one week before the exam.
</div>

<div tags="m--cs2103">
<include src="courseBriefings.md#exam-briefing-video" />

## Exam admin info to note



1. **Schedule/venue:** The final exam will be as per the normal exam schedule, which will be sent to you by the Registrar's Office (or you can find via EduRec -> Academics -> Exams -> View exam schedule). You can find the date/time from [NUSMODS](https://nusmods.com/modules/{{ course }}) as well.
1. **Scope:**
   * All topics in the textbook, excluding level 4 topics (i.e., optional topics), are examinable. For your convenience, you can view the examinable portion of the textbook in [this printable view of the textbook](../se-book-adapted/print.html) (same as the PDF version of the textbook provided to you).
   * In addition, you are expected to be aware of SE-related things (i.e., tools, techniques, concepts) encountered while dong the iP and the tP %%e.g., Was testing technique X used in the tP?%%.<br>
     That is, you are expected to strengthen your SE _knowledge_ (not just hands-on skills) as you do the course projects -- in particular, to be able to connect theory to practice.
1. **Mode: F2F, using Examplify**. You ==need to **bring your own device**== (<span class="text-danger">iPads not suitable</span>), which can connect to the NUS Wi-Fi network.<br>
  Please use these resources if you haven't used Examplify in the recent past (the behavior may be different from the version you used last semester):
   * See [NUS Guides on Examplify](https://nus.atlassian.net/wiki/spaces/DAstudent/overview).
   * Try a few practice exams provided in the above link.
   * Write to NUS CIT (citbox25@nus.edu.sg) if you run into any technical issues.
   * If you do not have a working laptop for the exam, please contact IT Care itcare@nus.edu.sg directly for a laptop loan (for exam purpose only).
1. ==**Examplify will use the full lock-down**== mode during the exam. That is, you will not be able to access Internet.
   That is, you will not be able to access any applications/files in your computer while you are doing the exam.<br>
   %%Reason: Because of the risk of locally-installed LLMs affecting the integrity of the exam, NUS recommends using full-lockdown mode.%%
1. **Consider this as a 'cheat-sheet' exam**, as that is the best match to the nature of the questions in this exam. However, you will have the following additional flexibilities:
   * **No limit on cheat-sheet page count.** You may bring any number of pages, and use any written/printed documents. %%For example, you may bring a printed copy of the entire textbook.%%
   * **An _exam reference_ PDF file will be available inside Examplify**, containing the full textbook, UML reference sheet, and the coding standard.
     * Caveat: Don't plan to refer to this file frequently. The Examplify UI is not optimized for quick opening/searching of big PDF files. So, use it only when your memory or the hard-copy cheat-sheets are not sufficient.
     * A copy of this file will be provided to you in advance (in Canvas/files/handouts), in case you want to use it during exam preparations.
1. **==You need to check the exam-compatibility of your device early==** (as given in the panel below) -- even if you have used Examplify for other exams before, as the Examplify behaviour varies based on the specific exam configuration -- and work with NUS CIT to resolve any issues you encounter.<br>
   Issues encountered by past students include problems in viewing and searching the _exam reference_ PDF file inside Examplify.

<div class="indented-level1">

<panel type="info" header="**How to check compatibility of your device**" expanded>

* **Ensure you have Examplify installed**{.text-info} in your exam device. {texts="['i.', 'ii.', 'iii.', 'iv.', 'v.']" t-class="fw-bold text-info"}
* **Ensure you have Adobe Acrobat Reader installed**{.text-info} in your exam device, as Examplify will be using that software to open PDF files.
* **Download the mock exam**{.text-info} we have provided. It has only three dummy questions, for you to get familiar with the exam mode.
* **Do the mock exam**{.text-info} (password: `Hello123`).<br>
  **Confirm you are able to open/resize/navigate/search the PDF file**{.text-info} we have provided as an attachment inside Examplify (this file can be accessed via the `EXAM CONTROLS` menu in the Examplify UI).
</panel>
<p/>
</div>

7. **Not required to record the screen**.
1. **Download all parts of the exam before you come to the exam** (i.e., parts 1, 2). We'll give you the password for opening each part at the exam, at the respective starting time of each part.<br>
  You will be notified when they are ready for download (typically, around 24 hours before the exam start time).
1. **If you have a doubt/query about a question**, or want to make an assumption about a question, please write it down in the 'NOTES' text box. ==Do not try to communicate those with the invigilator during the exam.== %%(reason: at an exam of this scale, it is not practical to clarify such doubts on-the-spot on a timely manner)%%. We'll take your doubt/query/assumption into account when grading. For example, if many had queries about a specific question, we can conclude that the question is unclear and omit it from grading.

<include src="exam-doubts-fragment.md" />

9. **Bring your computer fully charged**, although some charging points will be available at the exam venue (so, bring the charger too).

{{ show_faq("examSitNearChargingPoint") }}

10. **You must start the exam within 5 minutes of receiving the password**.


## Structure/format

<div tags="m--cs2103">

* The exam will be divided into 2 parts.
* Although the official duration of the exam is 1.5 hours, note that the actual exam might take up to 2 hours (due to technical issues). So, please don't schedule anything important right after the exam.

### Final exam - part 1

* You will be asked to draw some UML diagrams, **to be hand-drawn on paper** (not on a tablet).<br>
  You may use pencils if you wish.
* Duration: 20 minutes
* The questions will be in Examplify.
* **Bring 1-2 sheets of A4 size papers when you come to the exam:**
* These diagrams will not be graded directly. Instead, you will use them when answering part 2 of the exam.<br>
  However, we may use the diagrams to give _some_ consolation marks should you score very low in the corresponding MCQ questions.<br>
  For that purpose, the papers will be collected at the end of the full exam (i.e., after part 2 is over).
</div>
<div tags="m--cs2103">

### Final exam - part 2

* A quiz containing 32 MCQ questions. All questions are estimated to be equal size/difficulty.
* You only need to answer 30 questions correctly to get full marks. The extra two questions are there to cushion you against careless mistakes or misinterpreting a question.
* Questions will appear in random order.
* You #r#will not be able to go back to previous questions##.<br>

{{ show_faq("examWhyNoBackwardNavigation") }}

* Duration: **70 minutes** <span tags="m--cs2103">(recommended: allocate 2 minutes per question, which gives you a 6-minute buffer)</span>
* Most MCQ question have a short-answer follow-up question.
* Given below is an example question. The answer is `a` and the answer to the follow-up question can be `OOP is only one of the choices for an SE project`.
<div class="indented-level2">

<panel header="Sample question 1" expanded >

Choose the incorrect statement.

- ( ) a. Software engineering projects always use OOP.
- ( ) b. Some software engineering projects can be large and complex.
- ( ) c. Some software engineering projects can go on for many years.
- ( ) d. Software projects can involve people who are not software engineers.
- ( ) e. Software engineering projects can deliver the end product incrementally.

Why is it incorrect? ______

</panel>
<p/>
</div>

* Here is another example question. Note the ==[**SELECT ALL**]== at the start of the question text, which tells you that this question can have multiple correct answers, and you need to select all of them i.e., it is a checkbox type question<br>
The answer is `C`, `D`.

<div class="indented-level2">

<panel header="Sample question 2" expanded >

==[**SELECT ALL**]== Which of these are UML diagrams depicting behavior (as opposed to structure)?.

A. Class diagrams.<br>
B. Object diagrams.<br>
C. Activity diagrams.<br>
D. Sequence diagrams.<br>
E. Gantt charts.

</panel>
<p/>
</div>

</div>

## Exam preparation resources

{% set handouts_link = "[Canvas/files/handouts](" + url_files +"/folder/handouts)" %}

<box type="info" seamless>

The following exam resources will be **available from the start of week 13**.
</box>

<include src="courseBriefings.md#exam-briefing-video" />


* **A mock exam** (consisting of just a few questions), via Examplify.
  You can use it to get familiar with the quiz format that will be used for the final exam.
  Password: `Hello123`<br>
  Model answers are in {{ handouts_link }}.
* **A practice exam** of same format/length/difficulty as the actual exam will be available at least one week before the exam.<br>
  You can use it to practice your timing/pace. Multiple attempts are allowed.
    * Recommended:
        * Watch the exam briefing video and finish studying the topics before
          you attempt the practice exam, to get its full benefit.<br>
        * Do the mock exam (to get used to the software and question structure) before the practice exam.
    * Where to find it: on Examplify. Password: `Hello123`
    * Model answers are available on {{ handouts_link }}.
* **Some extra practice questions** for exam part 1 are in
  {{ handouts_link }} -- look for the file `Additional practice questions for part 1.pdf`
* **All weekly quizzes** will be reopened on [Canvas Quizzes]({{ url_canvas_home }}/quizzes).
  You can retake them to self-test your knowledge (note: retaking them will not affect participation marks).
* **Recordings of all tutorial Zoom sessions** should be available in a file named `Recordings.docx` inside
  your tutorial group's MS Team (in the 'Files' section). Remind your tutor to update that file if recording
  links are missing.
* **Recordings of all weekly briefings** are available on the [Canvas home page]({{ url_canvas_home }}).
* **The _Topics Overview_ video** given below explains how course topics fit into a big picture, and as a bonus, touches on some exam-like questions as well.

<include src="courseBriefings.md#topics-video" />

* **PDF files useful for the exam** (given in {{ handouts_link }}):
  * Exam Reference PDF
  * Topics infographic (shows how the various topics fit into the big picture)

{{ show_faq("examMorePastPapersAndAnswers") }}

</div>

</div>

{% endcall %}
