# Diary

## 2026-09-09 — Minimal redesign

Reduced the personal site from a five-page, sidebar-based layout to three
pages in a single centred column.

**Structure.** `index.html` is now the whole homepage: name, affiliation, a
two-sentence intro, the research list, and a footer linking onward.
`bio.html` (orphaned — nothing had linked to it), `contact.html` and
`writing.html` were deleted, their content either folded into the homepage
or dropped. `cv.html` was added to hold education, experience, and a mirror
of the research list. `public_goods.html` kept its content and lost its
sidebar.

**Research list.** Titles were shortened and the 2024 IMF–World Bank policy
brief removed at the user's direction. Abstracts, cut in the first pass as
"description", came back at the end as collapsed `<details>` toggles on the
two working papers only.

**Styling.** `style.css` was rewritten around a 620px column. Over the
session the green accent (`--accent`) was removed entirely: links now
inherit the body colour with a light grey underline, the treatment the
Project ACCESS link had been using. Headings are unbolded Palatino. The
portrait was pulled from the page but `profile.jpg` is still in the repo,
since the user said "for now".

**Dead ends.** Two worth remembering. A `\25B8` escape for the toggle caret
was mangled into a literal control byte on the way into the file and
rendered as tofu; the caret is now drawn with CSS borders, which depends on
no font. And when the user reported the name was not in Palatino, it already
was — serving the site locally and reading the computed style showed
`font-weight: 400` and the Palatino stack, and the deployed `style.css` was
current. The cause was almost certainly a cached stylesheet, so prefer
checking a render over re-editing CSS that already looks right.

**Open threads.** The research list is duplicated in `index.html` and
`cv.html`, so edits must be made in both — a Jekyll include would fix it and
was offered but not taken up. The footer email is the gmail address while
the user's CV heads with the DLSU one, left as-is deliberately.
