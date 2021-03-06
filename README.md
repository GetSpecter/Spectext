# Specdown

## Just A Markdown Flavor

Specdown combines the [original markdown specification](http://daringfireball.net/projects/markdown/) created by John Gruber, the latest and greatest flavors of markdown, various other lightweight markup languages, and new syntax for semantic notation and improved machine readability. Specdown seeks to provide the most complete set of syntax while considering both backward compatibility and future need. While Specdown may stray from full backward compatability, it is with the goal of improving speed, usability, and readability.


Try the live demo at [http://specdown.org](http://specdown.org)

---

Table of Contents
-----------------

- [Syntax Cheatsheet](#syntax-cheatsheet)
- [Syntax Details](#syntax-details)

---

Syntax Cheatsheet
-----------------

<table>
<tr>
<th>description</th>
<th>specdown</th>
</tr>

<tr>
<td><a href="#escaped-characters">escaped characters</a></td>
<td><pre>
\*
</pre></td>
</tr>

<tr>
<td><a href="#comments">comments</a></td>
<td><pre>
/// comment ///
///! comment ///
</pre></td>
</tr>

<tr>
<td><a href="#phrase-formattings">phrase formattings</a></td>
<td><pre>
*bold*           ~italic~        _underline_
**strong**       ~~strike~~
***emphasis***   ~~~mark~~~
^superscript^    ^^subscript^^
</pre></td>
</tr>

<tr>
<td><a href="#headers">headers</a></td>
<td><pre>
Header One
==========

Header Two
----------

# Header One
## Header Two
### Header Three
#### Header Four
##### Header Five
###### Header Six

#(!anchor) Header
</pre></td>
</tr>

<tr>
<td><a href="#horizontal-rules">horizontal rules</a></td>
<td><pre>
---
***
</pre></td>
</tr>

<tr>
<td><a href="#blockquotes">blockquotes</a></td>
<td><pre>
>! cite
> text
> text
</pre></td>
</tr>

<tr>
<td><a href="#details">details</a></td>
<td><pre>
&lt;! summary
&lt; text
&lt; text
</pre></td>
</tr>

<tr>
<td><a href="#unordered-lists">unordered lists</a></td>
<td><pre>
- item
- item
- item
</pre></td>
</tr>

<tr>
<td><a href="#ordered-lists">ordered lists</a></td>
<td><pre>
1. item
2. item
3. item
</pre></td>
</tr>

<tr>
<td><a href="#definition-lists">definition lists</a></td>
<td><pre>
: term
:: definition
:: definition
</pre></td>
</tr>

<tr>
<td><a href="#task-lists">task lists</a></td>
<td><pre>
- [ ] item
- [x] item
</pre></td>
</tr>

<tr>
<td><a href="#nested-lists">nested lists</a></td>
<td><pre>
- item
  - sub item
  - sub item
- item
  - sub item

1. item
  1. sub item
  2. sub item
2. item
  1. sub item

- item
  1. sub item
  2. sub item

1. item
  - sub item
  - sub item
</pre></td>
</tr>

<tr>
<td><a href="#spans">spans</a></td>
<td><pre>
[text]
</pre></td>
</tr>

<tr>
<td><a href="#links">links</a></td>
<td><pre>
[text](url title)
[text](email title)
[text](!anchor title)
[text][reference]
[reference][]

[reference]: url title
[reference]: email title
[reference]: !anchor title

[[url]]
[[email]]
[[!anchor]]
[[[url_to_parse]]]
[[[!anchor_to_parse]]]
</pre></td>
</tr>

<tr>
<td><a href="#images">images</a></td>
<td><pre>
![alt](url title width height)
![alt][reference]
![reference][]

![reference]: url title width height
</pre></td>
</tr>

<tr>
<td><a href="#macros">macros</a></td>
<td><pre>
%[alt](type args)
%[alt][reference]
%[reference][]

%[reference]: type args
</pre></td>
</tr>

<tr>
<td><a href="#citations">citations</a></td>
<td><pre>
@[reference]
@reference

@[reference]: type args
</pre></td>
</tr>

<tr>
<td><a href="#notes">notes</a></td>
<td><pre>
&[reference]
&reference

&[reference]: note
</pre></td>
</tr>

<tr>
<td><a href="#variables">variables</a></td>
<td><pre>
$[reference]
$reference

$[reference]: value
</pre></td>
</tr>

<tr>
<td><a href="#abbreviations">abbreviations</a></td>
<td><pre>
+[abbreviation]: expansion
</pre></td>
</tr>

<tr>
<td><a href="#tables">tables</a></td>
<td><pre>
| header | header | header |
| :----- | :----: | -----: |
| left   | center |  right |
</pre></td>
</tr>

<tr>
<td><a href="#metas">metas</a></td>
<td><pre>
{{{ data }}}
{{{! data }}}
</pre></td>
</tr>

<tr>
<td><a href="#classes">classes</a></td>
<td><pre>
#&lt;class&gt; Header
#(!anchor)&lt;class&gt; Header

---&lt;class&gt;
*****&lt;class&gt;

>!&lt;class&gt; cite

>&lt;class&gt; text

&lt;!&lt;class&gt; summary


-&lt;&lt;class&gt; item
-&lt;class&gt; item

1.&lt;&lt;class&gt; item
2.&lt;class&gt; item

:&lt;&lt;class&gt; term
  :&lt;class&gt; definition

[text]&lt;class&gt;

[text](url title)&lt;class&gt;
[text][reference]&lt;class&gt;

![alt](url title width height)&lt;class&gt;
![alt][reference]&lt;class&gt;

@[reference]&lt;class&gt;

&[reference]&lt;class&gt;

| header | header | header |&lt;&lt;class-table&gt;
| ------ | ------ | ------ |
| col    | col    | col    |&lt;class-row&gt;

</pre></td>
</tr>

</table>

---

Syntax Details
--------------

- [Escaped Characters](#escaped-characters)
- [Comments](#comments)
- [Paragraphs](#paragraphs)
- [Phrase Formattings](#phrase-formattings)
- [Headers](#headers)
- [Horizontal Rules](#horizontal-rules)
- [Blockquotes](#blockquotes)
- [Details](#details)
- [Unordered Lists](#unordered-lists)
- [Ordered Lists](#ordered-lists)
- [Task Lists](#task-lists)
- [Definition Lists](#definition-lists)
- [Nested Lists](#nested-lists)
- [Links](#links)
- [Automatic Links](#automatic-links)
- [Images](#images)
- [Macros](#macros)
- [Citations](#citations)
- [Notes](#notes)
- [Variables](#variables)
- [Abbreviations](#abbreviations)
- [Inline Codes](#inline-codes)
- [Block Pre Codes](#block-pre-codes)
- [Inline Samples](#inline-samples)
- [Block Pre Samples](#block-pre-samples)
- [Tables](#tables)
- [Metas](#metas)
- [Spans](#spans)
- [Classes](#classes)

### Escaped Characters
- Any non whitespace special character can be escaped with `\` to markup the ascii representation and remove its Specdown meaning.
- Applied to escaped characters anywhere, without exception. Including pre and comments.

###### specdown
```
\*Actual asterisk surrounded text\*
```
###### markup
```
&#42;Actual asterisk surrounded text&#42;
```


### Comments
- Pairs of three or more `/` will be removed from markup.
- Pairs of three or more `/` with a `!` will be markuped to a html comment.
- Can be applied inline or block.
- Can be used inside of words.
- Pairs of n or more `/` can be used to comment n or less `/`.
- Applied anywhere, without exception. Including pre.

###### specdown
```
Hide /// the comment /// from this sentence.

///
Hide this block.
///

Put in a ///! comment ///

///!
Comment block
///

Comment out three //// /// //// slashes
```
###### markup
```
Hide  from this sentence.


Put in a <!-- comment -->

<!--
Comment Block
-->

Comment out three  slashes
```


### Paragraphs
- Text preceeded and proceeded by a blank line or block syntax will be wrapped in a paragraph.
- Line returns without following whitespace will be treated as breaks within a single paragraph.
- Text within pre block syntax or comment syntax should not be markuped.
- A blank line is a line that appears to be blank. This includes lines with no characters, lines with only spaces and tabs, and the start and end of a file.
- Note: diverges from daringfireball by not allowing "hard-wrapped" text paragraphs.

###### specdown
```
The first paragraph

This is one paragraph
with a manual break inserted
```
###### markup
```
<p>
The first paragraph
</p>

<p>
This one paragraph
<br />
with a manual break inserted
</p>
```


### Phrase Formattings
- Phrase formatting can be nested inside of other syntax, including other phrase formattings.
- Phrase formatting is only translated when both starting and ending syntax is found in the same line.
- Phrase formatting can contain multiple words on the same line.
- Phrase formatting can be inside of words, with the exception of underline.
- Opening phrase formatting proceeded by whitespace and closing phrase formatting preceeded by whitespace will not be translated as phrase formatting.
- Note: diverges almost completely from daringfireball.

###### specdown
```
*bold*  **strong**  ***emphasis***
~italic~  ~~strikethrough~~  ~~~mark~~~~
~*italic bold*~
^superscript^  ^^subscript^^
_underline_
some_file_name
some_file_ name
put a * in the **
```
###### markup
```
<b>bold</em>  <strong>strong</strong>  <em>emphasis</em>
<i>italic</i>  <strike>strikethrough</strike>  <mark>mark</mark>
<i><b>italic bold</b></i>
<sup>superscript</sup>  <sub>subscript</sub>
<u>underline</u>
some_file_name
some_file_ name
put a * in the **
```


### Headers
- Lines of text with 3 or more `=` alone on the proceeding line will be markuped to h1 tags.
- Lines of text with 3 or more `-` alone on the proceeding line will be markuped to h2 tags.
- Lines of text beginning with 1 or more `#` will be markuped to h tags with level indicated by the number of `#`.
- Headers are automatically given internal anchor links based on header text, or can be manually defined.
- Headers with identical header text will be given unique numbered anchors based on header text.
- Note: diverges from daringfireball by not markuping trailing `#`.

###### specdown
```
Header 1
========

Header 2
--------

# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6

##(!anchor) Header 2
##<class> Header 2
##(!anchor)<class> Header 2
```
###### markup
```
<h1><a name="header-1">Header 1</a></h1>

<h2><a name="header-2">Header 2</a></h2>

<h1><a name="header-1">Header 1</a></h1>
<h2><a name="header-2-2">Header 2</a></h2>
<h3><a name="header-3">Header 3</a></h3>
<h4><a name="header-4">Header 4</a></h4>
<h5><a name="header-5">Header 5</a></h5>
<h6><a name="header-6">Header 6</a></h6>

<h2><a name="anchor">Header 2</a></h2>
<h2 class="class"><a name="header-2-3">Header 2</a></h2>
<h2 class="class"><a name="anchor-2">Header 2</a></h2>
```


### Horizontal Rules
- Three or more `-` or `*` on a line, alone, will create a horizontal rule. 
- Note: diverges from daringfireball by not allowing `-` and `*` to be seperated by spaces.

###### specdown
```
---

***

------------

*********

---<class>

*****<class-one class-two>
```
###### markup
```
<hr />

<hr />

<hr />

<hr />

<hr class="class" />

<hr class="class-one class-two" />
```


### Blockquotes
- Blockquotes can be nested as needed and can contain any other syntax.
- All lines of a blockquote must begin with `>`.
- `>>` can be used to signify the end of a blockquote, including nested blockquotes, to avoid translation errors.
- One are more blank lines between blockquote lines will markup the lines as difference blockquotes.
- Blockquotes can be nested a max of 10 times.
- Note: diverges from daringfireball by requiring that all lines of a blockquote begin with `>`.

###### specdown
```
> Paragraph one
> 
>> Second paragraph

>! cite 
> Block Quote
> with citation

> level one
> >! cite
> > level two
> > also level two
> back on level one
> >> level two again
> > level two, but not the same as the above line

>!<class> cite
> block quote

><class-one class-two> block quote
```
###### markup
```
<blockquote>
<p>
Paragraph one
</p>
<p>
Second paragraph
</p>
</blockquote><!-- -->

<blockquote cite="cite">
<p>
Block Quote<br />
with citation
</p>
</blockquote>

<blockquote>
<p>
level one
</p>
<blockquote cite="cite">
<p>
level two<br />
also level two
</p>
</blockquote>
<p>
back on level two
</p>
<blockquote>
<p>
level two again
</p>
</blockquote><!-- -->
<blockquote>
<p>
level two, but not the same as the above live
</p>
</blockquote>
</blockquote>

<blockquote class="class" cite="cite">
<p>
block quote
</p>
</blockquote>

<blockquote class="class-one class-two">
<p>
block quote
</p>
</blockquote>
```


### Details
- The first line of a details must include `!` and will always be used as its summary.
- All lines of a details must begin with `<`.
- `<<` can be used to signify the end of a details, including nested details, to avoid translation errors. 
- One are more blank lines between details lines will markup the lines as difference details.
- Detail blocks can be nested up to 10 times and can contain any other syntax.

###### specdown
```
<! summary
< Paragaph One
<
< Second Paragraph

<!<class-one class-two> summary
< Paragraph One
```
###### markup
```
<details>
<summary>summary</summary>
<p>
Paragraph One
</p>
<p>
Second Paragraph
</p>
</details>

<details class="class-one class-two">
<p>
Paragraph One
</p>
</details>
```


### Unordered Lists
- A `- `, `* `, or `+ ` followed by text will be markuped to an unordered lists. 
- Multiple line list items will be translated into paragraphs.
- Lists should be followed by two or more blankish lines to signify the list end.
- Two or more blankish lines between list items will be markuped as two seperate lists.
- `<class>` is markuped on the li and cannot be used with `<<class>`.
- `<<class>` is markuped on the ul and can only be used on the first list item.

###### specdown
```
- Item
- Item
- Item


* Item

* Item
   
  With a second paragraph
* Item


+<<class-one class-two> Item
+ Item
+<class> Item
```
###### markup
```
<ul>
<li>Item</li>
<li>Item</li>
<li>Item</li>
</ul>


<ul>
<li>
<p>
Item
</p>
</li>
<li>
<p>
Item
</p>
<p>
With a second paragraph
</p>
</li>
<li>Item</li>
</ul>


<ul class="class-one class-two">
<li>Item</li>
<li>Item</li>
<li class="class">Item</li>
</ul>
```


### Ordered Lists
- Numbering does not need to be unique or sequential.
- The first number will be used as the starting value of the list.
- Multiple line list items will be translated into paragraphs.
- Lists should be followed by two or more blankish lines to signify the list end.
- Two or more blankish lines between list items will be markuped as two seperate lists.
- `<class>` is markuped on the li and cannot be used with `<<class>`.
- `<<class>` is markuped on the ol and can only be used on the first list item.

###### specdown
```
1. One
2. Two
3. Three


50. Fifty
34. Fifty One
34. Fifty Two


1.<<class-one class-two> One
2. Two
3.<class> Three
```
###### markup
```
<ol>
<li>One</li>
<li>Two</li>
<li>Three</li>
</ol>


<ol start="50">
<li>Fifty</li>
<li>Fifty One</li>
<li>fifty Two</li>
</ol>


<ol class="class-one class-two">
<li>One</li>
<li>Two</li>
<li class="class">Three</li>
</ol>
```


### Task Lists
- Task lists can be used with any list type and can be used with nested lists.
- Task lists use checkbox type input tags, and require CSS for correct visual display.

###### specdown
```
- [ ] Task 1
- [x] Task 2
- [ ] Task 3
  1. [x] Sub Task 1
  2. [x] Sub Task 2
  3. [ ] Sub Task 3
```
###### markup
```
<ul>
<li><input type="checkbox" /> Task 1</li>
<li><input type="checkbox" checked /> Task 2</li>
<li><input type="checkbox" /> Task 3
<ol>
<li><input type="checkbox" checked /> Sub Task 1</li>
<li><input type="checkbox" checked /> Sub Task 2</li>
<li><input type="checkbox" /> Sub Task 3</li>
</ol>
</li>
</ul>
```


### Definition Lists
- `:` will be markuped to a definition term.
- `::` will be markuped to a definition definition. 
- A term may have multiple definitions.
- Multiple line list items will be translated into paragraphs.
- Lists should be followed by two or more blankish lines to signify the list end.
- Two or more blankish lines between list items will be markuped as two seperate lists.
- `<class>` is markuped on the dt or dd and cannot be used with `<<class>`.
- `<<class>` is markuped on the dl and can only be used on the first list item.

###### specdown
```
: Term One
:: Definition
: Term Two
:: Definition One
  
   With a second paragraph.
:: Definition Two


:<<class-one class-two> Term
:: Definition
::<class> Definition
:<class> Term
:: Definition
```
###### markup
```
<dl>
<dt>Term One</dt>
<dd>Definition</dd>
<dt>Term Two</dt>
<dd>
<p>
Definition One
</p>
<p>
With a second paragraph.
</p>
</dd>
<dd>Definition Two</dd>
</dl>


<dl class="class-one class-two">
<dt>Term</dt>
<dd>Definition</dd>
<dd class="class">Definition</dd>
<dt class="class">Term</dt>
<dd>Definition</dd>
</dl>
```


### Nested Lists
- All list types may be nested in each other.
- Indention depth is dynamically sensed and applied based on first indention whitespace.
- Indention depth is rounded up for non-multiples of first indention.
  - Example: First indent is 2 spaces and sets the depth deliminator. An indent of 3 or 4 spaces would have a depth of 2.

###### specdown
```
- Item
  1. One
  2. Two
- Item
  - Sub Item
    1. One
    2. Two
- Item
```
###### markup
```
<ul>
<li>Item
<ol>
<li>One</li>
<li>Two</li>
</ol>
</li>
<li>Item
<ul>
<li>Sub Item
<ul>
<li>One</li>
<li>Two</li>
</ul>
</li>
</ul>
<li>
<li>Item</li>
</ul>
```


### Links
- `[linked text](url title)` will be markuped to a tags.
- `[linked text][linkReference]` will be markuped to a tags.
- `[[url]]` or `[[email]]` will be markuped to a tags.
  - Must contain atleast one non-whitespace character
- `[[[url]]]` or `[[[email]]]` will be parsed on `_` and will be markuped to a tags.
  - Must contain atlease one non-whitespace character
- `[linkReference]: url title` will be removed from markup, but used to define a link reference.
  - Must be at start of new line.
- Links must be preceeded by whitespace or line start.
- Urls can be absolute or relative, and will be automatically uri encoded.
- Urls containing whitespace should be wrapped in single or double quotes.
- Emails are automatically markuped to ascii decimal encoding.
- Urls beginning with `!` will define an anchor.
- Urls beginning with `#` will link to an anchor.
- Title is optional, and linked text will be used if not explicitly defined.
- Note: diverges from daringfireball by not allowing `()` to surround titles.
- Note: diverges from daringfireball by not allowing multi-line references.
- Note: diverges from daringfireball by using `[[]]` instead of `<>` for automatic links.

###### specdown
```
[text](url)
[text](url "Title")

[text](!anchor title)
[text](#anchor "long title")

[text][reference]
[reference][]
[reference]: url 'long title'

[[url]]
[[[auto_parsed_url]]]
[[!anchor]]
[[#anchor]]
[[[parsed_url#anchor]]]


[text](url title)<class>
[text][reference]<class-one class-two>
[[url]]<class>
```
###### markup
```
<a href="url">text</a>
<a href="url" title="Title">text</a>

<a name="anchor" title="title">text</a>
<a href="#anchor" title="long title">text</a>

<a href="url" title="long title">text</a>
<a href="url" title="long title">text</a>

<a href="url">url</a>
<a href="auto/parsed/url">auto parsed url</a>
<a name="anchor">anchor</a>
<a href="#anchor">anchor</a>
<a href="parsed/url#anchor">parsed url anchor</a>

<a class="class" href="url" title="Title">text</a>
<a class="class-one class-two" href="url" title="long title">text</a>
<a class="class" href="url">url</a>
```


### Automatic Links
- Absolute urls and email addresses will be automatically markuped to a tags.
- Links must be preceeded by whitespace.
- Urls are automatically url encoded.
- Emails are automatically ascii decimal encoded.

###### specdown
```
Go to index.html
Go to http://url.com
Email addr@email.com
```
###### markup
```
Go to index.html
Go to <a href="http://url.com">http://url.com</a>
Email <a href="mailto:&#97;&#100;&#100;&#114;&#64;&#101;&#109;&#97;&#105;&#108;&#46;&#99;&#111;&#109;" title="&#97;&#100;&#100;&#114;&#64;&#101;&#109;&#97;&#105;&#108;&#46;&#99;&#111;&#109;">&#97;&#100;&#100;&#114;&#64;&#101;&#109;&#97;&#105;&#108;&#46;&#99;&#111;&#109;</a>
```


### Images
- `![alt text](url title width height)` will be markuped to img tags.
- `![alt text][imageReference]` will be markuped to img tags.
- `![imageReference][]` will be markuped to img tags.
- `![imageReference]: url title width height` will be removed from markup, but will define an image.
- urls can be absolute or relative.
- title, width, and height are optional.
- Usage of an undefined imageReference will be markuped to img tags with only alt text.

###### specdown
```
![alt text](url title)
![alt text](url "Title" 350px 100%)
![alt text](url '' 100%)

![alt text][reference]
![reference][]
![reference]: url "Title Long" width height

![alt text](url)<class>
![alt text][reference]<class>
```
###### markup
```
<img src="url" title="title" alt="alt text" />
<img src="url" title="Title" alt="alt text" width="350px" height="100%" />
<img src="url" alt="alt text" width="100%" />

<img src="url" title="Title Long" alt="alt text" width="width" height="height" />

<img src="url" class="class" alt="alt text" />
<img src="url" class="class" title="Title Long" alt="alt text" width="width" height="height" />
```


### Macros
- `%[alt text](macro arg1 ...)` will be markuped depending on the macro.
- `%[alt text][macroReference]` will be markuped depending on the macro.
- `%[macroReference][]` will be markuped depending on the macro.
- `%[macroReference]: macro arg1 ...` will be removed from markup, but will define a macro.
- Macros can be used to embed video, other media, or custom markups.
- Usage of an undefined or invalid macroReference will be markuped to the alt text.
- The first argument must be the macro name. 
- Any number and type of arguments can be included after the first argument depending on the macro.
- Macros do not support class syntax.

###### specdown
```
%[alt text](macro arg1 arg2 arg3 ...)

%[alt text][reference]
%[reference][]
%[reference]: macro arg1 arg2 arg3 arg4
```
###### markup
```
varied based on macro

varied based on macro
varied based on macro
```


### Citations
- `@[citationReference]` will be markuped to a superscript numbered anchor linked to the citation in page.
- `@citationReference` will be markuped to a superscript numbered anchor linked to the citation in page.
- `@[citationReference]: type arg1 ...` will be markuped depending on type, and will define a citation.
- Citation references must be placed together in the document where they should be displayed and will be translated as a list.
- Citation reference names must begin with an alphanumeric character, contain no spaces, and are case sensative.
- Citation references list is given a `citations` class.
- Citation sup tags are given a `citation` class.
- Citations are automatically numbered based on list order. 
- Any number and type of arguments can be included after the first argument depending on the citation type.
- If the first argument in a citation reference is a known type of citation its arguments will be used to autoformat a citation in MLA. 
- If the first argument is not a known citation type, the string will be used directly.

###### specdown
```
This sentence is from something trustworthy @[refOne]. 
This sentence is way less trustworthy @refTwo.
Yeah for classes @[refOne]<class-one class-two>.

@[refOne]: type arg1 arg2
@[refTwo]: type arg1 arg2 arg3
@[refThree]: A preformated citation
```
###### markup
```
This sentence is from something trustworthy<sup class="citation"><a href="#cite-1" title="bibliography">1</a></sup>. 
This sentence is way less trustworthy<sup class="citation"><a href="#cite-2" title="bibliography">2</a></sup>.
Yeah for classes<sup class="citation class-one class-two"><a href="#cite-1" title="bibliography">1</a></sup>.

<ol class="citations">
<li><a name="cite-1">bibliography based on type</a></li>
<li><a name="cite-2">bibliography based on type</a></li>
<li><a name="cite-3">A preformatted citation</a></li>
</ol>
```


### Notes
- `&[noteReference]` will be markuped to a superscript numbered anchor linked to the note in page.
- `&noteReference` will be markuped to a superscript numbered anchor linked to the note in page.
- `&[noteReference]: note text` will be markuped as a list, and will define a citation.
- Note references must be placed together in the document where they should be displayed and will be translated as a list.
- Note reference names must begin with an alphanumeric character, contain no spaces, and are case sensative. 
- Notes are automatically numbered based on list order.
- Note references list is given a `notes` class.
- Note sup tags are given a `note` class.

###### specdown
```
This sentence needs a note &[refOne]. 
This sentence also needs a note &refTwo. 
This sentence gets a fancy note &[refTwo]<class-one>.

&[refOne]: note text
&[refTwo]: note text
```
###### markup
```
This sentence needs a note<sup class="note"><a href="#note-1" title="note text">1</a></sup>.
This sentence also needs a note<sup class="note"><a href="#note-2" title="note text">2</a></sup>.
This sentence gets a fancy note<sup class="note class-one"><a href="#note-2" title="note text">2</a></sup>.

<ol class="notes">
<li><a name="note-1">note text</a></li>
<li><a name="note-2">note text</a></li>
</ol>
```


### Variables
- `$[variableName]` will be markuped to the variable value, or variable name if definition not found.
- `$variableName` will be markuped to the variable value, or left alone if definition not found.
- `$[variableName]: variable value` will be removed from markup, but used to define a variable.
- Variable definitions can be anywhere in the markdown and will be markuped before any variable usage.
- Variable definitions are case sensative.
- Duplicate variable definitions will overwrite previous values.

###### specdown
```
Current version $[variable]
Current version $variable

$[variable]: value
```
###### markup
```
Current version value
Current version value
```


### Abbreviations
- Defined abbreviations used in text are automatically markuped and do not need special markdown.
- `$[abbreviation]: full` will be removed from markup, but used to define an abbreviation.
- Abbreviation definitions can be anywhere in the markdown and will be markuped before any usage.
- Abbreviation definitions are case sensative and can contain multiple words and spaces.
- Duplicate abbreviation definitions will overwrite previous values.

###### specdown
```
The HTML specification
The Primary Standard is good

+[HTML]: Hyper Text Markup Language
+[Primary Standard]: Main Standard
```
###### markup
```
The <abbr title="Hyper Text Markup Language">HTML</abbr> specification
The <abbr title="Main Standard">Primary Standard</abbr> is good
```


### Inline Codes
- Pairs of one or more backticks on the same line will be markuped to code tags. 
- Pairs of n backticks can contain groups of less than n backticks.
- All special characters are markuped to their ascii representation.
- Must contain at least one whitespace or non backtick character.

###### specdown
```
The `<body></body>` tags
Encase `` `ticks` ``
```
###### markup
```
The <code>&lt;body&gt;&lt;/body&gt;</code> tags
Encase <code> &#96;ticks&#96; </code>
```


### Block Pre Codes
- Pairs of three or more backticks at the start of a line and not on the same line will be markuped to pre and code tags. 
- Pairs of n backticks can contain groups of less than n backticks.
- All special characters are markuped to their ascii representation.
- Text on the same line as the opening backticks will be markuped as class on the code tag.

###### specdown
```
'''
<body></body>
'''
  
'''' syntax
<body></body>
''''
```
###### markup
```
<pre><code>
&lt;body&gt;&lt;/body&gt;
</code></pre>

<pre><code class="syntax">
&lt;body&gt;&lt;/body&gt;
</code></pre>
```


### Inline Samples
- Pairs of one or more backticks on the same line with a `!` will be markuped to samp tags. 
- Pairs of n backticks can contain groups of less than n backticks.
- All special characters are markuped to their ascii representation.
- Must contain at least one whitespace or non backtick character.

###### specdown
```
The `!<body></body>` tags
Encase ``! `ticks` ``
```
###### markup
```
The <samp>&lt;body&gt;&lt;/body&gt;</samp> tags
Encase <samp> &#96;ticks&#96; </samp>
```


### Block Pre Samples
- Pairs of three or more backticks with a `!` at the start of a line and not on the same line will be markuped to pre and samp tags. 
- Pairs of n backticks can contain groups of less than n backticks.
- All special characters are markuped to their ascii representation.
- Text on the same line as the opening backticks will be markuped as class on the samp tag.

###### specdown
```
'''!
> Output from a bash script
'''

'''''! syntax
sample output
'''''
```
###### markup
```
<pre><samp>
&gt; Output from a bash script
</samp></pre>

<pre><samp class="syntax">
sample output
</samp></pre>
```


### Tables
- Tables must have preceeding and proceeding `|`.
- The first text row will always be markuped as the head row.
- The first row with only bars, dashes, and colons will always be used to define aligns.
- Remaining text rows will be markuped as body rows.
- Aligns are applied to head and body rows.
- Column text lengths do not need to be equal between columns or rows.
- Table rows must be on the same line.
- All other inline syntax can be nested inside table syntax.
- `<class>` is markuped on the tr and cannot be used with `<<class>`.
- `<<class>` is markuped on the table and can only be used on the head row.

###### specdown
```
| Header One | Header Two |<<class-one>
| ---------- | ---------- |
| Content    | Content    |<class>

| Left | Center | Right |
| :--- | :----: | ----: |
| Content    |   Content  |    Content |
```
###### markup
```
<table class="class-one">
<thead>
<tr>
<th>Header One</th>
<th>Header Two</th>
</tr>
</thead>
<tbody>
<tr class="class">
<td>Content</td>
<td>Content</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th align="left">Left</th>
<th align="center">Center</th>
<th align="right">Right</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Content</td>
<td align="center">Content</td>
<td align="right">Content</td>
</tr>
</tbody>
</table>
```


### Metas
- `{{{ }}}` will be treated as meta data (sematic data) and can be retrieved and used for machine magic.
- `{{{ }}}` will be removed from markup and not parsed.
- `{{{! }}}` will be parsed and markuped as an html comment.
- Meta can be used inline or block.
- Applied anywhere, without exception.
- Meta parser
  - `( )` can be used to define an array. 
  - `[ ]` can be used to define a json-ish data structure. 
  - Whitespace is used for parsing and is otherwise ignored.

###### specdown
```
{{{ pageTitle "The page title" }}}
{{{ author (
  [
    first: "Author",
    last: "One",
    role: "Contributor"
  ],
  [
    first: "Author",
    last: "Two",
    role: "Editor"
  ]
) }}}
{{{ backPage url }}}
{{{ nextPage url }}}
{{{ siblings (Sibling One, Sibling Two) }}}
{{{ isA Object url }}}
{{{ hasA Object url }}}
```
###### markup
```

```


### Spans
- `[text]` will be markuped to a span tag.
- Spans can be on multiple lines.
- Spans can be used inside any other syntax.
- Spans can be used within words.
- Spans are primarily used with class syntax.

###### specdown
```
Put a span [around this text].

something[SpannedUp]<class>.
```
###### markup
```
Put a span <span>around this text</span>

something<span class="class">SpannedUp</span>.
```


### Classes
- `<class>` can be added to any other syntax to add a css class to its markup.
- Classes can define more than one class.

###### specdown
```
#<class> Header

---<class>

-<class> Item
- Item

[linked text](url title)<classOne classTwo>

How about [some styled text]<class>!
```
###### markup
```
<h1 class="class"><a name="header">Header</a></h1>

<hr class="class" />

<ul class="class">
<li>
Item
</li>
<li>
Item
</li>
</ul>

<a href="url" title="title" class="classOne classTwo">linked text</a>

How about <span class="class">some styled text</span>!
```
