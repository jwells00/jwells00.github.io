# Plain-Text Markdown Cheat Sheet

For quick, readable notes that still look clean in a plain text editor, the best Markdown subset focuses on structure over complex formatting. The goal is to avoid heavy, noisy markup like HTML or excessive symbols. 

Here is a recommended, highly readable subset:

---

## 1. Structure & Headers
Use ATX-style headers (hashes) for hierarchy. They are clear and easy to skim.
# Level 1 (Title)
## Level 2 (Section)
### Level 3 (Subsection)

**Markup:**
~~~
# Level 1 (Title)
## Level 2 (Section)
### Level 3 (Subsection)
~~~

---

## 2. Lists (The "Plain Text" Superpower)
Lists in Markdown are naturally readable.  You can use hyphens (-), asterisks (*), and pluses (+) to render unordered lists with bullet points the exact same way.  While they all work, choose one symbol for consistency throughout a document for better readability and maintainability.  Or, use different symbols to depict different levels of nesting to help visually distinguish levels in the plain text source.

**Unordered List**
- Use a hyphen followed by a space to denote the outer level bullet.
  * Use an asterisk preceded by two spaces to denote a second level sub-bullet.
    + Use a plus preceded by four spaces to denote a third level sub-bullet.
    + Blah
  * Blah
- Blah

**Markup:**
~~~
- Use a hyphen followed by a space to denote the outer level bullet.
  * Use an asterisk preceded by two spaces to denote a second level sub-bullet.
    + Use a plus preceded by four spaces to denote a third level sub-bullet.
    + Blah
  * Blah
- Blah
~~~

**Ordered List**
1) Use a number followed by a ")" or "." to start a an ordered list.
2) Blah
   * You can also next unordered lists
   * Blah
3) Blah
   a) Or you can nest ordered lists
   b) Blah

**Markup:**
~~~
1) Use a number followed by a ")" or "." to start a an ordered list.
2) Blah
   * You can also next unordered lists
   * Blah
3) Blah
   a) Or you can nest ordered lists
   b) Blah
~~~

---

## 3. Emphasis: Bold and Italic
Surround text with double asterisks for **bold text** and and single asterisks for *italic text*.

**Markup:**
~~~
Surround text with double asterisks for **bold text** and and single asterisks for *italic text*.
~~~

---

## 4. Horizontal Rules
Content blocks can be separated with lines.  These can be a indicated with as little as three dashes, or longer to look better in plain text:

---
Section heading with underline
---

-------------------------------------------------------------------------------
Section heading with underline
-------------------------------------------------------------------------------

**Markup:**
~~~
---
Section heading with underline
---

-------------------------------------------------------------------------------
Section heading with underline
-------------------------------------------------------------------------------
~~~

---

## 5. Code & Notes
**Code**
Use backticks (``) to highlight technical terms or file names `inline`.  Or use three tildes to show a code block list this:
~~~
python3 -c "print('Hello World')"
~~~

**Markup:**
~~~~
Use backticks (``) to highlight technical terms or file names `inline`.  Or use three tildes to show a code block list this:
~~~
python3 -c "print('Hello World')"
~~~
~~~~

**Blockquote**
> Use a ">" symbol to denote a blockquote.  These can be used for quotes or highlighting specific notes.
> It keeps the text wrapped together visually, and looks like an indented email reply. 

**Markup:**
~~~
> Use a ">" symbol to denote a blockquote.  These can be used for quotes or highlighting specific notes.
> It keeps the text wrapped together visually, and looks like an indented email reply. 
~~~

---

## 6. Other
**Links**
You can use `[Link Text](URL)` to depict hyperlinks that will be clickable when rendered in HTML, like this:

[Google](https://www.google.com)

**Markup:**
~~~
You can use `[Link Text](URL)` to depict hyperlinks that will be clickable when rendered in HTML, like this:

[Google](https://www.google.com)
~~~

**Example Note in Markdown**
---
# Meeting Notes - 2026-02-08

## Key Takeaways
* **Project Alpha** is ahead of schedule.
* _Remember_ to email the client regarding budget.

## Action Items
1.  [ ] Draft proposal
2.  [ ] Review code `v1.2`
3.  [ ] Send to team

> "The quick brown fox jumps over the lazy dog."
---
**Markup:**
---
~~~
# Meeting Notes - 2026-02-08

## Key Takeaways
* **Project Alpha** is ahead of schedule.
* _Remember_ to email the client regarding budget.

## Action Items
1.  [ ] Draft proposal
2.  [ ] Review code `v1.2`
3.  [ ] Send to team

> "The quick brown fox jumps over the lazy dog."
~~~
---

