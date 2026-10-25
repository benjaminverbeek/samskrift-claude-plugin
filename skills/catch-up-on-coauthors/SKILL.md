---
name: catch-up-on-coauthors
description: Summarise what changed in a shared Samskrift project and what co-authors are asking. Use when the user asks what their co-authors did, what changed recently, which comments are open, or wants to catch up after time away from a paper.
---

1. Find the project. If the user did not name one, call `list_projects` and
   ask when more than one shared project could fit.
2. Call `project_history` (raise `limit` when the user asks about a longer
   period). Group the edits by author and file.
3. For the files with the biggest changes, compare the current text from
   `read_file` with an earlier version from `read_file_version`, and describe
   what changed in content terms (for example "rewrote the related-work
   section", "added two references"), not as line counts.
4. Call `list_comments` for open review threads and `read_chat` for recent
   messages. Note who asked what, and which questions are addressed to the
   user.
5. Reply with a short summary: changes by author, open comments that need the
   user, and anything that looks unfinished.
6. Offer to draft replies. Post with `reply_to_comment`, `resolve_comment` or
   `send_chat_message` only after the user has approved the exact text. Chat
   messages and replies appear under the user's name, so end each one with
   "(via Claude)" unless the user says otherwise.
