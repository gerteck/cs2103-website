{% from "common/macros.njk" import embed_topic, get_date, thumb, show_as_tab, timing_badge with context %}
{% from "common/topics.njk" import panopto with context %}

#### {{ thumb(1) }} Demonstrate an assertion failure

* Task: Demonstrate an assertion failure using your tP code.
* Objective: to verify that assertions are being checked when you run the code locally.

Here are the steps:

1. Java assertions are not enabled by default.
   * If using Gradle to run your app, [check if your `build.gradle` has been updated to enable assertions](https://se-education.org/guides/tutorials/gradle.html#enabling-assertions).<br>
     If needed, update it as necessary.
   * If using Intellij's native features to run your app (i.e., `Gradle` is not selected in this [setting](https://se-education.org/guides/tutorials/images/gradle/intellijRunUsingGradle.png)), [check if you have enabled assertions in IntelliJ settings](https://se-education.org/guides/tutorials/intellijUsefulSettings.html).
1. Modify the code of your tP to deliberately cause an assertion failure<br>
   e.g., add `assert false;`{.java} somewhere in your code.
1. Run the code so that the application crashes with an assertion failure.
1. Take a ==screenshot that shows the assertion error message== and save it somewhere. During the tutorial, the tutor will ask you to paste it in the tutorial workspace document.


#### {{ thumb(2) }} Give examples of defensive programming

* Note down examples of _defensive programming_ from AB3 or your tP.<br>
  During the tutorial, the tutor will ask you for these examples.


#### {{ thumb(3) }} Review sample <tooltip content="Developer Guide">DG</tooltip> extracts

* Download the sample DG extracts in `T10-DG-Extracts.pdf` (in [Canvas/Files]({{ url_files }})/Handouts).
* Evaluate the given extract to find errors or areas to improve. Note them down (e.g., add comments to the PDF file).
* In particular, detect the following DG bugs (they are the same bugs against which your final DG will be evaluated).

{{ embed_topic("../../admin/tp-grading-bugs-fragment.md#architectureDiagramBugs", "Admin " + icon_embedding + " tP Grading → DG Bugs → Architecture Section → Possible Bugs", "3", indent="2", status="expanded", type="danger") }}
{{ embed_topic("../../admin/tp-grading-bugs-fragment.md#umlDiagramBugs", "Admin " + icon_embedding + " tP Grading → DG Bugs → UML Diagrams → Possible Bugs", "3", indent="2", status="expanded", type="danger") }}
{{ embed_topic("../../admin/tp-grading-bugs-fragment.md#generalDocBugs", "Admin " + icon_embedding + " tP Grading → General Documentation Bugs", "3", indent="2", status="expanded", type="danger") }}

* Also, lookout for places where these tips can be applied.

{{ embed_topic("../../admin/tp-deliverables-dg-fragment.md#dgTips", "Admin " + icon_embedding + " tP: Deliverables → DG → Tips", "3", indent="2", status="expanded", type="success") }}

* During the tutorial, the tutor will ask you for the observations you've noted down.
