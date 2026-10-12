# Web App Sources

This folder contains the Grade 5 curriculum PDFs and the options used by the
Subject, Term, Week, Learning Competency, and Suggested Activities dropdowns.

## Updating dropdown choices

Edit `lesson-options.js`, then reload `index.html` in the browser.

- Add or remove week choices in the `weeks` array.
- The Subject dropdown is built from the subject keys under `subjects`.
  Routine and school-event rows are listed separately under `scheduleItems`.
- Add supported term choices under a subject's `terms` array.
- Add competencies under `competenciesByTerm`, using the term number as the
  key (for example, `"1"`). Most subjects show competencies for the selected
  subject and term. English and Filipino show the combined competencies for
  all terms, regardless of the selected term.
- If a source does not provide competencies for a term, leave that term's
  array empty and explain the limitation in `termNotes`. Its competency
  dropdown will be disabled rather than showing choices from another term.
- Add subject-specific activities under that subject's `activities` array.
  EPP includes activity examples extracted from its PDFs; other subjects have
  subject-matched starter activities.
- Source PDF filenames are listed with each subject for reference.

Changing the subject or term refreshes the dependent dropdowns. Selections are
saved in the browser and restored when the page is reopened.

## Generate a weekly lesson workbook

Click **Generate Weekly Lesson** in the app toolbar to download a completed
copy of the `WEEKLY SUMMARY.xlsx` template. No file selection is required, and
the source template is not changed. Subject, term, week, daily competencies,
activities, and each day's notes are transferred into the workbook. Empty
schedule rows are omitted. Repeated lessons for the same subject, term, week,
and day are combined in their day cells. The export corrects the template's
last two repeated day headings to Day 4 and Day 5.
Only English, Filipino, Mathematics, Science, EPP, Araling Panlipunan, MAPEH,
and GMRC are included in generated lesson files. Routine and school-event
schedule items such as Flag Raising and Daily Routine are excluded.

The template is embedded in `weekly-summary-template.js` so the app can use it
when opened as a local file. If `WEEKLY SUMMARY.xlsx` is replaced, refresh the
embedded base64 template in that JavaScript file as well. Generation is
performed in the browser; app data is not uploaded.

## Generate a daily lesson summary

Choose a weekday from the **Day** dropdown beside **Generate Daily Lesson
Summary**, then click the button. The day dropdown follows the currently
selected weekday tab and can also be changed directly. The button downloads a
completed copy of `DAILY SUMMARY.xlsx` named for the selected weekday. The
selected day, subject, term, week, competencies, activities, and that day's
notes are included. Empty lesson rows are omitted, and repeated entries for
the same subject, term, and week are combined. The source workbook is not
changed.

The daily workbook template is embedded in `daily-summary-template.js` for
one-click use from a local app page. If `DAILY SUMMARY.xlsx` is replaced,
refresh the embedded template there as well.
