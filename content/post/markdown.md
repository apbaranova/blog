---
title: Git Version Control
subtitle: Getting started

# Summary for listings and search engines
summary: Markdown is a simple markup language used to create rich text (e.g. HTML) with a plain text editor. It lets you add basic formatting to your text, using symbols known and accessible on all keyboards. Font size, colour, and other, more advanced options are not available with Markdown.

# Link this post with a project
projects: []

# Date published
date: '2022-05-12T00:00:00Z'

# Date updated
lastmod: '2022-05-12T00:00:00Z'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
#image:
#  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/CpkOjOcXdUY)'
#  focal_point: ''
#  placement: 2
#  preview_only: false

authors:
  - admin

tags:
  - Academic

categories:
  - Demo
---

## Markdown

Angle brackets

If you use angle brackets in text in your file (for example, to denote a placeholder), you need to manually encode the angle brackets. Otherwise, Markdown thinks that they're intended to be an HTML tag.

For example, encode <script name> as &lt;script name&gt; or \<script name>.

Angle brackets don't have to be escaped in text formatted as inline code or in code blocks.
Apostrophes and quotation marks

If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks. These need to be encoded or changed to basic apostrophes or quotation marks. Otherwise, you end up with things like this when the file is published: Itâ€™s

Here are the encodings for the "smart" versions of these punctuation marks:

    Left (opening) quotation mark: &#8220;
    Right (closing) quotation mark: &#8221;
    Right (closing) single quotation mark or apostrophe: &#8217;
    Left (opening) single quotation mark (rarely used): &#8216;

Tip

To avoid "smart" characters in your Markdown files, rely on the Docs Authoring Pack's smart quote replacement feature. For more information, see smart quote replacement.
Blockquotes

Blockquotes are created using the > character:
Markdown

> This is a blockquote. It is usually rendered indented and with a different background color.

The preceding example renders as follows:

    This is a blockquote. It is usually rendered indented and with a different background color.

Bold and italic text

To format text as bold, enclose it in two asterisks:
Markdown

This text is **bold**.

To format text as italic, enclose it in a single asterisk:
Markdown

This text is *italic*.

To format text as both bold and italic, enclose it in three asterisks:
Markdown

This text is both ***bold and italic***.

For guidance on when to use bold and italic text, see text formatting guidelines.
Code snippets

Docs Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences. For more information, see How to add code to docs.
Columns

The columns Markdown extension gives Docs authors the ability to add column-based content layouts that are more flexible and powerful than basic Markdown tables, which are only suited for true tabular data. You can add up to four columns, and use the optional span attribute to merge two or more columns.

While the columns extension still works, we no longer recommend it for creating custom layouts. We've found that many custom column layouts have accessibility issues or otherwise violate Docs style guidelines. Don't create custom layouts. Use standard Docs features.

The syntax for columns is as follows:
Markdown

:::row:::
   :::column span="":::
      Content...
   :::column-end:::
   :::column span="":::
      More content...
   :::column-end:::
:::row-end:::

Columns should only contain basic Markdown, including images. Headings, tables, tabs, and other complex structures shouldn't be included. A row can't have any content outside of column.

For example, the following Markdown creates one column that spans two column widths, and one standard (no span) column:
Markdown

:::row:::
   :::column span="2":::
      **This is a 2-span column with lots of text.**

      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec vestibulum mollis nunc
      ornare commodo. Nullam ac metus imperdiet, rutrum justo vel, vulputate leo. Donec
      rutrum non eros eget consectetur.
   :::column-end:::
   :::column span="":::
      **This is a single-span column with an image in it.**

      ![Doc.U.Ment](media/markdown-reference/document.png)
   :::column-end:::
:::row-end:::

This renders as follows:

This is a 2-span column with lots of text.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec vestibulum mollis nunc ornare commodo. Nullam ac metus imperdiet, rutrum justo vel, vulputate leo. Donec rutrum non eros eget consectetur.

Comments

Docs supports HTML comments if you must comment out sections of your article:

<!--- Here's my comment --->

Warning

Do not put private or sensitive information in HTML comments. Docs carries HTML comments through to the published HTML that goes public. While HTML comments are invisible to the reader's eye, they are exposed in the HTML underneath.
Headings

Docs supports six levels of Markdown headings:
Markdown

# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)

    There must be a space between the last # and heading text.
    Each Markdown file must have one and only one H1 heading.
    The H1 heading must be the first content in the file after the YML metadata block.
    H2 headings automatically appear in the right-hand navigating menu of the published file. Lower-level headings don't appear, so use H2s strategically to help readers navigate your content.
    HTML headings, such as <h1>, aren't recommended, and in some cases will cause build warnings.
    You can link to individual headings in a file via bookmark links.

HTML

Although Markdown supports inline HTML, HTML isn't recommended for publishing to Docs, and except for a limited list of values will cause build errors or warnings.
Images

The following file types are supported by default for images:

    .jpg
    .png

To support other image types, such as .gif, you must add them as resources in docfx.json:
Markdown

"resource": [
  {
    "files" : [
      "**/*.png",
      "**/*.jpg,
      "**/*.gif"
    ],

Standard conceptual images (default Markdown)

The basic Markdown syntax to embed an image is:
Markdown

![<alt text>](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)

Where <alt text> is a brief description of the image and <folder path> is a relative path to the image. Alternate text is required for screen readers for the visually impaired. It's also useful if there's a site bug where the image can't render.

Underscores in alt text aren't rendered properly unless you escape them by prefixing them with a backslash (\_). However, don't copy file names for use as alt text. For example, instead of this:
Markdown

![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)

Write this:
Markdown

![Active Directory extension for two-factor authentication, step 4: Configure](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)

Standard conceptual images (Docs Markdown)

The Docs custom :::image::: extension supports standard images, complex images, and icons.

For standard images, the older Markdown syntax will still work, but the new extension is recommended because it supports more powerful functionality, such as specifying a localization scope that's different from the parent topic. Other advanced functionality, such as selecting from the shared image gallery instead of specifying a local image, will be available in the future. The new syntax is as follows:
Markdown

:::image type="content" source="<folderPath>" alt-text="<alt text>":::

If type="content" (the default), both source and alt-text are required.
Complex images with long descriptions

You can also use this extension to add an image with a long description that is read by screen readers but not rendered visually on the published page. Long descriptions are an accessibility requirement for complex images, such as graphs. The syntax is the following:
Markdown

:::image type="complex" source="<folderPath>" alt-text="<alt text>":::
   <long description here>
:::image-end:::

If type="complex", source, alt-text, a long description, and the :::image-end::: tag are all required.

When your changes are in preview or published, you can check whether the long description exists by right-clicking on the image and selecting Inspect (when using Microsoft Edge browser, although other browsers have similar features). This action brings you to the image source in the HTML code, underneath which you'll find a visually-hidden class. Expand the dropdown on this class, and you'll find your long description.

Automatic borders

The :::image::: extension also supports the border property, which automatically adds a 1-pixel gray border around your image. The border property is true by default for content and complex images, so you'll get the border automatically unless you explicitly add the property with a value of false. The border property is false by default for icon images.

The border property is the recommended way to add a border. Don't create your own borders manually.
Specifying loc-scope

Sometimes the localization scope for an image is different from that of the article or module that contains it. This can cause a bad global experience: for example, if a screenshot of a product is accidentally localized into a language the product isn't available in. To prevent this, you can specify the optional loc-scope attribute in images of types content and complex, and is required for screenshots that show a product with a different localization scope than the article or module that contains it.
Icons

The image extension supports icons, which are decorative images and should not have alt text. The syntax for icons is:
Markdown

:::image type="icon" source="<folderPath>":::

If type="icon", source should be specified but alt-text shouldn't be.

The border property is false by default for icons. If your decorative image requires the standard image border, explicitly add border="true" to the :::image::: tag.
Included Markdown files

Where markdown files need to be repeated in multiple articles, you can use an include file. The includes feature instructs Docs to replace the reference with the contents of the include file at build time. You can use includes in the following ways:

    Inline: Reuse a common text snippet inline with within a sentence.
    Block: Reuse an entire Markdown file as a block, nested within a section of an article.

An inline or block include file is a Markdown (.md) file. It can contain any valid Markdown. Include files are typically located in a common includes subdirectory, in the root of the repository. When the article is published, the included file is seamlessly integrated into it.
Includes syntax

Block include is on its own line:
Markdown

[!INCLUDE [<title>](<filepath>)]

Inline include is within a line:
Markdown

Text before [!INCLUDE [<title>](<filepath>)] and after.

Where <title> is the name of the file and <filepath> is the relative path to the file. INCLUDE must be capitalized and there must be a space before the <title>.

Here are requirements and considerations for include files:

    Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section. Don't use them for anything smaller than a sentence.
    Includes won't be rendered in the GitHub-rendered view of your article because they rely on Docs extensions. They'll be rendered only after publication.
    Write all the text in an include file in complete sentences or phrases that don't depend on preceding or following text in the article that references the include. Ignoring this guidance creates an untranslatable string in the article.
    Don't embed include files within other include files.
    /Includes folders are excluded from build. Therefore, images stored in /includes folders and referenced in included files won't be displayed in published content. Store images in a /media folder outside the /includes folder.
    As with regular articles, don't share media between include files. Use a separate file with a unique name for each include and article. Store the media file in the media folder that's associated with the include.
    Don't use an include as the only content of an article. Includes are meant to be supplemental to the content in the rest of the article.

Indentation

In Markdown, spaces before the first character of a line determine the line's alignment relative to the preceding lines. Indentation especially influences numbered and bulleted lists to render multiple levels of nesting in a hierarchical or outline format.

To indent text to align with a preceding paragraph or an item in a numbered or bulleted list, use spaces.

The following two examples show how indented paragraphs render based on their relationship to other paragraphs.

1. This is a numbered list example (one space after the period before the letter T).
   This sentence is indented three spaces.
   This code block is indented three spaces.
   
- This is a bulleted list example (one space after the bullet before the letter T).
  This sentence is indented two spaces.
  > [!TIP]
  > This tip is indented two spaces.
  - This is a second-level bullet (indented two spaces, with one space after the bullet before the letter T).
    This sentence is indented four spaces.
    > This quote block is indented four spaces.

The example above renders as:

    This is a numbered list example (one space after the period before the letter T).

    This sentence is indented three spaces.

    This code block is indented three spaces.

    This is a bulleted list example (one space after the bullet before the letter T).

    This sentence is indented two spaces.

    Tip

    This tip is indented two spaces.

        This is a second-level bullet (indented two spaces, with one space after the bullet before the letter T).

        This sentence is indented four spaces.

            This quote block is indented four spaces.

Links

For information on syntax for links, see Use links in documentation.
Lists (Numbered, Bulleted, Checklist)
Numbered list

To create a numbered list, you can use all 1s. The numbers are rendered in ascending order as a sequential list when published. For increased source readability, you can increment your lists manually.

Don't use letters in lists, including nested lists. They don't render correctly when published to Docs. Nested lists using numbers will render as lowercase letters when published. For example:
Markdown

1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)

This renders as follows:

    This is
    a parent numbered list
        and this is
        a nested numbered list
    (fin)

Bulleted list

To create a bulleted list, use - or * followed by a space at the beginning of each line:
Markdown

- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!

This renders as follows:

    This is
    a parent bulleted list
        and this is
        a nested bulleted list
    All done!

Whichever syntax you use, - or *, use it consistently within an article.
Checklist

Checklists are available for use on Docs via a custom Markdown extension:
Markdown

> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3

This example renders on Docs like this:

    List item 1
    List item 2
    List item 3

Use checklists at the beginning or end of an article to summarize "What will you learn" or "What have you learned" content. Do not add random checklists throughout your articles.
Next step action

You can use a custom extension to add a next step action button to Docs pages.

The syntax is as follows:
markdown

> [!div class="nextstepaction"]
> [button text](link to topic)

For example:
Markdown

> [!div class="nextstepaction"]
> [Learn about adding code to articles](code-in-docs.md)

This renders as follows:

You can use any supported link in a next step action, including a Markdown link to another web page. In most cases, the next action link will be a relative link to another file in the same docset.
Non-localized strings

You can use the custom no-loc Markdown extension to identify strings of content that you would like the localization process to ignore.

All strings called out will be case-sensitive; that is, the string must match exactly to be ignored for localization.

To mark an individual string as non-localizable, use this syntax:
markdown

:::no-loc text="String":::

For example, in the following, only the single instance of Document will be ignored during the localization process:
Markdown

# Heading 1 of the Document

Markdown content within the :::no-loc text="Document":::.  The are multiple instances of Document, document, and documents.

Note

Use \ to escape special characters:
markdown

Lorem :::no-loc text="Find a \"Quotation\""::: Ipsum.

You can also use metadata in the YAML header to mark all instances of a string within the current Markdown file as non-localizable:
yml

author: cillroy
no-loc: [Global, Strings, to be, Ignored]

Note

The no-loc metadata is not supported as global metadata in docfx.json file. The localization pipeline doesn't read the docfx.json file, so the no-loc metadata must be added into each individual source file.

In the following example, both in the metadata title and the Markdown header the word Document will be ignored during the localization process.

In the metadata description and the Markdown main content the word document is localized, because it does not start with a capital D.
Markdown

---
title: Title of the Document
author: author-name
description: Description for the document
no-loc: [Title, Document]
---
# Heading 1 of the Document

Markdown content within the document.

Selectors

Selectors are UI elements that let the user switch between multiple flavors of the same article. They are used in some doc sets to address differences in implementation across technologies or platforms. Selectors are typically most applicable to our mobile platform content for developers.

Because the same selector Markdown goes in each article file that uses the selector, we recommend placing the selector for your article in an include file. Then you can reference that include file in all your article files that use the same selector.

There are two types of selectors: a single selector and a multi-selector.
Single selector
Markdown

> [!div class="op_single_selector"]
> - [Universal Windows](../articles/notification-hubs-windows-store-dotnet-get-started/)
> - [Windows Phone](../articles/notification-hubs-windows-phone-get-started/)
> - [iOS](../articles/notification-hubs-ios-get-started/)
> - [Android](../articles/notification-hubs-android-get-started/)
> - [Kindle](../articles/notification-hubs-kindle-get-started/)
> - [Baidu](../articles/notification-hubs-baidu-get-started/)
> - [Xamarin.iOS](../articles/partner-xamarin-notification-hubs-ios-get-started/)
> - [Xamarin.Android](../articles/partner-xamarin-notification-hubs-android-get-started/)

... will be rendered like this:
Multi-selector
Markdown

> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](./mobile-services-dotnet-backend-ios-get-started-push.md)
> - [(iOS | JavaScript)](./mobile-services-javascript-backend-ios-get-started-push.md)
> - [(Windows universal C# | .NET)](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)
> - [(Windows universal C# | Javascript)](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)
> - [(Windows Phone | .NET)](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)
> - [(Windows Phone | Javascript)](./mobile-services-javascript-backend-windows-phone-get-started-push.md)
> - [(Android | .NET)](./mobile-services-dotnet-backend-android-get-started-push.md)
> - [(Android | Javascript)](./mobile-services-javascript-backend-android-get-started-push.md)
> - [(Xamarin iOS | Javascript)](./partner-xamarin-mobile-services-ios-get-started-push.md)
> - [(Xamarin Android | Javascript)](./partner-xamarin-mobile-services-android-get-started-push.md)

... will be rendered like this:
Platform
Backend
Subscript and superscript

You should only use subscript or superscript when necessary for technical accuracy, such as when writing about mathematical formulas. Don't use them for non-standard styles, such as footnotes.

For both subscript and superscript, use HTML:
HTML

Hello <sub>This is subscript!</sub>

This renders as follows:

Hello This is subscript!
HTML

Goodbye <sup>This is superscript!</sup>

This renders as follows:

Goodbye This is superscript!
Tables

The simplest way to create a table in Markdown is to use pipes and lines. To create a standard table with a header, follow the first line with dashed line:
Markdown

|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|

This renders as follows:
This is 	a simple 	table header
table 	data 	here
it doesn't 	actually 	have to line up nicely!

You can align the columns by using colons:
Markdown

| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |

Line breaks within words in any table cell

Long words in a Markdown table might make the table expand to the right navigation and become unreadable. You can solve that by allowing Docs rendering to automatically insert line breaks within words when needed. Just wrap up the table with the custom class [!div class="mx-tdBreakAll"].

Here is a Markdown sample of a table with three rows that will be wrapped by a div with the class name mx-tdBreakAll.
Markdown

> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|

It will be rendered like this:
Name 	Syntax 	Mandatory for silent installation? 	Description
Quiet 	/quiet 	Yes 	Runs the installer, displaying no UI and no prompts.
NoRestart 	/norestart 	No 	Suppresses any attempts to restart. By default, the UI will prompt before restart.
Help 	/help 	No 	Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.
Line breaks within words in second column table cells

You might want line breaks to be automatically inserted within words only in the second column of a table. To limit the breaks to the second column, apply the class mx-tdCol2BreakAll by using the div wrapper syntax as shown earlier.
Inconsistent column widths between tables

You may notice that the column widths of the tables in your articles look odd or inconsistent. This behavior occurs because the length of text within the cells determines the layout of the table. Unfortunately, there's no way to control how the tables render. This is a limitation of Markdown. Even though it would look nicer to have the width of table columns be consistent, this would have some disadvantages too:

    Interlacing HTML code with Markdown makes topics more complicated and discourages community contributions.
    A table that you make look good for a specific screen size may end up looking unreadable at different screen sizes as it preempts responsive rendering.

Data matrix tables

A data matrix table has both a header and a weighted first column, creating a matrix with an empty cell in the top left. Docs has custom Markdown for data matrix tables:
Markdown

|                  |Header 1 |Header 2|
|------------------|---------|--------|
|**First column A**|Cell 1A  |Cell 2A |
|**First column B**|Cell 1B  |Cell 2B |

The example renders as:
	Header 1 	Header 2
First column A 	Cell 1A 	Cell 2A
First column B 	Cell 1B 	Cell 2B

Every entry in the first column must be styled as bold (**bold**); otherwise the tables won't be accessible for screen readers or valid for Docs.

Tip

The Docs Authoring Pack for VS Code includes a function to convert a regular Markdown table into a data matrix table. Just select the table, right-click, and select Convert to data matrix table.
HTML Tables

HTML tables aren't recommended for Docs. They aren't human readable in the source - which is a key principle of Markdown.

Have a great time using Markdown!