---
name: fix-latex-compile-errors
description: Fix a Samskrift LaTeX document that will not compile or compiles with errors. Use when the user says their paper, thesis, report or CV on Samskrift won't build, shows errors, has a broken PDF, missing references or undefined citations.
---

Goal: get the document compiling with the smallest possible changes, without
rewriting the author's content.

1. Find the project. If the user did not name one, call `list_projects` and
   ask which project when more than one could fit.
2. Call `compile_project`. It returns parsed errors and warnings with file and
   line numbers. If it succeeds with no errors, say so and stop.
3. For each error, starting with the first one (later errors are often caused
   by the first), call `read_file` with `line_start` and `line_end` about 15
   lines around the reported line. Use `search_project` when the cause may be
   in another file, such as a label, a macro or a bibliography key.
4. Look up the error message in `references/common-errors.md` for the usual
   cause and fix.
5. Fix it with `edit_file`, using exact search-and-replace edits that change
   only what is needed. Never use `write_file` to replace a whole file just to
   fix an error.
6. Call `compile_project` again. Repeat steps 3 to 6 for up to five rounds.
   Stop early if a round fixes nothing, and explain what is left.
7. Tell the user what you changed, file by file, in one line each. Mention
   that every edit is in the project's version history and can be undone with
   `restore_file_version`.

Rules:

- Do not change the document's wording, structure or style while fixing
  errors. If an error can only be fixed by a content decision (for example a
  missing figure file), ask the user instead of guessing.
- Leave warnings such as overfull boxes alone unless the user asks.
- If the document only fails with the current engine (for example `fontspec`
  needs XeLaTeX or LuaLaTeX), suggest switching with `update_project` and ask
  before doing it.
