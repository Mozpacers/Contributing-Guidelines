This page outlines the style guide for CSS stylesheets in all Mozpacers' projects.

## CSSComb

In general, all Mozpacers' repositories has a `.csscomb.json` file with the configuration as follows:

```json
{
    "remove-empty-rulesets": true,
    "always-semicolon": true,
    "color-case": "upper",
    "block-indent": "  ",
    "color-shorthand": false,
    "element-case": "lower",
    "leading-zero": true,
    "quotes": "single",
    "sort-order-fallback": "abc",
    "space-before-colon": "",
    "space-after-colon": " ",
    "space-before-combinator": " ",
    "space-after-combinator": " ",
    "space-between-declarations": "\n",
    "space-before-opening-brace": " ",
    "space-after-opening-brace": "\n",
    "space-after-selector-delimiter": " ",
    "space-before-selector-delimiter": "",
    "space-before-closing-brace": "\n",
    "strip-spaces": true,
    "tab-size": true,
    "unitless-zero": true,
    "vendor-prefix-align": true
}
```

Just run the CSSComb command at the end of your work and you'll be good to go.

#### How to use CSSComb

**Use from text-editor:**

We're listing out plugins for the most popular text-editors that you can use to run CSSComb.

- Atom: [Atom CSSComb Plugin](https://atom.io/packages/atom-csscomb)
- Sublime: [Sublime CSSComb Plugin](https://github.com/csscomb/sublime-csscomb)
- Brackets: [Brackets CSSComb Plugin](https://github.com/i-akhmadullin/brackets-csscomb)
- Vim: [Vim CSSComb Plugin](https://github.com/csscomb/vim-csscomb/)

**Use from CLI**

You'll need to do a global installation of CSSComb as a npm package

```bash
npm install csscomb -g
```

After that, you can use it as follows

```bash
csscomb assets/css
```

## Spacing

- Indentation with two spaces.
- No whitespace at the end of line or on blank lines.
- Use a space after a property name's colon, do not use a space before the colon.
- Put a space before `{` in rule declaration.
    Example:
    ```css
    p {
    padding-left: 2px;
    }
    ```
- Place the closing brace of a rule declaration on a new line.
- When listing multiple selectors associated with the same CSS rule, add a space after each `,` and not before `,`.
- The only time you should indent selectors is within nested rule declarations, like media queries.
- No spaces within () for urls.
- The line length should be no more than 80 characters.
- Unix-style linebreaks ('\n'), not Windows-style ('\r\n').


## Formatting

- Use hex color codes (#5C8FB3) unless using rgba().
- When possible, use full hex values.
- Use upper case letters when declaring hex codes.
- Don't specify units for 0 values.
- Avoid cascading selectors that are more than 3 selectors long.
- Avoid unnecessary cascading selectors.
- Use shorthand properties when possible.
  - Instead of writing out
    ```css
    padding-left: 10px;
    padding-right: 10px;
    padding-top: 20px;
    padding-bottom: 5px;
    ```
    shorten it to one rule
    ```css
    padding: 20px 10px 5px 10px;
    ```
    However, if you're only changing the left padding, then it is appropriate to use `padding-left`.
- Don't omit leading zeros in decimal values.
- Use single quotes instead of double quotes.
- Always have a semicolon at the end of each declaration.
- Avoid the use of !important. Use specific selectors instead.
- While creating styles try to follow a top-down approach in writing element selectors. Each new rule should go to specific section where the HTML selector is actually placed.

    Example:

    ```css
    /* Header */
    header{
      ...
    }
    /* End of header */

    /* Home Section */
    section#home{
      ...
    }
    /End of home section */

    /* Footer */
    footer{
      ...
    }
    /* End of footer section */
    ```

## Imports

- Don't use @import in distribution files. It is slower, adds extra page requests, and can cause other unforeseen problems.
- Do not use more than 31 @imports in a single CSS file, it will break IE.
- Do not nest @imports, you will not be able to guarantee their order.

## Comments

Comments are always preceded by a blank line. Comments start with a capital first letter, but don't require a period at the end, unless you're writing full sentences. There must be a single space between the comment token and the comment text.

When comments take up multiple lines, use a * at the beginning of each line. There must be a space between the first word and the * on each line.

```css
/* Good single line comment */

/*
* Good example of a multi-line comment.
* If your comment takes up multiple lines, please do this.
*/
```

## Class Names

- Class names should be all lowercase letters.
- Build class names with hyphens (-).
- Avoid excessive and arbitrary shorthand notation for classes. `.ui-button` is useful for button, but `.b` doesn't mean anything.
- Use classes to identify selectors instead of ids.

    ```css
    /* Bad Example */
    .uiButton,
    .ui_button,
    #uiButton,
    .b {

    }

    /* Good Example */
    .ui-button {

     }
    ```
**Proudly forked from [jQuery](https://github.com/jquery/contribute.jquery.org)**