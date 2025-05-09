{% from "common/macros.njk" import embed_topic with context %}

<box>

{{ icon_info }} **In UG/DG, using hierarchical section numbering and figure numbering is optional** (reason: it's not easy to do in Markdown), but make sure it does not inconvenience the reader (e.g., use section/figure title and/or hyperlinks to point to the section/figure being referred to). Examples:

>In the section [_Implementation_]() given above ...

<div tags="m--cs2103 m--cs2113">

**{{ course }}T does not require you to indicate author name of DG/UG sections** (CS2101 requirements may differ). We recommend (but not require) you to ensure that the code dashboard reflect the authorship of doc files accurately.
</div>

</box>

<div tags="m--cs2113">

* **Follow the [AddressBook-Level3 (AB3) UG]({{ url_ab3_upstream_website }}/UserGuide.html) structure**.
</div>

* The main content you add should be in the `docs/UserGuide.md` file (for ease of tracking by grading scripts).
* **Should cover all current features**.<br>
  **Ensure those descriptions match the product precisely**, as it will be used by {{ "peer" if has_pe }} testers (==inaccuracies will be considered bugs==).
* {{ optional }} **You can also cover future features**. Mark those as `Coming soon`.
* **It is not necessary for the UG to contain every nitty-gritty detail** about the product behavior. Some rarely needed information can be omitted from the UG, if the user is expected to know that information already or if the user is kept informed in other ways. %%For example, if a certain invalid input is unlikely to be used anyway, it is fine to not specify it in the UG, as long as the product is able to give an informative error message when that invalid input is used.%%
* **Refrain from overusing screenshots**. While it is good to have screenshots in the UG, note that they are hard to maintain. For example, if a future version changes the GUI slightly, it will require all your screenshots to be updated. Here are some tips:
  * In general, don't use more screenshots than necessary.
  * In some cases, you may want to crop the screenshot to show only the elements being discussed. That way, the screenshot doesn't need to be updated when other parts of the GUI is modified in a later version.
  * Don't use a higher resolution than necessary as it can increase the UG file size unnecessarily.

* Also note the following constraint:

  {{ embed_topic("tp-constraints.md#Constraint-File-Size", "Admin " + icon_embedding + " tP Constraints → Constraint-File-Size", "2", indent="1") }}

