---
name: add-figure-or-table
description: Add a figure, image or table to a Samskrift LaTeX document. Use when the user attaches an image or chart to place in their paper, asks to insert a table of results, or wants a figure environment with caption, label and reference.
---

1. Find the project and the file where the figure or table belongs. Use
   `list_files`, then `read_file` to find the right section. Ask if the place
   is unclear.
2. For an image the user attached, upload it with `upload_asset` into the
   project's figures folder (use the existing one if there is one, for example
   `figures/` or `images/`; otherwise create `figures/`). Use a short,
   lowercase file name without spaces.
3. Check the preamble of the main file with `read_file`. Add
   `\usepackage{graphicx}` for images and `\usepackage{booktabs}` for tables
   if they are missing.
4. Insert the environment with `edit_file` at the chosen place:
   - Figures: `figure` with `[htbp]`, `\centering`, `\includegraphics` with a
     width relative to `\linewidth`, `\caption{...}` and then `\label{fig:...}`.
   - Tables: `table` with `[htbp]`, `\centering`, `\caption{...}`,
     `\label{tab:...}`, and a `tabular` using `\toprule`, `\midrule` and
     `\bottomrule` instead of vertical lines.
   Match the style of figures and tables already in the document when there
   are any.
5. Add a reference in the surrounding text, such as `Figure~\ref{fig:...}`,
   unless the user asked not to.
6. Call `compile_project` and fix any error your change caused.
7. Tell the user where you put it and how it is labelled.

Write captions from what the user told you. Do not invent data, numbers or
claims for a table or caption; ask instead.
