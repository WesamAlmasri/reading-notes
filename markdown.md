# Markdown

![MarkDown logo](https://kirkstrobeck.github.io/whatismarkdown.com/img/markdown.png)

**Markdown** is a way to style text on the web. You control the display of the document; formatting words as bold or italic, adding images, and creating lists are just a few of the things we can do with Markdown. Mostly.

Markdown is just regular text with a few non-alphabetic characters to style the text like, `#` or `*`.

The Markdown can be used in github within files with .md or .markdown extension.

### Styling text

The text can be syled as follow:

| Style                  | Syntax             | Example                                  | Output                                 |
| ---------------------- | ------------------ | ---------------------------------------- | -------------------------------------- |
| Bold                   | `** **` or `__ __` | `**This is bold text**`                  | **This is bold text**                  |
| Italic                 | `* *` or `_ _`     | `*This text is italicized*`              | *This text is italicized*              |
| Strikethrough          | `~~ ~~`            | `~~This was mistaken text~~`             | ~~This was mistaken text~~             |
| Bold and nested italic | `** ** and _ _`    | `**This text is _extremely_ important**` | **This text is _extremely_ important** |
| All bold and italic    | `*** ***`          | `***All this text is important***`       | ***All this text is important***       |

### Quoting text and code

You can quote text with a >.

```

In the words of Abraham Lincoln:

> Pardon my French

```

You can call out code or a command within a sentence with single backticks. The text within the backticks will not be formatted.

```Use `git status` to list all new or modified files that haven't yet been committed.```

Use `git status` to list all new or modified files that haven't yet been committed.

To format code or text into its own distinct block, use triple backticks.

    Some basic Git commands are:

    ```
    git status
    git add
    git commit
    ```
Some basic Git commands are:

```bash
git status
git add
git commit
```

## Links

You can create an inline link by wrapping link text in brackets [ ], and then wrapping the URL in parentheses ( ). You can also use the keyboard shortcut command + k to create a link.

```This site was built using [GitHub Pages](https://pages.github.com/).```

This site was built using [GitHub Pages](https://pages.github.com/).

## Lists

You can make an unordered list by preceding one or more lines of text with - or * and ordered list with by preceding each line with a number.

```
- George Washington
- John Adams
- Thomas Jefferson
```

- George Washington
- John Adams
- Thomas Jefferson

```
1. James Madison
2. James Monroe
3. John Quincy Adams
```

1. James Madison
2. James Monroe
3. John Quincy Adams

You can create a nested list by indenting one or more list items below another item.

```
1. First list item
   - First nested list item
     - Second nested list item
```

1. First list item
   - First nested list item
     - Second nested list item

## Task lists

To create a task list, preface list items with a regular space character followed by `[ ]`. To mark a task as complete, use `[x]`.

```
- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request
```

- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request

## Tables

You can create tables by assembling a list of words and dividing them with hyphens `-` (for the first row), and then separating each column with a pipe `|`:

```
First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column
```

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column


## Images

You can use an image by wrapping image alt text in brackets [ ], and then wrapping the URL of the image (or the relative path) in parentheses ( ).

```
![GitHub Logo](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)
```

![GitHub Logo](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)

## Mentioning people and teams

You can mention a person or team on GitHub by typing @ plus their username or team name. This will trigger a notification and bring their attention to the conversation.

`@github/support What do you think about these updates?`

## Using emoji

You can add emoji to your writing by typing `:EMOJICODE:`.

`@octocat :+1: This PR looks great - it's ready to merge! :shipit:`

@octocat :+1: This PR looks great - it's ready to merge! :shipit:

## Ignoring Markdown formatting

You can tell GitHub to ignore (or escape) Markdown formatting by using \ before the Markdown character.

`Let's rename \*our-new-project\* to \*our-old-project\*.`

Let's rename \*our-new-project\* to \*our-old-project\*.
