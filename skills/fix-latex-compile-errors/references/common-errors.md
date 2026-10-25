# Common LaTeX errors and their usual fixes

| Error message (start) | Usual cause | Usual fix |
| --- | --- | --- |
| `Undefined control sequence` | A typo in a command, or a command from a package that is not loaded | Correct the spelling, or add the missing `\usepackage{...}` to the preamble |
| `Missing $ inserted` | Math such as `_`, `^` or `\alpha` used outside math mode, often an underscore in plain text | Wrap the math in `$...$`, or write `\_` for a literal underscore |
| `Environment ... undefined` | A typo in `\begin{...}`, or the package that defines the environment is missing | Fix the name or load the package (for example `amsmath` for `align`) |
| `\begin{...} ended by \end{...}` | Mismatched or misspelled environment names | Make `\begin` and `\end` match, and close environments in reverse order |
| `File '...' not found` | A wrong path in `\input`, `\include` or `\includegraphics`, or the file was never uploaded | Check the path with `list_files`; paths are relative to the main file. Ask the user if the file is missing |
| `Missing } inserted` / `Extra }, or forgotten $` | Unbalanced braces | Find the unmatched brace near the reported line |
| `Runaway argument?` / `Paragraph ended before ... was complete` | A missing closing brace in a command argument | Close the argument before the blank line |
| `Citation '...' undefined` | The key is missing from the `.bib` file or misspelled | Check the key with `search_project`; fix the spelling or ask the user for the reference |
| `Reference '...' undefined` | `\ref` to a label that does not exist | Fix the label name, or add the `\label` after the caption or section |
| `Package inputenc Error: Unicode character` | A character pdfLaTeX cannot typeset, often pasted symbols | Replace it with its LaTeX command, or switch to XeLaTeX or LuaLaTeX (ask first) |
| `Package fontspec Error` / `requires XeTeX or LuaTeX` | `fontspec` used with pdfLaTeX | Switch the engine to XeLaTeX or LuaLaTeX with `update_project` (ask first) |
| `Misplaced alignment tab character &` | `&` outside a table or alignment, often in text | Write `\&` in text |
| `Too many }'s` | An extra closing brace | Remove the extra brace near the reported line |
| `Option clash for package ...` | The same package loaded twice with different options | Load it once with all options combined |
| `LaTeX Error: Can be used only in preamble` | A preamble-only command (such as `\usepackage`) after `\begin{document}` | Move it above `\begin{document}` |
