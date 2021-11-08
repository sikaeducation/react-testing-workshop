# ARIA Roles

## Forms

| ARIA Role | Elements that have this role | Description |
| --- | --- | --- |
| `form` | `<form>` | |
| `textbox` | `<input type="text">`, `<textarea>` | Text input |
| `checkbox` | `<input type="checkbox">` | Checkable interactive control |
| `spinbutton` | `<input type="number" />` | |
| `radio` | `<input type="radio" />` | |
| `slider` | `<input type="range" />` | |
| `search` | `<input type="search" />` | |
| `combobox` | `<select>` | |
| `option` | `<option>` | |
| `button` | `<button>`, `<input type="button" />`, `<input type="submit" />`, `<input type="reset" />`, `<input type="image" />` | Clickable elements that trigger a response |

## Structure

| ARIA Role | Elements that have this role | Description |
| --- | --- | --- |
| `article` | `<article>` | Standalone content |
| `heading` | `<h1>`-`<h6>` | Heading to a page or section |
| `complementary` | `<aside />` | |
| `footer` | `<footer>` | Only applies if it's not a child of a sectioning element like `<article>` or `<main>` or one of the ARIA roles corresponding to them |
| `header` | `<header>` | Only applies if it's not a child of a sectioning element like `<article>` or `<main>` or one of the ARIA roles corresponding to them |
| `navigation` | `<nav>` | |
| `section` (needs name)
| `table` | `<table>` | |

## Elements

| ARIA Role | Elements that have this role | Description |
| --- | --- | --- |
| `button` | `<button>`, `<input type="button" />`, `<input type="submit" />`, `<input type="reset" />`, `<input type="image" />` | Clickable elements that trigger a response |
| `link` | `<a>` | Hyperlink to a resource |
| `img` | `<img />` | Should be treated as an image |
| `list` | `<ol>`, `<ul>` | |
| `listitem` | `<li>` | |

    progressbar
    scrollbar
    searchbox
    separator (when focusable)
    slider
    spinbutton
    switch
    tab
    tabpanel
    textbox
    treeitem

Composite roles

The techniques below describe each composite role as well as their required and optional child roles.

    combobox
    grid (including row, gridcell, rowheader, columnheader roles)
    listbox (including option role)
    menu
    menubar
    radiogroup (see radio role)
    tablist (including tab and tabpanel roles)
    tree
    treegrid

Document structure roles

    application
    article
    cell
    columnheader
    definition
    directory
    document
    feed
    figure
    group
    heading
    img
    list
    listitem
    math
    none
    note
    presentation
    row
    rowgroup
    rowheader
    separator
    table
    term
    toolbar
    tooltip

Landmark roles

    banner
    complementary
    contentinfo
    form
    main
    navigation
    region
    search

Live Region Roles

    alert
    log
    marquee
    status
    timer

Window Roles

    alertdialog
    dialog


## Additional Resources

| Resource | Description |
| --- | --- |
| [W3C: ARIA in HTML](https://www.w3.org/TR/html-aria/) | Official reference for how HTML elements align to ARIA roles. |
