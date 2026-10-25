# Samskrift

Work on your [Samskrift](https://samskrift.com) LaTeX projects from Claude:
fix documents that won't compile, add figures and tables, and catch up on what
your co-authors changed and commented. Samskrift is a collaborative LaTeX
editor; every change Claude makes shows up live for your co-authors and in the
project's version history, so anything can be undone.

## Set up

1. Install the plugin, then open its **Connectors** tab and connect
   **Samskrift**.
2. Sign in with your Samskrift account and approve access. Claude can reach
   only the projects that account can reach.

## Use it

Ask in plain words, for example:

- "My thesis on Samskrift won't compile. Fix it."
- "Add the figure I attached to the results section of my paper and refer to
  it in the text."
- "What did my co-authors change in our paper this week, and which comments
  are still open?"

The plugin includes three skills that guide Claude through these jobs:

- **fix-latex-compile-errors**: compile, read the parsed errors, make the
  smallest fix, and recompile until the document builds.
- **add-figure-or-table**: upload an image or build a table, insert it with a
  caption and label, and reference it from the text.
- **catch-up-on-coauthors**: summarise recent edits, open comments and chat
  messages, and draft replies for you to approve.

## Data

The plugin connects Claude to your Samskrift account at
`https://samskrift.com/mcp`. Claude sends Samskrift the file contents, edits,
comments and messages it needs for the task you asked for, signed in as you.
The plugin itself stores nothing. Samskrift's handling of your data is
described in its [privacy policy](https://samskrift.com/privacy). Samskrift
never sends email on your behalf except when you invite a collaborator by
email.

## Support

Setup guide and full tool list: <https://samskrift.com/connect>.
Questions and help: <https://samskrift.com/faq>.
