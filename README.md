# Churn-Model
A company X required a churn model to mitigate the monetary losses from discounts provided to customers.

```html
<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>hackaton_AvilesKarla</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>




<style type="text/css">
    pre { line-height: 125%; }
td.linenos pre { color: #000000; background-color: #f0f0f0; padding-left: 5px; padding-right: 5px; }
span.linenos { color: #000000; background-color: #f0f0f0; padding-left: 5px; padding-right: 5px; }
td.linenos pre.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>



<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/*
 * Webkit scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-corner {
  background: var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-thumb {
  background: rgb(var(--jp-scrollbar-thumb-color));
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-right: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-bottom: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar */

[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-corner,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-corner {
  background-color: transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-thumb,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid transparent;
  border-right: var(--jp-scrollbar-endpad) solid transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid transparent;
  border-bottom: var(--jp-scrollbar-endpad) solid transparent;
}

/*
 * Phosphor
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Widget, /* </DEPRECATED> */
.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  cursor: default;
}


/* <DEPRECATED> */ .p-Widget.p-mod-hidden, /* </DEPRECATED> */
.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-CommandPalette, /* </DEPRECATED> */
.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-CommandPalette-search, /* </DEPRECATED> */
.lm-CommandPalette-search {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-content, /* </DEPRECATED> */
.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-CommandPalette-header, /* </DEPRECATED> */
.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}


/* <DEPRECATED> */ .p-CommandPalette-item, /* </DEPRECATED> */
.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}


/* <DEPRECATED> */ .p-CommandPalette-itemIcon, /* </DEPRECATED> */
.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemContent, /* </DEPRECATED> */
.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}


/* <DEPRECATED> */ .p-CommandPalette-itemShortcut, /* </DEPRECATED> */
.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemLabel, /* </DEPRECATED> */
.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-DockPanel, /* </DEPRECATED> */
.lm-DockPanel {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-widget, /* </DEPRECATED> */
.lm-DockPanel-widget {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-tabBar, /* </DEPRECATED> */
.lm-DockPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-DockPanel-handle, /* </DEPRECATED> */
.lm-DockPanel-handle {
  z-index: 2;
}


/* <DEPRECATED> */ .p-DockPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-DockPanel-handle:after, /* </DEPRECATED> */
.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}


/* <DEPRECATED> */ .p-DockPanel-overlay, /* </DEPRECATED> */
.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}


/* <DEPRECATED> */ .p-DockPanel-overlay.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Menu, /* </DEPRECATED> */
.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-Menu-content, /* </DEPRECATED> */
.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-Menu-item, /* </DEPRECATED> */
.lm-Menu-item {
  display: table-row;
}


/* <DEPRECATED> */
.p-Menu-item.p-mod-hidden,
.p-Menu-item.p-mod-collapsed,
/* </DEPRECATED> */
.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}


/* <DEPRECATED> */
.p-Menu-itemIcon,
.p-Menu-itemSubmenuIcon,
/* </DEPRECATED> */
.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}


/* <DEPRECATED> */ .p-Menu-itemLabel, /* </DEPRECATED> */
.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}


/* <DEPRECATED> */ .p-Menu-itemShortcut, /* </DEPRECATED> */
.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-MenuBar, /* </DEPRECATED> */
.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-MenuBar-content, /* </DEPRECATED> */
.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}


/* <DEPRECATED> */ .p--MenuBar-item, /* </DEPRECATED> */
.lm-MenuBar-item {
  box-sizing: border-box;
}


/* <DEPRECATED> */
.p-MenuBar-itemIcon,
.p-MenuBar-itemLabel,
/* </DEPRECATED> */
.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-ScrollBar, /* </DEPRECATED> */
.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-ScrollBar-button, /* </DEPRECATED> */
.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-track, /* </DEPRECATED> */
.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-thumb, /* </DEPRECATED> */
.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-SplitPanel-child, /* </DEPRECATED> */
.lm-SplitPanel-child {
  z-index: 0;
}


/* <DEPRECATED> */ .p-SplitPanel-handle, /* </DEPRECATED> */
.lm-SplitPanel-handle {
  z-index: 1;
}


/* <DEPRECATED> */ .p-SplitPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-SplitPanel-handle:after, /* </DEPRECATED> */
.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabBar, /* </DEPRECATED> */
.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='horizontal'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='vertical'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-content, /* </DEPRECATED> */
.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='horizontal'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='vertical'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
}


/* <DEPRECATED> */
.p-TabBar-tabIcon,
.p-TabBar-tabCloseIcon,
/* </DEPRECATED> */
.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-TabBar-tabLabel, /* </DEPRECATED> */
.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}


/* <DEPRECATED> */ .p-TabBar-tab.p-mod-hidden, /* </DEPRECATED> */
.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-TabBar.p-mod-dragging .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='horizontal'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='vertical'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging .p-TabBar-tab.p-mod-dragging
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabPanel-tabBar, /* </DEPRECATED> */
.lm-TabPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-TabPanel-stackedPanel, /* </DEPRECATED> */
.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

@charset "UTF-8";
/*!

Copyright 2015-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
html{
  -webkit-box-sizing:border-box;
          box-sizing:border-box; }

*,
*::before,
*::after{
  -webkit-box-sizing:inherit;
          box-sizing:inherit; }

body{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400;
  color:#182026;
  font-family:-apple-system, "BlinkMacSystemFont", "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Open Sans", "Helvetica Neue", "Icons16", sans-serif; }

p{
  margin-top:0;
  margin-bottom:10px; }

small{
  font-size:12px; }

strong{
  font-weight:600; }

::-moz-selection{
  background:rgba(125, 188, 255, 0.6); }

::selection{
  background:rgba(125, 188, 255, 0.6); }
.bp3-heading{
  color:#182026;
  font-weight:600;
  margin:0 0 10px;
  padding:0; }
  .bp3-dark .bp3-heading{
    color:#f5f8fa; }

h1.bp3-heading, .bp3-running-text h1{
  line-height:40px;
  font-size:36px; }

h2.bp3-heading, .bp3-running-text h2{
  line-height:32px;
  font-size:28px; }

h3.bp3-heading, .bp3-running-text h3{
  line-height:25px;
  font-size:22px; }

h4.bp3-heading, .bp3-running-text h4{
  line-height:21px;
  font-size:18px; }

h5.bp3-heading, .bp3-running-text h5{
  line-height:19px;
  font-size:16px; }

h6.bp3-heading, .bp3-running-text h6{
  line-height:16px;
  font-size:14px; }
.bp3-ui-text{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400; }

.bp3-monospace-text{
  text-transform:none;
  font-family:monospace; }

.bp3-text-muted{
  color:#5c7080; }
  .bp3-dark .bp3-text-muted{
    color:#a7b6c2; }

.bp3-text-disabled{
  color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-text-disabled{
    color:rgba(167, 182, 194, 0.6); }

.bp3-text-overflow-ellipsis{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal; }
.bp3-running-text{
  line-height:1.5;
  font-size:14px; }
  .bp3-running-text h1{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h1{
      color:#f5f8fa; }
  .bp3-running-text h2{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h2{
      color:#f5f8fa; }
  .bp3-running-text h3{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h3{
      color:#f5f8fa; }
  .bp3-running-text h4{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h4{
      color:#f5f8fa; }
  .bp3-running-text h5{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h5{
      color:#f5f8fa; }
  .bp3-running-text h6{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h6{
      color:#f5f8fa; }
  .bp3-running-text hr{
    margin:20px 0;
    border:none;
    border-bottom:1px solid rgba(16, 22, 26, 0.15); }
    .bp3-dark .bp3-running-text hr{
      border-color:rgba(255, 255, 255, 0.15); }
  .bp3-running-text p{
    margin:0 0 10px;
    padding:0; }

.bp3-text-large{
  font-size:16px; }

.bp3-text-small{
  font-size:12px; }
a{
  text-decoration:none;
  color:#106ba3; }
  a:hover{
    cursor:pointer;
    text-decoration:underline;
    color:#106ba3; }
  a .bp3-icon, a .bp3-icon-standard, a .bp3-icon-large{
    color:inherit; }
  a code,
  .bp3-dark a code{
    color:inherit; }
  .bp3-dark a,
  .bp3-dark a:hover{
    color:#48aff0; }
    .bp3-dark a .bp3-icon, .bp3-dark a .bp3-icon-standard, .bp3-dark a .bp3-icon-large,
    .bp3-dark a:hover .bp3-icon,
    .bp3-dark a:hover .bp3-icon-standard,
    .bp3-dark a:hover .bp3-icon-large{
      color:inherit; }
.bp3-running-text code, .bp3-code{
  text-transform:none;
  font-family:monospace;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
  background:rgba(255, 255, 255, 0.7);
  padding:2px 5px;
  color:#5c7080;
  font-size:smaller; }
  .bp3-dark .bp3-running-text code, .bp3-running-text .bp3-dark code, .bp3-dark .bp3-code{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#a7b6c2; }
  .bp3-running-text a > code, a > .bp3-code{
    color:#137cbd; }
    .bp3-dark .bp3-running-text a > code, .bp3-running-text .bp3-dark a > code, .bp3-dark a > .bp3-code{
      color:inherit; }

.bp3-running-text pre, .bp3-code-block{
  text-transform:none;
  font-family:monospace;
  display:block;
  margin:10px 0;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
  background:rgba(255, 255, 255, 0.7);
  padding:13px 15px 12px;
  line-height:1.4;
  color:#182026;
  font-size:13px;
  word-break:break-all;
  word-wrap:break-word; }
  .bp3-dark .bp3-running-text pre, .bp3-running-text .bp3-dark pre, .bp3-dark .bp3-code-block{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
  .bp3-running-text pre > code, .bp3-code-block > code{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    padding:0;
    color:inherit;
    font-size:inherit; }

.bp3-running-text kbd, .bp3-key{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  min-width:24px;
  height:24px;
  padding:3px 6px;
  vertical-align:middle;
  line-height:24px;
  color:#5c7080;
  font-family:inherit;
  font-size:12px; }
  .bp3-running-text kbd .bp3-icon, .bp3-key .bp3-icon, .bp3-running-text kbd .bp3-icon-standard, .bp3-key .bp3-icon-standard, .bp3-running-text kbd .bp3-icon-large, .bp3-key .bp3-icon-large{
    margin-right:5px; }
  .bp3-dark .bp3-running-text kbd, .bp3-running-text .bp3-dark kbd, .bp3-dark .bp3-key{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
    background:#394b59;
    color:#a7b6c2; }
.bp3-running-text blockquote, .bp3-blockquote{
  margin:0 0 10px;
  border-left:solid 4px rgba(167, 182, 194, 0.5);
  padding:0 20px; }
  .bp3-dark .bp3-running-text blockquote, .bp3-running-text .bp3-dark blockquote, .bp3-dark .bp3-blockquote{
    border-color:rgba(115, 134, 148, 0.5); }
.bp3-running-text ul,
.bp3-running-text ol, .bp3-list{
  margin:10px 0;
  padding-left:30px; }
  .bp3-running-text ul li:not(:last-child), .bp3-running-text ol li:not(:last-child), .bp3-list li:not(:last-child){
    margin-bottom:5px; }
  .bp3-running-text ul ol, .bp3-running-text ol ol, .bp3-list ol,
  .bp3-running-text ul ul,
  .bp3-running-text ol ul,
  .bp3-list ul{
    margin-top:5px; }

.bp3-list-unstyled{
  margin:0;
  padding:0;
  list-style:none; }
  .bp3-list-unstyled li{
    padding:0; }
.bp3-rtl{
  text-align:right; }

.bp3-dark{
  color:#f5f8fa; }

:focus{
  outline:rgba(19, 124, 189, 0.6) auto 2px;
  outline-offset:2px;
  -moz-outline-radius:6px; }

.bp3-focus-disabled :focus{
  outline:none !important; }
  .bp3-focus-disabled :focus ~ .bp3-control-indicator{
    outline:none !important; }

.bp3-alert{
  max-width:400px;
  padding:20px; }

.bp3-alert-body{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-alert-body .bp3-icon{
    margin-top:0;
    margin-right:20px;
    font-size:40px; }

.bp3-alert-footer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:reverse;
      -ms-flex-direction:row-reverse;
          flex-direction:row-reverse;
  margin-top:10px; }
  .bp3-alert-footer .bp3-button{
    margin-left:10px; }
.bp3-breadcrumbs{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:wrap;
      flex-wrap:wrap;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  margin:0;
  cursor:default;
  height:30px;
  padding:0;
  list-style:none; }
  .bp3-breadcrumbs > li{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }
    .bp3-breadcrumbs > li::after{
      display:block;
      margin:0 5px;
      background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.71 7.29l-4-4a1.003 1.003 0 0 0-1.42 1.42L8.59 8 5.3 11.29c-.19.18-.3.43-.3.71a1.003 1.003 0 0 0 1.71.71l4-4c.18-.18.29-.43.29-.71 0-.28-.11-.53-.29-.71z' fill='%235C7080'/%3e%3c/svg%3e");
      width:16px;
      height:16px;
      content:""; }
    .bp3-breadcrumbs > li:last-of-type::after{
      display:none; }

.bp3-breadcrumb,
.bp3-breadcrumb-current,
.bp3-breadcrumbs-collapsed{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  font-size:16px; }

.bp3-breadcrumb,
.bp3-breadcrumbs-collapsed{
  color:#5c7080; }

.bp3-breadcrumb:hover{
  text-decoration:none; }

.bp3-breadcrumb.bp3-disabled{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-breadcrumb .bp3-icon{
  margin-right:5px; }

.bp3-breadcrumb-current{
  color:inherit;
  font-weight:600; }
  .bp3-breadcrumb-current .bp3-input{
    vertical-align:baseline;
    font-size:inherit;
    font-weight:inherit; }

.bp3-breadcrumbs-collapsed{
  margin-right:2px;
  border:none;
  border-radius:3px;
  background:#ced9e0;
  cursor:pointer;
  padding:1px 5px;
  vertical-align:text-bottom; }
  .bp3-breadcrumbs-collapsed::before{
    display:block;
    background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cg fill='%235C7080'%3e%3ccircle cx='2' cy='8.03' r='2'/%3e%3ccircle cx='14' cy='8.03' r='2'/%3e%3ccircle cx='8' cy='8.03' r='2'/%3e%3c/g%3e%3c/svg%3e") center no-repeat;
    width:16px;
    height:16px;
    content:""; }
  .bp3-breadcrumbs-collapsed:hover{
    background:#bfccd6;
    text-decoration:none;
    color:#182026; }

.bp3-dark .bp3-breadcrumb,
.bp3-dark .bp3-breadcrumbs-collapsed{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumbs > li::after{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumb.bp3-disabled{
  color:rgba(167, 182, 194, 0.6); }

.bp3-dark .bp3-breadcrumb-current{
  color:#f5f8fa; }

.bp3-dark .bp3-breadcrumbs-collapsed{
  background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-breadcrumbs-collapsed:hover{
    background:rgba(16, 22, 26, 0.6);
    color:#f5f8fa; }
.bp3-button{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  min-width:30px;
  min-height:30px; }
  .bp3-button > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-button > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-button::before,
  .bp3-button > *{
    margin-right:7px; }
  .bp3-button:empty::before,
  .bp3-button > :last-child{
    margin-right:0; }
  .bp3-button:empty{
    padding:0 !important; }
  .bp3-button:disabled, .bp3-button.bp3-disabled{
    cursor:not-allowed; }
  .bp3-button.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button.bp3-align-right,
  .bp3-align-right .bp3-button{
    text-align:right; }
  .bp3-button.bp3-align-left,
  .bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026; }
    .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-button:not([class*="bp3-intent-"]):active, .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active:hover, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-button.bp3-intent-primary{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover, .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#106ba3; }
    .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0e5a8a;
      background-image:none; }
    .bp3-button.bp3-intent-primary:disabled, .bp3-button.bp3-intent-primary.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(19, 124, 189, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-success{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#0f9960;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-success:hover, .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-success:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#0d8050; }
    .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0a6640;
      background-image:none; }
    .bp3-button.bp3-intent-success:disabled, .bp3-button.bp3-intent-success.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(15, 153, 96, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-warning{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#d9822b;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover, .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#bf7326; }
    .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a66321;
      background-image:none; }
    .bp3-button.bp3-intent-warning:disabled, .bp3-button.bp3-intent-warning.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(217, 130, 43, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-danger{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#db3737;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover, .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#c23030; }
    .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a82a2a;
      background-image:none; }
    .bp3-button.bp3-intent-danger:disabled, .bp3-button.bp3-intent-danger.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(219, 55, 55, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
    stroke:#ffffff; }
  .bp3-button.bp3-large,
  .bp3-large .bp3-button{
    min-width:40px;
    min-height:40px;
    padding:5px 15px;
    font-size:16px; }
    .bp3-button.bp3-large::before,
    .bp3-button.bp3-large > *,
    .bp3-large .bp3-button::before,
    .bp3-large .bp3-button > *{
      margin-right:10px; }
    .bp3-button.bp3-large:empty::before,
    .bp3-button.bp3-large > :last-child,
    .bp3-large .bp3-button:empty::before,
    .bp3-large .bp3-button > :last-child{
      margin-right:0; }
  .bp3-button.bp3-small,
  .bp3-small .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-button.bp3-loading{
    position:relative; }
    .bp3-button.bp3-loading[class*="bp3-icon-"]::before{
      visibility:hidden; }
    .bp3-button.bp3-loading .bp3-button-spinner{
      position:absolute;
      margin:0; }
    .bp3-button.bp3-loading > :not(.bp3-button-spinner){
      visibility:hidden; }
  .bp3-button[class*="bp3-icon-"]::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    color:#5c7080; }
  .bp3-button .bp3-icon, .bp3-button .bp3-icon-standard, .bp3-button .bp3-icon-large{
    color:#5c7080; }
    .bp3-button .bp3-icon.bp3-align-right, .bp3-button .bp3-icon-standard.bp3-align-right, .bp3-button .bp3-icon-large.bp3-align-right{
      margin-left:7px; }
  .bp3-button .bp3-icon:first-child:last-child,
  .bp3-button .bp3-spinner + .bp3-icon:last-child{
    margin:0 -7px; }
  .bp3-dark .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover, .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"])[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-large{
      color:#a7b6c2; }
  .bp3-dark .bp3-button[class*="bp3-intent-"]{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:active, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:disabled, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-image:none;
      color:rgba(255, 255, 255, 0.3); }
    .bp3-dark .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
      stroke:#8a9ba8; }
  .bp3-button:disabled::before,
  .bp3-button:disabled .bp3-icon, .bp3-button:disabled .bp3-icon-standard, .bp3-button:disabled .bp3-icon-large, .bp3-button.bp3-disabled::before,
  .bp3-button.bp3-disabled .bp3-icon, .bp3-button.bp3-disabled .bp3-icon-standard, .bp3-button.bp3-disabled .bp3-icon-large, .bp3-button[class*="bp3-intent-"]::before,
  .bp3-button[class*="bp3-intent-"] .bp3-icon, .bp3-button[class*="bp3-intent-"] .bp3-icon-standard, .bp3-button[class*="bp3-intent-"] .bp3-icon-large{
    color:inherit !important; }
  .bp3-button.bp3-minimal{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button.bp3-minimal:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button.bp3-minimal:active, .bp3-button.bp3-minimal.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button.bp3-minimal:disabled, .bp3-button.bp3-minimal:disabled:hover, .bp3-button.bp3-minimal.bp3-disabled, .bp3-button.bp3-minimal.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-minimal{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-minimal:hover, .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button.bp3-minimal:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-minimal:disabled, .bp3-dark .bp3-button.bp3-minimal:disabled:hover, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover, .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover, .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover, .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover, .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }

a.bp3-button{
  text-align:center;
  text-decoration:none;
  -webkit-transition:none;
  transition:none; }
  a.bp3-button, a.bp3-button:hover, a.bp3-button:active{
    color:#182026; }
  a.bp3-button.bp3-disabled{
    color:rgba(92, 112, 128, 0.6); }

.bp3-button-text{
  -webkit-box-flex:0;
      -ms-flex:0 1 auto;
          flex:0 1 auto; }

.bp3-button.bp3-align-left .bp3-button-text, .bp3-button.bp3-align-right .bp3-button-text,
.bp3-button-group.bp3-align-left .bp3-button-text,
.bp3-button-group.bp3-align-right .bp3-button-text{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto; }
.bp3-button-group{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex; }
  .bp3-button-group .bp3-button{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    position:relative;
    z-index:4; }
    .bp3-button-group .bp3-button:focus{
      z-index:5; }
    .bp3-button-group .bp3-button:hover{
      z-index:6; }
    .bp3-button-group .bp3-button:active, .bp3-button-group .bp3-button.bp3-active{
      z-index:7; }
    .bp3-button-group .bp3-button:disabled, .bp3-button-group .bp3-button.bp3-disabled{
      z-index:3; }
    .bp3-button-group .bp3-button[class*="bp3-intent-"]{
      z-index:9; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:focus{
        z-index:10; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:hover{
        z-index:11; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:active, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-active{
        z-index:12; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:disabled, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-disabled{
        z-index:8; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:first-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:first-child){
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:-1px;
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-button-group.bp3-minimal .bp3-button{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button-group.bp3-minimal .bp3-button:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button-group.bp3-minimal .bp3-button{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
      color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
      color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
  .bp3-button-group .bp3-popover-wrapper,
  .bp3-button-group .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button-group .bp3-button.bp3-fill,
  .bp3-button-group.bp3-fill .bp3-button:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    vertical-align:top; }
    .bp3-button-group.bp3-vertical.bp3-fill{
      width:unset;
      height:100%; }
    .bp3-button-group.bp3-vertical .bp3-button{
      margin-right:0 !important;
      width:100%; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:first-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:first-child{
      border-radius:3px 3px 0 0; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:last-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:last-child{
      border-radius:0 0 3px 3px; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:not(:last-child){
      margin-bottom:-1px; }
  .bp3-button-group.bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:1px; }
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-button:not(:last-child){
    margin-bottom:1px; }
.bp3-callout{
  line-height:1.5;
  font-size:14px;
  position:relative;
  border-radius:3px;
  background-color:rgba(138, 155, 168, 0.15);
  width:100%;
  padding:10px 12px 9px; }
  .bp3-callout[class*="bp3-icon-"]{
    padding-left:40px; }
    .bp3-callout[class*="bp3-icon-"]::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout.bp3-callout-icon{
    padding-left:40px; }
    .bp3-callout.bp3-callout-icon > .bp3-icon:first-child{
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout .bp3-heading{
    margin-top:0;
    margin-bottom:5px;
    line-height:20px; }
    .bp3-callout .bp3-heading:last-child{
      margin-bottom:0; }
  .bp3-dark .bp3-callout{
    background-color:rgba(138, 155, 168, 0.2); }
    .bp3-dark .bp3-callout[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
  .bp3-callout.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15); }
    .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-primary .bp3-heading{
      color:#106ba3; }
    .bp3-dark .bp3-callout.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-primary .bp3-heading{
        color:#48aff0; }
  .bp3-callout.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15); }
    .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-success .bp3-heading{
      color:#0d8050; }
    .bp3-dark .bp3-callout.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-success .bp3-heading{
        color:#3dcc91; }
  .bp3-callout.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15); }
    .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-warning .bp3-heading{
      color:#bf7326; }
    .bp3-dark .bp3-callout.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-warning .bp3-heading{
        color:#ffb366; }
  .bp3-callout.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15); }
    .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-danger .bp3-heading{
      color:#c23030; }
    .bp3-dark .bp3-callout.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-danger .bp3-heading{
        color:#ff7373; }
  .bp3-running-text .bp3-callout{
    margin:20px 0; }
.bp3-card{
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
  background-color:#ffffff;
  padding:20px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-card.bp3-dark,
  .bp3-dark .bp3-card{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
    background-color:#30404d; }

.bp3-elevation-0{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }
  .bp3-elevation-0.bp3-dark,
  .bp3-dark .bp3-elevation-0{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

.bp3-elevation-1{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-1.bp3-dark,
  .bp3-dark .bp3-elevation-1{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-elevation-2{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-2.bp3-dark,
  .bp3-dark .bp3-elevation-2{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4); }

.bp3-elevation-3{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-3.bp3-dark,
  .bp3-dark .bp3-elevation-3{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-elevation-4{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-4.bp3-dark,
  .bp3-dark .bp3-elevation-4{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:hover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  cursor:pointer; }
  .bp3-card.bp3-interactive:hover.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:active{
  opacity:0.9;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  -webkit-transition-duration:0;
          transition-duration:0; }
  .bp3-card.bp3-interactive:active.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-collapse{
  height:0;
  overflow-y:hidden;
  -webkit-transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-collapse .bp3-collapse-body{
    -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-collapse .bp3-collapse-body[aria-hidden="true"]{
      display:none; }

.bp3-context-menu .bp3-popover-target{
  display:block; }

.bp3-context-menu-popover-target{
  position:fixed; }

.bp3-divider{
  margin:5px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  border-bottom:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-dialog-container{
  opacity:1;
  -webkit-transform:scale(1);
          transform:scale(1);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  min-height:100%;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-dialog-container.bp3-overlay-enter > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5); }
  .bp3-dialog-container.bp3-overlay-enter-active > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear-active > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-dialog-container.bp3-overlay-exit > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-dialog-container.bp3-overlay-exit-active > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }

.bp3-dialog{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:30px 0;
  border-radius:6px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ebf1f5;
  width:500px;
  padding-bottom:20px;
  pointer-events:all;
  -webkit-user-select:text;
     -moz-user-select:text;
      -ms-user-select:text;
          user-select:text; }
  .bp3-dialog:focus{
    outline:0; }
  .bp3-dialog.bp3-dark,
  .bp3-dark .bp3-dialog{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#293742;
    color:#f5f8fa; }

.bp3-dialog-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border-radius:6px 6px 0 0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  background:#ffffff;
  min-height:40px;
  padding-right:5px;
  padding-left:20px; }
  .bp3-dialog-header .bp3-icon-large,
  .bp3-dialog-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-dialog-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-dialog-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-dialog-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
    background:#30404d; }
    .bp3-dark .bp3-dialog-header .bp3-icon-large,
    .bp3-dark .bp3-dialog-header .bp3-icon{
      color:#a7b6c2; }

.bp3-dialog-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  margin:20px;
  line-height:18px; }

.bp3-dialog-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  margin:0 20px; }

.bp3-dialog-footer-actions{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:end;
      -ms-flex-pack:end;
          justify-content:flex-end; }
  .bp3-dialog-footer-actions .bp3-button{
    margin-left:10px; }
.bp3-drawer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  padding:0; }
  .bp3-drawer:focus{
    outline:0; }
  .bp3-drawer.bp3-position-top{
    top:0;
    right:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter, .bp3-drawer.bp3-position-top.bp3-overlay-appear{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%); }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter-active, .bp3-drawer.bp3-position-top.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit-active{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-bottom{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter-active, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-left{
    top:0;
    bottom:0;
    left:0;
    width:50%; }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter, .bp3-drawer.bp3-position-left.bp3-overlay-appear{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%); }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter-active, .bp3-drawer.bp3-position-left.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit-active{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-right{
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter, .bp3-drawer.bp3-position-right.bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter-active, .bp3-drawer.bp3-position-right.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right):not(.bp3-vertical){
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right).bp3-vertical{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-dark,
  .bp3-dark .bp3-drawer{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#30404d;
    color:#f5f8fa; }

.bp3-drawer-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border-radius:0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  min-height:40px;
  padding:5px;
  padding-left:20px; }
  .bp3-drawer-header .bp3-icon-large,
  .bp3-drawer-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-drawer-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-drawer-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-drawer-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-drawer-header .bp3-icon-large,
    .bp3-dark .bp3-drawer-header .bp3-icon{
      color:#a7b6c2; }

.bp3-drawer-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  overflow:auto;
  line-height:18px; }

.bp3-drawer-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
  padding:10px 20px; }
  .bp3-dark .bp3-drawer-footer{
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4); }
.bp3-editable-text{
  display:inline-block;
  position:relative;
  cursor:text;
  max-width:100%;
  vertical-align:top;
  white-space:nowrap; }
  .bp3-editable-text::before{
    position:absolute;
    top:-3px;
    right:-3px;
    bottom:-3px;
    left:-3px;
    border-radius:3px;
    content:"";
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
  .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#137cbd; }
  .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4); }
  .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#0f9960; }
  .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4); }
  .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#d9822b; }
  .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4); }
  .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#db3737; }
  .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4); }
  .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15); }
  .bp3-dark .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
  .bp3-dark .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#48aff0; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4);
            box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#3dcc91; }
  .bp3-dark .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4);
            box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#ffb366; }
  .bp3-dark .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4);
            box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#ff7373; }
  .bp3-dark .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4);
            box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-editable-text-input,
.bp3-editable-text-content{
  display:inherit;
  position:relative;
  min-width:inherit;
  max-width:inherit;
  vertical-align:top;
  text-transform:inherit;
  letter-spacing:inherit;
  color:inherit;
  font:inherit;
  resize:none; }

.bp3-editable-text-input{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  width:100%;
  padding:0;
  white-space:pre-wrap; }
  .bp3-editable-text-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:focus{
    outline:none; }
  .bp3-editable-text-input::-ms-clear{
    display:none; }

.bp3-editable-text-content{
  overflow:hidden;
  padding-right:2px;
  text-overflow:ellipsis;
  white-space:pre; }
  .bp3-editable-text-editing > .bp3-editable-text-content{
    position:absolute;
    left:0;
    visibility:hidden; }
  .bp3-editable-text-placeholder > .bp3-editable-text-content{
    color:rgba(92, 112, 128, 0.6); }
    .bp3-dark .bp3-editable-text-placeholder > .bp3-editable-text-content{
      color:rgba(167, 182, 194, 0.6); }

.bp3-editable-text.bp3-multiline{
  display:block; }
  .bp3-editable-text.bp3-multiline .bp3-editable-text-content{
    overflow:auto;
    white-space:pre-wrap;
    word-wrap:break-word; }
.bp3-control-group{
  -webkit-transform:translateZ(0);
          transform:translateZ(0);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:stretch;
      -ms-flex-align:stretch;
          align-items:stretch; }
  .bp3-control-group > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select,
  .bp3-control-group .bp3-input,
  .bp3-control-group .bp3-select{
    position:relative; }
  .bp3-control-group .bp3-input{
    z-index:2;
    border-radius:inherit; }
    .bp3-control-group .bp3-input:focus{
      z-index:14;
      border-radius:3px; }
    .bp3-control-group .bp3-input[class*="bp3-intent"]{
      z-index:13; }
      .bp3-control-group .bp3-input[class*="bp3-intent"]:focus{
        z-index:15; }
    .bp3-control-group .bp3-input[readonly], .bp3-control-group .bp3-input:disabled, .bp3-control-group .bp3-input.bp3-disabled{
      z-index:1; }
  .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input{
    z-index:13; }
    .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input:focus{
      z-index:15; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select select,
  .bp3-control-group .bp3-select select{
    -webkit-transform:translateZ(0);
            transform:translateZ(0);
    z-index:4;
    border-radius:inherit; }
    .bp3-control-group .bp3-button:focus,
    .bp3-control-group .bp3-html-select select:focus,
    .bp3-control-group .bp3-select select:focus{
      z-index:5; }
    .bp3-control-group .bp3-button:hover,
    .bp3-control-group .bp3-html-select select:hover,
    .bp3-control-group .bp3-select select:hover{
      z-index:6; }
    .bp3-control-group .bp3-button:active,
    .bp3-control-group .bp3-html-select select:active,
    .bp3-control-group .bp3-select select:active{
      z-index:7; }
    .bp3-control-group .bp3-button[readonly], .bp3-control-group .bp3-button:disabled, .bp3-control-group .bp3-button.bp3-disabled,
    .bp3-control-group .bp3-html-select select[readonly],
    .bp3-control-group .bp3-html-select select:disabled,
    .bp3-control-group .bp3-html-select select.bp3-disabled,
    .bp3-control-group .bp3-select select[readonly],
    .bp3-control-group .bp3-select select:disabled,
    .bp3-control-group .bp3-select select.bp3-disabled{
      z-index:3; }
    .bp3-control-group .bp3-button[class*="bp3-intent"],
    .bp3-control-group .bp3-html-select select[class*="bp3-intent"],
    .bp3-control-group .bp3-select select[class*="bp3-intent"]{
      z-index:9; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:focus{
        z-index:10; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:hover{
        z-index:11; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:active{
        z-index:12; }
      .bp3-control-group .bp3-button[class*="bp3-intent"][readonly], .bp3-control-group .bp3-button[class*="bp3-intent"]:disabled, .bp3-control-group .bp3-button[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"].bp3-disabled{
        z-index:8; }
  .bp3-control-group .bp3-input-group > .bp3-icon,
  .bp3-control-group .bp3-input-group > .bp3-button,
  .bp3-control-group .bp3-input-group > .bp3-input-action{
    z-index:16; }
  .bp3-control-group .bp3-select::after,
  .bp3-control-group .bp3-html-select::after,
  .bp3-control-group .bp3-select > .bp3-icon,
  .bp3-control-group .bp3-html-select > .bp3-icon{
    z-index:17; }
  .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:-1px; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:0; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > .bp3-button + .bp3-button{
    margin-left:1px; }
  .bp3-control-group .bp3-popover-wrapper,
  .bp3-control-group .bp3-popover-target{
    border-radius:inherit; }
  .bp3-control-group > :first-child{
    border-radius:3px 0 0 3px; }
  .bp3-control-group > :last-child{
    margin-right:0;
    border-radius:0 3px 3px 0; }
  .bp3-control-group > :only-child{
    margin-right:0;
    border-radius:3px; }
  .bp3-control-group .bp3-input-group .bp3-button{
    border-radius:3px; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-fill > *:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-control-group.bp3-vertical > *{
      margin-top:-1px; }
    .bp3-control-group.bp3-vertical > :first-child{
      margin-top:0;
      border-radius:3px 3px 0 0; }
    .bp3-control-group.bp3-vertical > :last-child{
      border-radius:0 0 3px 3px; }
.bp3-control{
  display:block;
  position:relative;
  margin-bottom:10px;
  cursor:pointer;
  text-transform:none; }
  .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control:not(.bp3-align-right){
    padding-left:26px; }
    .bp3-control:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-26px; }
  .bp3-control.bp3-align-right{
    padding-right:26px; }
    .bp3-control.bp3-align-right .bp3-control-indicator{
      margin-right:-26px; }
  .bp3-control.bp3-disabled{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-control.bp3-inline{
    display:inline-block;
    margin-right:20px; }
  .bp3-control input{
    position:absolute;
    top:0;
    left:0;
    opacity:0;
    z-index:-1; }
  .bp3-control .bp3-control-indicator{
    display:inline-block;
    position:relative;
    margin-top:-3px;
    margin-right:10px;
    border:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    cursor:pointer;
    width:1em;
    height:1em;
    vertical-align:middle;
    font-size:16px;
    -webkit-user-select:none;
       -moz-user-select:none;
        -ms-user-select:none;
            user-select:none; }
    .bp3-control .bp3-control-indicator::before{
      display:block;
      width:1em;
      height:1em;
      content:""; }
  .bp3-control:hover .bp3-control-indicator{
    background-color:#ebf1f5; }
  .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#d8e1e8; }
  .bp3-control input:disabled ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed; }
  .bp3-control input:focus ~ .bp3-control-indicator{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:2px;
    -moz-outline-radius:6px; }
  .bp3-control.bp3-align-right .bp3-control-indicator{
    float:right;
    margin-top:1px;
    margin-left:10px; }
  .bp3-control.bp3-large{
    font-size:16px; }
    .bp3-control.bp3-large:not(.bp3-align-right){
      padding-left:30px; }
      .bp3-control.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
        margin-left:-30px; }
    .bp3-control.bp3-large.bp3-align-right{
      padding-right:30px; }
      .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
        margin-right:-30px; }
    .bp3-control.bp3-large .bp3-control-indicator{
      font-size:20px; }
    .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-top:0; }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control.bp3-checkbox .bp3-control-indicator{
    border-radius:3px; }
  .bp3-control.bp3-checkbox input:checked ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M12 5c-.28 0-.53.11-.71.29L7 9.59l-2.29-2.3a1.003 1.003 0 0 0-1.42 1.42l3 3c.18.18.43.29.71.29s.53-.11.71-.29l5-5A1.003 1.003 0 0 0 12 5z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M11 7H5c-.55 0-1 .45-1 1s.45 1 1 1h6c.55 0 1-.45 1-1s-.45-1-1-1z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-radio .bp3-control-indicator{
    border-radius:50%; }
  .bp3-control.bp3-radio input:checked ~ .bp3-control-indicator::before{
    background-image:radial-gradient(#ffffff, #ffffff 28%, transparent 32%); }
  .bp3-control.bp3-radio input:checked:disabled ~ .bp3-control-indicator::before{
    opacity:0.5; }
  .bp3-control.bp3-radio input:focus ~ .bp3-control-indicator{
    -moz-outline-radius:16px; }
  .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(167, 182, 194, 0.5); }
  .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(115, 134, 148, 0.5); }
  .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(92, 112, 128, 0.5); }
  .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5); }
    .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5); }
    .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch:not(.bp3-align-right){
    padding-left:38px; }
    .bp3-control.bp3-switch:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-38px; }
  .bp3-control.bp3-switch.bp3-align-right{
    padding-right:38px; }
    .bp3-control.bp3-switch.bp3-align-right .bp3-control-indicator{
      margin-right:-38px; }
  .bp3-control.bp3-switch .bp3-control-indicator{
    border:none;
    border-radius:1.75em;
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    width:auto;
    min-width:1.75em;
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-control.bp3-switch .bp3-control-indicator::before{
      position:absolute;
      left:0;
      margin:2px;
      border-radius:50%;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
      background:#ffffff;
      width:calc(1em - 4px);
      height:calc(1em - 4px);
      -webkit-transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    left:calc(100% - 1em); }
  .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right){
    padding-left:45px; }
    .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-45px; }
  .bp3-control.bp3-switch.bp3-large.bp3-align-right{
    padding-right:45px; }
    .bp3-control.bp3-switch.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-right:-45px; }
  .bp3-dark .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.7); }
  .bp3-dark .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.9); }
  .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(57, 75, 89, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-dark .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-dark .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch .bp3-control-indicator::before{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background:#394b59; }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-control.bp3-switch .bp3-switch-inner-text{
    text-align:center;
    font-size:0.7em; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:first-child{
    visibility:hidden;
    margin-right:1.2em;
    margin-left:0.5em;
    line-height:0; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:last-child{
    visibility:visible;
    margin-right:0.5em;
    margin-left:1.2em;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:first-child{
    visibility:visible;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:last-child{
    visibility:hidden;
    line-height:0; }
  .bp3-dark .bp3-control{
    color:#f5f8fa; }
    .bp3-dark .bp3-control.bp3-disabled{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-control .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0)); }
    .bp3-dark .bp3-control:hover .bp3-control-indicator{
      background-color:#30404d; }
    .bp3-dark .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background:#202b33; }
    .bp3-dark .bp3-control input:disabled ~ .bp3-control-indicator{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      cursor:not-allowed; }
    .bp3-dark .bp3-control.bp3-checkbox input:disabled:checked ~ .bp3-control-indicator, .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
      color:rgba(167, 182, 194, 0.6); }
.bp3-file-input{
  display:inline-block;
  position:relative;
  cursor:pointer;
  height:30px; }
  .bp3-file-input input{
    opacity:0;
    margin:0;
    min-width:200px; }
    .bp3-file-input input:disabled + .bp3-file-upload-input,
    .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(206, 217, 224, 0.5);
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6);
      resize:none; }
      .bp3-file-input input:disabled + .bp3-file-upload-input::after,
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
        outline:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(206, 217, 224, 0.5);
        background-image:none;
        cursor:not-allowed;
        color:rgba(92, 112, 128, 0.6); }
        .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active:hover,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active:hover{
          background:rgba(206, 217, 224, 0.7); }
      .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input, .bp3-dark
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:rgba(57, 75, 89, 0.5);
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after, .bp3-dark
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
          -webkit-box-shadow:none;
                  box-shadow:none;
          background-color:rgba(57, 75, 89, 0.5);
          background-image:none;
          color:rgba(167, 182, 194, 0.6); }
          .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-dark
          .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active{
            background:rgba(57, 75, 89, 0.7); }
  .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#182026; }
  .bp3-dark .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#f5f8fa; }
  .bp3-file-input.bp3-fill{
    width:100%; }
  .bp3-file-input.bp3-large,
  .bp3-large .bp3-file-input{
    height:40px; }
  .bp3-file-input .bp3-file-upload-input-custom-text::after{
    content:attr(bp3-button-text); }

.bp3-file-upload-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  position:absolute;
  top:0;
  right:0;
  left:0;
  padding-right:80px;
  color:rgba(92, 112, 128, 0.6);
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-file-upload-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:focus, .bp3-file-upload-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-file-upload-input[type="search"], .bp3-file-upload-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-file-upload-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-file-upload-input:disabled, .bp3-file-upload-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-file-upload-input::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026;
    min-width:24px;
    min-height:24px;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    position:absolute;
    top:0;
    right:0;
    margin:3px;
    border-radius:3px;
    width:70px;
    text-align:center;
    line-height:24px;
    content:"Browse"; }
    .bp3-file-upload-input::after:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-file-upload-input::after:active, .bp3-file-upload-input::after.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-file-upload-input::after:disabled, .bp3-file-upload-input::after.bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-file-upload-input::after:disabled.bp3-active, .bp3-file-upload-input::after:disabled.bp3-active:hover, .bp3-file-upload-input::after.bp3-disabled.bp3-active, .bp3-file-upload-input::after.bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-file-upload-input:hover::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-file-upload-input:active::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-large .bp3-file-upload-input{
    height:40px;
    line-height:40px;
    font-size:16px;
    padding-right:95px; }
    .bp3-large .bp3-file-upload-input[type="search"], .bp3-large .bp3-file-upload-input.bp3-round{
      padding:0 15px; }
    .bp3-large .bp3-file-upload-input::after{
      min-width:30px;
      min-height:30px;
      margin:5px;
      width:85px;
      line-height:30px; }
  .bp3-dark .bp3-file-upload-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:disabled, .bp3-dark .bp3-file-upload-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover, .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
        background-color:#30404d; }
      .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
        background-color:#202b33;
        background-image:none; }
      .bp3-dark .bp3-file-upload-input::after:disabled, .bp3-dark .bp3-file-upload-input::after.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(57, 75, 89, 0.5);
        background-image:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-upload-input::after:disabled.bp3-active, .bp3-dark .bp3-file-upload-input::after.bp3-disabled.bp3-active{
          background:rgba(57, 75, 89, 0.7); }
      .bp3-dark .bp3-file-upload-input::after .bp3-button-spinner .bp3-spinner-head{
        background:rgba(16, 22, 26, 0.5);
        stroke:#8a9ba8; }
    .bp3-dark .bp3-file-upload-input:hover::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-file-upload-input:active::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }

.bp3-file-upload-input::after{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
.bp3-form-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0 0 15px; }
  .bp3-form-group label.bp3-label{
    margin-bottom:5px; }
  .bp3-form-group .bp3-control{
    margin-top:7px; }
  .bp3-form-group .bp3-form-helper-text{
    margin-top:5px;
    color:#5c7080;
    font-size:12px; }
  .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#106ba3; }
  .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#0d8050; }
  .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#bf7326; }
  .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#c23030; }
  .bp3-form-group.bp3-inline{
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-form-group.bp3-inline.bp3-large label.bp3-label{
      margin:0 10px 0 0;
      line-height:40px; }
    .bp3-form-group.bp3-inline label.bp3-label{
      margin:0 10px 0 0;
      line-height:30px; }
  .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-dark .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#48aff0; }
  .bp3-dark .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#3dcc91; }
  .bp3-dark .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#ffb366; }
  .bp3-dark .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#ff7373; }
  .bp3-dark .bp3-form-group .bp3-form-helper-text{
    color:#a7b6c2; }
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(167, 182, 194, 0.6) !important; }
.bp3-input-group{
  display:block;
  position:relative; }
  .bp3-input-group .bp3-input{
    position:relative;
    width:100%; }
    .bp3-input-group .bp3-input:not(:first-child){
      padding-left:30px; }
    .bp3-input-group .bp3-input:not(:last-child){
      padding-right:30px; }
  .bp3-input-group .bp3-input-action,
  .bp3-input-group > .bp3-button,
  .bp3-input-group > .bp3-icon{
    position:absolute;
    top:0; }
    .bp3-input-group .bp3-input-action:first-child,
    .bp3-input-group > .bp3-button:first-child,
    .bp3-input-group > .bp3-icon:first-child{
      left:0; }
    .bp3-input-group .bp3-input-action:last-child,
    .bp3-input-group > .bp3-button:last-child,
    .bp3-input-group > .bp3-icon:last-child{
      right:0; }
  .bp3-input-group .bp3-button{
    min-width:24px;
    min-height:24px;
    margin:3px;
    padding:0 7px; }
    .bp3-input-group .bp3-button:empty{
      padding:0; }
  .bp3-input-group > .bp3-icon{
    z-index:1;
    color:#5c7080; }
    .bp3-input-group > .bp3-icon:empty{
      line-height:1;
      font-family:"Icons16", sans-serif;
      font-size:16px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased; }
  .bp3-input-group > .bp3-icon,
  .bp3-input-group .bp3-input-action > .bp3-spinner{
    margin:7px; }
  .bp3-input-group .bp3-tag{
    margin:5px; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus),
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
    color:#5c7080; }
    .bp3-dark .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus), .bp3-dark
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
      color:#a7b6c2; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large{
      color:#5c7080; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled,
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled{
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-large{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-input-group.bp3-disabled{
    cursor:not-allowed; }
    .bp3-input-group.bp3-disabled .bp3-icon{
      color:rgba(92, 112, 128, 0.6); }
  .bp3-input-group.bp3-large .bp3-button{
    min-width:30px;
    min-height:30px;
    margin:5px; }
  .bp3-input-group.bp3-large > .bp3-icon,
  .bp3-input-group.bp3-large .bp3-input-action > .bp3-spinner{
    margin:12px; }
  .bp3-input-group.bp3-large .bp3-input{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input-group.bp3-large .bp3-input[type="search"], .bp3-input-group.bp3-large .bp3-input.bp3-round{
      padding:0 15px; }
    .bp3-input-group.bp3-large .bp3-input:not(:first-child){
      padding-left:40px; }
    .bp3-input-group.bp3-large .bp3-input:not(:last-child){
      padding-right:40px; }
  .bp3-input-group.bp3-small .bp3-button{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small .bp3-tag{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small > .bp3-icon,
  .bp3-input-group.bp3-small .bp3-input-action > .bp3-spinner{
    margin:4px; }
  .bp3-input-group.bp3-small .bp3-input{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input-group.bp3-small .bp3-input[type="search"], .bp3-input-group.bp3-small .bp3-input.bp3-round{
      padding:0 12px; }
    .bp3-input-group.bp3-small .bp3-input:not(:first-child){
      padding-left:24px; }
    .bp3-input-group.bp3-small .bp3-input:not(:last-child){
      padding-right:24px; }
  .bp3-input-group.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-input-group.bp3-round .bp3-button,
  .bp3-input-group.bp3-round .bp3-input,
  .bp3-input-group.bp3-round .bp3-tag{
    border-radius:30px; }
  .bp3-dark .bp3-input-group .bp3-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-input-group.bp3-disabled .bp3-icon{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-input-group.bp3-intent-primary .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input-group.bp3-intent-primary .bp3-input:disabled, .bp3-input-group.bp3-intent-primary .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-primary > .bp3-icon{
    color:#106ba3; }
    .bp3-dark .bp3-input-group.bp3-intent-primary > .bp3-icon{
      color:#48aff0; }
  .bp3-input-group.bp3-intent-success .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input-group.bp3-intent-success .bp3-input:disabled, .bp3-input-group.bp3-intent-success .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-success > .bp3-icon{
    color:#0d8050; }
    .bp3-dark .bp3-input-group.bp3-intent-success > .bp3-icon{
      color:#3dcc91; }
  .bp3-input-group.bp3-intent-warning .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input-group.bp3-intent-warning .bp3-input:disabled, .bp3-input-group.bp3-intent-warning .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-warning > .bp3-icon{
    color:#bf7326; }
    .bp3-dark .bp3-input-group.bp3-intent-warning > .bp3-icon{
      color:#ffb366; }
  .bp3-input-group.bp3-intent-danger .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input-group.bp3-intent-danger .bp3-input:disabled, .bp3-input-group.bp3-intent-danger .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-danger > .bp3-icon{
    color:#c23030; }
    .bp3-dark .bp3-input-group.bp3-intent-danger > .bp3-icon{
      color:#ff7373; }
.bp3-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none; }
  .bp3-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:focus, .bp3-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-input[type="search"], .bp3-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-input:disabled, .bp3-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-input.bp3-large{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input.bp3-large[type="search"], .bp3-input.bp3-large.bp3-round{
      padding:0 15px; }
  .bp3-input.bp3-small{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input.bp3-small[type="search"], .bp3-input.bp3-small.bp3-round{
      padding:0 12px; }
  .bp3-input.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-dark .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark .bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input:disabled, .bp3-dark .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
  .bp3-input.bp3-intent-primary{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input.bp3-intent-primary:disabled, .bp3-input.bp3-intent-primary.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary:focus{
        -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #137cbd;
                box-shadow:inset 0 0 0 1px #137cbd; }
      .bp3-dark .bp3-input.bp3-intent-primary:disabled, .bp3-dark .bp3-input.bp3-intent-primary.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-success{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input.bp3-intent-success:disabled, .bp3-input.bp3-intent-success.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-success{
      -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success:focus{
        -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #0f9960;
                box-shadow:inset 0 0 0 1px #0f9960; }
      .bp3-dark .bp3-input.bp3-intent-success:disabled, .bp3-dark .bp3-input.bp3-intent-success.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-warning{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input.bp3-intent-warning:disabled, .bp3-input.bp3-intent-warning.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning:focus{
        -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #d9822b;
                box-shadow:inset 0 0 0 1px #d9822b; }
      .bp3-dark .bp3-input.bp3-intent-warning:disabled, .bp3-dark .bp3-input.bp3-intent-warning.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-danger{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input.bp3-intent-danger:disabled, .bp3-input.bp3-intent-danger.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger:focus{
        -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #db3737;
                box-shadow:inset 0 0 0 1px #db3737; }
      .bp3-dark .bp3-input.bp3-intent-danger:disabled, .bp3-dark .bp3-input.bp3-intent-danger.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input::-ms-clear{
    display:none; }
textarea.bp3-input{
  max-width:100%;
  padding:10px; }
  textarea.bp3-input, textarea.bp3-input.bp3-large, textarea.bp3-input.bp3-small{
    height:auto;
    line-height:inherit; }
  textarea.bp3-input.bp3-small{
    padding:8px; }
  .bp3-dark textarea.bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark textarea.bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input:disabled, .bp3-dark textarea.bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
label.bp3-label{
  display:block;
  margin-top:0;
  margin-bottom:15px; }
  label.bp3-label .bp3-html-select,
  label.bp3-label .bp3-input,
  label.bp3-label .bp3-select,
  label.bp3-label .bp3-slider,
  label.bp3-label .bp3-popover-wrapper{
    display:block;
    margin-top:5px;
    text-transform:none; }
  label.bp3-label .bp3-button-group{
    margin-top:5px; }
  label.bp3-label .bp3-select select,
  label.bp3-label .bp3-html-select select{
    width:100%;
    vertical-align:top;
    font-weight:400; }
  label.bp3-label.bp3-disabled,
  label.bp3-label.bp3-disabled .bp3-text-muted{
    color:rgba(92, 112, 128, 0.6); }
  label.bp3-label.bp3-inline{
    line-height:30px; }
    label.bp3-label.bp3-inline .bp3-html-select,
    label.bp3-label.bp3-inline .bp3-input,
    label.bp3-label.bp3-inline .bp3-input-group,
    label.bp3-label.bp3-inline .bp3-select,
    label.bp3-label.bp3-inline .bp3-popover-wrapper{
      display:inline-block;
      margin:0 0 0 5px;
      vertical-align:top; }
    label.bp3-label.bp3-inline .bp3-button-group{
      margin:0 0 0 5px; }
    label.bp3-label.bp3-inline .bp3-input-group .bp3-input{
      margin-left:0; }
    label.bp3-label.bp3-inline.bp3-large{
      line-height:40px; }
  label.bp3-label:not(.bp3-inline) .bp3-popover-target{
    display:block; }
  .bp3-dark label.bp3-label{
    color:#f5f8fa; }
    .bp3-dark label.bp3-label.bp3-disabled,
    .bp3-dark label.bp3-label.bp3-disabled .bp3-text-muted{
      color:rgba(167, 182, 194, 0.6); }
.bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button{
  -webkit-box-flex:1;
      -ms-flex:1 1 14px;
          flex:1 1 14px;
  width:30px;
  min-height:0;
  padding:0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:first-child{
    border-radius:0 3px 0 0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:last-child{
    border-radius:0 0 3px 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:first-child{
  border-radius:3px 0 0 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:last-child{
  border-radius:0 0 0 3px; }

.bp3-numeric-input.bp3-large .bp3-button-group.bp3-vertical > .bp3-button{
  width:40px; }

form{
  display:block; }
.bp3-html-select select,
.bp3-select select{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  border-radius:3px;
  width:100%;
  height:30px;
  padding:0 25px 0 10px;
  -moz-appearance:none;
  -webkit-appearance:none; }
  .bp3-html-select select > *, .bp3-select select > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-html-select select > .bp3-fill, .bp3-select select > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-html-select select::before,
  .bp3-select select::before, .bp3-html-select select > *, .bp3-select select > *{
    margin-right:7px; }
  .bp3-html-select select:empty::before,
  .bp3-select select:empty::before,
  .bp3-html-select select > :last-child,
  .bp3-select select > :last-child{
    margin-right:0; }
  .bp3-html-select select:hover,
  .bp3-select select:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-html-select select:active,
  .bp3-select select:active, .bp3-html-select select.bp3-active,
  .bp3-select select.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-html-select select:disabled,
  .bp3-select select:disabled, .bp3-html-select select.bp3-disabled,
  .bp3-select select.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select select:disabled.bp3-active,
    .bp3-select select:disabled.bp3-active, .bp3-html-select select:disabled.bp3-active:hover,
    .bp3-select select:disabled.bp3-active:hover, .bp3-html-select select.bp3-disabled.bp3-active,
    .bp3-select select.bp3-disabled.bp3-active, .bp3-html-select select.bp3-disabled.bp3-active:hover,
    .bp3-select select.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }

.bp3-html-select.bp3-minimal select,
.bp3-select.bp3-minimal select{
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none; }
  .bp3-html-select.bp3-minimal select:hover,
  .bp3-select.bp3-minimal select:hover{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(167, 182, 194, 0.3);
    text-decoration:none;
    color:#182026; }
  .bp3-html-select.bp3-minimal select:active,
  .bp3-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal select.bp3-active,
  .bp3-select.bp3-minimal select.bp3-active{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(115, 134, 148, 0.3);
    color:#182026; }
  .bp3-html-select.bp3-minimal select:disabled,
  .bp3-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal select:disabled:hover,
  .bp3-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal select.bp3-disabled,
  .bp3-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal select.bp3-disabled:hover,
  .bp3-select.bp3-minimal select.bp3-disabled:hover{
    background:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select.bp3-minimal select:disabled.bp3-active,
    .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active{
      background:rgba(115, 134, 148, 0.3); }
  .bp3-dark .bp3-html-select.bp3-minimal select, .bp3-html-select.bp3-minimal .bp3-dark select,
  .bp3-dark .bp3-select.bp3-minimal select, .bp3-select.bp3-minimal .bp3-dark select{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    color:inherit; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover, .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover{
      background:rgba(138, 155, 168, 0.15); }
    .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:rgba(138, 155, 168, 0.3);
      color:#f5f8fa; }
    .bp3-dark .bp3-html-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal .bp3-dark select:disabled,
    .bp3-dark .bp3-select.bp3-minimal select:disabled, .bp3-select.bp3-minimal .bp3-dark select:disabled, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select:disabled:hover, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-html-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active{
        background:rgba(138, 155, 168, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-primary,
  .bp3-select.bp3-minimal select.bp3-intent-primary{
    color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover{
      background:rgba(19, 124, 189, 0.15);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      background:rgba(19, 124, 189, 0.3);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled{
      background:none;
      color:rgba(16, 107, 163, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active{
        background:rgba(19, 124, 189, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
      stroke:#106ba3; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary{
      color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.2);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(72, 175, 240, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-success,
  .bp3-select.bp3-minimal select.bp3-intent-success{
    color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover{
      background:rgba(15, 153, 96, 0.15);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      background:rgba(15, 153, 96, 0.3);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled{
      background:none;
      color:rgba(13, 128, 80, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active{
        background:rgba(15, 153, 96, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
      stroke:#0d8050; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success{
      color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.2);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(61, 204, 145, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-warning,
  .bp3-select.bp3-minimal select.bp3-intent-warning{
    color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover{
      background:rgba(217, 130, 43, 0.15);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      background:rgba(217, 130, 43, 0.3);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled{
      background:none;
      color:rgba(191, 115, 38, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active{
        background:rgba(217, 130, 43, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
      stroke:#bf7326; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning{
      color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.2);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(255, 179, 102, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-danger,
  .bp3-select.bp3-minimal select.bp3-intent-danger{
    color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover{
      background:rgba(219, 55, 55, 0.15);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      background:rgba(219, 55, 55, 0.3);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled{
      background:none;
      color:rgba(194, 48, 48, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active{
        background:rgba(219, 55, 55, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
      stroke:#c23030; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger{
      color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.2);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(255, 115, 115, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }

.bp3-html-select.bp3-large select,
.bp3-select.bp3-large select{
  height:40px;
  padding-right:35px;
  font-size:16px; }

.bp3-dark .bp3-html-select select, .bp3-dark .bp3-select select{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
  background-color:#394b59;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
  color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover, .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }
  .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#202b33;
    background-image:none; }
  .bp3-dark .bp3-html-select select:disabled, .bp3-dark .bp3-select select:disabled, .bp3-dark .bp3-html-select select.bp3-disabled, .bp3-dark .bp3-select select.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(57, 75, 89, 0.5);
    background-image:none;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-html-select select:disabled.bp3-active, .bp3-dark .bp3-select select:disabled.bp3-active, .bp3-dark .bp3-html-select select.bp3-disabled.bp3-active, .bp3-dark .bp3-select select.bp3-disabled.bp3-active{
      background:rgba(57, 75, 89, 0.7); }
  .bp3-dark .bp3-html-select select .bp3-button-spinner .bp3-spinner-head, .bp3-dark .bp3-select select .bp3-button-spinner .bp3-spinner-head{
    background:rgba(16, 22, 26, 0.5);
    stroke:#8a9ba8; }

.bp3-html-select select:disabled,
.bp3-select select:disabled{
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:rgba(206, 217, 224, 0.5);
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-html-select .bp3-icon,
.bp3-select .bp3-icon, .bp3-select::after{
  position:absolute;
  top:7px;
  right:7px;
  color:#5c7080;
  pointer-events:none; }
  .bp3-html-select .bp3-disabled.bp3-icon,
  .bp3-select .bp3-disabled.bp3-icon, .bp3-disabled.bp3-select::after{
    color:rgba(92, 112, 128, 0.6); }
.bp3-html-select,
.bp3-select{
  display:inline-block;
  position:relative;
  vertical-align:middle;
  letter-spacing:normal; }
  .bp3-html-select select::-ms-expand,
  .bp3-select select::-ms-expand{
    display:none; }
  .bp3-html-select .bp3-icon,
  .bp3-select .bp3-icon{
    color:#5c7080; }
    .bp3-html-select .bp3-icon:hover,
    .bp3-select .bp3-icon:hover{
      color:#182026; }
    .bp3-dark .bp3-html-select .bp3-icon, .bp3-dark
    .bp3-select .bp3-icon{
      color:#a7b6c2; }
      .bp3-dark .bp3-html-select .bp3-icon:hover, .bp3-dark
      .bp3-select .bp3-icon:hover{
        color:#f5f8fa; }
  .bp3-html-select.bp3-large::after,
  .bp3-html-select.bp3-large .bp3-icon,
  .bp3-select.bp3-large::after,
  .bp3-select.bp3-large .bp3-icon{
    top:12px;
    right:12px; }
  .bp3-html-select.bp3-fill,
  .bp3-html-select.bp3-fill select,
  .bp3-select.bp3-fill,
  .bp3-select.bp3-fill select{
    width:100%; }
  .bp3-dark .bp3-html-select option, .bp3-dark
  .bp3-select option{
    background-color:#30404d;
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select::after, .bp3-dark
  .bp3-select::after{
    color:#a7b6c2; }

.bp3-select::after{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  content:""; }
.bp3-running-text table, table.bp3-html-table{
  border-spacing:0;
  font-size:14px; }
  .bp3-running-text table th, table.bp3-html-table th,
  .bp3-running-text table td,
  table.bp3-html-table td{
    padding:11px;
    vertical-align:top;
    text-align:left; }
  .bp3-running-text table th, table.bp3-html-table th{
    color:#182026;
    font-weight:600; }
  
  .bp3-running-text table td,
  table.bp3-html-table td{
    color:#182026; }
  .bp3-running-text table tbody tr:first-child th, table.bp3-html-table tbody tr:first-child th,
  .bp3-running-text table tbody tr:first-child td,
  table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-running-text table th, .bp3-running-text .bp3-dark table th, .bp3-dark table.bp3-html-table th{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table td, .bp3-running-text .bp3-dark table td, .bp3-dark table.bp3-html-table td{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table tbody tr:first-child th, .bp3-running-text .bp3-dark table tbody tr:first-child th, .bp3-dark table.bp3-html-table tbody tr:first-child th,
  .bp3-dark .bp3-running-text table tbody tr:first-child td,
  .bp3-running-text .bp3-dark table tbody tr:first-child td,
  .bp3-dark table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }

table.bp3-html-table.bp3-html-table-condensed th,
table.bp3-html-table.bp3-html-table-condensed td, table.bp3-html-table.bp3-small th,
table.bp3-html-table.bp3-small td{
  padding-top:6px;
  padding-bottom:6px; }

table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(191, 204, 214, 0.15); }

table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:none;
          box-shadow:none; }
  table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(191, 204, 214, 0.3);
  cursor:pointer; }

table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(191, 204, 214, 0.4); }

.bp3-dark table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(92, 112, 128, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:first-child{
    -webkit-box-shadow:none;
            box-shadow:none; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(92, 112, 128, 0.3);
  cursor:pointer; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(92, 112, 128, 0.4); }

.bp3-key-combo{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center; }
  .bp3-key-combo > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-key-combo > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-key-combo::before,
  .bp3-key-combo > *{
    margin-right:5px; }
  .bp3-key-combo:empty::before,
  .bp3-key-combo > :last-child{
    margin-right:0; }

.bp3-hotkey-dialog{
  top:40px;
  padding-bottom:0; }
  .bp3-hotkey-dialog .bp3-dialog-body{
    margin:0;
    padding:0; }
  .bp3-hotkey-dialog .bp3-hotkey-label{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1; }

.bp3-hotkey-column{
  margin:auto;
  max-height:80vh;
  overflow-y:auto;
  padding:30px; }
  .bp3-hotkey-column .bp3-heading{
    margin-bottom:20px; }
    .bp3-hotkey-column .bp3-heading:not(:first-child){
      margin-top:40px; }

.bp3-hotkey{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:justify;
      -ms-flex-pack:justify;
          justify-content:space-between;
  margin-right:0;
  margin-left:0; }
  .bp3-hotkey:not(:last-child){
    margin-bottom:10px; }
.bp3-icon{
  display:inline-block;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  vertical-align:text-bottom; }
  .bp3-icon:not(:empty)::before{
    content:"" !important;
    content:unset !important; }
  .bp3-icon > svg{
    display:block; }
    .bp3-icon > svg:not([fill]){
      fill:currentColor; }

.bp3-icon.bp3-intent-primary, .bp3-icon-standard.bp3-intent-primary, .bp3-icon-large.bp3-intent-primary{
  color:#106ba3; }
  .bp3-dark .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-icon-large.bp3-intent-primary{
    color:#48aff0; }

.bp3-icon.bp3-intent-success, .bp3-icon-standard.bp3-intent-success, .bp3-icon-large.bp3-intent-success{
  color:#0d8050; }
  .bp3-dark .bp3-icon.bp3-intent-success, .bp3-dark .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-icon-large.bp3-intent-success{
    color:#3dcc91; }

.bp3-icon.bp3-intent-warning, .bp3-icon-standard.bp3-intent-warning, .bp3-icon-large.bp3-intent-warning{
  color:#bf7326; }
  .bp3-dark .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-icon-large.bp3-intent-warning{
    color:#ffb366; }

.bp3-icon.bp3-intent-danger, .bp3-icon-standard.bp3-intent-danger, .bp3-icon-large.bp3-intent-danger{
  color:#c23030; }
  .bp3-dark .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-icon-large.bp3-intent-danger{
    color:#ff7373; }

span.bp3-icon-standard{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon-large{
  line-height:1;
  font-family:"Icons20", sans-serif;
  font-size:20px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon:empty{
  line-height:1;
  font-family:"Icons20";
  font-size:inherit;
  font-weight:400;
  font-style:normal; }
  span.bp3-icon:empty::before{
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased; }

.bp3-icon-add::before{
  content:""; }

.bp3-icon-add-column-left::before{
  content:""; }

.bp3-icon-add-column-right::before{
  content:""; }

.bp3-icon-add-row-bottom::before{
  content:""; }

.bp3-icon-add-row-top::before{
  content:""; }

.bp3-icon-add-to-artifact::before{
  content:""; }

.bp3-icon-add-to-folder::before{
  content:""; }

.bp3-icon-airplane::before{
  content:""; }

.bp3-icon-align-center::before{
  content:""; }

.bp3-icon-align-justify::before{
  content:""; }

.bp3-icon-align-left::before{
  content:""; }

.bp3-icon-align-right::before{
  content:""; }

.bp3-icon-alignment-bottom::before{
  content:""; }

.bp3-icon-alignment-horizontal-center::before{
  content:""; }

.bp3-icon-alignment-left::before{
  content:""; }

.bp3-icon-alignment-right::before{
  content:""; }

.bp3-icon-alignment-top::before{
  content:""; }

.bp3-icon-alignment-vertical-center::before{
  content:""; }

.bp3-icon-annotation::before{
  content:""; }

.bp3-icon-application::before{
  content:""; }

.bp3-icon-applications::before{
  content:""; }

.bp3-icon-archive::before{
  content:""; }

.bp3-icon-arrow-bottom-left::before{
  content:"↙"; }

.bp3-icon-arrow-bottom-right::before{
  content:"↘"; }

.bp3-icon-arrow-down::before{
  content:"↓"; }

.bp3-icon-arrow-left::before{
  content:"←"; }

.bp3-icon-arrow-right::before{
  content:"→"; }

.bp3-icon-arrow-top-left::before{
  content:"↖"; }

.bp3-icon-arrow-top-right::before{
  content:"↗"; }

.bp3-icon-arrow-up::before{
  content:"↑"; }

.bp3-icon-arrows-horizontal::before{
  content:"↔"; }

.bp3-icon-arrows-vertical::before{
  content:"↕"; }

.bp3-icon-asterisk::before{
  content:"*"; }

.bp3-icon-automatic-updates::before{
  content:""; }

.bp3-icon-badge::before{
  content:""; }

.bp3-icon-ban-circle::before{
  content:""; }

.bp3-icon-bank-account::before{
  content:""; }

.bp3-icon-barcode::before{
  content:""; }

.bp3-icon-blank::before{
  content:""; }

.bp3-icon-blocked-person::before{
  content:""; }

.bp3-icon-bold::before{
  content:""; }

.bp3-icon-book::before{
  content:""; }

.bp3-icon-bookmark::before{
  content:""; }

.bp3-icon-box::before{
  content:""; }

.bp3-icon-briefcase::before{
  content:""; }

.bp3-icon-bring-data::before{
  content:""; }

.bp3-icon-build::before{
  content:""; }

.bp3-icon-calculator::before{
  content:""; }

.bp3-icon-calendar::before{
  content:""; }

.bp3-icon-camera::before{
  content:""; }

.bp3-icon-caret-down::before{
  content:"⌄"; }

.bp3-icon-caret-left::before{
  content:"〈"; }

.bp3-icon-caret-right::before{
  content:"〉"; }

.bp3-icon-caret-up::before{
  content:"⌃"; }

.bp3-icon-cell-tower::before{
  content:""; }

.bp3-icon-changes::before{
  content:""; }

.bp3-icon-chart::before{
  content:""; }

.bp3-icon-chat::before{
  content:""; }

.bp3-icon-chevron-backward::before{
  content:""; }

.bp3-icon-chevron-down::before{
  content:""; }

.bp3-icon-chevron-forward::before{
  content:""; }

.bp3-icon-chevron-left::before{
  content:""; }

.bp3-icon-chevron-right::before{
  content:""; }

.bp3-icon-chevron-up::before{
  content:""; }

.bp3-icon-circle::before{
  content:""; }

.bp3-icon-circle-arrow-down::before{
  content:""; }

.bp3-icon-circle-arrow-left::before{
  content:""; }

.bp3-icon-circle-arrow-right::before{
  content:""; }

.bp3-icon-circle-arrow-up::before{
  content:""; }

.bp3-icon-citation::before{
  content:""; }

.bp3-icon-clean::before{
  content:""; }

.bp3-icon-clipboard::before{
  content:""; }

.bp3-icon-cloud::before{
  content:"☁"; }

.bp3-icon-cloud-download::before{
  content:""; }

.bp3-icon-cloud-upload::before{
  content:""; }

.bp3-icon-code::before{
  content:""; }

.bp3-icon-code-block::before{
  content:""; }

.bp3-icon-cog::before{
  content:""; }

.bp3-icon-collapse-all::before{
  content:""; }

.bp3-icon-column-layout::before{
  content:""; }

.bp3-icon-comment::before{
  content:""; }

.bp3-icon-comparison::before{
  content:""; }

.bp3-icon-compass::before{
  content:""; }

.bp3-icon-compressed::before{
  content:""; }

.bp3-icon-confirm::before{
  content:""; }

.bp3-icon-console::before{
  content:""; }

.bp3-icon-contrast::before{
  content:""; }

.bp3-icon-control::before{
  content:""; }

.bp3-icon-credit-card::before{
  content:""; }

.bp3-icon-cross::before{
  content:"✗"; }

.bp3-icon-crown::before{
  content:""; }

.bp3-icon-cube::before{
  content:""; }

.bp3-icon-cube-add::before{
  content:""; }

.bp3-icon-cube-remove::before{
  content:""; }

.bp3-icon-curved-range-chart::before{
  content:""; }

.bp3-icon-cut::before{
  content:""; }

.bp3-icon-dashboard::before{
  content:""; }

.bp3-icon-data-lineage::before{
  content:""; }

.bp3-icon-database::before{
  content:""; }

.bp3-icon-delete::before{
  content:""; }

.bp3-icon-delta::before{
  content:"Δ"; }

.bp3-icon-derive-column::before{
  content:""; }

.bp3-icon-desktop::before{
  content:""; }

.bp3-icon-diagram-tree::before{
  content:""; }

.bp3-icon-direction-left::before{
  content:""; }

.bp3-icon-direction-right::before{
  content:""; }

.bp3-icon-disable::before{
  content:""; }

.bp3-icon-document::before{
  content:""; }

.bp3-icon-document-open::before{
  content:""; }

.bp3-icon-document-share::before{
  content:""; }

.bp3-icon-dollar::before{
  content:"$"; }

.bp3-icon-dot::before{
  content:"•"; }

.bp3-icon-double-caret-horizontal::before{
  content:""; }

.bp3-icon-double-caret-vertical::before{
  content:""; }

.bp3-icon-double-chevron-down::before{
  content:""; }

.bp3-icon-double-chevron-left::before{
  content:""; }

.bp3-icon-double-chevron-right::before{
  content:""; }

.bp3-icon-double-chevron-up::before{
  content:""; }

.bp3-icon-doughnut-chart::before{
  content:""; }

.bp3-icon-download::before{
  content:""; }

.bp3-icon-drag-handle-horizontal::before{
  content:""; }

.bp3-icon-drag-handle-vertical::before{
  content:""; }

.bp3-icon-draw::before{
  content:""; }

.bp3-icon-drive-time::before{
  content:""; }

.bp3-icon-duplicate::before{
  content:""; }

.bp3-icon-edit::before{
  content:"✎"; }

.bp3-icon-eject::before{
  content:"⏏"; }

.bp3-icon-endorsed::before{
  content:""; }

.bp3-icon-envelope::before{
  content:"✉"; }

.bp3-icon-equals::before{
  content:""; }

.bp3-icon-eraser::before{
  content:""; }

.bp3-icon-error::before{
  content:""; }

.bp3-icon-euro::before{
  content:"€"; }

.bp3-icon-exchange::before{
  content:""; }

.bp3-icon-exclude-row::before{
  content:""; }

.bp3-icon-expand-all::before{
  content:""; }

.bp3-icon-export::before{
  content:""; }

.bp3-icon-eye-off::before{
  content:""; }

.bp3-icon-eye-on::before{
  content:""; }

.bp3-icon-eye-open::before{
  content:""; }

.bp3-icon-fast-backward::before{
  content:""; }

.bp3-icon-fast-forward::before{
  content:""; }

.bp3-icon-feed::before{
  content:""; }

.bp3-icon-feed-subscribed::before{
  content:""; }

.bp3-icon-film::before{
  content:""; }

.bp3-icon-filter::before{
  content:""; }

.bp3-icon-filter-keep::before{
  content:""; }

.bp3-icon-filter-list::before{
  content:""; }

.bp3-icon-filter-open::before{
  content:""; }

.bp3-icon-filter-remove::before{
  content:""; }

.bp3-icon-flag::before{
  content:"⚑"; }

.bp3-icon-flame::before{
  content:""; }

.bp3-icon-flash::before{
  content:""; }

.bp3-icon-floppy-disk::before{
  content:""; }

.bp3-icon-flow-branch::before{
  content:""; }

.bp3-icon-flow-end::before{
  content:""; }

.bp3-icon-flow-linear::before{
  content:""; }

.bp3-icon-flow-review::before{
  content:""; }

.bp3-icon-flow-review-branch::before{
  content:""; }

.bp3-icon-flows::before{
  content:""; }

.bp3-icon-folder-close::before{
  content:""; }

.bp3-icon-folder-new::before{
  content:""; }

.bp3-icon-folder-open::before{
  content:""; }

.bp3-icon-folder-shared::before{
  content:""; }

.bp3-icon-folder-shared-open::before{
  content:""; }

.bp3-icon-follower::before{
  content:""; }

.bp3-icon-following::before{
  content:""; }

.bp3-icon-font::before{
  content:""; }

.bp3-icon-fork::before{
  content:""; }

.bp3-icon-form::before{
  content:""; }

.bp3-icon-full-circle::before{
  content:""; }

.bp3-icon-full-stacked-chart::before{
  content:""; }

.bp3-icon-fullscreen::before{
  content:""; }

.bp3-icon-function::before{
  content:""; }

.bp3-icon-gantt-chart::before{
  content:""; }

.bp3-icon-geolocation::before{
  content:""; }

.bp3-icon-geosearch::before{
  content:""; }

.bp3-icon-git-branch::before{
  content:""; }

.bp3-icon-git-commit::before{
  content:""; }

.bp3-icon-git-merge::before{
  content:""; }

.bp3-icon-git-new-branch::before{
  content:""; }

.bp3-icon-git-pull::before{
  content:""; }

.bp3-icon-git-push::before{
  content:""; }

.bp3-icon-git-repo::before{
  content:""; }

.bp3-icon-glass::before{
  content:""; }

.bp3-icon-globe::before{
  content:""; }

.bp3-icon-globe-network::before{
  content:""; }

.bp3-icon-graph::before{
  content:""; }

.bp3-icon-graph-remove::before{
  content:""; }

.bp3-icon-greater-than::before{
  content:""; }

.bp3-icon-greater-than-or-equal-to::before{
  content:""; }

.bp3-icon-grid::before{
  content:""; }

.bp3-icon-grid-view::before{
  content:""; }

.bp3-icon-group-objects::before{
  content:""; }

.bp3-icon-grouped-bar-chart::before{
  content:""; }

.bp3-icon-hand::before{
  content:""; }

.bp3-icon-hand-down::before{
  content:""; }

.bp3-icon-hand-left::before{
  content:""; }

.bp3-icon-hand-right::before{
  content:""; }

.bp3-icon-hand-up::before{
  content:""; }

.bp3-icon-header::before{
  content:""; }

.bp3-icon-header-one::before{
  content:""; }

.bp3-icon-header-two::before{
  content:""; }

.bp3-icon-headset::before{
  content:""; }

.bp3-icon-heart::before{
  content:"♥"; }

.bp3-icon-heart-broken::before{
  content:""; }

.bp3-icon-heat-grid::before{
  content:""; }

.bp3-icon-heatmap::before{
  content:""; }

.bp3-icon-help::before{
  content:"?"; }

.bp3-icon-helper-management::before{
  content:""; }

.bp3-icon-highlight::before{
  content:""; }

.bp3-icon-history::before{
  content:""; }

.bp3-icon-home::before{
  content:"⌂"; }

.bp3-icon-horizontal-bar-chart::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-asc::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-desc::before{
  content:""; }

.bp3-icon-horizontal-distribution::before{
  content:""; }

.bp3-icon-id-number::before{
  content:""; }

.bp3-icon-image-rotate-left::before{
  content:""; }

.bp3-icon-image-rotate-right::before{
  content:""; }

.bp3-icon-import::before{
  content:""; }

.bp3-icon-inbox::before{
  content:""; }

.bp3-icon-inbox-filtered::before{
  content:""; }

.bp3-icon-inbox-geo::before{
  content:""; }

.bp3-icon-inbox-search::before{
  content:""; }

.bp3-icon-inbox-update::before{
  content:""; }

.bp3-icon-info-sign::before{
  content:"ℹ"; }

.bp3-icon-inheritance::before{
  content:""; }

.bp3-icon-inner-join::before{
  content:""; }

.bp3-icon-insert::before{
  content:""; }

.bp3-icon-intersection::before{
  content:""; }

.bp3-icon-ip-address::before{
  content:""; }

.bp3-icon-issue::before{
  content:""; }

.bp3-icon-issue-closed::before{
  content:""; }

.bp3-icon-issue-new::before{
  content:""; }

.bp3-icon-italic::before{
  content:""; }

.bp3-icon-join-table::before{
  content:""; }

.bp3-icon-key::before{
  content:""; }

.bp3-icon-key-backspace::before{
  content:""; }

.bp3-icon-key-command::before{
  content:""; }

.bp3-icon-key-control::before{
  content:""; }

.bp3-icon-key-delete::before{
  content:""; }

.bp3-icon-key-enter::before{
  content:""; }

.bp3-icon-key-escape::before{
  content:""; }

.bp3-icon-key-option::before{
  content:""; }

.bp3-icon-key-shift::before{
  content:""; }

.bp3-icon-key-tab::before{
  content:""; }

.bp3-icon-known-vehicle::before{
  content:""; }

.bp3-icon-label::before{
  content:""; }

.bp3-icon-layer::before{
  content:""; }

.bp3-icon-layers::before{
  content:""; }

.bp3-icon-layout::before{
  content:""; }

.bp3-icon-layout-auto::before{
  content:""; }

.bp3-icon-layout-balloon::before{
  content:""; }

.bp3-icon-layout-circle::before{
  content:""; }

.bp3-icon-layout-grid::before{
  content:""; }

.bp3-icon-layout-group-by::before{
  content:""; }

.bp3-icon-layout-hierarchy::before{
  content:""; }

.bp3-icon-layout-linear::before{
  content:""; }

.bp3-icon-layout-skew-grid::before{
  content:""; }

.bp3-icon-layout-sorted-clusters::before{
  content:""; }

.bp3-icon-learning::before{
  content:""; }

.bp3-icon-left-join::before{
  content:""; }

.bp3-icon-less-than::before{
  content:""; }

.bp3-icon-less-than-or-equal-to::before{
  content:""; }

.bp3-icon-lifesaver::before{
  content:""; }

.bp3-icon-lightbulb::before{
  content:""; }

.bp3-icon-link::before{
  content:""; }

.bp3-icon-list::before{
  content:"☰"; }

.bp3-icon-list-columns::before{
  content:""; }

.bp3-icon-list-detail-view::before{
  content:""; }

.bp3-icon-locate::before{
  content:""; }

.bp3-icon-lock::before{
  content:""; }

.bp3-icon-log-in::before{
  content:""; }

.bp3-icon-log-out::before{
  content:""; }

.bp3-icon-manual::before{
  content:""; }

.bp3-icon-manually-entered-data::before{
  content:""; }

.bp3-icon-map::before{
  content:""; }

.bp3-icon-map-create::before{
  content:""; }

.bp3-icon-map-marker::before{
  content:""; }

.bp3-icon-maximize::before{
  content:""; }

.bp3-icon-media::before{
  content:""; }

.bp3-icon-menu::before{
  content:""; }

.bp3-icon-menu-closed::before{
  content:""; }

.bp3-icon-menu-open::before{
  content:""; }

.bp3-icon-merge-columns::before{
  content:""; }

.bp3-icon-merge-links::before{
  content:""; }

.bp3-icon-minimize::before{
  content:""; }

.bp3-icon-minus::before{
  content:"−"; }

.bp3-icon-mobile-phone::before{
  content:""; }

.bp3-icon-mobile-video::before{
  content:""; }

.bp3-icon-moon::before{
  content:""; }

.bp3-icon-more::before{
  content:""; }

.bp3-icon-mountain::before{
  content:""; }

.bp3-icon-move::before{
  content:""; }

.bp3-icon-mugshot::before{
  content:""; }

.bp3-icon-multi-select::before{
  content:""; }

.bp3-icon-music::before{
  content:""; }

.bp3-icon-new-drawing::before{
  content:""; }

.bp3-icon-new-grid-item::before{
  content:""; }

.bp3-icon-new-layer::before{
  content:""; }

.bp3-icon-new-layers::before{
  content:""; }

.bp3-icon-new-link::before{
  content:""; }

.bp3-icon-new-object::before{
  content:""; }

.bp3-icon-new-person::before{
  content:""; }

.bp3-icon-new-prescription::before{
  content:""; }

.bp3-icon-new-text-box::before{
  content:""; }

.bp3-icon-ninja::before{
  content:""; }

.bp3-icon-not-equal-to::before{
  content:""; }

.bp3-icon-notifications::before{
  content:""; }

.bp3-icon-notifications-updated::before{
  content:""; }

.bp3-icon-numbered-list::before{
  content:""; }

.bp3-icon-numerical::before{
  content:""; }

.bp3-icon-office::before{
  content:""; }

.bp3-icon-offline::before{
  content:""; }

.bp3-icon-oil-field::before{
  content:""; }

.bp3-icon-one-column::before{
  content:""; }

.bp3-icon-outdated::before{
  content:""; }

.bp3-icon-page-layout::before{
  content:""; }

.bp3-icon-panel-stats::before{
  content:""; }

.bp3-icon-panel-table::before{
  content:""; }

.bp3-icon-paperclip::before{
  content:""; }

.bp3-icon-paragraph::before{
  content:""; }

.bp3-icon-path::before{
  content:""; }

.bp3-icon-path-search::before{
  content:""; }

.bp3-icon-pause::before{
  content:""; }

.bp3-icon-people::before{
  content:""; }

.bp3-icon-percentage::before{
  content:""; }

.bp3-icon-person::before{
  content:""; }

.bp3-icon-phone::before{
  content:"☎"; }

.bp3-icon-pie-chart::before{
  content:""; }

.bp3-icon-pin::before{
  content:""; }

.bp3-icon-pivot::before{
  content:""; }

.bp3-icon-pivot-table::before{
  content:""; }

.bp3-icon-play::before{
  content:""; }

.bp3-icon-plus::before{
  content:"+"; }

.bp3-icon-polygon-filter::before{
  content:""; }

.bp3-icon-power::before{
  content:""; }

.bp3-icon-predictive-analysis::before{
  content:""; }

.bp3-icon-prescription::before{
  content:""; }

.bp3-icon-presentation::before{
  content:""; }

.bp3-icon-print::before{
  content:"⎙"; }

.bp3-icon-projects::before{
  content:""; }

.bp3-icon-properties::before{
  content:""; }

.bp3-icon-property::before{
  content:""; }

.bp3-icon-publish-function::before{
  content:""; }

.bp3-icon-pulse::before{
  content:""; }

.bp3-icon-random::before{
  content:""; }

.bp3-icon-record::before{
  content:""; }

.bp3-icon-redo::before{
  content:""; }

.bp3-icon-refresh::before{
  content:""; }

.bp3-icon-regression-chart::before{
  content:""; }

.bp3-icon-remove::before{
  content:""; }

.bp3-icon-remove-column::before{
  content:""; }

.bp3-icon-remove-column-left::before{
  content:""; }

.bp3-icon-remove-column-right::before{
  content:""; }

.bp3-icon-remove-row-bottom::before{
  content:""; }

.bp3-icon-remove-row-top::before{
  content:""; }

.bp3-icon-repeat::before{
  content:""; }

.bp3-icon-reset::before{
  content:""; }

.bp3-icon-resolve::before{
  content:""; }

.bp3-icon-rig::before{
  content:""; }

.bp3-icon-right-join::before{
  content:""; }

.bp3-icon-ring::before{
  content:""; }

.bp3-icon-rotate-document::before{
  content:""; }

.bp3-icon-rotate-page::before{
  content:""; }

.bp3-icon-satellite::before{
  content:""; }

.bp3-icon-saved::before{
  content:""; }

.bp3-icon-scatter-plot::before{
  content:""; }

.bp3-icon-search::before{
  content:""; }

.bp3-icon-search-around::before{
  content:""; }

.bp3-icon-search-template::before{
  content:""; }

.bp3-icon-search-text::before{
  content:""; }

.bp3-icon-segmented-control::before{
  content:""; }

.bp3-icon-select::before{
  content:""; }

.bp3-icon-selection::before{
  content:"⦿"; }

.bp3-icon-send-to::before{
  content:""; }

.bp3-icon-send-to-graph::before{
  content:""; }

.bp3-icon-send-to-map::before{
  content:""; }

.bp3-icon-series-add::before{
  content:""; }

.bp3-icon-series-configuration::before{
  content:""; }

.bp3-icon-series-derived::before{
  content:""; }

.bp3-icon-series-filtered::before{
  content:""; }

.bp3-icon-series-search::before{
  content:""; }

.bp3-icon-settings::before{
  content:""; }

.bp3-icon-share::before{
  content:""; }

.bp3-icon-shield::before{
  content:""; }

.bp3-icon-shop::before{
  content:""; }

.bp3-icon-shopping-cart::before{
  content:""; }

.bp3-icon-signal-search::before{
  content:""; }

.bp3-icon-sim-card::before{
  content:""; }

.bp3-icon-slash::before{
  content:""; }

.bp3-icon-small-cross::before{
  content:""; }

.bp3-icon-small-minus::before{
  content:""; }

.bp3-icon-small-plus::before{
  content:""; }

.bp3-icon-small-tick::before{
  content:""; }

.bp3-icon-snowflake::before{
  content:""; }

.bp3-icon-social-media::before{
  content:""; }

.bp3-icon-sort::before{
  content:""; }

.bp3-icon-sort-alphabetical::before{
  content:""; }

.bp3-icon-sort-alphabetical-desc::before{
  content:""; }

.bp3-icon-sort-asc::before{
  content:""; }

.bp3-icon-sort-desc::before{
  content:""; }

.bp3-icon-sort-numerical::before{
  content:""; }

.bp3-icon-sort-numerical-desc::before{
  content:""; }

.bp3-icon-split-columns::before{
  content:""; }

.bp3-icon-square::before{
  content:""; }

.bp3-icon-stacked-chart::before{
  content:""; }

.bp3-icon-star::before{
  content:"★"; }

.bp3-icon-star-empty::before{
  content:"☆"; }

.bp3-icon-step-backward::before{
  content:""; }

.bp3-icon-step-chart::before{
  content:""; }

.bp3-icon-step-forward::before{
  content:""; }

.bp3-icon-stop::before{
  content:""; }

.bp3-icon-stopwatch::before{
  content:""; }

.bp3-icon-strikethrough::before{
  content:""; }

.bp3-icon-style::before{
  content:""; }

.bp3-icon-swap-horizontal::before{
  content:""; }

.bp3-icon-swap-vertical::before{
  content:""; }

.bp3-icon-symbol-circle::before{
  content:""; }

.bp3-icon-symbol-cross::before{
  content:""; }

.bp3-icon-symbol-diamond::before{
  content:""; }

.bp3-icon-symbol-square::before{
  content:""; }

.bp3-icon-symbol-triangle-down::before{
  content:""; }

.bp3-icon-symbol-triangle-up::before{
  content:""; }

.bp3-icon-tag::before{
  content:""; }

.bp3-icon-take-action::before{
  content:""; }

.bp3-icon-taxi::before{
  content:""; }

.bp3-icon-text-highlight::before{
  content:""; }

.bp3-icon-th::before{
  content:""; }

.bp3-icon-th-derived::before{
  content:""; }

.bp3-icon-th-disconnect::before{
  content:""; }

.bp3-icon-th-filtered::before{
  content:""; }

.bp3-icon-th-list::before{
  content:""; }

.bp3-icon-thumbs-down::before{
  content:""; }

.bp3-icon-thumbs-up::before{
  content:""; }

.bp3-icon-tick::before{
  content:"✓"; }

.bp3-icon-tick-circle::before{
  content:""; }

.bp3-icon-time::before{
  content:"⏲"; }

.bp3-icon-timeline-area-chart::before{
  content:""; }

.bp3-icon-timeline-bar-chart::before{
  content:""; }

.bp3-icon-timeline-events::before{
  content:""; }

.bp3-icon-timeline-line-chart::before{
  content:""; }

.bp3-icon-tint::before{
  content:""; }

.bp3-icon-torch::before{
  content:""; }

.bp3-icon-tractor::before{
  content:""; }

.bp3-icon-train::before{
  content:""; }

.bp3-icon-translate::before{
  content:""; }

.bp3-icon-trash::before{
  content:""; }

.bp3-icon-tree::before{
  content:""; }

.bp3-icon-trending-down::before{
  content:""; }

.bp3-icon-trending-up::before{
  content:""; }

.bp3-icon-truck::before{
  content:""; }

.bp3-icon-two-columns::before{
  content:""; }

.bp3-icon-unarchive::before{
  content:""; }

.bp3-icon-underline::before{
  content:"⎁"; }

.bp3-icon-undo::before{
  content:"⎌"; }

.bp3-icon-ungroup-objects::before{
  content:""; }

.bp3-icon-unknown-vehicle::before{
  content:""; }

.bp3-icon-unlock::before{
  content:""; }

.bp3-icon-unpin::before{
  content:""; }

.bp3-icon-unresolve::before{
  content:""; }

.bp3-icon-updated::before{
  content:""; }

.bp3-icon-upload::before{
  content:""; }

.bp3-icon-user::before{
  content:""; }

.bp3-icon-variable::before{
  content:""; }

.bp3-icon-vertical-bar-chart-asc::before{
  content:""; }

.bp3-icon-vertical-bar-chart-desc::before{
  content:""; }

.bp3-icon-vertical-distribution::before{
  content:""; }

.bp3-icon-video::before{
  content:""; }

.bp3-icon-volume-down::before{
  content:""; }

.bp3-icon-volume-off::before{
  content:""; }

.bp3-icon-volume-up::before{
  content:""; }

.bp3-icon-walk::before{
  content:""; }

.bp3-icon-warning-sign::before{
  content:""; }

.bp3-icon-waterfall-chart::before{
  content:""; }

.bp3-icon-widget::before{
  content:""; }

.bp3-icon-widget-button::before{
  content:""; }

.bp3-icon-widget-footer::before{
  content:""; }

.bp3-icon-widget-header::before{
  content:""; }

.bp3-icon-wrench::before{
  content:""; }

.bp3-icon-zoom-in::before{
  content:""; }

.bp3-icon-zoom-out::before{
  content:""; }

.bp3-icon-zoom-to-fit::before{
  content:""; }
.bp3-submenu > .bp3-popover-wrapper{
  display:block; }

.bp3-submenu .bp3-popover-target{
  display:block; }

.bp3-submenu.bp3-popover{
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0 5px; }
  .bp3-submenu.bp3-popover > .bp3-popover-content{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-submenu.bp3-popover, .bp3-submenu.bp3-popover.bp3-dark{
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-dark .bp3-submenu.bp3-popover > .bp3-popover-content, .bp3-submenu.bp3-popover.bp3-dark > .bp3-popover-content{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
.bp3-menu{
  margin:0;
  border-radius:3px;
  background:#ffffff;
  min-width:180px;
  padding:5px;
  list-style:none;
  text-align:left;
  color:#182026; }

.bp3-menu-divider{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-menu-divider{
    border-top-color:rgba(255, 255, 255, 0.15); }

.bp3-menu-item{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  border-radius:2px;
  padding:5px 7px;
  text-decoration:none;
  line-height:20px;
  color:inherit;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-menu-item > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-menu-item > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-menu-item::before,
  .bp3-menu-item > *{
    margin-right:7px; }
  .bp3-menu-item:empty::before,
  .bp3-menu-item > :last-child{
    margin-right:0; }
  .bp3-menu-item > .bp3-fill{
    word-break:break-word; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    background-color:rgba(167, 182, 194, 0.3);
    cursor:pointer;
    text-decoration:none; }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-menu-item{
    color:inherit; }
    .bp3-dark .bp3-menu-item:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
      background-color:rgba(138, 155, 168, 0.15);
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-disabled{
      background-color:inherit;
      color:rgba(167, 182, 194, 0.6); }
  .bp3-menu-item.bp3-intent-primary{
    color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-primary::before, .bp3-menu-item.bp3-intent-primary::after,
    .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
      color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary.bp3-active{
      background-color:#137cbd; }
    .bp3-menu-item.bp3-intent-primary:active{
      background-color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary:active, .bp3-menu-item.bp3-intent-primary:active::before, .bp3-menu-item.bp3-intent-primary:active::after,
    .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-menu-item.bp3-intent-primary.bp3-active::after,
    .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-success{
    color:#0d8050; }
    .bp3-menu-item.bp3-intent-success .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-success::before, .bp3-menu-item.bp3-intent-success::after,
    .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
      color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success.bp3-active{
      background-color:#0f9960; }
    .bp3-menu-item.bp3-intent-success:active{
      background-color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-menu-item.bp3-intent-success:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success:active, .bp3-menu-item.bp3-intent-success:active::before, .bp3-menu-item.bp3-intent-success:active::after,
    .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-menu-item.bp3-intent-success.bp3-active::after,
    .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-warning{
    color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-warning::before, .bp3-menu-item.bp3-intent-warning::after,
    .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
      color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning.bp3-active{
      background-color:#d9822b; }
    .bp3-menu-item.bp3-intent-warning:active{
      background-color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning:active, .bp3-menu-item.bp3-intent-warning:active::before, .bp3-menu-item.bp3-intent-warning:active::after,
    .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-menu-item.bp3-intent-warning.bp3-active::after,
    .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-danger{
    color:#c23030; }
    .bp3-menu-item.bp3-intent-danger .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-danger::before, .bp3-menu-item.bp3-intent-danger::after,
    .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
      color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger.bp3-active{
      background-color:#db3737; }
    .bp3-menu-item.bp3-intent-danger:active{
      background-color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger:active, .bp3-menu-item.bp3-intent-danger:active::before, .bp3-menu-item.bp3-intent-danger:active::after,
    .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-menu-item.bp3-intent-danger.bp3-active::after,
    .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    margin-right:7px; }
  .bp3-menu-item::before,
  .bp3-menu-item > .bp3-icon{
    margin-top:2px;
    color:#5c7080; }
  .bp3-menu-item .bp3-menu-item-label{
    color:#5c7080; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    color:inherit; }
  .bp3-menu-item.bp3-active, .bp3-menu-item:active{
    background-color:rgba(115, 134, 148, 0.3); }
  .bp3-menu-item.bp3-disabled{
    outline:none !important;
    background-color:inherit !important;
    cursor:not-allowed !important;
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-menu-item.bp3-disabled::before,
    .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-large .bp3-menu-item{
    padding:9px 7px;
    line-height:22px;
    font-size:16px; }
    .bp3-large .bp3-menu-item .bp3-icon{
      margin-top:3px; }
    .bp3-large .bp3-menu-item::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      margin-top:1px;
      margin-right:10px; }

button.bp3-menu-item{
  border:none;
  background:none;
  width:100%;
  text-align:left; }
.bp3-menu-header{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15);
  cursor:default;
  padding-left:2px; }
  .bp3-dark .bp3-menu-header{
    border-top-color:rgba(255, 255, 255, 0.15); }
  .bp3-menu-header:first-of-type{
    border-top:none; }
  .bp3-menu-header > h6{
    color:#182026;
    font-weight:600;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    margin:0;
    padding:10px 7px 0 1px;
    line-height:17px; }
    .bp3-dark .bp3-menu-header > h6{
      color:#f5f8fa; }
  .bp3-menu-header:first-of-type > h6{
    padding-top:0; }
  .bp3-large .bp3-menu-header > h6{
    padding-top:15px;
    padding-bottom:5px;
    font-size:18px; }
  .bp3-large .bp3-menu-header:first-of-type > h6{
    padding-top:0; }

.bp3-dark .bp3-menu{
  background:#30404d;
  color:#f5f8fa; }

.bp3-dark .bp3-menu-item.bp3-intent-primary{
  color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary::before, .bp3-dark .bp3-menu-item.bp3-intent-primary::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
    color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active{
    background-color:#137cbd; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active{
    background-color:#106ba3; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary:active, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-success{
  color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-success::before, .bp3-dark .bp3-menu-item.bp3-intent-success::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
    color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active{
    background-color:#0f9960; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:active{
    background-color:#0d8050; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success:active, .bp3-dark .bp3-menu-item.bp3-intent-success:active::before, .bp3-dark .bp3-menu-item.bp3-intent-success:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-warning{
  color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning::before, .bp3-dark .bp3-menu-item.bp3-intent-warning::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
    color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active{
    background-color:#d9822b; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active{
    background-color:#bf7326; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning:active, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-danger{
  color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger::before, .bp3-dark .bp3-menu-item.bp3-intent-danger::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
    color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active{
    background-color:#db3737; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active{
    background-color:#c23030; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger:active, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item::before,
.bp3-dark .bp3-menu-item > .bp3-icon{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item .bp3-menu-item-label{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item.bp3-active, .bp3-dark .bp3-menu-item:active{
  background-color:rgba(138, 155, 168, 0.3); }

.bp3-dark .bp3-menu-item.bp3-disabled{
  color:rgba(167, 182, 194, 0.6) !important; }
  .bp3-dark .bp3-menu-item.bp3-disabled::before,
  .bp3-dark .bp3-menu-item.bp3-disabled > .bp3-icon,
  .bp3-dark .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
    color:rgba(167, 182, 194, 0.6) !important; }

.bp3-dark .bp3-menu-divider,
.bp3-dark .bp3-menu-header{
  border-color:rgba(255, 255, 255, 0.15); }

.bp3-dark .bp3-menu-header > h6{
  color:#f5f8fa; }

.bp3-label .bp3-menu{
  margin-top:5px; }
.bp3-navbar{
  position:relative;
  z-index:10;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:100%;
  height:50px;
  padding:0 15px; }
  .bp3-navbar.bp3-dark,
  .bp3-dark .bp3-navbar{
    background-color:#394b59; }
  .bp3-navbar.bp3-dark{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-navbar{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-navbar.bp3-fixed-top{
    position:fixed;
    top:0;
    right:0;
    left:0; }

.bp3-navbar-heading{
  margin-right:15px;
  font-size:16px; }

.bp3-navbar-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  height:50px; }
  .bp3-navbar-group.bp3-align-left{
    float:left; }
  .bp3-navbar-group.bp3-align-right{
    float:right; }

.bp3-navbar-divider{
  margin:0 10px;
  border-left:1px solid rgba(16, 22, 26, 0.15);
  height:20px; }
  .bp3-dark .bp3-navbar-divider{
    border-left-color:rgba(255, 255, 255, 0.15); }
.bp3-non-ideal-state{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  height:100%;
  text-align:center; }
  .bp3-non-ideal-state > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-non-ideal-state > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-non-ideal-state::before,
  .bp3-non-ideal-state > *{
    margin-bottom:20px; }
  .bp3-non-ideal-state:empty::before,
  .bp3-non-ideal-state > :last-child{
    margin-bottom:0; }
  .bp3-non-ideal-state > *{
    max-width:400px; }

.bp3-non-ideal-state-visual{
  color:rgba(92, 112, 128, 0.6);
  font-size:60px; }
  .bp3-dark .bp3-non-ideal-state-visual{
    color:rgba(167, 182, 194, 0.6); }

.bp3-overflow-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:nowrap;
      flex-wrap:nowrap;
  min-width:0; }

.bp3-overflow-list-spacer{
  -ms-flex-negative:1;
      flex-shrink:1;
  width:1px; }

body.bp3-overlay-open{
  overflow:hidden; }

.bp3-overlay{
  position:static;
  top:0;
  right:0;
  bottom:0;
  left:0;
  z-index:20; }
  .bp3-overlay:not(.bp3-overlay-open){
    pointer-events:none; }
  .bp3-overlay.bp3-overlay-container{
    position:fixed;
    overflow:hidden; }
    .bp3-overlay.bp3-overlay-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-scroll-container{
    position:fixed;
    overflow:auto; }
    .bp3-overlay.bp3-overlay-scroll-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-inline{
    display:inline;
    overflow:visible; }

.bp3-overlay-content{
  position:fixed;
  z-index:20; }
  .bp3-overlay-inline .bp3-overlay-content,
  .bp3-overlay-scroll-container .bp3-overlay-content{
    position:absolute; }

.bp3-overlay-backdrop{
  position:fixed;
  top:0;
  right:0;
  bottom:0;
  left:0;
  opacity:1;
  z-index:20;
  background-color:rgba(16, 22, 26, 0.7);
  overflow:auto;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-overlay-backdrop.bp3-overlay-enter, .bp3-overlay-backdrop.bp3-overlay-appear{
    opacity:0; }
  .bp3-overlay-backdrop.bp3-overlay-enter-active, .bp3-overlay-backdrop.bp3-overlay-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop.bp3-overlay-exit{
    opacity:1; }
  .bp3-overlay-backdrop.bp3-overlay-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop:focus{
    outline:none; }
  .bp3-overlay-inline .bp3-overlay-backdrop{
    position:absolute; }
.bp3-panel-stack{
  position:relative;
  overflow:hidden; }

.bp3-panel-stack-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  z-index:1;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  height:30px; }
  .bp3-dark .bp3-panel-stack-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack-header > span{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch; }
  .bp3-panel-stack-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack-view{
  position:absolute;
  top:0;
  right:0;
  bottom:0;
  left:0;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  background-color:#ffffff;
  overflow-y:auto; }
  .bp3-dark .bp3-panel-stack-view{
    background-color:#30404d; }

.bp3-panel-stack-push .bp3-panel-stack-enter, .bp3-panel-stack-push .bp3-panel-stack-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack-push .bp3-panel-stack-enter-active, .bp3-panel-stack-push .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-push .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-push .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter, .bp3-panel-stack-pop .bp3-panel-stack-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter-active, .bp3-panel-stack-pop .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-pop .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }
.bp3-popover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1);
  display:inline-block;
  z-index:20;
  border-radius:3px; }
  .bp3-popover .bp3-popover-arrow{
    position:absolute;
    width:30px;
    height:30px; }
    .bp3-popover .bp3-popover-arrow::before{
      margin:5px;
      width:20px;
      height:20px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover{
    margin-top:-17px;
    margin-bottom:17px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
      bottom:-11px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover{
    margin-left:17px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
      left:-11px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover{
    margin-top:17px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
      top:-11px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover{
    margin-right:17px;
    margin-left:-17px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
      right:-11px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-popover > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-popover > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
    top:-0.3934px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
    right:-0.3934px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
    left:-0.3934px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
    bottom:-0.3934px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-popover .bp3-popover-content{
    background:#ffffff;
    color:inherit; }
  .bp3-popover .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-popover .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-popover .bp3-popover-arrow-fill{
    fill:#ffffff; }
  .bp3-popover-enter > .bp3-popover, .bp3-popover-appear > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3); }
  .bp3-popover-enter-active > .bp3-popover, .bp3-popover-appear-active > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover .bp3-popover-content{
    position:relative;
    border-radius:3px; }
  .bp3-popover.bp3-popover-content-sizing .bp3-popover-content{
    max-width:350px;
    padding:20px; }
  .bp3-popover-target + .bp3-overlay .bp3-popover.bp3-popover-content-sizing{
    width:350px; }
  .bp3-popover.bp3-minimal{
    margin:0 !important; }
    .bp3-popover.bp3-minimal .bp3-popover-arrow{
      display:none; }
    .bp3-popover.bp3-minimal.bp3-popover{
      -webkit-transform:scale(1);
              transform:scale(1); }
      .bp3-popover-enter > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-enter-active > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
      .bp3-popover-exit > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-exit-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
  .bp3-popover.bp3-dark,
  .bp3-dark .bp3-popover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-popover .bp3-popover-content{
      background:#30404d;
      color:inherit; }
    .bp3-popover.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-popover .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-popover .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-popover.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-popover .bp3-popover-arrow-fill{
      fill:#30404d; }

.bp3-popover-arrow::before{
  display:block;
  position:absolute;
  -webkit-transform:rotate(45deg);
          transform:rotate(45deg);
  border-radius:2px;
  content:""; }

.bp3-tether-pinned .bp3-popover-arrow{
  display:none; }

.bp3-popover-backdrop{
  background:rgba(255, 255, 255, 0); }

.bp3-transition-container{
  opacity:1;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  z-index:20; }
  .bp3-transition-container.bp3-popover-enter, .bp3-transition-container.bp3-popover-appear{
    opacity:0; }
  .bp3-transition-container.bp3-popover-enter-active, .bp3-transition-container.bp3-popover-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container.bp3-popover-exit{
    opacity:1; }
  .bp3-transition-container.bp3-popover-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container:focus{
    outline:none; }
  .bp3-transition-container.bp3-popover-leave .bp3-popover-content{
    pointer-events:none; }
  .bp3-transition-container[data-x-out-of-boundaries]{
    display:none; }

span.bp3-popover-target{
  display:inline-block; }

.bp3-popover-wrapper.bp3-fill{
  width:100%; }

.bp3-portal{
  position:absolute;
  top:0;
  right:0;
  left:0; }
@-webkit-keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }
@keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }

.bp3-progress-bar{
  display:block;
  position:relative;
  border-radius:40px;
  background:rgba(92, 112, 128, 0.2);
  width:100%;
  height:8px;
  overflow:hidden; }
  .bp3-progress-bar .bp3-progress-meter{
    position:absolute;
    border-radius:40px;
    background:linear-gradient(-45deg, rgba(255, 255, 255, 0.2) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.2) 50%, rgba(255, 255, 255, 0.2) 75%, transparent 75%);
    background-color:rgba(92, 112, 128, 0.8);
    background-size:30px 30px;
    width:100%;
    height:100%;
    -webkit-transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-progress-bar:not(.bp3-no-animation):not(.bp3-no-stripes) .bp3-progress-meter{
    animation:linear-progress-bar-stripes 300ms linear infinite reverse; }
  .bp3-progress-bar.bp3-no-stripes .bp3-progress-meter{
    background-image:none; }

.bp3-dark .bp3-progress-bar{
  background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-progress-bar .bp3-progress-meter{
    background-color:#8a9ba8; }

.bp3-progress-bar.bp3-intent-primary .bp3-progress-meter{
  background-color:#137cbd; }

.bp3-progress-bar.bp3-intent-success .bp3-progress-meter{
  background-color:#0f9960; }

.bp3-progress-bar.bp3-intent-warning .bp3-progress-meter{
  background-color:#d9822b; }

.bp3-progress-bar.bp3-intent-danger .bp3-progress-meter{
  background-color:#db3737; }
@-webkit-keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
@keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
.bp3-skeleton{
  border-color:rgba(206, 217, 224, 0.2) !important;
  border-radius:2px;
  -webkit-box-shadow:none !important;
          box-shadow:none !important;
  background:rgba(206, 217, 224, 0.2);
  background-clip:padding-box !important;
  cursor:default;
  color:transparent !important;
  -webkit-animation:1000ms linear infinite alternate skeleton-glow;
          animation:1000ms linear infinite alternate skeleton-glow;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-skeleton::before, .bp3-skeleton::after,
  .bp3-skeleton *{
    visibility:hidden !important; }
.bp3-slider{
  width:100%;
  min-width:150px;
  height:40px;
  position:relative;
  outline:none;
  cursor:default;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-slider:hover{
    cursor:pointer; }
  .bp3-slider:active{
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-slider.bp3-disabled{
    opacity:0.5;
    cursor:not-allowed; }
  .bp3-slider.bp3-slider-unlabeled{
    height:16px; }

.bp3-slider-track,
.bp3-slider-progress{
  top:5px;
  right:0;
  left:0;
  height:6px;
  position:absolute; }

.bp3-slider-track{
  border-radius:3px;
  overflow:hidden; }

.bp3-slider-progress{
  background:rgba(92, 112, 128, 0.2); }
  .bp3-dark .bp3-slider-progress{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-slider-progress.bp3-intent-primary{
    background-color:#137cbd; }
  .bp3-slider-progress.bp3-intent-success{
    background-color:#0f9960; }
  .bp3-slider-progress.bp3-intent-warning{
    background-color:#d9822b; }
  .bp3-slider-progress.bp3-intent-danger{
    background-color:#db3737; }

.bp3-slider-handle{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  position:absolute;
  top:0;
  left:0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
  cursor:pointer;
  width:16px;
  height:16px; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-slider-handle:active, .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-slider-handle:disabled, .bp3-slider-handle.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-slider-handle:disabled.bp3-active, .bp3-slider-handle:disabled.bp3-active:hover, .bp3-slider-handle.bp3-disabled.bp3-active, .bp3-slider-handle.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }
  .bp3-slider-handle:focus{
    z-index:1; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5;
    z-index:2;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
    cursor:-webkit-grab;
    cursor:grab; }
  .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-disabled .bp3-slider-handle{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#bfccd6;
    pointer-events:none; }
  .bp3-dark .bp3-slider-handle{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover, .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-slider-handle:disabled, .bp3-dark .bp3-slider-handle.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-slider-handle:disabled.bp3-active, .bp3-dark .bp3-slider-handle.bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-slider-handle .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-slider-handle, .bp3-dark .bp3-slider-handle:hover{
      background-color:#394b59; }
    .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#293742; }
  .bp3-dark .bp3-disabled .bp3-slider-handle{
    border-color:#5c7080;
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#5c7080; }
  .bp3-slider-handle .bp3-slider-label{
    margin-left:8px;
    border-radius:3px;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
    background:#394b59;
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
      background:#e1e8ed;
      color:#394b59; }
    .bp3-disabled .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-slider-handle.bp3-start, .bp3-slider-handle.bp3-end{
    width:8px; }
  .bp3-slider-handle.bp3-start{
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-slider-handle.bp3-end{
    margin-left:8px;
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
    .bp3-slider-handle.bp3-end .bp3-slider-label{
      margin-left:0; }

.bp3-slider-label{
  -webkit-transform:translate(-50%, 20px);
          transform:translate(-50%, 20px);
  display:inline-block;
  position:absolute;
  padding:2px 5px;
  vertical-align:top;
  line-height:1;
  font-size:12px; }

.bp3-slider.bp3-vertical{
  width:40px;
  min-width:40px;
  height:150px; }
  .bp3-slider.bp3-vertical .bp3-slider-track,
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:0;
    bottom:0;
    left:5px;
    width:6px;
    height:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-label{
    -webkit-transform:translate(20px, 50%);
            transform:translate(20px, 50%); }
  .bp3-slider.bp3-vertical .bp3-slider-handle{
    top:auto; }
    .bp3-slider.bp3-vertical .bp3-slider-handle .bp3-slider-label{
      margin-top:-8px;
      margin-left:0; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end, .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      margin-left:0;
      width:16px;
      height:8px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      border-top-left-radius:0;
      border-bottom-right-radius:3px; }
      .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start .bp3-slider-label{
        -webkit-transform:translate(20px);
                transform:translate(20px); }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end{
      margin-bottom:8px;
      border-top-left-radius:3px;
      border-bottom-left-radius:0;
      border-bottom-right-radius:0; }

@-webkit-keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

@keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

.bp3-spinner{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  overflow:visible;
  vertical-align:middle; }
  .bp3-spinner svg{
    display:block; }
  .bp3-spinner path{
    fill-opacity:0; }
  .bp3-spinner .bp3-spinner-head{
    -webkit-transform-origin:center;
            transform-origin:center;
    -webkit-transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    stroke:rgba(92, 112, 128, 0.8);
    stroke-linecap:round; }
  .bp3-spinner .bp3-spinner-track{
    stroke:rgba(92, 112, 128, 0.2); }

.bp3-spinner-animation{
  -webkit-animation:pt-spinner-animation 500ms linear infinite;
          animation:pt-spinner-animation 500ms linear infinite; }
  .bp3-no-spin > .bp3-spinner-animation{
    -webkit-animation:none;
            animation:none; }

.bp3-dark .bp3-spinner .bp3-spinner-head{
  stroke:#8a9ba8; }

.bp3-dark .bp3-spinner .bp3-spinner-track{
  stroke:rgba(16, 22, 26, 0.5); }

.bp3-spinner.bp3-intent-primary .bp3-spinner-head{
  stroke:#137cbd; }

.bp3-spinner.bp3-intent-success .bp3-spinner-head{
  stroke:#0f9960; }

.bp3-spinner.bp3-intent-warning .bp3-spinner-head{
  stroke:#d9822b; }

.bp3-spinner.bp3-intent-danger .bp3-spinner-head{
  stroke:#db3737; }
.bp3-tabs.bp3-vertical{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-tabs.bp3-vertical > .bp3-tab-list{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab{
      border-radius:3px;
      width:100%;
      padding:0 10px; }
      .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab[aria-selected="true"]{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(19, 124, 189, 0.2); }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab-indicator-wrapper .bp3-tab-indicator{
      top:0;
      right:0;
      bottom:0;
      left:0;
      border-radius:3px;
      background-color:rgba(19, 124, 189, 0.2);
      height:auto; }
  .bp3-tabs.bp3-vertical > .bp3-tab-panel{
    margin-top:0;
    padding-left:20px; }

.bp3-tab-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:end;
      -ms-flex-align:end;
          align-items:flex-end;
  position:relative;
  margin:0;
  border:none;
  padding:0;
  list-style:none; }
  .bp3-tab-list > *:not(:last-child){
    margin-right:20px; }

.bp3-tab{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  cursor:pointer;
  max-width:100%;
  vertical-align:top;
  line-height:30px;
  color:#182026;
  font-size:14px; }
  .bp3-tab a{
    display:block;
    text-decoration:none;
    color:inherit; }
  .bp3-tab-indicator-wrapper ~ .bp3-tab{
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    background-color:transparent !important; }
  .bp3-tab[aria-disabled="true"]{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-tab[aria-selected="true"]{
    border-radius:0;
    -webkit-box-shadow:inset 0 -3px 0 #106ba3;
            box-shadow:inset 0 -3px 0 #106ba3; }
  .bp3-tab[aria-selected="true"], .bp3-tab:not([aria-disabled="true"]):hover{
    color:#106ba3; }
  .bp3-tab:focus{
    -moz-outline-radius:0; }
  .bp3-large > .bp3-tab{
    line-height:40px;
    font-size:16px; }

.bp3-tab-panel{
  margin-top:20px; }
  .bp3-tab-panel[aria-hidden="true"]{
    display:none; }

.bp3-tab-indicator-wrapper{
  position:absolute;
  top:0;
  left:0;
  -webkit-transform:translateX(0), translateY(0);
          transform:translateX(0), translateY(0);
  -webkit-transition:height, width, -webkit-transform;
  transition:height, width, -webkit-transform;
  transition:height, transform, width;
  transition:height, transform, width, -webkit-transform;
  -webkit-transition-duration:200ms;
          transition-duration:200ms;
  -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
          transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
  pointer-events:none; }
  .bp3-tab-indicator-wrapper .bp3-tab-indicator{
    position:absolute;
    right:0;
    bottom:0;
    left:0;
    background-color:#106ba3;
    height:3px; }
  .bp3-tab-indicator-wrapper.bp3-no-animation{
    -webkit-transition:none;
    transition:none; }

.bp3-dark .bp3-tab{
  color:#f5f8fa; }
  .bp3-dark .bp3-tab[aria-disabled="true"]{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tab[aria-selected="true"]{
    -webkit-box-shadow:inset 0 -3px 0 #48aff0;
            box-shadow:inset 0 -3px 0 #48aff0; }
  .bp3-dark .bp3-tab[aria-selected="true"], .bp3-dark .bp3-tab:not([aria-disabled="true"]):hover{
    color:#48aff0; }

.bp3-dark .bp3-tab-indicator{
  background-color:#48aff0; }

.bp3-flex-expander{
  -webkit-box-flex:1;
      -ms-flex:1 1;
          flex:1 1; }
.bp3-tag{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:#5c7080;
  min-width:20px;
  max-width:100%;
  min-height:20px;
  padding:2px 6px;
  line-height:16px;
  color:#f5f8fa;
  font-size:12px; }
  .bp3-tag.bp3-interactive{
    cursor:pointer; }
    .bp3-tag.bp3-interactive:hover{
      background-color:rgba(92, 112, 128, 0.85); }
    .bp3-tag.bp3-interactive.bp3-active, .bp3-tag.bp3-interactive:active{
      background-color:rgba(92, 112, 128, 0.7); }
  .bp3-tag > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag::before,
  .bp3-tag > *{
    margin-right:4px; }
  .bp3-tag:empty::before,
  .bp3-tag > :last-child{
    margin-right:0; }
  .bp3-tag:focus{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:0;
    -moz-outline-radius:6px; }
  .bp3-tag.bp3-round{
    border-radius:30px;
    padding-right:8px;
    padding-left:8px; }
  .bp3-dark .bp3-tag{
    background-color:#bfccd6;
    color:#182026; }
    .bp3-dark .bp3-tag.bp3-interactive{
      cursor:pointer; }
      .bp3-dark .bp3-tag.bp3-interactive:hover{
        background-color:rgba(191, 204, 214, 0.85); }
      .bp3-dark .bp3-tag.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-interactive:active{
        background-color:rgba(191, 204, 214, 0.7); }
    .bp3-dark .bp3-tag > .bp3-icon, .bp3-dark .bp3-tag .bp3-icon-standard, .bp3-dark .bp3-tag .bp3-icon-large{
      fill:currentColor; }
  .bp3-tag > .bp3-icon, .bp3-tag .bp3-icon-standard, .bp3-tag .bp3-icon-large{
    fill:#ffffff; }
  .bp3-tag.bp3-large,
  .bp3-large .bp3-tag{
    min-width:30px;
    min-height:30px;
    padding:0 10px;
    line-height:20px;
    font-size:14px; }
    .bp3-tag.bp3-large::before,
    .bp3-tag.bp3-large > *,
    .bp3-large .bp3-tag::before,
    .bp3-large .bp3-tag > *{
      margin-right:7px; }
    .bp3-tag.bp3-large:empty::before,
    .bp3-tag.bp3-large > :last-child,
    .bp3-large .bp3-tag:empty::before,
    .bp3-large .bp3-tag > :last-child{
      margin-right:0; }
    .bp3-tag.bp3-large.bp3-round,
    .bp3-large .bp3-tag.bp3-round{
      padding-right:12px;
      padding-left:12px; }
  .bp3-tag.bp3-intent-primary{
    background:#137cbd;
    color:#ffffff; }
    .bp3-tag.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.85); }
      .bp3-tag.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.7); }
  .bp3-tag.bp3-intent-success{
    background:#0f9960;
    color:#ffffff; }
    .bp3-tag.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.85); }
      .bp3-tag.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.7); }
  .bp3-tag.bp3-intent-warning{
    background:#d9822b;
    color:#ffffff; }
    .bp3-tag.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.85); }
      .bp3-tag.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.7); }
  .bp3-tag.bp3-intent-danger{
    background:#db3737;
    color:#ffffff; }
    .bp3-tag.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.85); }
      .bp3-tag.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.7); }
  .bp3-tag.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-tag.bp3-minimal > .bp3-icon, .bp3-tag.bp3-minimal .bp3-icon-standard, .bp3-tag.bp3-minimal .bp3-icon-large{
    fill:#5c7080; }
  .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
    background-color:rgba(138, 155, 168, 0.2);
    color:#182026; }
    .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
        background-color:rgba(92, 112, 128, 0.3); }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
        background-color:rgba(92, 112, 128, 0.4); }
    .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
      color:#f5f8fa; }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
          background-color:rgba(191, 204, 214, 0.3); }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
          background-color:rgba(191, 204, 214, 0.4); }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) > .bp3-icon, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-large{
        fill:#a7b6c2; }
  .bp3-tag.bp3-minimal.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15);
    color:#106ba3; }
    .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-primary > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-large{
      fill:#137cbd; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25);
      color:#48aff0; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
          background-color:rgba(19, 124, 189, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
          background-color:rgba(19, 124, 189, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15);
    color:#0d8050; }
    .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-success > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-large{
      fill:#0f9960; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25);
      color:#3dcc91; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
          background-color:rgba(15, 153, 96, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
          background-color:rgba(15, 153, 96, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15);
    color:#bf7326; }
    .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-warning > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-large{
      fill:#d9822b; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25);
      color:#ffb366; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
          background-color:rgba(217, 130, 43, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
          background-color:rgba(217, 130, 43, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15);
    color:#c23030; }
    .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-danger > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-large{
      fill:#db3737; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25);
      color:#ff7373; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
          background-color:rgba(219, 55, 55, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
          background-color:rgba(219, 55, 55, 0.45); }

.bp3-tag-remove{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  opacity:0.5;
  margin-top:-2px;
  margin-right:-6px !important;
  margin-bottom:-2px;
  border:none;
  background:none;
  cursor:pointer;
  padding:2px;
  padding-left:0;
  color:inherit; }
  .bp3-tag-remove:hover{
    opacity:0.8;
    background:none;
    text-decoration:none; }
  .bp3-tag-remove:active{
    opacity:1; }
  .bp3-tag-remove:empty::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    content:""; }
  .bp3-large .bp3-tag-remove{
    margin-right:-10px !important;
    padding:5px;
    padding-left:0; }
    .bp3-large .bp3-tag-remove:empty::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal; }
.bp3-tag-input{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  cursor:text;
  height:auto;
  min-height:30px;
  padding-right:0;
  padding-left:5px;
  line-height:inherit; }
  .bp3-tag-input > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag-input > .bp3-tag-input-values{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag-input .bp3-tag-input-icon{
    margin-top:7px;
    margin-right:7px;
    margin-left:2px;
    color:#5c7080; }
  .bp3-tag-input .bp3-tag-input-values{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -ms-flex-wrap:wrap;
        flex-wrap:wrap;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    -ms-flex-item-align:stretch;
        align-self:stretch;
    margin-top:5px;
    margin-right:7px;
    min-width:0; }
    .bp3-tag-input .bp3-tag-input-values > *{
      -webkit-box-flex:0;
          -ms-flex-positive:0;
              flex-grow:0;
      -ms-flex-negative:0;
          flex-shrink:0; }
    .bp3-tag-input .bp3-tag-input-values > .bp3-fill{
      -webkit-box-flex:1;
          -ms-flex-positive:1;
              flex-grow:1;
      -ms-flex-negative:1;
          flex-shrink:1; }
    .bp3-tag-input .bp3-tag-input-values::before,
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-right:5px; }
    .bp3-tag-input .bp3-tag-input-values:empty::before,
    .bp3-tag-input .bp3-tag-input-values > :last-child{
      margin-right:0; }
    .bp3-tag-input .bp3-tag-input-values:first-child .bp3-input-ghost:first-child{
      padding-left:5px; }
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-bottom:5px; }
  .bp3-tag-input .bp3-tag{
    overflow-wrap:break-word; }
    .bp3-tag-input .bp3-tag.bp3-active{
      outline:rgba(19, 124, 189, 0.6) auto 2px;
      outline-offset:0;
      -moz-outline-radius:6px; }
  .bp3-tag-input .bp3-input-ghost{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:80px;
    line-height:20px; }
    .bp3-tag-input .bp3-input-ghost:disabled, .bp3-tag-input .bp3-input-ghost.bp3-disabled{
      cursor:not-allowed; }
  .bp3-tag-input .bp3-button,
  .bp3-tag-input .bp3-spinner{
    margin:3px;
    margin-left:0; }
  .bp3-tag-input .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-tag-input.bp3-large{
    height:auto;
    min-height:40px; }
    .bp3-tag-input.bp3-large::before,
    .bp3-tag-input.bp3-large > *{
      margin-right:10px; }
    .bp3-tag-input.bp3-large:empty::before,
    .bp3-tag-input.bp3-large > :last-child{
      margin-right:0; }
    .bp3-tag-input.bp3-large .bp3-tag-input-icon{
      margin-top:10px;
      margin-left:5px; }
    .bp3-tag-input.bp3-large .bp3-input-ghost{
      line-height:30px; }
    .bp3-tag-input.bp3-large .bp3-button{
      min-width:30px;
      min-height:30px;
      padding:5px 10px;
      margin:5px;
      margin-left:0; }
    .bp3-tag-input.bp3-large .bp3-spinner{
      margin:8px;
      margin-left:0; }
  .bp3-tag-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
    .bp3-tag-input.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-tag-input .bp3-tag-input-icon, .bp3-tag-input.bp3-dark .bp3-tag-input-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-tag-input .bp3-input-ghost, .bp3-tag-input.bp3-dark .bp3-input-ghost{
    color:#f5f8fa; }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-webkit-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-moz-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost:-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::placeholder{
      color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tag-input.bp3-active, .bp3-tag-input.bp3-dark.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-primary, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-success, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-warning, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-danger, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-input-ghost{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  padding:0; }
  .bp3-input-ghost::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:focus{
    outline:none !important; }
.bp3-toast{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  position:relative !important;
  margin:20px 0 0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  min-width:300px;
  max-width:500px;
  pointer-events:all; }
  .bp3-toast.bp3-toast-enter, .bp3-toast.bp3-toast-appear{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active, .bp3-toast.bp3-toast-appear-active{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-enter ~ .bp3-toast, .bp3-toast.bp3-toast-appear ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active ~ .bp3-toast, .bp3-toast.bp3-toast-appear-active ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit{
    opacity:1;
    -webkit-filter:blur(0);
            filter:blur(0); }
  .bp3-toast.bp3-toast-exit-active{
    opacity:0;
    -webkit-filter:blur(10px);
            filter:blur(10px);
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:opacity, filter;
    transition-property:opacity, filter, -webkit-filter;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0); }
  .bp3-toast.bp3-toast-exit-active ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:50ms;
            transition-delay:50ms; }
  .bp3-toast .bp3-button-group{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    padding:5px;
    padding-left:0; }
  .bp3-toast > .bp3-icon{
    margin:12px;
    margin-right:0;
    color:#5c7080; }
  .bp3-toast.bp3-dark,
  .bp3-dark .bp3-toast{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
    background-color:#394b59; }
    .bp3-toast.bp3-dark > .bp3-icon,
    .bp3-dark .bp3-toast > .bp3-icon{
      color:#a7b6c2; }
  .bp3-toast[class*="bp3-intent-"] a{
    color:rgba(255, 255, 255, 0.7); }
    .bp3-toast[class*="bp3-intent-"] a:hover{
      color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] > .bp3-icon{
    color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button, .bp3-toast[class*="bp3-intent-"] .bp3-button::before,
  .bp3-toast[class*="bp3-intent-"] .bp3-button .bp3-icon, .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    color:rgba(255, 255, 255, 0.7) !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:focus{
    outline-color:rgba(255, 255, 255, 0.5); }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:hover{
    background-color:rgba(255, 255, 255, 0.15) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    background-color:rgba(255, 255, 255, 0.3) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button::after{
    background:rgba(255, 255, 255, 0.3) !important; }
  .bp3-toast.bp3-intent-primary{
    background-color:#137cbd;
    color:#ffffff; }
  .bp3-toast.bp3-intent-success{
    background-color:#0f9960;
    color:#ffffff; }
  .bp3-toast.bp3-intent-warning{
    background-color:#d9822b;
    color:#ffffff; }
  .bp3-toast.bp3-intent-danger{
    background-color:#db3737;
    color:#ffffff; }

.bp3-toast-message{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  padding:11px;
  word-break:break-word; }

.bp3-toast-container{
  display:-webkit-box !important;
  display:-ms-flexbox !important;
  display:flex !important;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:fixed;
  right:0;
  left:0;
  z-index:40;
  overflow:hidden;
  padding:0 20px 20px;
  pointer-events:none; }
  .bp3-toast-container.bp3-toast-container-top{
    top:0;
    bottom:auto; }
  .bp3-toast-container.bp3-toast-container-bottom{
    -webkit-box-orient:vertical;
    -webkit-box-direction:reverse;
        -ms-flex-direction:column-reverse;
            flex-direction:column-reverse;
    top:auto;
    bottom:0; }
  .bp3-toast-container.bp3-toast-container-left{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
  .bp3-toast-container.bp3-toast-container-right{
    -webkit-box-align:end;
        -ms-flex-align:end;
            align-items:flex-end; }

.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active) ~ .bp3-toast, .bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active) ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-leave-active ~ .bp3-toast{
  -webkit-transform:translateY(60px);
          transform:translateY(60px); }
.bp3-tooltip{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1); }
  .bp3-tooltip .bp3-popover-arrow{
    position:absolute;
    width:22px;
    height:22px; }
    .bp3-tooltip .bp3-popover-arrow::before{
      margin:4px;
      width:14px;
      height:14px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip{
    margin-top:-11px;
    margin-bottom:11px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
      bottom:-8px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip{
    margin-left:11px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
      left:-8px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip{
    margin-top:11px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
      top:-8px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip{
    margin-right:11px;
    margin-left:-11px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
      right:-8px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-tooltip > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-tooltip > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
    top:-0.22183px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
    right:-0.22183px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
    left:-0.22183px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
    bottom:-0.22183px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-tooltip .bp3-popover-content{
    background:#394b59;
    color:#f5f8fa; }
  .bp3-tooltip .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-tooltip .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-tooltip .bp3-popover-arrow-fill{
    fill:#394b59; }
  .bp3-popover-enter > .bp3-tooltip, .bp3-popover-appear > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8); }
  .bp3-popover-enter-active > .bp3-tooltip, .bp3-popover-appear-active > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-tooltip .bp3-popover-content{
    padding:10px 12px; }
  .bp3-tooltip.bp3-dark,
  .bp3-dark .bp3-tooltip{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-tooltip .bp3-popover-content{
      background:#e1e8ed;
      color:#394b59; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-fill{
      fill:#e1e8ed; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-content{
    background:#137cbd;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-arrow-fill{
    fill:#137cbd; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-content{
    background:#0f9960;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-arrow-fill{
    fill:#0f9960; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-content{
    background:#d9822b;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-arrow-fill{
    fill:#d9822b; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-content{
    background:#db3737;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-arrow-fill{
    fill:#db3737; }

.bp3-tooltip-indicator{
  border-bottom:dotted 1px;
  cursor:help; }
.bp3-tree .bp3-icon, .bp3-tree .bp3-icon-standard, .bp3-tree .bp3-icon-large{
  color:#5c7080; }
  .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-tree .bp3-icon.bp3-intent-success, .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-tree-node-list{
  margin:0;
  padding-left:0;
  list-style:none; }

.bp3-tree-root{
  position:relative;
  background-color:transparent;
  cursor:default;
  padding-left:0; }

.bp3-tree-node-content-0{
  padding-left:0px; }

.bp3-tree-node-content-1{
  padding-left:23px; }

.bp3-tree-node-content-2{
  padding-left:46px; }

.bp3-tree-node-content-3{
  padding-left:69px; }

.bp3-tree-node-content-4{
  padding-left:92px; }

.bp3-tree-node-content-5{
  padding-left:115px; }

.bp3-tree-node-content-6{
  padding-left:138px; }

.bp3-tree-node-content-7{
  padding-left:161px; }

.bp3-tree-node-content-8{
  padding-left:184px; }

.bp3-tree-node-content-9{
  padding-left:207px; }

.bp3-tree-node-content-10{
  padding-left:230px; }

.bp3-tree-node-content-11{
  padding-left:253px; }

.bp3-tree-node-content-12{
  padding-left:276px; }

.bp3-tree-node-content-13{
  padding-left:299px; }

.bp3-tree-node-content-14{
  padding-left:322px; }

.bp3-tree-node-content-15{
  padding-left:345px; }

.bp3-tree-node-content-16{
  padding-left:368px; }

.bp3-tree-node-content-17{
  padding-left:391px; }

.bp3-tree-node-content-18{
  padding-left:414px; }

.bp3-tree-node-content-19{
  padding-left:437px; }

.bp3-tree-node-content-20{
  padding-left:460px; }

.bp3-tree-node-content{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  width:100%;
  height:30px;
  padding-right:5px; }
  .bp3-tree-node-content:hover{
    background-color:rgba(191, 204, 214, 0.4); }

.bp3-tree-node-caret,
.bp3-tree-node-caret-none{
  min-width:30px; }

.bp3-tree-node-caret{
  color:#5c7080;
  -webkit-transform:rotate(0deg);
          transform:rotate(0deg);
  cursor:pointer;
  padding:7px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tree-node-caret:hover{
    color:#182026; }
  .bp3-dark .bp3-tree-node-caret{
    color:#a7b6c2; }
    .bp3-dark .bp3-tree-node-caret:hover{
      color:#f5f8fa; }
  .bp3-tree-node-caret.bp3-tree-node-caret-open{
    -webkit-transform:rotate(90deg);
            transform:rotate(90deg); }
  .bp3-tree-node-caret.bp3-icon-standard::before{
    content:""; }

.bp3-tree-node-icon{
  position:relative;
  margin-right:7px; }

.bp3-tree-node-label{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  position:relative;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-label span{
    display:inline; }

.bp3-tree-node-secondary-label{
  padding:0 5px;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-secondary-label .bp3-popover-wrapper,
  .bp3-tree-node-secondary-label .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-content{
  background-color:inherit;
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-disabled .bp3-tree-node-caret,
.bp3-tree-node.bp3-disabled .bp3-tree-node-icon{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content,
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-standard, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-large{
    color:#ffffff; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret::before{
    color:rgba(255, 255, 255, 0.7); }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret:hover::before{
    color:#ffffff; }

.bp3-dark .bp3-tree-node-content:hover{
  background-color:rgba(92, 112, 128, 0.3); }

.bp3-dark .bp3-tree .bp3-icon, .bp3-dark .bp3-tree .bp3-icon-standard, .bp3-dark .bp3-tree .bp3-icon-large{
  color:#a7b6c2; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-dark .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
/*!

Copyright 2017-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
.bp3-omnibar{
  -webkit-filter:blur(0);
          filter:blur(0);
  opacity:1;
  top:20vh;
  left:calc(50% - 250px);
  z-index:21;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:500px; }
  .bp3-omnibar.bp3-overlay-enter, .bp3-omnibar.bp3-overlay-appear{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2; }
  .bp3-omnibar.bp3-overlay-enter-active, .bp3-omnibar.bp3-overlay-appear-active{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar.bp3-overlay-exit{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1; }
  .bp3-omnibar.bp3-overlay-exit-active{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar .bp3-input{
    border-radius:0;
    background-color:transparent; }
    .bp3-omnibar .bp3-input, .bp3-omnibar .bp3-input:focus{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-omnibar .bp3-menu{
    border-radius:0;
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
    background-color:transparent;
    max-height:calc(60vh - 40px);
    overflow:auto; }
    .bp3-omnibar .bp3-menu:empty{
      display:none; }
  .bp3-dark .bp3-omnibar, .bp3-omnibar.bp3-dark{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }

.bp3-omnibar-overlay .bp3-overlay-backdrop{
  background-color:rgba(16, 22, 26, 0.2); }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }

.bp3-multi-select{
  min-width:150px; }

.bp3-multi-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto; }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDhoLTIuODFjLS40NS0uNzgtMS4wNy0xLjQ1LTEuODItMS45NkwxNyA0LjQxIDE1LjU5IDNsLTIuMTcgMi4xN0MxMi45NiA1LjA2IDEyLjQ5IDUgMTIgNWMtLjQ5IDAtLjk2LjA2LTEuNDEuMTdMOC40MSAzIDcgNC40MWwxLjYyIDEuNjNDNy44OCA2LjU1IDcuMjYgNy4yMiA2LjgxIDhINHYyaDIuMDljLS4wNS4zMy0uMDkuNjYtLjA5IDF2MUg0djJoMnYxYzAgLjM0LjA0LjY3LjA5IDFINHYyaDIuODFjMS4wNCAxLjc5IDIuOTcgMyA1LjE5IDNzNC4xNS0xLjIxIDUuMTktM0gyMHYtMmgtMi4wOWMuMDUtLjMzLjA5LS42Ni4wOS0xdi0xaDJ2LTJoLTJ2LTFjMC0uMzQtLjA0LS42Ny0uMDktMUgyMFY4em0tNiA4aC00di0yaDR2MnptMC00aC00di0yaDR2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTYuMTdMNC44MyAxMmwtMS40MiAxLjQxTDkgMTkgMjEgN2wtMS40MS0xLjQxeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1pY29uLWJyYW5kMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNmZmYiPgogICAgPHBhdGggZD0iTTEwNSAxMjcuM2g0MHYxMi44aC00MHpNNTEuMSA3N0w3NCA5OS45bC0yMy4zIDIzLjMgMTAuNSAxMC41IDIzLjMtMjMuM0w5NSA5OS45IDg0LjUgODkuNCA2MS42IDY2LjV6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNGOUE4MjUiPgogICAgPHBhdGggZD0iTTIwLjIgMTEuOGMtMS42IDAtMS43LjUtMS43IDEgMCAuNC4xLjkuMSAxLjMuMS41LjEuOS4xIDEuMyAwIDEuNy0xLjQgMi4zLTMuNSAyLjNoLS45di0xLjloLjVjMS4xIDAgMS40IDAgMS40LS44IDAtLjMgMC0uNi0uMS0xIDAtLjQtLjEtLjgtLjEtMS4yIDAtMS4zIDAtMS44IDEuMy0yLTEuMy0uMi0xLjMtLjctMS4zLTIgMC0uNC4xLS44LjEtMS4yLjEtLjQuMS0uNy4xLTEgMC0uOC0uNC0uNy0xLjQtLjhoLS41VjQuMWguOWMyLjIgMCAzLjUuNyAzLjUgMi4zIDAgLjQtLjEuOS0uMSAxLjMtLjEuNS0uMS45LS4xIDEuMyAwIC41LjIgMSAxLjcgMXYxLjh6TTEuOCAxMC4xYzEuNiAwIDEuNy0uNSAxLjctMSAwLS40LS4xLS45LS4xLTEuMy0uMS0uNS0uMS0uOS0uMS0xLjMgMC0xLjYgMS40LTIuMyAzLjUtMi4zaC45djEuOWgtLjVjLTEgMC0xLjQgMC0xLjQuOCAwIC4zIDAgLjYuMSAxIDAgLjIuMS42LjEgMSAwIDEuMyAwIDEuOC0xLjMgMkM2IDExLjIgNiAxMS43IDYgMTNjMCAuNC0uMS44LS4xIDEuMi0uMS4zLS4xLjctLjEgMSAwIC44LjMuOCAxLjQuOGguNXYxLjloLS45Yy0yLjEgMC0zLjUtLjYtMy41LTIuMyAwLS40LjEtLjkuMS0xLjMuMS0uNS4xLS45LjEtMS4zIDAtLjUtLjItMS0xLjctMXYtMS45eiIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSIxMy44IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY3g9IjExIiBjeT0iOC4yIiByPSIyLjEiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgPGcgY2xhc3M9ImpwLWljb24td2FybjAiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4=);
  --jp-icon-listings-info: url(data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iaXNvLTg4NTktMSI/Pg0KPHN2ZyB2ZXJzaW9uPSIxLjEiIGlkPSJDYXBhXzEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiIHg9IjBweCIgeT0iMHB4Ig0KCSB2aWV3Qm94PSIwIDAgNTAuOTc4IDUwLjk3OCIgc3R5bGU9ImVuYWJsZS1iYWNrZ3JvdW5kOm5ldyAwIDAgNTAuOTc4IDUwLjk3ODsiIHhtbDpzcGFjZT0icHJlc2VydmUiPg0KPGc+DQoJPGc+DQoJCTxnPg0KCQkJPHBhdGggc3R5bGU9ImZpbGw6IzAxMDAwMjsiIGQ9Ik00My41Miw3LjQ1OEMzOC43MTEsMi42NDgsMzIuMzA3LDAsMjUuNDg5LDBDMTguNjcsMCwxMi4yNjYsMi42NDgsNy40NTgsNy40NTgNCgkJCQljLTkuOTQzLDkuOTQxLTkuOTQzLDI2LjExOSwwLDM2LjA2MmM0LjgwOSw0LjgwOSwxMS4yMTIsNy40NTYsMTguMDMxLDcuNDU4YzAsMCwwLjAwMSwwLDAuMDAyLDANCgkJCQljNi44MTYsMCwxMy4yMjEtMi42NDgsMTguMDI5LTcuNDU4YzQuODA5LTQuODA5LDcuNDU3LTExLjIxMiw3LjQ1Ny0xOC4wM0M1MC45NzcsMTguNjcsNDguMzI4LDEyLjI2Niw0My41Miw3LjQ1OHoNCgkJCQkgTTQyLjEwNiw0Mi4xMDVjLTQuNDMyLDQuNDMxLTEwLjMzMiw2Ljg3Mi0xNi42MTUsNi44NzJoLTAuMDAyYy02LjI4NS0wLjAwMS0xMi4xODctMi40NDEtMTYuNjE3LTYuODcyDQoJCQkJYy05LjE2Mi05LjE2My05LjE2Mi0yNC4wNzEsMC0zMy4yMzNDMTMuMzAzLDQuNDQsMTkuMjA0LDIsMjUuNDg5LDJjNi4yODQsMCwxMi4xODYsMi40NCwxNi42MTcsNi44NzINCgkJCQljNC40MzEsNC40MzEsNi44NzEsMTAuMzMyLDYuODcxLDE2LjYxN0M0OC45NzcsMzEuNzcyLDQ2LjUzNiwzNy42NzUsNDIuMTA2LDQyLjEwNXoiLz4NCgkJPC9nPg0KCQk8Zz4NCgkJCTxwYXRoIHN0eWxlPSJmaWxsOiMwMTAwMDI7IiBkPSJNMjMuNTc4LDMyLjIxOGMtMC4wMjMtMS43MzQsMC4xNDMtMy4wNTksMC40OTYtMy45NzJjMC4zNTMtMC45MTMsMS4xMS0xLjk5NywyLjI3Mi0zLjI1Mw0KCQkJCWMwLjQ2OC0wLjUzNiwwLjkyMy0xLjA2MiwxLjM2Ny0xLjU3NWMwLjYyNi0wLjc1MywxLjEwNC0xLjQ3OCwxLjQzNi0yLjE3NWMwLjMzMS0wLjcwNywwLjQ5NS0xLjU0MSwwLjQ5NS0yLjUNCgkJCQljMC0xLjA5Ni0wLjI2LTIuMDg4LTAuNzc5LTIuOTc5Yy0wLjU2NS0wLjg3OS0xLjUwMS0xLjMzNi0yLjgwNi0xLjM2OWMtMS44MDIsMC4wNTctMi45ODUsMC42NjctMy41NSwxLjgzMg0KCQkJCWMtMC4zMDEsMC41MzUtMC41MDMsMS4xNDEtMC42MDcsMS44MTRjLTAuMTM5LDAuNzA3LTAuMjA3LDEuNDMyLTAuMjA3LDIuMTc0aC0yLjkzN2MtMC4wOTEtMi4yMDgsMC40MDctNC4xMTQsMS40OTMtNS43MTkNCgkJCQljMS4wNjItMS42NCwyLjg1NS0yLjQ4MSw1LjM3OC0yLjUyN2MyLjE2LDAuMDIzLDMuODc0LDAuNjA4LDUuMTQxLDEuNzU4YzEuMjc4LDEuMTYsMS45MjksMi43NjQsMS45NSw0LjgxMQ0KCQkJCWMwLDEuMTQyLTAuMTM3LDIuMTExLTAuNDEsMi45MTFjLTAuMzA5LDAuODQ1LTAuNzMxLDEuNTkzLTEuMjY4LDIuMjQzYy0wLjQ5MiwwLjY1LTEuMDY4LDEuMzE4LTEuNzMsMi4wMDINCgkJCQljLTAuNjUsMC42OTctMS4zMTMsMS40NzktMS45ODcsMi4zNDZjLTAuMjM5LDAuMzc3LTAuNDI5LDAuNzc3LTAuNTY1LDEuMTk5Yy0wLjE2LDAuOTU5LTAuMjE3LDEuOTUxLTAuMTcxLDIuOTc5DQoJCQkJQzI2LjU4OSwzMi4yMTgsMjMuNTc4LDMyLjIxOCwyMy41NzgsMzIuMjE4eiBNMjMuNTc4LDM4LjIydi0zLjQ4NGgzLjA3NnYzLjQ4NEgyMy41Nzh6Ii8+DQoJCTwvZz4NCgk8L2c+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8L3N2Zz4NCg==);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMEQ0N0ExIj4KICAgIDxwYXRoIGQ9Ik0xMS4xIDYuOVY1LjhINi45YzAtLjUgMC0xLjMuMi0xLjYuNC0uNy44LTEuMSAxLjctMS40IDEuNy0uMyAyLjUtLjMgMy45LS4xIDEgLjEgMS45LjkgMS45IDEuOXY0LjJjMCAuNS0uOSAxLjYtMiAxLjZIOC44Yy0xLjUgMC0yLjQgMS40LTIuNCAyLjh2Mi4ySDQuN0MzLjUgMTUuMSAzIDE0IDMgMTMuMVY5Yy0uMS0xIC42LTIgMS44LTIgMS41LS4xIDYuMy0uMSA2LjMtLjF6Ii8+CiAgICA8cGF0aCBkPSJNMTAuOSAxNS4xdjEuMWg0LjJjMCAuNSAwIDEuMy0uMiAxLjYtLjQuNy0uOCAxLjEtMS43IDEuNC0xLjcuMy0yLjUuMy0zLjkuMS0xLS4xLTEuOS0uOS0xLjktMS45di00LjJjMC0uNS45LTEuNiAyLTEuNmgzLjhjMS41IDAgMi40LTEuNCAyLjQtMi44VjYuNmgxLjdDMTguNSA2LjkgMTkgOCAxOSA4LjlWMTNjMCAxLS43IDIuMS0xLjkgMi4xaC02LjJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMikiIGZpbGw9IiMzMzMzMzMiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uLWFjY2VudDIganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGQ9Ik01LjA1NjY0IDguNzYxNzJDNS4wNTY2NCA4LjU5NzY2IDUuMDMxMjUgOC40NTMxMiA0Ljk4MDQ3IDguMzI4MTJDNC45MzM1OSA4LjE5OTIyIDQuODU1NDcgOC4wODIwMyA0Ljc0NjA5IDcuOTc2NTZDNC42NDA2MiA3Ljg3MTA5IDQuNSA3Ljc3NTM5IDQuMzI0MjIgNy42ODk0NUM0LjE1MjM0IDcuNTk5NjEgMy45NDMzNiA3LjUxMTcyIDMuNjk3MjcgNy40MjU3OEMzLjMwMjczIDcuMjg1MTYgMi45NDMzNiA3LjEzNjcyIDIuNjE5MTQgNi45ODA0N0MyLjI5NDkyIDYuODI0MjIgMi4wMTc1OCA2LjY0MjU4IDEuNzg3MTEgNi40MzU1NUMxLjU2MDU1IDYuMjI4NTIgMS4zODQ3NyA1Ljk4ODI4IDEuMjU5NzcgNS43MTQ4NEMxLjEzNDc3IDUuNDM3NSAxLjA3MjI3IDUuMTA5MzggMS4wNzIyNyA0LjczMDQ3QzEuMDcyMjcgNC4zOTg0NCAxLjEyODkxIDQuMDk1NyAxLjI0MjE5IDMuODIyMjdDMS4zNTU0NyAzLjU0NDkyIDEuNTE1NjIgMy4zMDQ2OSAxLjcyMjY2IDMuMTAxNTZDMS45Mjk2OSAyLjg5ODQ0IDIuMTc5NjkgMi43MzQzNyAyLjQ3MjY2IDIuNjA5MzhDMi43NjU2MiAyLjQ4NDM4IDMuMDkxOCAyLjQwNDMgMy40NTExNyAyLjM2OTE0VjEuMTA5MzhINC4zODg2N1YyLjM4MDg2QzQuNzQwMjMgMi40Mjc3MyA1LjA1NjY0IDIuNTIzNDQgNS4zMzc4OSAyLjY2Nzk3QzUuNjE5MTQgMi44MTI1IDUuODU3NDIgMy4wMDE5NSA2LjA1MjczIDMuMjM2MzNDNi4yNTE5NSAzLjQ2NjggNi40MDQzIDMuNzQwMjMgNi41MDk3NyA0LjA1NjY0QzYuNjE5MTQgNC4zNjkxNCA2LjY3MzgzIDQuNzIwNyA2LjY3MzgzIDUuMTExMzNINS4wNDQ5MkM1LjA0NDkyIDQuNjM4NjcgNC45Mzc1IDQuMjgxMjUgNC43MjI2NiA0LjAzOTA2QzQuNTA3ODEgMy43OTI5NyA0LjIxNjggMy42Njk5MiAzLjg0OTYxIDMuNjY5OTJDMy42NTAzOSAzLjY2OTkyIDMuNDc2NTYgMy42OTcyNyAzLjMyODEyIDMuNzUxOTVDMy4xODM1OSAzLjgwMjczIDMuMDY0NDUgMy44NzY5NSAyLjk3MDcgMy45NzQ2MUMyLjg3Njk1IDQuMDY4MzYgMi44MDY2NCA0LjE3OTY5IDIuNzU5NzcgNC4zMDg1OUMyLjcxNjggNC40Mzc1IDIuNjk1MzEgNC41NzgxMiAyLjY5NTMxIDQuNzMwNDdDMi42OTUzMSA0Ljg4MjgxIDIuNzE2OCA1LjAxOTUzIDIuNzU5NzcgNS4xNDA2MkMyLjgwNjY0IDUuMjU3ODEgMi44ODI4MSA1LjM2NzE5IDIuOTg4MjggNS40Njg3NUMzLjA5NzY2IDUuNTcwMzEgMy4yNDAyMyA1LjY2Nzk3IDMuNDE2MDIgNS43NjE3MkMzLjU5MTggNS44NTE1NiAzLjgxMDU1IDUuOTQzMzYgNC4wNzIyNyA2LjAzNzExQzQuNDY2OCA2LjE4NTU1IDQuODI0MjIgNi4zMzk4NCA1LjE0NDUzIDYuNUM1LjQ2NDg0IDYuNjU2MjUgNS43MzgyOCA2LjgzOTg0IDUuOTY0ODQgNy4wNTA3OEM2LjE5NTMxIDcuMjU3ODEgNi4zNzEwOSA3LjUgNi40OTIxOSA3Ljc3NzM0QzYuNjE3MTkgOC4wNTA3OCA2LjY3OTY5IDguMzc1IDYuNjc5NjkgOC43NUM2LjY3OTY5IDkuMDkzNzUgNi42MjMwNSA5LjQwNDMgNi41MDk3NyA5LjY4MTY0QzYuMzk2NDggOS45NTUwOCA2LjIzNDM4IDEwLjE5MTQgNi4wMjM0NCAxMC4zOTA2QzUuODEyNSAxMC41ODk4IDUuNTU4NTkgMTAuNzUgNS4yNjE3MiAxMC44NzExQzQuOTY0ODQgMTAuOTg4MyA0LjYzMjgxIDExLjA2NDUgNC4yNjU2MiAxMS4wOTk2VjEyLjI0OEgzLjMzMzk4VjExLjA5OTZDMy4wMDE5NSAxMS4wNjg0IDIuNjc5NjkgMTAuOTk2MSAyLjM2NzE5IDEwLjg4MjhDMi4wNTQ2OSAxMC43NjU2IDEuNzc3MzQgMTAuNTk3NyAxLjUzNTE2IDEwLjM3ODlDMS4yOTY4OCAxMC4xNjAyIDEuMTA1NDcgOS44ODQ3NyAwLjk2MDkzOCA5LjU1MjczQzAuODE2NDA2IDkuMjE2OCAwLjc0NDE0MSA4LjgxNDQ1IDAuNzQ0MTQxIDguMzQ1N0gyLjM3ODkxQzIuMzc4OTEgOC42MjY5NSAyLjQxOTkyIDguODYzMjggMi41MDE5NSA5LjA1NDY5QzIuNTgzOTggOS4yNDIxOSAyLjY4OTQ1IDkuMzkyNTggMi44MTgzNiA5LjUwNTg2QzIuOTUxMTcgOS42MTUyMyAzLjEwMTU2IDkuNjkzMzYgMy4yNjk1MyA5Ljc0MDIzQzMuNDM3NSA5Ljc4NzExIDMuNjA5MzggOS44MTA1NSAzLjc4NTE2IDkuODEwNTVDNC4yMDMxMiA5LjgxMDU1IDQuNTE5NTMgOS43MTI4OSA0LjczNDM4IDkuNTE3NThDNC45NDkyMiA5LjMyMjI3IDUuMDU2NjQgOS4wNzAzMSA1LjA1NjY0IDguNzYxNzJaTTEzLjQxOCAxMi4yNzE1SDguMDc0MjJWMTFIMTMuNDE4VjEyLjI3MTVaIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzLjk1MjY0IDYpIiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTUgMTVIM3YyaDEydi0yem0wLThIM3YyaDEyVjd6TTMgMTNoMTh2LTJIM3Yyem0wIDhoMTh2LTJIM3Yyek0zIDN2MmgxOFYzSDN6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}
.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}
.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}
.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}
.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}
.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}
.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}
.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}
.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}
.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}
.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}
.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}
.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}
.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}
.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}
.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}
.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}
.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}
.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}
.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}
.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}
.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}
.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}
.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}
.jp-FileIcon {
  background-image: var(--jp-icon-file);
}
.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}
.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}
.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}
.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}
.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}
.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}
.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}
.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}
.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}
.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}
.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}
.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}
.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}
.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}
.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}
.jp-ListIcon {
  background-image: var(--jp-icon-list);
}
.jp-ListingsInfoIcon {
  background-image: var(--jp-icon-listings-info);
}
.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}
.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}
.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}
.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}
.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}
.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}
.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}
.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}
.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}
.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}
.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}
.jp-RunIcon {
  background-image: var(--jp-icon-run);
}
.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}
.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}
.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}
.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}
.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}
.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}
.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}
.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}
.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}
.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}
.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}
.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}
.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

:root {
  --jp-icon-search-white: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
}

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}
/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}
/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}
/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}
.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}
.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}
.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}
.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}
.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}
.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}
.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}
.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}
/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}
.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}
.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}
.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}
.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}
.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}
.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}
/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

/* CSS for icons in selected items in the settings editor */
#setting-editor .jp-PluginList .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
#setting-editor
  .jp-PluginList
  .jp-mod-selected
  .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected tabs in the sidebar tab manager */
#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable[fill] {
  fill: #fff;
}

#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable[fill] {
  fill: var(--jp-brand-color1);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable-inverse[fill] {
  fill: #fff;
}

/**
 * TODO: come up with non css-hack solution for showing the busy icon on top
 *  of the close icon
 * CSS for complex behavior of close icon of tabs in the sidebar tab manager
 */
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-dirty.jp-mod-active
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: #fff;
}

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) svg {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

/* Override Blueprint's _reset.scss styles */
html {
  box-sizing: unset;
}

*,
*::before,
*::after {
  box-sizing: unset;
}

body {
  color: unset;
  font-family: var(--jp-ui-font-family);
}

p {
  margin-top: unset;
  margin-bottom: unset;
}

small {
  font-size: unset;
}

strong {
  font-weight: unset;
}

/* Override Blueprint's _typography.scss styles */
a {
  text-decoration: unset;
  color: unset;
}
a:hover {
  text-decoration: unset;
  color: unset;
}

/* Override Blueprint's _accessibility.scss styles */
:focus {
  outline: unset;
  outline-offset: unset;
  -moz-outline-radius: unset;
}

/* Styles for ui-components */
.jp-Button {
  border-radius: var(--jp-border-radius);
  padding: 0px 12px;
  font-size: var(--jp-ui-font-size1);
}

/* Use our own theme for hover styles */
button.jp-Button.bp3-button.bp3-minimal:hover {
  background-color: var(--jp-layout-color2);
}
.jp-Button.minimal {
  color: unset !important;
}

.jp-Button.jp-ToolbarButtonComponent {
  text-transform: none;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color3);
}

.jp-BPIcon {
  display: inline-block;
  vertical-align: middle;
  margin: auto;
}

/* Stop blueprint futzing with our icon fills */
.bp3-icon.jp-BPIcon > svg:not([fill]) {
  fill: var(--jp-inverse-layout-color3);
}

.jp-InputGroupAction {
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

/* Use our own theme for hover and option styles */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}
select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-top: 1px solid var(--jp-border-color2);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-Collapse-header {
  padding: 1px 12px;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size2);
}

.jp-Collapse-header:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Collapse-contents {
  padding: 0px 12px 0px 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0px;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0px 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.lm-CommandPalette-wrapper::after {
  content: ' ';
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  height: 30px;
  width: 10px;
  padding: 0px 10px;
  background-image: var(--jp-icon-search-white);
  background-size: 20px;
  background-repeat: no-repeat;
  background-position: center;
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color3);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0px;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item.lm-mod-active {
  background: var(--jp-layout-color3);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  background: var(--jp-layout-color4);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.4;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty:after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0px 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0px;
  left: 0px;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px;
  padding-bottom: 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0px;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

.jp-Dialog-header {
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0px 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

.jp-HoverBox.jp-mod-outofview {
  display: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;

  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;

  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #aa00ff;

  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;

  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;

  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;

  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;

  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;

  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;

  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;

  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;

  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;

  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ffff00;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;

  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;

  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;

  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;

  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;

  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eeeeee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;

  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent:before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent:after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0px 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  height: 28px;
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  background-color: var(--jp-layout-color1);
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0px 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  height: 32px;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 1;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px;
  margin: 0px;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px 6px;
  margin: 0px;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent span {
  padding: 0px;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ body.p-mod-override-cursor *, /* </DEPRECATED> */
body.lm-mod-override-cursor * {
  cursor: inherit !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* BASICS */

.CodeMirror {
  /* Set height, width, borders, and global font properties here */
  font-family: monospace;
  height: 300px;
  color: black;
  direction: ltr;
}

/* PADDING */

.CodeMirror-lines {
  padding: 4px 0; /* Vertical padding around content */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  padding: 0 4px; /* Horizontal padding of content */
}

.CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  background-color: white; /* The little square between H and V scrollbars */
}

/* GUTTER */

.CodeMirror-gutters {
  border-right: 1px solid #ddd;
  background-color: #f7f7f7;
  white-space: nowrap;
}
.CodeMirror-linenumbers {}
.CodeMirror-linenumber {
  padding: 0 3px 0 5px;
  min-width: 20px;
  text-align: right;
  color: #999;
  white-space: nowrap;
}

.CodeMirror-guttermarker { color: black; }
.CodeMirror-guttermarker-subtle { color: #999; }

/* CURSOR */

.CodeMirror-cursor {
  border-left: 1px solid black;
  border-right: none;
  width: 0;
}
/* Shown when moving in bi-directional text */
.CodeMirror div.CodeMirror-secondarycursor {
  border-left: 1px solid silver;
}
.cm-fat-cursor .CodeMirror-cursor {
  width: auto;
  border: 0 !important;
  background: #7e7;
}
.cm-fat-cursor div.CodeMirror-cursors {
  z-index: 1;
}
.cm-fat-cursor-mark {
  background-color: rgba(20, 255, 20, 0.5);
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
}
.cm-animate-fat-cursor {
  width: auto;
  border: 0;
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
  background-color: #7e7;
}
@-moz-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@-webkit-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}

/* Can style cursor different in overwrite (non-insert) mode */
.CodeMirror-overwrite .CodeMirror-cursor {}

.cm-tab { display: inline-block; text-decoration: inherit; }

.CodeMirror-rulers {
  position: absolute;
  left: 0; right: 0; top: -50px; bottom: 0;
  overflow: hidden;
}
.CodeMirror-ruler {
  border-left: 1px solid #ccc;
  top: 0; bottom: 0;
  position: absolute;
}

/* DEFAULT THEME */

.cm-s-default .cm-header {color: blue;}
.cm-s-default .cm-quote {color: #090;}
.cm-negative {color: #d44;}
.cm-positive {color: #292;}
.cm-header, .cm-strong {font-weight: bold;}
.cm-em {font-style: italic;}
.cm-link {text-decoration: underline;}
.cm-strikethrough {text-decoration: line-through;}

.cm-s-default .cm-keyword {color: #708;}
.cm-s-default .cm-atom {color: #219;}
.cm-s-default .cm-number {color: #164;}
.cm-s-default .cm-def {color: #00f;}
.cm-s-default .cm-variable,
.cm-s-default .cm-punctuation,
.cm-s-default .cm-property,
.cm-s-default .cm-operator {}
.cm-s-default .cm-variable-2 {color: #05a;}
.cm-s-default .cm-variable-3, .cm-s-default .cm-type {color: #085;}
.cm-s-default .cm-comment {color: #a50;}
.cm-s-default .cm-string {color: #a11;}
.cm-s-default .cm-string-2 {color: #f50;}
.cm-s-default .cm-meta {color: #555;}
.cm-s-default .cm-qualifier {color: #555;}
.cm-s-default .cm-builtin {color: #30a;}
.cm-s-default .cm-bracket {color: #997;}
.cm-s-default .cm-tag {color: #170;}
.cm-s-default .cm-attribute {color: #00c;}
.cm-s-default .cm-hr {color: #999;}
.cm-s-default .cm-link {color: #00c;}

.cm-s-default .cm-error {color: #f00;}
.cm-invalidchar {color: #f00;}

.CodeMirror-composing { border-bottom: 2px solid; }

/* Default styles for common addons */

div.CodeMirror span.CodeMirror-matchingbracket {color: #0b0;}
div.CodeMirror span.CodeMirror-nonmatchingbracket {color: #a22;}
.CodeMirror-matchingtag { background: rgba(255, 150, 0, .3); }
.CodeMirror-activeline-background {background: #e8f2ff;}

/* STOP */

/* The rest of this file contains styles related to the mechanics of
   the editor. You probably shouldn't touch them. */

.CodeMirror {
  position: relative;
  overflow: hidden;
  background: white;
}

.CodeMirror-scroll {
  overflow: scroll !important; /* Things will break if this is overridden */
  /* 30px is the magic margin used to hide the element's real scrollbars */
  /* See overflow: hidden in .CodeMirror */
  margin-bottom: -30px; margin-right: -30px;
  padding-bottom: 30px;
  height: 100%;
  outline: none; /* Prevent dragging from highlighting the element */
  position: relative;
}
.CodeMirror-sizer {
  position: relative;
  border-right: 30px solid transparent;
}

/* The fake, visible scrollbars. Used to force redraw during scrolling
   before actual scrolling happens, thus preventing shaking and
   flickering artifacts. */
.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  position: absolute;
  z-index: 6;
  display: none;
}
.CodeMirror-vscrollbar {
  right: 0; top: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}
.CodeMirror-hscrollbar {
  bottom: 0; left: 0;
  overflow-y: hidden;
  overflow-x: scroll;
}
.CodeMirror-scrollbar-filler {
  right: 0; bottom: 0;
}
.CodeMirror-gutter-filler {
  left: 0; bottom: 0;
}

.CodeMirror-gutters {
  position: absolute; left: 0; top: 0;
  min-height: 100%;
  z-index: 3;
}
.CodeMirror-gutter {
  white-space: normal;
  height: 100%;
  display: inline-block;
  vertical-align: top;
  margin-bottom: -30px;
}
.CodeMirror-gutter-wrapper {
  position: absolute;
  z-index: 4;
  background: none !important;
  border: none !important;
}
.CodeMirror-gutter-background {
  position: absolute;
  top: 0; bottom: 0;
  z-index: 4;
}
.CodeMirror-gutter-elt {
  position: absolute;
  cursor: default;
  z-index: 4;
}
.CodeMirror-gutter-wrapper ::selection { background-color: transparent }
.CodeMirror-gutter-wrapper ::-moz-selection { background-color: transparent }

.CodeMirror-lines {
  cursor: text;
  min-height: 1px; /* prevents collapsing before first draw */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  /* Reset some styles that the rest of the page might have set */
  -moz-border-radius: 0; -webkit-border-radius: 0; border-radius: 0;
  border-width: 0;
  background: transparent;
  font-family: inherit;
  font-size: inherit;
  margin: 0;
  white-space: pre;
  word-wrap: normal;
  line-height: inherit;
  color: inherit;
  z-index: 2;
  position: relative;
  overflow: visible;
  -webkit-tap-highlight-color: transparent;
  -webkit-font-variant-ligatures: contextual;
  font-variant-ligatures: contextual;
}
.CodeMirror-wrap pre.CodeMirror-line,
.CodeMirror-wrap pre.CodeMirror-line-like {
  word-wrap: break-word;
  white-space: pre-wrap;
  word-break: normal;
}

.CodeMirror-linebackground {
  position: absolute;
  left: 0; right: 0; top: 0; bottom: 0;
  z-index: 0;
}

.CodeMirror-linewidget {
  position: relative;
  z-index: 2;
  padding: 0.1px; /* Force widget margins to stay inside of the container */
}

.CodeMirror-widget {}

.CodeMirror-rtl pre { direction: rtl; }

.CodeMirror-code {
  outline: none;
}

/* Force content-box sizing for the elements where we expect it */
.CodeMirror-scroll,
.CodeMirror-sizer,
.CodeMirror-gutter,
.CodeMirror-gutters,
.CodeMirror-linenumber {
  -moz-box-sizing: content-box;
  box-sizing: content-box;
}

.CodeMirror-measure {
  position: absolute;
  width: 100%;
  height: 0;
  overflow: hidden;
  visibility: hidden;
}

.CodeMirror-cursor {
  position: absolute;
  pointer-events: none;
}
.CodeMirror-measure pre { position: static; }

div.CodeMirror-cursors {
  visibility: hidden;
  position: relative;
  z-index: 3;
}
div.CodeMirror-dragcursors {
  visibility: visible;
}

.CodeMirror-focused div.CodeMirror-cursors {
  visibility: visible;
}

.CodeMirror-selected { background: #d9d9d9; }
.CodeMirror-focused .CodeMirror-selected { background: #d7d4f0; }
.CodeMirror-crosshair { cursor: crosshair; }
.CodeMirror-line::selection, .CodeMirror-line > span::selection, .CodeMirror-line > span > span::selection { background: #d7d4f0; }
.CodeMirror-line::-moz-selection, .CodeMirror-line > span::-moz-selection, .CodeMirror-line > span > span::-moz-selection { background: #d7d4f0; }

.cm-searching {
  background-color: #ffa;
  background-color: rgba(255, 255, 0, .4);
}

/* Used to force a border model for a node */
.cm-force-border { padding-right: .1px; }

@media print {
  /* Hide the cursor when printing */
  .CodeMirror div.CodeMirror-cursors {
    visibility: hidden;
  }
}

/* See issue #2901 */
.cm-tab-wrap-hack:after { content: ''; }

/* Help users use markselection to safely style text background */
span.CodeMirror-selectedtext { background: none; }

.CodeMirror-dialog {
  position: absolute;
  left: 0; right: 0;
  background: inherit;
  z-index: 15;
  padding: .1em .8em;
  overflow: hidden;
  color: inherit;
}

.CodeMirror-dialog-top {
  border-bottom: 1px solid #eee;
  top: 0;
}

.CodeMirror-dialog-bottom {
  border-top: 1px solid #eee;
  bottom: 0;
}

.CodeMirror-dialog input {
  border: none;
  outline: none;
  background: transparent;
  width: 20em;
  color: inherit;
  font-family: monospace;
}

.CodeMirror-dialog button {
  font-size: 70%;
}

.CodeMirror-foldmarker {
  color: blue;
  text-shadow: #b9f 1px 1px 2px, #b9f -1px -1px 2px, #b9f 1px -1px 2px, #b9f -1px 1px 2px;
  font-family: arial;
  line-height: .3;
  cursor: pointer;
}
.CodeMirror-foldgutter {
  width: .7em;
}
.CodeMirror-foldgutter-open,
.CodeMirror-foldgutter-folded {
  cursor: pointer;
}
.CodeMirror-foldgutter-open:after {
  content: "\25BE";
}
.CodeMirror-foldgutter-folded:after {
  content: "\25B8";
}

/*
  Name:       material
  Author:     Mattia Astorino (http://github.com/equinusocio)
  Website:    https://material-theme.site/
*/

.cm-s-material.CodeMirror {
  background-color: #263238;
  color: #EEFFFF;
}

.cm-s-material .CodeMirror-gutters {
  background: #263238;
  color: #546E7A;
  border: none;
}

.cm-s-material .CodeMirror-guttermarker,
.cm-s-material .CodeMirror-guttermarker-subtle,
.cm-s-material .CodeMirror-linenumber {
  color: #546E7A;
}

.cm-s-material .CodeMirror-cursor {
  border-left: 1px solid #FFCC00;
}

.cm-s-material div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material.CodeMirror-focused div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::selection,
.cm-s-material .CodeMirror-line>span::selection,
.cm-s-material .CodeMirror-line>span>span::selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::-moz-selection,
.cm-s-material .CodeMirror-line>span::-moz-selection,
.cm-s-material .CodeMirror-line>span>span::-moz-selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.5);
}

.cm-s-material .cm-keyword {
  color: #C792EA;
}

.cm-s-material .cm-operator {
  color: #89DDFF;
}

.cm-s-material .cm-variable-2 {
  color: #EEFFFF;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #f07178;
}

.cm-s-material .cm-builtin {
  color: #FFCB6B;
}

.cm-s-material .cm-atom {
  color: #F78C6C;
}

.cm-s-material .cm-number {
  color: #FF5370;
}

.cm-s-material .cm-def {
  color: #82AAFF;
}

.cm-s-material .cm-string {
  color: #C3E88D;
}

.cm-s-material .cm-string-2 {
  color: #f07178;
}

.cm-s-material .cm-comment {
  color: #546E7A;
}

.cm-s-material .cm-variable {
  color: #f07178;
}

.cm-s-material .cm-tag {
  color: #FF5370;
}

.cm-s-material .cm-meta {
  color: #FFCB6B;
}

.cm-s-material .cm-attribute {
  color: #C792EA;
}

.cm-s-material .cm-property {
  color: #C792EA;
}

.cm-s-material .cm-qualifier {
  color: #DECB6B;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #DECB6B;
}


.cm-s-material .cm-error {
  color: rgba(255, 255, 255, 1.0);
  background-color: #FF5370;
}

.cm-s-material .CodeMirror-matchingbracket {
  text-decoration: underline;
  color: white !important;
}
/**
 * "
 *  Using Zenburn color palette from the Emacs Zenburn Theme
 *  https://github.com/bbatsov/zenburn-emacs/blob/master/zenburn-theme.el
 *
 *  Also using parts of https://github.com/xavi/coderay-lighttable-theme
 * "
 * From: https://github.com/wisenomad/zenburn-lighttable-theme/blob/master/zenburn.css
 */

.cm-s-zenburn .CodeMirror-gutters { background: #3f3f3f !important; }
.cm-s-zenburn .CodeMirror-foldgutter-open, .CodeMirror-foldgutter-folded { color: #999; }
.cm-s-zenburn .CodeMirror-cursor { border-left: 1px solid white; }
.cm-s-zenburn { background-color: #3f3f3f; color: #dcdccc; }
.cm-s-zenburn span.cm-builtin { color: #dcdccc; font-weight: bold; }
.cm-s-zenburn span.cm-comment { color: #7f9f7f; }
.cm-s-zenburn span.cm-keyword { color: #f0dfaf; font-weight: bold; }
.cm-s-zenburn span.cm-atom { color: #bfebbf; }
.cm-s-zenburn span.cm-def { color: #dcdccc; }
.cm-s-zenburn span.cm-variable { color: #dfaf8f; }
.cm-s-zenburn span.cm-variable-2 { color: #dcdccc; }
.cm-s-zenburn span.cm-string { color: #cc9393; }
.cm-s-zenburn span.cm-string-2 { color: #cc9393; }
.cm-s-zenburn span.cm-number { color: #dcdccc; }
.cm-s-zenburn span.cm-tag { color: #93e0e3; }
.cm-s-zenburn span.cm-property { color: #dfaf8f; }
.cm-s-zenburn span.cm-attribute { color: #dfaf8f; }
.cm-s-zenburn span.cm-qualifier { color: #7cb8bb; }
.cm-s-zenburn span.cm-meta { color: #f0dfaf; }
.cm-s-zenburn span.cm-header { color: #f0efd0; }
.cm-s-zenburn span.cm-operator { color: #f0efd0; }
.cm-s-zenburn span.CodeMirror-matchingbracket { box-sizing: border-box; background: transparent; border-bottom: 1px solid; }
.cm-s-zenburn span.CodeMirror-nonmatchingbracket { border-bottom: 1px solid; background: none; }
.cm-s-zenburn .CodeMirror-activeline { background: #000000; }
.cm-s-zenburn .CodeMirror-activeline-background { background: #000000; }
.cm-s-zenburn div.CodeMirror-selected { background: #545454; }
.cm-s-zenburn .CodeMirror-focused div.CodeMirror-selected { background: #4f4f4f; }

.cm-s-abcdef.CodeMirror { background: #0f0f0f; color: #defdef; }
.cm-s-abcdef div.CodeMirror-selected { background: #515151; }
.cm-s-abcdef .CodeMirror-line::selection, .cm-s-abcdef .CodeMirror-line > span::selection, .cm-s-abcdef .CodeMirror-line > span > span::selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-line::-moz-selection, .cm-s-abcdef .CodeMirror-line > span::-moz-selection, .cm-s-abcdef .CodeMirror-line > span > span::-moz-selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-gutters { background: #555; border-right: 2px solid #314151; }
.cm-s-abcdef .CodeMirror-guttermarker { color: #222; }
.cm-s-abcdef .CodeMirror-guttermarker-subtle { color: azure; }
.cm-s-abcdef .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-abcdef .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-abcdef span.cm-keyword { color: darkgoldenrod; font-weight: bold; }
.cm-s-abcdef span.cm-atom { color: #77F; }
.cm-s-abcdef span.cm-number { color: violet; }
.cm-s-abcdef span.cm-def { color: #fffabc; }
.cm-s-abcdef span.cm-variable { color: #abcdef; }
.cm-s-abcdef span.cm-variable-2 { color: #cacbcc; }
.cm-s-abcdef span.cm-variable-3, .cm-s-abcdef span.cm-type { color: #def; }
.cm-s-abcdef span.cm-property { color: #fedcba; }
.cm-s-abcdef span.cm-operator { color: #ff0; }
.cm-s-abcdef span.cm-comment { color: #7a7b7c; font-style: italic;}
.cm-s-abcdef span.cm-string { color: #2b4; }
.cm-s-abcdef span.cm-meta { color: #C9F; }
.cm-s-abcdef span.cm-qualifier { color: #FFF700; }
.cm-s-abcdef span.cm-builtin { color: #30aabc; }
.cm-s-abcdef span.cm-bracket { color: #8a8a8a; }
.cm-s-abcdef span.cm-tag { color: #FFDD44; }
.cm-s-abcdef span.cm-attribute { color: #DDFF00; }
.cm-s-abcdef span.cm-error { color: #FF0000; }
.cm-s-abcdef span.cm-header { color: aquamarine; font-weight: bold; }
.cm-s-abcdef span.cm-link { color: blueviolet; }

.cm-s-abcdef .CodeMirror-activeline-background { background: #314151; }

/*

    Name:       Base16 Default Light
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-light.CodeMirror { background: #f5f5f5; color: #202020; }
.cm-s-base16-light div.CodeMirror-selected { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::selection, .cm-s-base16-light .CodeMirror-line > span::selection, .cm-s-base16-light .CodeMirror-line > span > span::selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::-moz-selection, .cm-s-base16-light .CodeMirror-line > span::-moz-selection, .cm-s-base16-light .CodeMirror-line > span > span::-moz-selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-gutters { background: #f5f5f5; border-right: 0px; }
.cm-s-base16-light .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-light .CodeMirror-guttermarker-subtle { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-linenumber { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-cursor { border-left: 1px solid #505050; }

.cm-s-base16-light span.cm-comment { color: #8f5536; }
.cm-s-base16-light span.cm-atom { color: #aa759f; }
.cm-s-base16-light span.cm-number { color: #aa759f; }

.cm-s-base16-light span.cm-property, .cm-s-base16-light span.cm-attribute { color: #90a959; }
.cm-s-base16-light span.cm-keyword { color: #ac4142; }
.cm-s-base16-light span.cm-string { color: #f4bf75; }

.cm-s-base16-light span.cm-variable { color: #90a959; }
.cm-s-base16-light span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-light span.cm-def { color: #d28445; }
.cm-s-base16-light span.cm-bracket { color: #202020; }
.cm-s-base16-light span.cm-tag { color: #ac4142; }
.cm-s-base16-light span.cm-link { color: #aa759f; }
.cm-s-base16-light span.cm-error { background: #ac4142; color: #505050; }

.cm-s-base16-light .CodeMirror-activeline-background { background: #DDDCDC; }
.cm-s-base16-light .CodeMirror-matchingbracket { color: #f5f5f5 !important; background-color: #6A9FB5 !important}

/*

    Name:       Base16 Default Dark
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-dark.CodeMirror { background: #151515; color: #e0e0e0; }
.cm-s-base16-dark div.CodeMirror-selected { background: #303030; }
.cm-s-base16-dark .CodeMirror-line::selection, .cm-s-base16-dark .CodeMirror-line > span::selection, .cm-s-base16-dark .CodeMirror-line > span > span::selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-line::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-gutters { background: #151515; border-right: 0px; }
.cm-s-base16-dark .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-dark .CodeMirror-guttermarker-subtle { color: #505050; }
.cm-s-base16-dark .CodeMirror-linenumber { color: #505050; }
.cm-s-base16-dark .CodeMirror-cursor { border-left: 1px solid #b0b0b0; }

.cm-s-base16-dark span.cm-comment { color: #8f5536; }
.cm-s-base16-dark span.cm-atom { color: #aa759f; }
.cm-s-base16-dark span.cm-number { color: #aa759f; }

.cm-s-base16-dark span.cm-property, .cm-s-base16-dark span.cm-attribute { color: #90a959; }
.cm-s-base16-dark span.cm-keyword { color: #ac4142; }
.cm-s-base16-dark span.cm-string { color: #f4bf75; }

.cm-s-base16-dark span.cm-variable { color: #90a959; }
.cm-s-base16-dark span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-dark span.cm-def { color: #d28445; }
.cm-s-base16-dark span.cm-bracket { color: #e0e0e0; }
.cm-s-base16-dark span.cm-tag { color: #ac4142; }
.cm-s-base16-dark span.cm-link { color: #aa759f; }
.cm-s-base16-dark span.cm-error { background: #ac4142; color: #b0b0b0; }

.cm-s-base16-dark .CodeMirror-activeline-background { background: #202020; }
.cm-s-base16-dark .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       dracula
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original dracula color scheme by Zeno Rocha (https://github.com/zenorocha/dracula-theme)

*/


.cm-s-dracula.CodeMirror, .cm-s-dracula .CodeMirror-gutters {
  background-color: #282a36 !important;
  color: #f8f8f2 !important;
  border: none;
}
.cm-s-dracula .CodeMirror-gutters { color: #282a36; }
.cm-s-dracula .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-dracula .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-dracula .CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::selection, .cm-s-dracula .CodeMirror-line > span::selection, .cm-s-dracula .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::-moz-selection, .cm-s-dracula .CodeMirror-line > span::-moz-selection, .cm-s-dracula .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula span.cm-comment { color: #6272a4; }
.cm-s-dracula span.cm-string, .cm-s-dracula span.cm-string-2 { color: #f1fa8c; }
.cm-s-dracula span.cm-number { color: #bd93f9; }
.cm-s-dracula span.cm-variable { color: #50fa7b; }
.cm-s-dracula span.cm-variable-2 { color: white; }
.cm-s-dracula span.cm-def { color: #50fa7b; }
.cm-s-dracula span.cm-operator { color: #ff79c6; }
.cm-s-dracula span.cm-keyword { color: #ff79c6; }
.cm-s-dracula span.cm-atom { color: #bd93f9; }
.cm-s-dracula span.cm-meta { color: #f8f8f2; }
.cm-s-dracula span.cm-tag { color: #ff79c6; }
.cm-s-dracula span.cm-attribute { color: #50fa7b; }
.cm-s-dracula span.cm-qualifier { color: #50fa7b; }
.cm-s-dracula span.cm-property { color: #66d9ef; }
.cm-s-dracula span.cm-builtin { color: #50fa7b; }
.cm-s-dracula span.cm-variable-3, .cm-s-dracula span.cm-type { color: #ffb86c; }

.cm-s-dracula .CodeMirror-activeline-background { background: rgba(255,255,255,0.1); }
.cm-s-dracula .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       Hopscotch
    Author:     Jan T. Sott

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-hopscotch.CodeMirror {background: #322931; color: #d5d3d5;}
.cm-s-hopscotch div.CodeMirror-selected {background: #433b42 !important;}
.cm-s-hopscotch .CodeMirror-gutters {background: #322931; border-right: 0px;}
.cm-s-hopscotch .CodeMirror-linenumber {color: #797379;}
.cm-s-hopscotch .CodeMirror-cursor {border-left: 1px solid #989498 !important;}

.cm-s-hopscotch span.cm-comment {color: #b33508;}
.cm-s-hopscotch span.cm-atom {color: #c85e7c;}
.cm-s-hopscotch span.cm-number {color: #c85e7c;}

.cm-s-hopscotch span.cm-property, .cm-s-hopscotch span.cm-attribute {color: #8fc13e;}
.cm-s-hopscotch span.cm-keyword {color: #dd464c;}
.cm-s-hopscotch span.cm-string {color: #fdcc59;}

.cm-s-hopscotch span.cm-variable {color: #8fc13e;}
.cm-s-hopscotch span.cm-variable-2 {color: #1290bf;}
.cm-s-hopscotch span.cm-def {color: #fd8b19;}
.cm-s-hopscotch span.cm-error {background: #dd464c; color: #989498;}
.cm-s-hopscotch span.cm-bracket {color: #d5d3d5;}
.cm-s-hopscotch span.cm-tag {color: #dd464c;}
.cm-s-hopscotch span.cm-link {color: #c85e7c;}

.cm-s-hopscotch .CodeMirror-matchingbracket { text-decoration: underline; color: white !important;}
.cm-s-hopscotch .CodeMirror-activeline-background { background: #302020; }

/****************************************************************/
/*   Based on mbonaci's Brackets mbo theme                      */
/*   https://github.com/mbonaci/global/blob/master/Mbo.tmTheme  */
/*   Create your own: http://tmtheme-editor.herokuapp.com       */
/****************************************************************/

.cm-s-mbo.CodeMirror { background: #2c2c2c; color: #ffffec; }
.cm-s-mbo div.CodeMirror-selected { background: #716C62; }
.cm-s-mbo .CodeMirror-line::selection, .cm-s-mbo .CodeMirror-line > span::selection, .cm-s-mbo .CodeMirror-line > span > span::selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-line::-moz-selection, .cm-s-mbo .CodeMirror-line > span::-moz-selection, .cm-s-mbo .CodeMirror-line > span > span::-moz-selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-gutters { background: #4e4e4e; border-right: 0px; }
.cm-s-mbo .CodeMirror-guttermarker { color: white; }
.cm-s-mbo .CodeMirror-guttermarker-subtle { color: grey; }
.cm-s-mbo .CodeMirror-linenumber { color: #dadada; }
.cm-s-mbo .CodeMirror-cursor { border-left: 1px solid #ffffec; }

.cm-s-mbo span.cm-comment { color: #95958a; }
.cm-s-mbo span.cm-atom { color: #00a8c6; }
.cm-s-mbo span.cm-number { color: #00a8c6; }

.cm-s-mbo span.cm-property, .cm-s-mbo span.cm-attribute { color: #9ddfe9; }
.cm-s-mbo span.cm-keyword { color: #ffb928; }
.cm-s-mbo span.cm-string { color: #ffcf6c; }
.cm-s-mbo span.cm-string.cm-property { color: #ffffec; }

.cm-s-mbo span.cm-variable { color: #ffffec; }
.cm-s-mbo span.cm-variable-2 { color: #00a8c6; }
.cm-s-mbo span.cm-def { color: #ffffec; }
.cm-s-mbo span.cm-bracket { color: #fffffc; font-weight: bold; }
.cm-s-mbo span.cm-tag { color: #9ddfe9; }
.cm-s-mbo span.cm-link { color: #f54b07; }
.cm-s-mbo span.cm-error { border-bottom: #636363; color: #ffffec; }
.cm-s-mbo span.cm-qualifier { color: #ffffec; }

.cm-s-mbo .CodeMirror-activeline-background { background: #494b41; }
.cm-s-mbo .CodeMirror-matchingbracket { color: #ffb928 !important; }
.cm-s-mbo .CodeMirror-matchingtag { background: rgba(255, 255, 255, .37); }

/*
  MDN-LIKE Theme - Mozilla
  Ported to CodeMirror by Peter Kroon <plakroon@gmail.com>
  Report bugs/issues here: https://github.com/codemirror/CodeMirror/issues
  GitHub: @peterkroon

  The mdn-like theme is inspired on the displayed code examples at: https://developer.mozilla.org/en-US/docs/Web/CSS/animation

*/
.cm-s-mdn-like.CodeMirror { color: #999; background-color: #fff; }
.cm-s-mdn-like div.CodeMirror-selected { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::selection, .cm-s-mdn-like .CodeMirror-line > span::selection, .cm-s-mdn-like .CodeMirror-line > span > span::selection { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span > span::-moz-selection { background: #cfc; }

.cm-s-mdn-like .CodeMirror-gutters { background: #f8f8f8; border-left: 6px solid rgba(0,83,159,0.65); color: #333; }
.cm-s-mdn-like .CodeMirror-linenumber { color: #aaa; padding-left: 8px; }
.cm-s-mdn-like .CodeMirror-cursor { border-left: 2px solid #222; }

.cm-s-mdn-like .cm-keyword { color: #6262FF; }
.cm-s-mdn-like .cm-atom { color: #F90; }
.cm-s-mdn-like .cm-number { color:  #ca7841; }
.cm-s-mdn-like .cm-def { color: #8DA6CE; }
.cm-s-mdn-like span.cm-variable-2, .cm-s-mdn-like span.cm-tag { color: #690; }
.cm-s-mdn-like span.cm-variable-3, .cm-s-mdn-like span.cm-def, .cm-s-mdn-like span.cm-type { color: #07a; }

.cm-s-mdn-like .cm-variable { color: #07a; }
.cm-s-mdn-like .cm-property { color: #905; }
.cm-s-mdn-like .cm-qualifier { color: #690; }

.cm-s-mdn-like .cm-operator { color: #cda869; }
.cm-s-mdn-like .cm-comment { color:#777; font-weight:normal; }
.cm-s-mdn-like .cm-string { color:#07a; font-style:italic; }
.cm-s-mdn-like .cm-string-2 { color:#bd6b18; } /*?*/
.cm-s-mdn-like .cm-meta { color: #000; } /*?*/
.cm-s-mdn-like .cm-builtin { color: #9B7536; } /*?*/
.cm-s-mdn-like .cm-tag { color: #997643; }
.cm-s-mdn-like .cm-attribute { color: #d6bb6d; } /*?*/
.cm-s-mdn-like .cm-header { color: #FF6400; }
.cm-s-mdn-like .cm-hr { color: #AEAEAE; }
.cm-s-mdn-like .cm-link { color:#ad9361; font-style:italic; text-decoration:none; }
.cm-s-mdn-like .cm-error { border-bottom: 1px solid red; }

div.cm-s-mdn-like .CodeMirror-activeline-background { background: #efefff; }
div.cm-s-mdn-like span.CodeMirror-matchingbracket { outline:1px solid grey; color: inherit; }

.cm-s-mdn-like.CodeMirror { background-image: url(data:image/png;base64,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); }

/*

    Name:       seti
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original seti color scheme by Jesse Weed (https://github.com/jesseweed/seti-syntax)

*/


.cm-s-seti.CodeMirror {
  background-color: #151718 !important;
  color: #CFD2D1 !important;
  border: none;
}
.cm-s-seti .CodeMirror-gutters {
  color: #404b53;
  background-color: #0E1112;
  border: none;
}
.cm-s-seti .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-seti .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-seti.CodeMirror-focused div.CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::selection, .cm-s-seti .CodeMirror-line > span::selection, .cm-s-seti .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::-moz-selection, .cm-s-seti .CodeMirror-line > span::-moz-selection, .cm-s-seti .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti span.cm-comment { color: #41535b; }
.cm-s-seti span.cm-string, .cm-s-seti span.cm-string-2 { color: #55b5db; }
.cm-s-seti span.cm-number { color: #cd3f45; }
.cm-s-seti span.cm-variable { color: #55b5db; }
.cm-s-seti span.cm-variable-2 { color: #a074c4; }
.cm-s-seti span.cm-def { color: #55b5db; }
.cm-s-seti span.cm-keyword { color: #ff79c6; }
.cm-s-seti span.cm-operator { color: #9fca56; }
.cm-s-seti span.cm-keyword { color: #e6cd69; }
.cm-s-seti span.cm-atom { color: #cd3f45; }
.cm-s-seti span.cm-meta { color: #55b5db; }
.cm-s-seti span.cm-tag { color: #55b5db; }
.cm-s-seti span.cm-attribute { color: #9fca56; }
.cm-s-seti span.cm-qualifier { color: #9fca56; }
.cm-s-seti span.cm-property { color: #a074c4; }
.cm-s-seti span.cm-variable-3, .cm-s-seti span.cm-type { color: #9fca56; }
.cm-s-seti span.cm-builtin { color: #9fca56; }
.cm-s-seti .CodeMirror-activeline-background { background: #101213; }
.cm-s-seti .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*
Solarized theme for code-mirror
http://ethanschoonover.com/solarized
*/

/*
Solarized color palette
http://ethanschoonover.com/solarized/img/solarized-palette.png
*/

.solarized.base03 { color: #002b36; }
.solarized.base02 { color: #073642; }
.solarized.base01 { color: #586e75; }
.solarized.base00 { color: #657b83; }
.solarized.base0 { color: #839496; }
.solarized.base1 { color: #93a1a1; }
.solarized.base2 { color: #eee8d5; }
.solarized.base3  { color: #fdf6e3; }
.solarized.solar-yellow  { color: #b58900; }
.solarized.solar-orange  { color: #cb4b16; }
.solarized.solar-red { color: #dc322f; }
.solarized.solar-magenta { color: #d33682; }
.solarized.solar-violet  { color: #6c71c4; }
.solarized.solar-blue { color: #268bd2; }
.solarized.solar-cyan { color: #2aa198; }
.solarized.solar-green { color: #859900; }

/* Color scheme for code-mirror */

.cm-s-solarized {
  line-height: 1.45em;
  color-profile: sRGB;
  rendering-intent: auto;
}
.cm-s-solarized.cm-s-dark {
  color: #839496;
  background-color: #002b36;
  text-shadow: #002b36 0 1px;
}
.cm-s-solarized.cm-s-light {
  background-color: #fdf6e3;
  color: #657b83;
  text-shadow: #eee8d5 0 1px;
}

.cm-s-solarized .CodeMirror-widget {
  text-shadow: none;
}

.cm-s-solarized .cm-header { color: #586e75; }
.cm-s-solarized .cm-quote { color: #93a1a1; }

.cm-s-solarized .cm-keyword { color: #cb4b16; }
.cm-s-solarized .cm-atom { color: #d33682; }
.cm-s-solarized .cm-number { color: #d33682; }
.cm-s-solarized .cm-def { color: #2aa198; }

.cm-s-solarized .cm-variable { color: #839496; }
.cm-s-solarized .cm-variable-2 { color: #b58900; }
.cm-s-solarized .cm-variable-3, .cm-s-solarized .cm-type { color: #6c71c4; }

.cm-s-solarized .cm-property { color: #2aa198; }
.cm-s-solarized .cm-operator { color: #6c71c4; }

.cm-s-solarized .cm-comment { color: #586e75; font-style:italic; }

.cm-s-solarized .cm-string { color: #859900; }
.cm-s-solarized .cm-string-2 { color: #b58900; }

.cm-s-solarized .cm-meta { color: #859900; }
.cm-s-solarized .cm-qualifier { color: #b58900; }
.cm-s-solarized .cm-builtin { color: #d33682; }
.cm-s-solarized .cm-bracket { color: #cb4b16; }
.cm-s-solarized .CodeMirror-matchingbracket { color: #859900; }
.cm-s-solarized .CodeMirror-nonmatchingbracket { color: #dc322f; }
.cm-s-solarized .cm-tag { color: #93a1a1; }
.cm-s-solarized .cm-attribute { color: #2aa198; }
.cm-s-solarized .cm-hr {
  color: transparent;
  border-top: 1px solid #586e75;
  display: block;
}
.cm-s-solarized .cm-link { color: #93a1a1; cursor: pointer; }
.cm-s-solarized .cm-special { color: #6c71c4; }
.cm-s-solarized .cm-em {
  color: #999;
  text-decoration: underline;
  text-decoration-style: dotted;
}
.cm-s-solarized .cm-error,
.cm-s-solarized .cm-invalidchar {
  color: #586e75;
  border-bottom: 1px dotted #dc322f;
}

.cm-s-solarized.cm-s-dark div.CodeMirror-selected { background: #073642; }
.cm-s-solarized.cm-s-dark.CodeMirror ::selection { background: rgba(7, 54, 66, 0.99); }
.cm-s-solarized.cm-s-dark .CodeMirror-line::-moz-selection, .cm-s-dark .CodeMirror-line > span::-moz-selection, .cm-s-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(7, 54, 66, 0.99); }

.cm-s-solarized.cm-s-light div.CodeMirror-selected { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::selection, .cm-s-light .CodeMirror-line > span::selection, .cm-s-light .CodeMirror-line > span > span::selection { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::-moz-selection, .cm-s-ligh .CodeMirror-line > span::-moz-selection, .cm-s-ligh .CodeMirror-line > span > span::-moz-selection { background: #eee8d5; }

/* Editor styling */



/* Little shadow on the view-port of the buffer view */
.cm-s-solarized.CodeMirror {
  -moz-box-shadow: inset 7px 0 12px -6px #000;
  -webkit-box-shadow: inset 7px 0 12px -6px #000;
  box-shadow: inset 7px 0 12px -6px #000;
}

/* Remove gutter border */
.cm-s-solarized .CodeMirror-gutters {
  border-right: 0;
}

/* Gutter colors and line number styling based of color scheme (dark / light) */

/* Dark */
.cm-s-solarized.cm-s-dark .CodeMirror-gutters {
  background-color: #073642;
}

.cm-s-solarized.cm-s-dark .CodeMirror-linenumber {
  color: #586e75;
  text-shadow: #021014 0 -1px;
}

/* Light */
.cm-s-solarized.cm-s-light .CodeMirror-gutters {
  background-color: #eee8d5;
}

.cm-s-solarized.cm-s-light .CodeMirror-linenumber {
  color: #839496;
}

/* Common */
.cm-s-solarized .CodeMirror-linenumber {
  padding: 0 5px;
}
.cm-s-solarized .CodeMirror-guttermarker-subtle { color: #586e75; }
.cm-s-solarized.cm-s-dark .CodeMirror-guttermarker { color: #ddd; }
.cm-s-solarized.cm-s-light .CodeMirror-guttermarker { color: #cb4b16; }

.cm-s-solarized .CodeMirror-gutter .CodeMirror-gutter-text {
  color: #586e75;
}

/* Cursor */
.cm-s-solarized .CodeMirror-cursor { border-left: 1px solid #819090; }

/* Fat cursor */
.cm-s-solarized.cm-s-light.cm-fat-cursor .CodeMirror-cursor { background: #77ee77; }
.cm-s-solarized.cm-s-light .cm-animate-fat-cursor { background-color: #77ee77; }
.cm-s-solarized.cm-s-dark.cm-fat-cursor .CodeMirror-cursor { background: #586e75; }
.cm-s-solarized.cm-s-dark .cm-animate-fat-cursor { background-color: #586e75; }

/* Active line */
.cm-s-solarized.cm-s-dark .CodeMirror-activeline-background {
  background: rgba(255, 255, 255, 0.06);
}
.cm-s-solarized.cm-s-light .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.06);
}

.cm-s-the-matrix.CodeMirror { background: #000000; color: #00FF00; }
.cm-s-the-matrix div.CodeMirror-selected { background: #2D2D2D; }
.cm-s-the-matrix .CodeMirror-line::selection, .cm-s-the-matrix .CodeMirror-line > span::selection, .cm-s-the-matrix .CodeMirror-line > span > span::selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-line::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span > span::-moz-selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-gutters { background: #060; border-right: 2px solid #00FF00; }
.cm-s-the-matrix .CodeMirror-guttermarker { color: #0f0; }
.cm-s-the-matrix .CodeMirror-guttermarker-subtle { color: white; }
.cm-s-the-matrix .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-the-matrix .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-the-matrix span.cm-keyword { color: #008803; font-weight: bold; }
.cm-s-the-matrix span.cm-atom { color: #3FF; }
.cm-s-the-matrix span.cm-number { color: #FFB94F; }
.cm-s-the-matrix span.cm-def { color: #99C; }
.cm-s-the-matrix span.cm-variable { color: #F6C; }
.cm-s-the-matrix span.cm-variable-2 { color: #C6F; }
.cm-s-the-matrix span.cm-variable-3, .cm-s-the-matrix span.cm-type { color: #96F; }
.cm-s-the-matrix span.cm-property { color: #62FFA0; }
.cm-s-the-matrix span.cm-operator { color: #999; }
.cm-s-the-matrix span.cm-comment { color: #CCCCCC; }
.cm-s-the-matrix span.cm-string { color: #39C; }
.cm-s-the-matrix span.cm-meta { color: #C9F; }
.cm-s-the-matrix span.cm-qualifier { color: #FFF700; }
.cm-s-the-matrix span.cm-builtin { color: #30a; }
.cm-s-the-matrix span.cm-bracket { color: #cc7; }
.cm-s-the-matrix span.cm-tag { color: #FFBD40; }
.cm-s-the-matrix span.cm-attribute { color: #FFF700; }
.cm-s-the-matrix span.cm-error { color: #FF0000; }

.cm-s-the-matrix .CodeMirror-activeline-background { background: #040; }

/*
Copyright (C) 2011 by MarkLogic Corporation
Author: Mike Brevoort <mike@brevoort.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
*/
.cm-s-xq-light span.cm-keyword { line-height: 1em; font-weight: bold; color: #5A5CAD; }
.cm-s-xq-light span.cm-atom { color: #6C8CD5; }
.cm-s-xq-light span.cm-number { color: #164; }
.cm-s-xq-light span.cm-def { text-decoration:underline; }
.cm-s-xq-light span.cm-variable { color: black; }
.cm-s-xq-light span.cm-variable-2 { color:black; }
.cm-s-xq-light span.cm-variable-3, .cm-s-xq-light span.cm-type { color: black; }
.cm-s-xq-light span.cm-property {}
.cm-s-xq-light span.cm-operator {}
.cm-s-xq-light span.cm-comment { color: #0080FF; font-style: italic; }
.cm-s-xq-light span.cm-string { color: red; }
.cm-s-xq-light span.cm-meta { color: yellow; }
.cm-s-xq-light span.cm-qualifier { color: grey; }
.cm-s-xq-light span.cm-builtin { color: #7EA656; }
.cm-s-xq-light span.cm-bracket { color: #cc7; }
.cm-s-xq-light span.cm-tag { color: #3F7F7F; }
.cm-s-xq-light span.cm-attribute { color: #7F007F; }
.cm-s-xq-light span.cm-error { color: #f00; }

.cm-s-xq-light .CodeMirror-activeline-background { background: #e8f2ff; }
.cm-s-xq-light .CodeMirror-matchingbracket { outline:1px solid grey;color:black !important;background:yellow; }

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.CodeMirror {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;
  /* Changed to auto to autogrow */
}

.CodeMirror pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* This causes https://github.com/jupyter/jupyterlab/issues/522 */
/* May not cause it not because we changed it! */
.CodeMirror-lines {
  padding: var(--jp-code-padding) 0;
}

.CodeMirror-linenumber {
  padding: 0 8px;
}

.jp-CodeMirrorEditor-static {
  margin: var(--jp-code-padding);
}

.jp-CodeMirrorEditor,
.jp-CodeMirrorEditor-static {
  cursor: text;
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.CodeMirror.jp-mod-readOnly .CodeMirror-cursor {
  display: none;
}

.CodeMirror-gutters {
  border-right: 1px solid var(--jp-border-color2);
  background-color: var(--jp-layout-color0);
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.CodeMirror-selectedtext.cm-searching {
  background-color: var(--jp-search-selected-match-background-color) !important;
  color: var(--jp-search-selected-match-color) !important;
}

.cm-searching {
  background-color: var(
    --jp-search-unselected-match-background-color
  ) !important;
  color: var(--jp-search-unselected-match-color) !important;
}

.CodeMirror-focused .CodeMirror-selected {
  background-color: var(--jp-editor-selected-focused-background);
}

.CodeMirror-selected {
  background-color: var(--jp-editor-selected-background);
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/**
 * Here is our jupyter theme for CodeMirror syntax highlighting
 * This is used in our marked.js syntax highlighting and CodeMirror itself
 * The string "jupyter" is set in ../codemirror/widget.DEFAULT_CODEMIRROR_THEME
 * This came from the classic notebook, which came form highlight.js/GitHub
 */

/**
 * CodeMirror themes are handling the background/color in this way. This works
 * fine for CodeMirror editors outside the notebook, but the notebook styles
 * these things differently.
 */
.CodeMirror.cm-s-jupyter {
  background: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* In the notebook, we want this styling to be handled by its container */
.jp-CodeConsole .CodeMirror.cm-s-jupyter,
.jp-Notebook .CodeMirror.cm-s-jupyter {
  background: transparent;
}

.cm-s-jupyter .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}
.cm-s-jupyter span.cm-keyword {
  color: var(--jp-mirror-editor-keyword-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-atom {
  color: var(--jp-mirror-editor-atom-color);
}
.cm-s-jupyter span.cm-number {
  color: var(--jp-mirror-editor-number-color);
}
.cm-s-jupyter span.cm-def {
  color: var(--jp-mirror-editor-def-color);
}
.cm-s-jupyter span.cm-variable {
  color: var(--jp-mirror-editor-variable-color);
}
.cm-s-jupyter span.cm-variable-2 {
  color: var(--jp-mirror-editor-variable-2-color);
}
.cm-s-jupyter span.cm-variable-3 {
  color: var(--jp-mirror-editor-variable-3-color);
}
.cm-s-jupyter span.cm-punctuation {
  color: var(--jp-mirror-editor-punctuation-color);
}
.cm-s-jupyter span.cm-property {
  color: var(--jp-mirror-editor-property-color);
}
.cm-s-jupyter span.cm-operator {
  color: var(--jp-mirror-editor-operator-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-comment {
  color: var(--jp-mirror-editor-comment-color);
  font-style: italic;
}
.cm-s-jupyter span.cm-string {
  color: var(--jp-mirror-editor-string-color);
}
.cm-s-jupyter span.cm-string-2 {
  color: var(--jp-mirror-editor-string-2-color);
}
.cm-s-jupyter span.cm-meta {
  color: var(--jp-mirror-editor-meta-color);
}
.cm-s-jupyter span.cm-qualifier {
  color: var(--jp-mirror-editor-qualifier-color);
}
.cm-s-jupyter span.cm-builtin {
  color: var(--jp-mirror-editor-builtin-color);
}
.cm-s-jupyter span.cm-bracket {
  color: var(--jp-mirror-editor-bracket-color);
}
.cm-s-jupyter span.cm-tag {
  color: var(--jp-mirror-editor-tag-color);
}
.cm-s-jupyter span.cm-attribute {
  color: var(--jp-mirror-editor-attribute-color);
}
.cm-s-jupyter span.cm-header {
  color: var(--jp-mirror-editor-header-color);
}
.cm-s-jupyter span.cm-quote {
  color: var(--jp-mirror-editor-quote-color);
}
.cm-s-jupyter span.cm-link {
  color: var(--jp-mirror-editor-link-color);
}
.cm-s-jupyter span.cm-error {
  color: var(--jp-mirror-editor-error-color);
}
.cm-s-jupyter span.cm-hr {
  color: #999;
}

.cm-s-jupyter span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}

.cm-s-jupyter .CodeMirror-activeline-background,
.cm-s-jupyter .CodeMirror-gutter {
  background-color: var(--jp-layout-color2);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0px;
  padding: 0px;
  line-height: normal;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}
.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}
.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
}
.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
}
.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}
.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}
.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0em;
}

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: 12px;
  table-layout: fixed;
  margin-left: auto;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon table {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0px;
}

.jp-RenderedHTMLCommon p {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}
/* ...or leave it untouched if they don't */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-dark-background {
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-light-background {
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}
.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}
.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}
.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}
.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}
.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}
.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}
.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}
.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: 0.8em;
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser {
  display: flex;
  flex-direction: column;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  border-bottom: none;
  height: auto;
  margin: var(--jp-toolbar-header-margin);
  box-shadow: none;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 4px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0px 2px;
  padding: 0px 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0px;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar.jp-Toolbar {
  padding: 0px;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  justify-content: space-evenly;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-Toolbar-item {
  flex: 1;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-ToolbarButtonComponent {
  width: 100%;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px 12px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-item.jp-mod-selected {
  color: white;
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon:before {
  color: limegreen;
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0px;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-DirListing-deadSpace {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

.jp-FileDialog.jp-mod-conflict input {
  color: red;
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
}

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: flex;
  flex-direction: row;
}

.jp-OutputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-OutputArea-output {
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea-child .jp-OutputArea-output {
  flex-grow: 1;
  flex-shrink: 1;
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0px;
  padding: 0px;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0px;
  flex: 1 1 auto;
}

.jp-OutputArea-executeResult.jp-RenderedText {
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-OutputArea-stdin {
  line-height: var(--jp-code-line-height);
  padding-top: var(--jp-code-padding);
  display: flex;
}

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;
  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0px;
  bottom: 0px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0px;
  width: 100%;
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: flex;
  flex-direction: row;
}

.jp-InputArea-editor {
  flex: 1 1 auto;
}

.jp-InputArea-editor {
  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0px;
  background: var(--jp-cell-editor-background);
}

.jp-InputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: flex;
  flex-direction: row;
  flex: 1 1 auto;
}

.jp-Placeholder-prompt {
  box-sizing: border-box;
}

.jp-Placeholder-content {
  flex: 1 1 auto;
  border: none;
  background: transparent;
  height: 20px;
  box-sizing: border-box;
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0px;
  margin: 0px;
  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 200px;
  box-shadow: inset 0 0 6px 2px rgba(0, 0, 0, 0.3);
  margin-left: var(--jp-private-cell-scrolling-output-offset);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  flex: 0 0
    calc(
      var(--jp-cell-prompt-width) -
        var(--jp-private-cell-scrolling-output-offset)
    );
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  flex: 1 1 auto;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: 2px;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: flex;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0px;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-NotebookTools-tool {
  padding: 0px 12px 0 12px;
}

.jp-ActiveCellTool {
  padding: 12px;
  background-color: var(--jp-layout-color1);
  border-top: none !important;
}

.jp-ActiveCellTool .jp-InputArea-prompt {
  flex: 0 0 auto;
  padding-left: 0px;
}

.jp-ActiveCellTool .jp-InputArea-editor {
  flex: 1 1 auto;
  background: var(--jp-cell-editor-background);
  border-color: var(--jp-cell-editor-border-color);
}

.jp-ActiveCellTool .jp-InputArea-editor .CodeMirror {
  background: transparent;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0px 12px 0px;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label {
  line-height: 1.4;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

</style>

    <style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0px 2px 1px -1px var(--jp-shadow-umbra-color),
    0px 1px 1px 0px var(--jp-shadow-penumbra-color),
    0px 1px 3px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0px 3px 1px -2px var(--jp-shadow-umbra-color),
    0px 2px 2px 0px var(--jp-shadow-penumbra-color),
    0px 1px 5px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0px 2px 4px -1px var(--jp-shadow-umbra-color),
    0px 4px 5px 0px var(--jp-shadow-penumbra-color),
    0px 1px 10px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0px 3px 5px -1px var(--jp-shadow-umbra-color),
    0px 6px 10px 0px var(--jp-shadow-penumbra-color),
    0px 1px 18px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0px 5px 5px -3px var(--jp-shadow-umbra-color),
    0px 8px 10px 1px var(--jp-shadow-penumbra-color),
    0px 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0px 7px 8px -4px var(--jp-shadow-umbra-color),
    0px 12px 17px 2px var(--jp-shadow-penumbra-color),
    0px 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0px 8px 10px -5px var(--jp-shadow-umbra-color),
    0px 16px 24px 2px var(--jp-shadow-penumbra-color),
    0px 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0px 10px 13px -6px var(--jp-shadow-umbra-color),
    0px 20px 31px 3px var(--jp-shadow-penumbra-color),
    0px 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0px 11px 15px -7px var(--jp-shadow-umbra-color),
    0px 24px 38px 3px var(--jp-shadow-penumbra-color),
    0px 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;

  --jp-ui-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica,
    Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;

  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);

  --jp-content-link-color: var(--md-blue-700);

  --jp-content-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: Menlo, Consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-700);
  --jp-brand-color1: var(--md-blue-500);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);

  --jp-accent-color0: var(--md-green-700);
  --jp-accent-color1: var(--md-green-500);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-700);
  --jp-warn-color1: var(--md-orange-500);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);

  --jp-error-color0: var(--md-red-700);
  --jp-error-color1: var(--md-red-500);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);

  --jp-success-color0: var(--md-green-700);
  --jp-success-color1: var(--md-green-500);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);

  --jp-info-color0: var(--md-cyan-700);
  --jp-info-color1: var(--md-cyan-500);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;

  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;

  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);

  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: 'Source Code Pro', monospace;
  --jp-cell-prompt-letter-spacing: 0px;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);
  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;
  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0px 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-border-color1);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: #05a;
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #aa22ff;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #aa22ff;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 180px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);
}
</style>

<style type="text/css">
a.anchor-link {
   display: none;
}
.highlight  {
    margin: 0.4em;
}

/* Input area styling */
.jp-InputArea {
    overflow: hidden;
}

.jp-InputArea-editor {
    overflow: hidden;
}

@media print {
  body {
    margin: 0;
  }
}
</style>



<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-MML-AM_CHTML-full,Safe"> </script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: { 
                    automatic: true 
                    }
                },
                "HTML-CSS": {
                    linebreaks: { 
                    automatic: true 
                    }
                }
            });
        
            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
    <!-- End of mathjax configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">
<div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">from</span> <span class="nn">datetime</span> <span class="kn">import</span> <span class="n">datetime</span>
<span class="kn">from</span> <span class="nn">dateutil.relativedelta</span> <span class="kn">import</span> <span class="n">relativedelta</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">MAIN_PATH</span> <span class="o">=</span> <span class="s1">&#39;data/clients_table.txt&#39;</span>
<span class="n">clients</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="n">MAIN_PATH</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clients</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CustomerId</th>
      <th>Surname</th>
      <th>Geography</th>
      <th>Gender</th>
      <th>HasCrCard</th>
      <th>IsActiveMember</th>
      <th>EstimatedSalary</th>
      <th>application_date</th>
      <th>exit_date</th>
      <th>birth_date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>15745584</td>
      <td>EIRLS</td>
      <td>Germany</td>
      <td>Female</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.00</td>
      <td>2018-12-14</td>
      <td>NaN</td>
      <td>1997-09-18</td>
    </tr>
    <tr>
      <th>1</th>
      <td>14990118</td>
      <td>MOLOCK</td>
      <td>Italy</td>
      <td>Male</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>121219.28</td>
      <td>2019-01-08</td>
      <td>NaN</td>
      <td>1980-08-03</td>
    </tr>
    <tr>
      <th>2</th>
      <td>14733224</td>
      <td>PAWLUCH</td>
      <td>Italy</td>
      <td>Female</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>159663.59</td>
      <td>2012-08-01</td>
      <td>2013-08-09</td>
      <td>1977-08-19</td>
    </tr>
    <tr>
      <th>3</th>
      <td>14648573</td>
      <td>NALLS</td>
      <td>Spain</td>
      <td>Male</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>140827.98</td>
      <td>2019-06-19</td>
      <td>NaN</td>
      <td>1979-02-27</td>
    </tr>
    <tr>
      <th>4</th>
      <td>15365443</td>
      <td>EBERLE</td>
      <td>Italy</td>
      <td>Male</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>35521.28</td>
      <td>2014-01-26</td>
      <td>2015-12-04</td>
      <td>1972-12-21</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clients</span><span class="o">.</span><span class="n">info</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>&lt;class &#39;pandas.core.frame.DataFrame&#39;&gt;
RangeIndex: 1545000 entries, 0 to 1544999
Data columns (total 10 columns):
 #   Column            Non-Null Count    Dtype  
---  ------            --------------    -----  
 0   CustomerId        1545000 non-null  int64  
 1   Surname           1470084 non-null  object 
 2   Geography         1486541 non-null  object 
 3   Gender            1470114 non-null  object 
 4   HasCrCard         1470114 non-null  float64
 5   IsActiveMember    1470114 non-null  float64
 6   EstimatedSalary   1470114 non-null  float64
 7   application_date  1545000 non-null  object 
 8   exit_date         1054586 non-null  object 
 9   birth_date        1470114 non-null  object 
dtypes: float64(3), int64(1), object(6)
memory usage: 117.9+ MB
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clients</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">]</span>  <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">clients</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">])</span>
<span class="n">clients</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">]</span>         <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">clients</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">])</span>
<span class="n">clients</span><span class="p">[</span><span class="s1">&#39;birth_date&#39;</span><span class="p">]</span>        <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">clients</span><span class="p">[</span><span class="s1">&#39;birth_date&#39;</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">num_total_clients</span> <span class="o">=</span> <span class="n">clients</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Contracts-from-2015-onwards">Contracts from 2015 onwards<a class="anchor-link" href="#Contracts-from-2015-onwards">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">get_data_from_year</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">year</span><span class="p">):</span>
    <span class="sd">&#39;&#39;&#39;</span>
<span class="sd">    Select data from a year onwards</span>

<span class="sd">    Parameters:</span>
<span class="sd">        data (Dataframe): data source</span>
<span class="sd">        year (int)      : threshold year</span>
<span class="sd">    </span>
<span class="sd">    Returns:</span>
<span class="sd">        data (Dataframe): dataframe filtered by year  </span>

<span class="sd">    &#39;&#39;&#39;</span>
    <span class="n">data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">dt</span><span class="o">.</span><span class="n">year</span> <span class="o">&gt;=</span> <span class="n">year</span><span class="p">]</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>
    <span class="k">return</span> <span class="n">data</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Number of contrats from 2015 onwards?</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">num_clients_after</span> <span class="o">=</span> <span class="n">get_data_from_year</span><span class="p">(</span><span class="n">clients</span><span class="p">,</span> <span class="mi">2015</span><span class="p">)</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">&quot;Number of clients after filter (only by this filter): </span><span class="si">{</span><span class="n">num_clients_after</span><span class="si">}</span><span class="s2">&quot;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Number of clients after filter (only by this filter): 623242
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">pie_data</span> <span class="o">=</span> <span class="p">[</span><span class="n">num_total_clients</span> <span class="o">-</span> <span class="n">num_clients_after</span><span class="p">,</span> <span class="n">num_clients_after</span><span class="p">]</span>
<span class="n">pie_labels</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Contrats before 2015&#39;</span><span class="p">,</span> <span class="s1">&#39;Contrats from 2015 and after&#39;</span><span class="p">]</span>
<span class="n">pie_colors</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">color_palette</span><span class="p">(</span><span class="s1">&#39;pastel&#39;</span><span class="p">)[</span><span class="mi">0</span><span class="p">:</span><span class="mi">2</span><span class="p">]</span>

<span class="n">plt</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">pie_data</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="n">pie_labels</span><span class="p">,</span> <span class="n">colors</span> <span class="o">=</span> <span class="n">pie_colors</span><span class="p">,</span> <span class="n">autopct</span><span class="o">=</span><span class="s1">&#39;</span><span class="si">%.0f%%</span><span class="s1">&#39;</span><span class="p">,</span> <span class="n">textprops</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;color&#39;</span><span class="p">:</span> <span class="s1">&#39;White&#39;</span><span class="p">,</span><span class="s1">&#39;fontsize&#39;</span><span class="p">:</span><span class="mi">14</span><span class="p">})</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAaoAAADnCAYAAABPPhLwAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjMuMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/Il7ecAAAACXBIWXMAAAsTAAALEwEAmpwYAAAm80lEQVR4nO3deZwU1bn/8U/Pjs0ugiAighsgokZbUFDcQrRNosaoSa4Tzc+bmKu5JtfkmsR0YkKSm9yfMZt6Y2Iitr+oSVwTcYmiXImircENRUAQFBCUnWmGWZ/fH6cGmmaWnmFmTnX39/161Wumq6pPPdU9008/p05VRcwMERGRsCrxHYCIiEh7lKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKhERCTUlKg6dilQ0w3t7APcC2wBDBjdDW2KiBS8XBPVMOCXwDKgDlgNPAqc3c3xzAIe7sb25gI3dWN7e+MLwMnAVGA48F4vb/9bwIvAVuBD4G/AkVnrRIDrgTVALe71m5C1znXAs0Aal3BbY61MV+xl/CJSpHJJVKOBBcAM3IfdUcAZwGzgNz0WWfvKPW13bxwCLAJeB9YCTV1oowQo7eL2pwO3ACcCpwGNwJPA4Ix1/hO4BvgKcDzwAfAE0C9jnUrgfuAXHWzvX3EJuWW6o4txi0ixM7OOpkfMbLWZ9W1l2cCM30eZ2QNmti2Y7jezkRnLrzezhWZ2sZktC9Z50MyGZCzPNt3MRge/f8bMnjKzWjO7ysz2NbO7zWxVMO8NM7ssY3uzWmlvtJmVm9mvzGyNmdWZ2Xtm9pN29v9SM6sxs4+b2RIz22FmT5vZmKz1Pm5m/wyWv2NmPzKzimDZ3Kw45gbzB5nZHWa2KdiHJ81sQivbPjt47RrN7Mig3Z8G+77dzF40sxnt7ENrU18zawrixswiZva+mV2XsU4fc+/Tl1p5/gXBvrTWtgXLOxOPJk2aNLU6dVRRDQY+BtxM68dpNgc/S4CHcF2EpwbTCOBBXHdSi9HARcB5wEeBY4AfBctuAP6M+5bf8i38uYzn/heuIhgftFuFq/TOwXVP/RK4FTg9WP9qYD5we0Z77wH/Hmz/YuDQIJ7FHbwOlcD3gMuAKbiq5v6MfZsB/BHXzTgB1813AfDjYPn5QRzzgzjOD+bPAk4APgnEgO3AY0CfjG1XAQngS8G+rwzaOgX4LK777g5cV96kDvYjUz/c+7YpeHwwsD/w94x1aoFncFVYZ/0SWI/rbrwCHQ8Vka7qIJPFzDmvg/XONPftfHTGvDFm1mxmZwSPrzdXbQzIWOc6M3s74/EsM3s4q+3RQQzX5JB57zGz2zIezzWzm7LW+ZWZzTFXQeSSzS8Ntn9SxryDgv1t2bdnzCyR9bxzzVVDLdu5yXZVUpjZoUG7J2fMG2BmW8zs8qxtfyRjnbHB6zoqa3sPmtktOe4TZvZnM3vZzEqDxycG28pu9w9m9ngrz2+vokqY2VQzOzp439Jm9p1OxKZJkyZNO6eyDvJYpIPlLcbhDsCvyJi3PJg3HlclgasGtmSsswYYmuM2Xsp6XAp8E1cRHYCreipwAwDaMwt33GUJrnp4BDcwpLmd5zQDqYzHK9l93z6Cq4iuzVinBFcZ7Q+830qb44J252fM24I7hjU+Y14j8ErG42Nx78ubWe1VAk+1sw+ZbsQN6phK146VdWRmxu+v4N6r64Af9sC2RKTAdZSoluJGbI0DHujiNjJHhjW0sizXLqF01uOv4w78X437cK/BdbV1lPgW4LogZ+C6Ce8AXgXOpP1k1dYIN3D78H3gL60s+7CDeDraVh27J5OSYPnx7Pl61ubQ9s9x3Z6n4r5MtFgb/BwGvJsxf1jGsq56AegftLVuL9sSkSLTUZLYCDwOXAX0bWX5wODnItwxqdEZy8YE87K/+benntxHtU3FHZe5E/etfRlwWI7tbcOd0/RlII4bBXdIO9sqwVVMLUbh9m1R8HgBcATwditTYxttLgranZIxrz8wkfZfs5dxFdX+rWxrdTvPA3fc6DO4/X0ra9k7uIR0Zsa8KmAaux8r7IqjgR3sOqYpIpKzjioqgCtx5828hDuo/xrug/JU3HD1Ubjur9dwAwquDp73a9wHeK7dUeC6Ds8CDgc2sHs3YbYluG6/qbiD9l/BDQh4Oau9GC6B1uAS71dxXXGv4CqSz+LOLVrVzrYaccOxr8ZVLT8H3mBXl+YPcOd/rcQNCGnEDXKI4YZ8t2YpbgDKrcAXcR/iPwpiuauD/f4jrgvzGtxrPBg3/Hw5bpBHa24GLgHOxQ2g2D+YXxNMFuzjt3FJbAnwnWBZZjyjgu2NDh4fHfx8O1j340Hb83Gv1am41+e3uOpQRKRTcklUy3HHRb4N/BR3PGgDrrvsi8E6hhu59ivg6WDek7jk0V6XWbbf4T5wX8JVcKey+3GvTD/EJaZHcR+Is3Af4JnHd27Ade29iTtedDCumvoGbsSf4RLbWbgRd22pwyWRJO6D+nncyL2WfXscV5klcF2SjbgP+lkd7O9luOTwV1z18ixulGVHXXiX4Y75/DcwEpeAU+x67Vvzb8HPOVnzv487yZegvT64pDYI12X3Udxr1uIHwOczHrd8MTgVd3ywIdjWjbiKcTnw3aDNbpFMpQ8GxuISZuY0qJXHfXDdxtvYlZRrsh5vwyXvZbgvEMurY9G2KmER6WURs87kEZHek0yly3HD/Y/OmCaxq8u5pzTiviAtxvUUvBJMS6tjUf3DiPQyJSoJjWQqPQl3ftgxuKQ0HjeSMyxqcBXk48Aj1bHoyx2sLyLdQIlKvEmm0lHc5bjiuO7XkX4j6rQ1uK7nR4AnqmPRbR2sLyJdoEQlvSqZSvfHHc/8NO74V6XfiLpNAzAPl7QeqY5FF3WwvojkSIlKelwyla4APoU7f2sGhZOc2vMm7pJfd1THot1xmxiRoqVEJT0mmUoPxp2rdiXuGofFaCtutOhN1bFoR9eUFJFWKFFJt0um0ocCX8MNY9/HczhhYbhTA24C/lYdi7Z3FRQRyaBEJd0mmUqfjDsJ+Rx0tfT2rMDdy+226lh0g+dYREJPiUr2SjKVLgUuBP4DOM5zOPkmjTvJ+v9Wx6K5XKdRpCgpUUmXJVPpE3FXnDjacyj57j3c5cju0gnFIntSopJOS6bSw3CVwCXkfisY6dgLwNeqY9H5Ha4pUkSUqCRnyVS6DHcl/euBAX6jKWj3ANdWx6LvdrimSBFQopKcBAMlbsLdhkR63g7gZ8BPdB6WFDslKmlXMpUejrsK/Wd9x1Kk3gOqq2PRub4DEfFFiUralEylzwf+gLr5fGvGVVffqY5F630HI9LblKhkD8GxqJ/ihpxLeLwMfE7XEZRio0Qlu0mm0iOAP+HunCzhsx34cnUsmvQdiEhvUaKSnZKp9GnA3cBQ37FIh24DvlIdi+7wHYhIT1OiEpKpdAT4Nu629KWew5HcvQxcUB2LLvcdiEhPUqIqcsEVzu8EzvYdi3TJJiCuk4SlkClRFbHgKuePAwf7jkX2Sho4rzoWfcJ3ICI9QVe4LlLJVHoS7o60SlL5Lwo8nEylP+U7EJGeoERVhJKp9BRgLjDMcyjSfSqAPyVT6S/4DkSkuylRFZlkKn0G8AQw0HMo0v1KgduSqbTOf5OCokRVRJKp9JnA33BdRVKYIsDPkqn0TN+BiHQXDaYoEslU+nRckurjOxbpNTcB/657XEm+U0VVBJKp9KnAX1GSKjZX4S4oLJLXVFEVuGQqHQOeQt19xexL1bHob30HIdJVSlQFLLhFx0vACN+xiFeNwFnVseiTvgMR6QolqgKVTKUrcUPQJ3sORcJhMzClOhZ9y3cgIp2lY1SF6xaUpGSXgcDsZCo9xHcgIp2liqoAJVPprwC/8h1Ha/qURzj2wHIOGFBGeSlsqzNeWFHHum3NO9eZdEA5h+5XRkVZhPU1zbywso4tte7vtCQCUw6u5MBBpexocM99f+uu5x4xrIz9+pYyb1ldr+9bnvgHcLpuwCj5RBVVgQlG+N3oO47WlJfCx8ZVATBnyQ4eeq2W1Mo6djTs+rI0YXg54/cvJ7WynkfeqGVHg3Hm4VWUBX+phw0tY99oCY++WcuSDxqYOrZq53P3qYgwfv9yXlypJNWOqbhbhIjkDSWqApJMpUcDfwbKPIfSqiOHl1PbYDy7vJ4N6WZq6o21W5vZsmNXoho3rIyFaxp4d1MTm2uNZ5fXUV4a4eB93S4NqCph1aZGttQai9c10qc8QmWwtyccVMGrqxvY0ehj7/LKJclU+jrfQYjkSomqQCRT6SjwIBDaYxAHDipjfbqZk8dW8ulj9uGcCVUcPnRXTu1bGWGfihLWbG3aOa/JYN22Job2c3+qG7c3M7RfKaURGDGglO31zdQ1wkGDSykribBsvbJUjr6fTKVP8B2ESC6UqArHzcAk30G0p19lhMOHlrGtrpk5i3ewaF0jxx5YsTNZ9SmPAOzWFdjyuGXZ2+sb2bi9mU8c1YeJI8p55u06ykvh2JEVPL+ijqNGlHPuUX2YcUQV/asivbuD+aUUuD0YHSoSaqHsIpLOCa7h93nfceRiQ7qZl1c1AK466l8V4fBh5Sz+ILdKyAxSK+th5a55U0ZXsPTDRvr3KWH0vmU8vLCWg/ctY+qYSh55U3dqb8c43F2dv+k7EJH2qKLKc8lUug/wG99x5KK2wdhS27zbvC21RrQisnM5QFX57pVQVXlk57Jsw/qVsG+0hDfeb2B4/1JWb26ksRne2dDIkL6lOwdhSJu+nkylj/cdhEh79G+c/64HxvgOIhcf1jTTv8/uf3L9qyKk610Sqqkzttc3M7x/6c7lJREY2q+UD7btnuBalp0wupL5K+ppSWORSGTnMve4+/ejwKgLUEJPiSqPBXfpzZt7D725toH9oiVMHF5Ov8oIBw0q5Yhh5Sxe17BznUXrGjlyeDmjBpUysE+Ek8ZU0thkvLNhz67Bo0aUs2ZLExvSLol9sK2JgwaVMmifEiYML2fT9mYamvZ4muxpAvBd30GItEUn/OapZCpdAjwP5FW3zQEDSjnmwHIGVJWQrjfeWtfAW+t2T0ItJ/xWlkX4sKaZ1Mo6Ntfu/nc6sE+E6YdW8fDCWhoziq3jR1UwZkgZ2+vd0PaN2/esxKRVjcDk6lj0n74DEcmmRJWnkqn01cAvfMchBeV14DhdtULCRl1/eSiZSh8I/NB3HFJwJgJf9x2ESDYlqvx0M9DXdxBSkK5NptL7+g5CJJMSVZ5JptLTgI/7jkMKVn/gW76DEMmkRJV/dI026WlXJlPpkb6DEGmhRJVHkqn0ccAM33FIwasCvuc7CJEWSlT55du+A5CicWkylT7IdxAioESVN5Kp9ATgXN9xSNEoA671HYQIKFHlk28BuiCQ9KYvJFPp4b6DEFGiygPJVHoscLHvOKToVALX+A5CRIkqP1yLu3ioSG+7IplK9/cdhBQ3JaqQS6bSB5An95qSghQFPu07CCluSlThdwVQ4TsIKWrVvgOQ4qaL0oZYMpWOAMuB0Z5DkeJmwJjqWHSF70CkOKmiCrdpKEmJfxHgX3wHIcVLiSrcLvEdgEhAf4vijbr+QiqZSlcBa4EBvmMRCUypjkWf9x2EFB9VVOE1AyUpCRcNqhAvlKjC63zfAYhkuSiZSmsEqvQ6JaoQSqbSZeieUxI+g4G47yCk+ChRhdOpwCDfQYi0Ql+gpNcpUYXTeb4DEGnDNN8BSPFRogqnU3wHINKGQ5Kp9P6+g5DiokQVMslUegAwznccIu1QVSW9SokqfI5H952ScFOikl6lRBU+k30HINIBJSrpVUpU4XOC7wBEOnBU0EUt0iuUqMJHiUrCrgQ40XcQUjyUqEIkmUqPAfbzHYdIDtT9J71GiSpcVE1JvlCikl6jRBUuSlSSL8b7DkCKhxJVuMR8ByCSo8HJVDrqOwgpDkpU4XKw7wBEOmGU7wCkOChRhUQylS5BAykkvyhRSa9QogqPoUCp7yBEOkGJSnqFElV4DPcdgEgnHeQ7ACkOSlThoStSS75RRSW9QokqPFRRSb5RopJeoUQVHqqoJN8oUUmvUKIKD1VUkm9GBqNVRXqU/sjCQ4lK8k05oJN+pccpUYXHMN8BiHRBue8ApPApUYVHhe8ARLpAiUp6nBJVeNT7DkCkC5SopMcpUYVHg+8ARLpAiUp6XJnvAGQnVVTdzax5Ss0T8w7ZsXA8ujxVj2iMlAPf9B2GFDglqvBQRdWN+jVtWnX2prs3VNqOU3zHUsjKraHZdwxS+JSowkOJqpsclZ7/j0nb50+KwEjfsRSBJt8BSOFTogoPdf3tpcrm7RvO3nTX0n7NW6f6jqWI6AuW9DglqvDQP/xeGLPjjRdP2vb30RFssu9YisxG3wFI4VOiCg9VVF1QZvXpj26+d8GQxrXTfMdShLYQT+gLlvQ4Jarw0D98Jw2vX/n6aVse6F9Ks5KUH+t9ByDFQYkqPNSFkqOINTWcsvXhZw+sXzYtomHnPn3oOwApDkpU4fGu7wDywaDGD5Z9bNOf6stpmO47FlFFJb1DiSo8VvoOINTMLFbz9LzDd7wSi0CV73AEUEUlvUSJKjxUUbVhn6at78c33fV+H9t+su9YZDdrfQcgxUGJKjxUUbVi/PaXnvtI+pnxETjWdyyyh8W+A5DioIvShkR1LFoDfOA7jrCoaK7d/MmNtz93XPqZEyMw0Hc80qq3fAcgxUEVVbgsAob6DsK3g+qWLJi2dfbwEuxE37FIuxb5DkCKgxJVuCwCivYiqqXWUHvGlvtfHNqweloEIr7jkXatIZ7Y6jsIKQ5KVOFStF0pQxtWLTpz830VpTRpwER+UDUlvUaJKlyK7p8/Ys1NJ217bN7BdW+dFNFN+PJJ0f2tij9KVOGyADCKpNtrQOOGlWdtvntbhdVP9x2LdNqrvgOQ4qFRfyFSHYuuB17zHUdvOKZm3rxPbLpjSIXVH+k7FumSZ3wHIMVDFVX4zAEm+Q6ip/Rpqvng7M13rYw21+hCsvlrLfHEEt9BSPFQRRU+c3wH0FMOq331+Qs2/rY02lxzvO9YZK/M8x2AFBdVVOHzDO6WHwUzsKC8uW7rjM1/em1w03rdebcwqNtPepUqqpAJrlCR8h1HdzmgbvmrF224ZauSVEFRopJepYoqnOYAJ/kOYm+UWFP9qVsenD+iYeW0iL4QFZKNwOu+g5DiokQVTnOA7/oOoqv2bXh/6YzNf7EyGov2KhsF7FHiCfMdhBQXJapweh7YDuzjO5BOMWueUvPEvEN2LJwSgQrf4UiPuNd3AFJ81CUTQtWxaD15NrKqb9PmVRdt+J/XD92x8BQlqYJVAzzmOwgpPqqowus+YIbvIHJxVPr5Zydtf25iBEb6jkV61CPEEzt8ByHFR4kqvO4GbgT6+g6kLZXN2zecvenupf2at+T1wA/Jmbr9xAt1/YVUMEz9z77jaMuYHW+8eOGGW5v6NW+Z7DsW6RXbgUd8ByHFSRVVuP0O+ILvIDKVWX36zM33Ltivca0ugVRcHiaeSPsOQoqTKqoQq45FnwcW+o6jxf71KxdetP6W9UpSRel/fAcgxUsVVfj9Hvi5zwAi1tRwytbZzx5Y//a0CJT6jEW8eIN4Yq7vIKR4KVGF353AT4BKHxsf2Pjh8rM231NXbg3TfWxfQuEW3wFIcVPXX8hVx6IbgAd7fcNmdnzN0898fNOdw8utYVyvb1/CYhvuy5KIN6qo8sNtwEW9tbF9mra+H9901/t9bPvJvbVNCa0k8cQ230FIcVOiyg9zgMXA4T29oXHb//nccen/HR+BY3t6WxJ6hrr9JAQiZrq+ZD5IptIXAn/qqfYrmms3n7X5njcHNG06sae2IXnnPuKJC3wHIaJjVPnjL8A/e6Lhg+qWLLhww29qlaQkQzN5fAV/KSyqqPJIMpU+E/h7d7VXag21Z2y5/8WhDaunRSDSXe1KQbiLeOJzvoMQAVVUeaU6Fn0Cd7xqrw1tWLXo4vW3rBnWsPpkJSnJ0gRc7zsIkRYaTJF/vsVe3Ko+Ys1NJ2177B8H1711YgTKuzEuKRxJ4omlvoMQaaGKKs9Ux6Iv4m4B0mkDGjesvGjDLW+OqXvrFCUpaUM98APfQYhkUqLKT9fhumdydkzNvHmf2HTHkAqrn9hDMUlh+BnxxArfQYhkUqLKQ9Wx6GLg9lzW7dNU8+GnNvz2xYm1L06LQLSHQ5P89g4w03cQItl0jCp/XQ9cCPRva4XDal99/oSaOYdG4PheiypfjD0JjjgNVrwIb2TcXf3Qk2HUsVBeBZtXw8LHoOZDt6ykFCaeA8MOh7oaWPgobHhn13NHHw8DR8IrD/TuvnSfK4knan0HIZJNFVWeqo5FVwPfaG1ZeXPd1nM2Jp+dXDNncgT27eXQwm/gATDqGNi6bvf5Y06EMZNd4vrH76FuO5zwOSitcMtHHQsDhsNzt8N7C+CY83Y9t6o/HDwZ3ny89/aje91LPPGo7yBEWqNElceqY9HfAk9kzjugbvmrF234n62Dm9br9vCtKauEo8+F1/4GDVnFw8ExWPYcrH3LVVGvPgRlFXDAkW553yGwbolbtuIlqIxCxT5u2ZFnwdL/hfrtvbo73WQbcLXvIETaokSV/y4HtpZYU/3pm++fe9rWByeW0DzSd1ChNTHuEtGGlbvP7zMQqvrBh8t2zWtuhI3vwqDg5dy6DgYfCCVlsN9Y2LHNJabh46G0DFa91mu70c2+QzyxxncQIm3RMao8Vx2Lvjv72WVXzdj85++U0TjddzyhduAxEB0Mrzy457Kqvu5nXdbd1uvSLoEBvPcK9BsKp1wB9bWw4D5XoR1xGrzwR3d8a8SR7vjV67MhvaEn96a7zAF+7TsIkfaooioA8ZPG3llG4yLfcYRadF84/FR4+QGw5q61Yc3u+NXTN8Gzv4dN78G4M+DdBa5bcPh4+MdtsPp1170YfhuAauIJXUdNQk0VVeG4HIgBw30HEkqDDnDHlE6+Yte8khIYfBCM+gg88xs3rzIKO7buWqcy6iqk1gweBQNGwMJH4Igz4IOl0FQPaxbCUee4QRhN9T23T3vvcnX5ST5QoioU8cR6Zs+sBh4DSn2HEzprF8Pm3+w+b9InIL0R3v6H66bbsQ2GjIEt77vlJaUwaBS89eSe7ZWUwpFnuwEXZhCJQCR42Xf+DPUlFH9JPPGg7yBEcqGuv0ISTzwJXOs7jFBqrHOj9TKnpno38q/lPKl3UjD2RNj/COi7H0z6pFtn9cI92ztkmht40ZLUNr7nntd/GIydAts+cNsMpxdo49QGkTBSoio08cTPgDt8h5GXlj8H77wAEz4GUy+Hyr5ukER2913f/WDEeFgyd9e8tYvcaMLJl8Cww+CVh3o19E5YB1xIPNHgOxCRXOl+VIVo9sxKYC4w2XMkEi7bgenEEy/6DkSkM1RRFaJ4og44D1jtOxQJjWbgs0pSko+UqApVPLEWOBfQtdsE4BriidD2R4q0R4mqkMUTLwHn4+4xJMXr18QTv/AdhEhXKVEVunjiMeAioNF3KOLFA8BXfQchsjeUqIqBO1/mEtxxCikeDwAXEU/ofZe8pkRVLOKJe4D/A2iYZ3G4Fw1DlwKhRFVM4olZwJUoWRW6PwGfIZ5Qd68UBJ1HVYxmz/wX4A9Aue9QpNvdhbvQbJPvQES6ixJVsZo98wzgPtq5lb3knd8BV+iYlBQaJapiNnvmJOARYITvUGSvNAPfIJ640XcgIj1BiarYzZ45CnfF9XG+Q5EuqcEdj3rYdyAiPUWDKYpdPPEucBLwuO9QpNPce6ckJQVOiUogntgEnAUkAB2Ezw/zgRjxxGu+AxHpaer6k93NnjkduBvY33Mk0rpm4KfA93SOlBQLJSrZ0+yZw3DDnE/zHYrsZhVwCfHEXN+BiPQmdf3JnuKJdcCZwHfRBW3D4l7gKCUpKUaqqKR9s2dOwJ2fM8V3KEVqG/BV4ok/+A5ExBdVVNK+eOINYCpwFe5DU3rPPcARSlJS7FRRSe5mzxwJ3AJ83HcoBe5N4Criiad9ByISBkpU0nmzZ34C+C9gvO9QCkwN8APgFxrRJ7KLEpV0zeyZJUA18H1glOdo8l0DcAdwPfHEat/BiISNEpXsndkzK4F/A74NDPEcTb5pAGYBPyaeWOE3FJHwUqKS7jF7Zj/gatz9rnSycPtaEtSPiCdWeo5FJPSUqKR7zZ5ZAVyIS1rHeY4mbDYBSeDnSlAiuVOikp4ze+ZJuIR1PlDqORqfngNuBf5CPFHrOxiRfKNEJT3PDWu/BPgXimek4Bbg/wG3Ek+87jsYkXymRCW9a/bMo4GLgQuAsX6D6XZbgb/hLnf0GPHEDs/xiBQEJSrxxyWtT+IufjsZqPAaT9esAB4OpqeJJ3RtRJFupkQl4TB7Zh/cDRxPxSWu44AyrzHtyXBXjXgumJ4lnljqNySRwqdEJeHkhrsfAxwJTAx+HgkM7KUI6oDlwFLgNVximk88sbmXtl8oPgncAByMO2Z3qddoittCXLf09XvRxj64katnAv1x7+uKvQ2sI0pUkl/cwIwJwIG487X2B4Zl/D4U14VYhhtpGMlqoR7YjBsqnjl9iEtKS4ElwLvEE83dEPEw3MnQ5wAjgfW4xPdr4JFuaL/FLNwJ1+d0U3tzcR9sV+1lO+uB23D7W4MbZOLTJOCbuAstDwHeBX6PS6aZ7/dE4CYgBmzEjdqciauqwf0Nfh84Fvdh/X32TADXA9/LmrcOf+cZdkeiugp3+5/Tcf8zUeBt4Hjgpb2Mr01h61oRaV88sQp3A8HczJ4ZYVfSopcHOIwGnsVddf5bwKu4OxacDvwGP5eeKsedcNwbBgL7Ao8DbV0aqgT3ZaKpl2L6CO4D9hJckorhbmNTBvw4WKc/8ATwDO4D+AjgdiAN/CxYZx9cJXE/8MN2trcYmJ7xuLf2s6ccAiwCWkayju7Gtito6/53ZqZJk6aemR4xs9Vm1reVZQMzfh9lZg+Y2bZgut/MRmYsv97MFprZxWa2LFjnQTMbkrE823QzGx38/hkze8rMas3sKjPb18zuNrNVwbw3zOyyjO3NaqW90WZWbma/MrM1ZlZnZu+Z2U/a2PfpbcR0qZnVmNnZwT41mtmRZjbIzO4ws01BTE+a2YSM9lqed5aZvWVm283sr2Y2wMwuMLOlZrbFzO40sz5txNTW9N9m9s+Mx182s61Z7XzH3HsZaeX5C829B9nzW963zsTS0XuDmc01s1vM7Mdmtt7MPjCzG8ysJGOdoWb2UNDGSjP7Qjtxtkxjg+esNbO0mS0ws3Oytpsp+3HLvJb1LzOzN81sh5ktMbOvZcVoZnalub/3dLAPrcam+1GJ9IzBwMeAm3FdXtk2Bz9LgIdwXYSnBtMI4EF277YcDVwEnAd8FHf87kfBshuAPwNPAsOD6bmM5/4X7vYs44N2q4AFuG7CCcAvcV1bpwfrXw3Mx1URLe29B/x7sP2LgUODeBa3sf/PBW0DfCorpiogAXwpiGklruvyBNwxrRiwHXgM6JPRZiVwDfC5INbjgPuAzwfbODfYp39rI6a29Md1/7aYAswDMk/Ofhz3vozuZNtjgDXAO7j7i43pYP2O3psWnwMagRNx3XFfxb0fLWbhqp8zcK9LdQ6x9wUexR1/moR7be/HVZTgTty/Hfe3MTx4HAuWfSxjHsC/4irU7wLjcO/btez53nwP1wU+Efe/0rpOZntNmjTlNsXMOa+D9c40syZzFUvLvDFm1mxmZwSPrzf3rXRAxjrXmdnbGY9nmdnDWW2PDmK4Jod47zGz2zIezzWzm7LW+ZWZzbHWq4rWpiHB9qdnzLs0mPeRjHmHBvNOzpg3wFyFdHnW8w7PWOeG4LUbkjGvtdehvenY4LX9VMa8v5vZH7LWGxVsf0orbbRVqZxlZhea2VHm3su55qqVfTsRX1vvzfysdZ7IWOewINaTMpYfFLxWrcXZ3vS8uWqy5fFNtnvV1PI3dlzW8941s0uy5n3VXIXV8tjM7Ne5xKGKSqRnZA/iaMs43DfuFRnzlgfzMq/isZLdByKswQ0cyUX2Qe5S4DrcoI4NuIrvfDo+ZjYLOBo32ORmIE7X7hLeCLyS8XgcbiDD/Ix5W3DHQTJfgzp2r+DWAWtxAzYy5+X6uhwOzAZ+gaseutujuEr3NVy1ew7u9fp8O8/J9b15Letx5t9Dy+uZyli+MlinPVHgv3GnYGwKtn1cK9vuyH64wU63Bm20TD9hz5P8cxqAocEUIj1jKW6E2DjggS62kTkkN3sAhJF7kkhnPf46rivmalwyqMF103T0Ab8A1300A9cVdQdugMiZ7D5iriN15D6oIPM1aGxlWVdflyOAp3Hdcd/MWrYW1xWbaVjGsq6qAd7AdZu2Jdf3Jpf97uyQ7htwXXhfx/39bscNRe/sifgtcVzB7l3Qrcn+22y3QRHpXhtxxzWuwvX9ZxsY/FzEnsc+xgTz3uzE9urJ/cK/U3GXeroTV9ksAw7Lsb1tuCHOX8ZVVKfhjoXsjUW4z6IpGfP6445bdOY1yNV43PD7vwBfa2X5fGAa7nhRizPZs/LtrCpcgny/nXVyeW868hbu9YxlzBuF+5tqz1RcYroPV7GtouPLnLWM0sv8W1mHe63G4oauZ0+dpkQl0nOuxHUBvgR8GtfVdATuQ76l6+bJ4Pc/4rpZjgt+XwA81YltrcCdEH047vyg8nbWXYKriKYG8dyEOxcou70YLoEOwX1W/AfwGVyVeAjwWdz1DXM/XaB1S3EDSm7FJYiJuJODtwJ37WXb2SbgKqm5uEpl/4ypxV24amIW7jU9H1d13ciuKqUC1w16NC4B7R/8npm0bwBOwb22J+ASfBRXibYll/emI4txA1FuxSX/o4N96ejK/Utwg2WOZdd7UNXuM+CDoN0ZuKpzQDD/e8B/4r4IHI57Hatxp2l0mhKVSM9ZjvunfwL4KS4hPQV8AvhisI7hRrp9iPsAfRrXvXQuneu6+R2uMnkpaOukdtb9Ie74xaO4c4XSuOSY6Qbct+U3g/ZG4aqpbwTPXYD7ADwL96G+ty4L2v1r8HMfXDdUd98W5dO4brSLcJVN5tRiC66CGoF7PW/GnT91Y8Y6I4CXg2ksbgTjy7iTm1uMBO7GJY77cV2ek3HHi9qSy3uTi0txIw2fwlVod9FxNfgfuMQzL9j+88Hv7WnEjQa9HFdFPRTMvw34Au58tVeDdr4YxNRpujKFiIiEmioqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJNSUqEREJtf8P0IohKFkzP80AAAAASUVORK5CYII="
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Operations-in-Italy-were-closed-this-year-(2019)">Operations in Italy were closed this year (2019)<a class="anchor-link" href="#Operations-in-Italy-were-closed-this-year-(2019)">&#182;</a></h3>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>As the product will no longer be offered in Italy, this market will no longer be relevant for the analysis.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">dismiss_country</span><span class="p">(</span><span class="n">data</span><span class="p">,</span><span class="n">country</span><span class="p">):</span>
    <span class="sd">&#39;&#39;&#39;</span>
<span class="sd">    Select data from a country</span>

<span class="sd">    Parameters:</span>
<span class="sd">        data (Dataframe): data source</span>
<span class="sd">        country (str)   : desired country</span>
<span class="sd">    </span>
<span class="sd">    Returns:</span>
<span class="sd">        data (Dataframe): dataframe filtered by country  </span>

<span class="sd">    &#39;&#39;&#39;</span>
    <span class="n">data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">data</span><span class="o">.</span><span class="n">Geography</span> <span class="o">!=</span> <span class="n">country</span><span class="p">]</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>
    <span class="k">return</span> <span class="n">data</span> 
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">num_clients_after</span> <span class="o">=</span> <span class="n">dismiss_country</span><span class="p">(</span><span class="n">clients</span><span class="p">,</span> <span class="s1">&#39;Italy&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">&quot;Number of clients after filter (only by this filter): </span><span class="si">{</span><span class="n">num_clients_after</span><span class="si">}</span><span class="s2">&quot;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Number of clients after filter (only by this filter): 1205906
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ax</span> <span class="o">=</span> <span class="n">clients</span><span class="p">[</span><span class="s1">&#39;Geography&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;tan&#39;</span><span class="p">,</span> <span class="s1">&#39;tan&#39;</span><span class="p">,</span> <span class="s1">&#39;tan&#39;</span><span class="p">,</span> <span class="s1">&#39;maroon&#39;</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Clients per country&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAYkAAAEsCAYAAAA2DE/gAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjMuMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/Il7ecAAAACXBIWXMAAAsTAAALEwEAmpwYAAAguElEQVR4nO3de7xcdX3u8c9jQhClIQG2OZREEzVWI0qUCPFlLxQqBNQGW7TQSqKlpj2ArdWq4LEHVDheepBKRdpoIgGrIeKFVGNjCqjltEA2gkCgHHZBSNJAtgkEFAETnv6xflsnm1n7lp2ZzM7zfr3mtdd81+07A5ln1nVkm4iIiGae1e4GIiJiz5WQiIiIWgmJiIiolZCIiIhaCYmIiKiVkIiIiFoJiegYks6T9MUy/HxJP5E0rt19RYxlCYnYo0j6Q0ndJQA2Sfq2pF/vP53tB2zvb3vHKKzzu5L+ZFeXM1ZI+pGk32l3H7FnSEjEHkPSe4C/Bf4PMAV4PvBZYH4b22oJVTri36Ok8e3uIVqnI/6njLFP0gHAR4AzbX/N9k9t/9z2P9l+X5Ppp0ty3weWpAMkLSlbHxslnd+3K0rS2yVdL+n/SnpY0n2STijjLgB+A/hM2Xr5TPnAvkjSZkmPSrpd0mE1fX9X0sck3VSmvVrSgQ3j50r6N0mPSPqhpKP7zXuBpP8HPA68sMnyp0n6mqReSVskfabUnyXpQ5LuL31eXt5DJB0taUO/5fxi66DstltR5nlM0jpJc8q4K6jC+Z/K+/H+hvf6dEkPANdK+pakd/Vbx22S3jzAf+boQAmJ2FO8Fng28PURzn8ZsB14MfAq4DigcRfSUcDdwMHAJ4ElkmT7fwH/CpxVdl+dVeb9TeAlwAHAW4EtA6x7AfDHwCGlh4sBJB0KfAs4HzgQ+Cvgq5K6GuY9DVgE/Apwf+NCS8h9s9SnA4cCy8vot5fHb1OFy/7AZwbosb/fLcuaBKzsm9f2acADwJvK+/HJhnl+C3gZcDywDHhbQ6+Hl/6+NYweogMkJGJPcRDwY9vbhzujpCnAicC7yxbIZuAi4JSGye63/blyDGMZ1Qf6lJpF/pzqQ/ulgGzfZXvTAC1cYfsO2z8F/hp4a/mAfxuwyvYq20/bXgN0l177XGZ7ne3ttn/eb7lHAr8KvK+8ridsX1/G/RHwKdv32v4JcA5wyjB2BV1f+toBXAEcPoR5zit9/IwqWF4iaWYZdxpwpe2nhrj+6BAJidhTbAEOHuH+7hcA+wCbym6dR4B/AJ7XMM2DfQO2Hy+D+zdbmO1rqb5ZXwJslrRY0sQB1r++Yfj+0svBpa+39PVU+vp1qoBqNm9/06jCrVlw/io7b3ncD4ynPvj6e7Bh+HHg2UN473/Rq+0ngCuBt5VjKadShU2MMQmJ2FP8O/AkcNII5l1f5j3Y9qTymGj75UOc/xm3QrZ9se0jgFlUu52ecVykwbSG4edTbYn8uPR1RUNPk2w/1/bHB1p3v9f1/JoP7/+iCqHG9W4HHgJ+Cjynb0TZquli6Op66l9fRrVFcyzwuO1/H8Y6okMkJGKPYHsb8L+BSySdJOk5kvaRdIKkTw4y7ybgO8CFkiaWg7ovkvRbQ1z9QzQcNJb0GklHSdqH6gP3CeDpAeZ/m6RZkp5DdfD9qrIb54vAmyQdL2mcpGeXg8pTh9jXTcAm4OOSnlvmf10Z92XgLyXNkLQ/1RlhV5atjv9PtWXwhvIaPgTsO8R1Qr/3o04JhaeBC8lWxJiVkIg9hu0LgfdQfaj1Un2TPgv4xhBmXwBMAO4EHgauYufdOgP5NHByOfPpYmAi8LmynPupdoX9zQDzX0F14PxBqoPvf15ez3qq03c/2PB63scQ/92VoHkT1cH4B4ANwB+U0UvLer8P3EcVZO8q820DzgA+D2ykCrqdznYaxMeAD5VdZH81yLSXA6+gCsQYg5QfHYoYOUnfBb5o+/Pt7qUdJC0AFtl+xgWPMTZkSyIiRqTsXjsDWNzuXmL3SUhExLBJOp5qF9pDwJfa3E7sRtndFBERtYa8JVHOzrhF0jfL8xmSbpTUI+lKSRNKfd/yvKeMn96wjHNK/e7yTaSvPq/UeiSd3VBvuo6IiGiNIW9JqLr52hxgou03SloBfM32ckl/D/zQ9qWSzgBeafvPJJ0CvNn2H0iaRXXaXt9VpP9Cdf45VKfsvZ7qDIy1wKm276xbx0B9HnzwwZ4+ffrw3oWIiL3czTff/GPbz7ieZkhXt5bzut8AXAC8R5KAY4A/LJMsA84DLqU65e+8Ur+K6sZpKvXltp8E7pPUQxUYAD227y3rWg7Ml3TXAOuoNX36dLq7u4fysiIiopB0f7P6UHc3/S3wfn55QdFBwCMNtwvYQHVzL8rf9QBl/LYy/S/q/eapqw+0jp1IWqTqNwi6e3t7h/iSIiJiMIOGhKQ3Aptt39yCfkbE9mLbc2zP6eoazt0HIiJiIEPZ3fQ64HclnUh1NelEqitUJ0kaX77pT6W6spPydxqwodxz5gCqK1b76n0a52lW3zLAOiIiogUG3ZKwfY7tqbanU916+VrbfwRcB5xcJlsIXF2GV5bnlPHXujo6vpLqVsb7SpoBzKS6N81aYGY5k2lCWcfKMk/dOiIiogV25WK6D1AdxO6hOn6wpNSXAAeV+nuAswFsrwNWUN1b55+pfoFsR9lKOAtYDdwFrCjTDrSOiIhogTF3Md2cOXOcs5siIoZH0s225/Sv57YcERFRKyERERG1EhIREVFrJL8nvNe5/VsXtruFIXnFG97b7hYiYoxJSETLdULodkrgdsJ7CZ3zfsYzZXdTRETUSkhERESthERERNRKSERERK2ERERE1EpIRERErYRERETUSkhERESthERERNRKSERERK2ERERE1EpIRERErYRERETUGjQkJD1b0k2SfihpnaQPl/plku6TdGt5zC51SbpYUo+k2yS9umFZCyXdUx4LG+pHSLq9zHOxJJX6gZLWlOnXSJo86u9ARETUGsqWxJPAMbYPB2YD8yTNLePeZ3t2edxaaicAM8tjEXApVB/4wLnAUcCRwLkNH/qXAu9smG9eqZ8NXGN7JnBNeR4RES0yaEi48pPydJ/y8ACzzAcuL/PdAEySdAhwPLDG9lbbDwNrqALnEGCi7RtsG7gcOKlhWcvK8LKGekREtMCQjklIGifpVmAz1Qf9jWXUBWWX0kWS9i21Q4H1DbNvKLWB6hua1AGm2N5Uhh8EptT0t0hSt6Tu3t7eobykiIgYgiGFhO0dtmcDU4EjJR0GnAO8FHgNcCDwgd3VZOnB1GzB2F5se47tOV1dXbuzjYiIvcqwzm6y/QhwHTDP9qayS+lJ4AtUxxkANgLTGmabWmoD1ac2qQM8VHZHUf5uHk6/ERGxa4ZydlOXpElleD/g9cB/NHx4i+pYwR1llpXAgnKW01xgW9lltBo4TtLkcsD6OGB1GfeopLllWQuAqxuW1XcW1MKGekREtMD4IUxzCLBM0jiqUFlh+5uSrpXUBQi4FfizMv0q4ESgB3gceAeA7a2SPgqsLdN9xPbWMnwGcBmwH/Dt8gD4OLBC0unA/cBbR/g6IyJiBAYNCdu3Aa9qUj+mZnoDZ9aMWwosbVLvBg5rUt8CHDtYjxERsXsMZUsiImKv8OHqOt493rke6CqE0ZXbckRERK2ERERE1EpIRERErYRERETUSkhERESthERERNRKSERERK2ERERE1EpIRERErYRERETUSkhERESthERERNRKSERERK2ERERE1EpIRERErYRERETUSkhEREStQUNC0rMl3STph5LWSfpwqc+QdKOkHklXSppQ6vuW5z1l/PSGZZ1T6ndLOr6hPq/UeiSd3VBvuo6IiGiNoWxJPAkcY/twYDYwT9Jc4BPARbZfDDwMnF6mPx14uNQvKtMhaRZwCvByYB7wWUnjJI0DLgFOAGYBp5ZpGWAdERHRAoOGhCs/KU/3KQ8DxwBXlfoy4KQyPL88p4w/VpJKfbntJ23fB/QAR5ZHj+17bT8FLAfml3nq1hERES0wpGMS5Rv/rcBmYA3wn8AjtreXSTYAh5bhQ4H1AGX8NuCgxnq/eerqBw2wjv79LZLULam7t7d3KC8pIiKGYEghYXuH7dnAVKpv/i/dnU0Nl+3FtufYntPV1dXudiIixoxhnd1k+xHgOuC1wCRJ48uoqcDGMrwRmAZQxh8AbGms95unrr5lgHVEREQLDOXspi5Jk8rwfsDrgbuowuLkMtlC4OoyvLI8p4y/1rZL/ZRy9tMMYCZwE7AWmFnOZJpAdXB7ZZmnbh0REdEC4wefhEOAZeUspGcBK2x/U9KdwHJJ5wO3AEvK9EuAKyT1AFupPvSxvU7SCuBOYDtwpu0dAJLOAlYD44CltteVZX2gZh0REdECg4aE7duAVzWp30t1fKJ//QngLTXLugC4oEl9FbBqqOuIiIjWyBXXERFRKyERERG1EhIREVErIREREbUSEhERUSshERERtRISERFRKyERERG1EhIREVErIREREbUSEhERUSshERERtRISERFRKyERERG1EhIREVErIREREbUSEhERUSshERERtQYNCUnTJF0n6U5J6yT9RamfJ2mjpFvL48SGec6R1CPpbknHN9TnlVqPpLMb6jMk3VjqV0qaUOr7luc9Zfz0UX31ERExoKFsSWwH3mt7FjAXOFPSrDLuItuzy2MVQBl3CvByYB7wWUnjJI0DLgFOAGYBpzYs5xNlWS8GHgZOL/XTgYdL/aIyXUREtMigIWF7k+0flOHHgLuAQweYZT6w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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Take-out-clients-with-more-than-75%-of-their-info-missing.">Take out clients with more than 75% of their info missing.<a class="anchor-link" href="#Take-out-clients-with-more-than-75%-of-their-info-missing.">&#182;</a></h3>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Since there are 10 columns, 75% would be 7.5 of them, however exit_date column is not considered because all Nan values represent that the contract is still active</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">dismiss_empty_cients</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">threshold</span><span class="p">):</span>
    <span class="sd">&#39;&#39;&#39;</span>
<span class="sd">    Select data with more than has 25% of the info filled</span>

<span class="sd">    Parameters:</span>
<span class="sd">        data (Dataframe): data source</span>
<span class="sd">        threshold (int)   : quantity of maximum empty columns </span>
<span class="sd">    </span>
<span class="sd">    Returns:</span>
<span class="sd">        data (Dataframe): dataframe filtered by quantity of empty columns  </span>

<span class="sd">    &#39;&#39;&#39;</span>
    <span class="n">data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">isnull</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span> <span class="o">&lt;=</span> <span class="n">threshold</span><span class="p">]</span>
    <span class="k">return</span> <span class="n">data</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">num_clients_after</span> <span class="o">=</span> <span class="n">dismiss_empty_cients</span><span class="p">(</span><span class="n">clients</span><span class="p">,</span> <span class="mi">6</span><span class="p">)</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">&quot;Number of clients after filter (only by this filter): </span><span class="si">{</span><span class="n">num_clients_after</span><span class="si">}</span><span class="s2">&quot;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Number of clients after filter (only by this filter): 1486541
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">pie_data</span> <span class="o">=</span> <span class="p">[</span><span class="n">num_total_clients</span> <span class="o">-</span> <span class="n">num_clients_after</span><span class="p">,</span> <span class="n">num_clients_after</span><span class="p">]</span>
<span class="n">pie_labels</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Clients with 75</span><span class="si">% i</span><span class="s1">nfo empty&#39;</span><span class="p">,</span> <span class="s1">&#39;Clients with enough info&#39;</span><span class="p">]</span>
<span class="n">pie_colors</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">color_palette</span><span class="p">(</span><span class="s1">&#39;pastel&#39;</span><span class="p">)[</span><span class="mi">0</span><span class="p">:</span><span class="mi">2</span><span class="p">]</span>

<span class="n">plt</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">pie_data</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="n">pie_labels</span><span class="p">,</span> <span class="n">colors</span> <span class="o">=</span> <span class="n">pie_colors</span><span class="p">,</span> <span class="n">autopct</span><span class="o">=</span><span class="s1">&#39;</span><span class="si">%.0f%%</span><span class="s1">&#39;</span><span class="p">,</span> <span class="n">textprops</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;color&#39;</span><span class="p">:</span> <span class="s1">&#39;White&#39;</span><span class="p">,</span><span class="s1">&#39;fontsize&#39;</span><span class="p">:</span><span class="mi">14</span><span class="p">})</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Each-client-should-only-have-one-contract-in-the-database,-no-more">Each client should only have one contract in the database, no more<a class="anchor-link" href="#Each-client-should-only-have-one-contract-in-the-database,-no-more">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">assert</span> <span class="n">clients</span><span class="o">.</span><span class="n">duplicated</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span> <span class="o">==</span> <span class="n">clients</span><span class="o">.</span><span class="n">duplicated</span><span class="p">(</span><span class="n">subset</span><span class="o">=</span> <span class="s1">&#39;CustomerId&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">drop_duplicates</span><span class="p">(</span><span class="n">data</span><span class="p">):</span>
    <span class="c1"># Drops duplicated data</span>
    <span class="n">data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">drop_duplicates</span><span class="p">()</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>
    <span class="k">return</span> <span class="n">data</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">num_clients_after</span> <span class="o">=</span> <span class="n">drop_duplicates</span><span class="p">(</span><span class="n">clients</span><span class="p">)</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">&quot;Number of clients after filter (only by this filter): </span><span class="si">{</span><span class="n">num_clients_after</span><span class="si">}</span><span class="s2">&quot;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Number of clients after filter (only by this filter): 1500000
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">pie_data</span> <span class="o">=</span> <span class="p">[</span><span class="n">num_total_clients</span> <span class="o">-</span> <span class="n">num_clients_after</span><span class="p">,</span> <span class="n">num_clients_after</span><span class="p">]</span>
<span class="n">pie_labels</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Clients with &gt; 1 register&#39;</span><span class="p">,</span> <span class="s1">&#39;Clients with 1 register&#39;</span><span class="p">]</span>
<span class="n">pie_colors</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">color_palette</span><span class="p">(</span><span class="s1">&#39;pastel&#39;</span><span class="p">)[</span><span class="mi">0</span><span class="p">:</span><span class="mi">2</span><span class="p">]</span>

<span class="n">plt</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">pie_data</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="n">pie_labels</span><span class="p">,</span> <span class="n">colors</span> <span class="o">=</span> <span class="n">pie_colors</span><span class="p">,</span> <span class="n">autopct</span><span class="o">=</span><span class="s1">&#39;</span><span class="si">%.0f%%</span><span class="s1">&#39;</span><span class="p">,</span> <span class="n">textprops</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;color&#39;</span><span class="p">:</span> <span class="s1">&#39;White&#39;</span><span class="p">,</span><span class="s1">&#39;fontsize&#39;</span><span class="p">:</span><span class="mi">14</span><span class="p">})</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAhIAAADnCAYAAABL/b88AAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjMuMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/Il7ecAAAACXBIWXMAAAsTAAALEwEAmpwYAAAjTUlEQVR4nO3deXxcdb3/8ddMtu47bWlL0rKUHb1dEC8XKCAqHFHkqoiCVkFB8f4QQf2B91zBAUWp60VFEUT9oUVwhQPIUlMQUChLWUpb6AKUpm1KSdu02ZrM74/PGTJJM8lkksx3zsz7+XjMo7PPZybTOe/z/X7P9xtLJpOIiIiI5CLuugARERGJLgUJERERyZmChIiIiORMQUJERERypiAhIiIiOVOQEBERkZwpSIiIiEjOFCREREQkZwoSIiIikjMFCREREcmZgoSIiIjkTEFCREREcqYgISIiIjlTkBAREZGcKUiIiIhIzhQkREREJGcKEiIiIpIzBQkRERHJmYKEiIiI5ExBQkRERHKmICEiIiI5U5AQERGRnClIiIiISM4UJERERCRnChIiIiKSMwUJERERyZmChIiIiOSs3HUBIjKIgkQcmA7MBGrC03RgFDACGBmeRqT9OxxoAnYAO8N/089vBzYAq4FVeP7mvL0fESl4sWQy6boGEclFkJgA/AcwDzgEOBg4CAsGQ2k78BKwCgsXq4Fn8PyVQ/y6IlKAFCREoiJIVAPHpZ0OBWJOa+pqK/Ao8AiwFFiG57e7LUlEhpqChEihChKjgPcDHhYc9nNbUL81ALXAA8BdeP4rTqsRkSGhICFSSILECCw4nAWcxtB3U+RLEmut+C3wezx/q+N6RGSQKEiIuBYkqoBTsfBwOjYIspi1AfdjoeLPeP4ux/WIyAAoSIi4EiRqgIuBTwNjHVfjyi7gL8BP8fx/uC5GRPpPQUIk34LEfOBS4ENAmeNqCsmjwLeBO/F8/TCJRISChEg+BIkY1m1xGTZwUjJbAVwH3Irnt7kuRkR6pyAhMpSCRBnwSeAr2DwPkr0NwA+An+P5Ox3XIiIZKEiIDJUg4WFN9Ye7LiXi6oGvATfh+R2uixGRrhQkRAZbkHgb8H3gRNelFJkngf/C8x9zXYiIdFKQEBksQWI8cDVwARpEOVSSwK3AV/D8OtfFiIiChMjgCBLnAdcCk1yXUiIasdD2fTy/1XUxIqVMQUJkIILEZOAm4H2uSylRq4Bz8fwnXBciUqoUJERyZYMpbwYmuy6lxO0BEsA1WiRMJP8UJET6y9bD+C5woetSpIt/AR/D89e6LkSklChIiPRHkJiLDfbTnBCFaTtwPp5/h+tCREqFgoRItoLEJdi8EBWuS5E+/QT4Ep7f4roQkWKnICHSlyBRDlyPHdYp0fEY8H4tWS4ytBQkRHoTJMYAvwfe47oUyclLwKl4/hrXhYgUKwUJkUyCRDVwF3Ck61JkQOqB0/H8f7kuRKQYxV0XIFKQgsQ87CgAhYjo2wdYQpD4gOtCRIqRgoRId7bBWQpMdV2KDJoRwB8JEhe5LkSk2ChIiKQLEmcAd2AbHikuceB6gsQ3XRciUkwUJERSgsSpwG1AuetSZEhdTpDwXRchUiw02FIEIEicBATAMNelSN5cjOf/yHURIlGnICESJI4F/gaMdF2K5FUS+DSef4vrQkSiTEFCSpsdnfEgMMZ1KeJEO3AWnv8H14WIRJWChJSuIHEkUAtMcFyJuNWKzYD5N9eFiESRgoSUpiAxGVgG7Oe6FCkIu4GTNGmVSP/pqA0pPUGiEvgjChHSaQRwB0FiH9eFiESNgoSUop8Ax7ouQgrODGAxQaLMdSEiUaIgIaUlSFwAnOe6DClYJwEJ10WIRInGSEjpCBJzgUeAKtelSEFLAmfg+X91XYhIFChISGkIEhOAJ4GZjiuRaNgOzNXy4yJ9U9eGlIpfoBAh2RsL/IEgMdx1ISKFTkFCil+Q+AjwQddlSOS8DbjOdREihU5dG1LcrEvjRWCy61IkkpLACXj+w64LESlUapGQYvcDFCIkdzHgJnVxiGSmICHFK0i8FzjXdRkSeQcBV7kuQqRQqWtDilOQGA08D1S7LkWKwh5gDp7/nOtCRAqNWiSkWF2LQoQMnnLgpwSJmOtCRAqNgoQUnyAxB/ic6zKk6BwLLHRdhEihUZCQYnQNNkhOZLBdS5AY4boIkUKiICHFJUgcB7zXdRlStCYDF7kuQqSQKEhIsbnGdQFS9L5CkBjlugiRQqEgIcXDDvc8znUZUvQmAV9wXYRIoVCQkGJytesCpGRcFh5iLFLyFCSkOASJM4G5rsuQkjERuNh1ESKFQEFCisU3XBcgJedLBImxrosQcU1BQqIvSJwEHO66DCk549FYCREFCSkKF7ouQErWZwkS+h2Vkqb/ABJtQWIKcIbrMqRkVQPvdl2EiEsKEhJ15wEVrouQkna+6wJEXNLqnxJd1qS8BpjpuBIpbW3ADDx/i+tCRFxQi4RE2XtQiBD3KoBPui5CxBUFCYkyDbKUQnGe6wJEXFHXhkRTkJgMbATKXJciEjoBz3/IdREi+aYWCYmq96MQIYXlHNcFiLigICFRdYbrAkS6OdV1ASIuqGtDoscWS6oHqlyXItLNUXj+c66LEMkntUhIFL0bhQgpTGqVkJKjICFRpB9rKVT6bkrJUZCQKHqP6wJEMjg27HoTKRkKEhItQeIIYIbrMkQyqADe5boIkXxSkJCoOdF1ASJ9UPeGlBQFCYmaua4LEOnDSa4LEMknBQmJGgUJKXQHECTGuy5CJF8UJCQ6gsRw4FDXZYhkQYFXSoaChETJ29C02BIN81wXIJIv5a4LEOmHOa4LEOlJEva0U76usWxs/ZaKaW0bK2dOW+C6KJE8UZCQKFGQEOeSsL0lNmxdQ/mkHZsq9ovXVVZPeqN8yqyOWPlBwEHh3SYNwUuvB64HFmW4HFVXAh8CjujlPjOBdcB8YNnQl1TQksCHgTtcF5KiICFRon5nyZskJDuIv7o7Prpua8XU5rqK6hGbKveb3lg2bjrw9j4ePvvXj++q+MTRI9uyfLkpwBXA+7B5UrYCzwL/C9yd4THzgV1ZPn+2rqTvjfpgW4S9z5RbsCD2vjzWkMm+wHexnZiDgN8AC10WhNX0Zpb3rQWeB74wZNWgICFRESTiwGGuy5DilISmtljl2h1l47dtrpiRrKusHldfPm1WW7yqBqjJ4SkrgNnAC1ncdybwCLATuBxYjo1fOxm4AajO8Lj6HOoqRI3haShMA7YAe3J8fBUW6q4FPjuAOiqAbENlXzYN0vP0RyXQmulGDbaUqNgH+zKLDEgHsU274yOXbaictfSJkSc8+tfx5677zaRLqhZP+sLhd4//+HFPjjrh+I2Vs45qi1cNdKrr2Vne7yfhv/OA3wOrgBexboujennceuCytMtjgZ9jG86dwFK6DvpciG2wT8b2UncBfwdmpd3+deBwrPk8Sefe9wXAaqAZ27D+jcw7oouxAJRydfhcx6Rd9xpwTnj+yrCe1PlPAl5aDQvSHlcD3A/sBlYAp2SoIeUzwAbge9hg7f5aD/wfrJVkW5aPmYnVfTawBGjCPj+AT2F1N2Of5yV03Q7Pxv5uzdj34DTsb7Yw7T5JrNUo5X+AV4AWLGT8Orz+FuAE4CI6P8uZ4W2HAQH2PdkC/A6YmvactwB3AV/FPr8Nvb1htUhIVOzrugCJltQAyJ1lY7fUV0zbU1dZM3pzxfTq5vjIqXT90Rwq2UzlPgF4L/Df9LxX3pDla8WwDcN2rEtgG7ZBXgIcDNSF96vCWj0+jW2sfoVt9N8D3IZ1abyPzo33diyM/Dh8vn8A4+h90q1a4Itplxdg4WMB8E/gQOyzqe3hsYuwQ7wnAOeG123DWhYArgG+DHwe+8wWY+EiU4vGt7FQdi42tmJF+J5vBTb38h4Gw7ewoHce1hrxGeAbwH8BT2Kf9Y3hbddjgeJPWBg4BhgO/IDeVzr+z/A1zgaeAybTGdguxoLJSqzbDKwVa1/gIeCm8LEV2Of6F+CdQEd43xOwv/97se9XRgoSEhXT+r6LFLWaeVA9B4aPs8uN9fDyw7DlZZLQ0D775N3xmXP36SDO2rodbz5eVz42NQBywog4xx1QxV3PN9l+WX5Mz+I+B2I/0i8O8LVOxMZt7IPtAQP4wOnYRvQ74XXl2B7qqvDyIuDmsIYmbIO8h67N59VY68VfsT3YV7Dul0xqgZ9iG6zt2FiO/8HCx7VYoFhDz3u5jWEdqb3r7r4P3BmevwL4RPi+/5Ghlmaslef32GdzNvZ5fBu4DwsVf6aXZvsB+F+6Doj0ga+kXbcO+zw+jwWJU7DQ927g9fA+l2DdXpnUYCHxPiyQvErnYNTt2PvaTdfP8nPY3++radd9Agts84DHw+uascDZ0tcbVZCQqFCLRKlr3kFy5YPJjt07NjaXj6lvn3n0hNHzPrrf35/bWt8YGzn5tP2Hj3tgdTPEOjhp9oTJK7c30dCUJAYcM6uSx19poT1/IQKya5HodU+vH+YCI9h73MQw4IC0yy10hgiAjViX4XgyN93fj4WHdViXxn3AH7FQ0ZOV2IZrQVjPGqy1w8f2fhfQc2tENp7tVjvYXng26oEfhaeTsS6A07AQlms9vUk/umQfYD/gZ1jISimn8ztwCPaeXk+7/Qk6Wwh6cjvW8pD629yLBb7eNv5zgePpuRXnADqDxPN9PM9bFCQkKtQiUWKSsLstVrlue9mEbVsqZiQ3NlePry+fNmvPiMrpwHQ2wllTYfjoMZPL2pO82dTBpp32m/vm7g7GDovT0NTOoVPLadjdQd2O3n6Ph0Q23ScvYW0kh2LN2rmKY031x/Vw2460890HHaaiVW/j5XZiRy0cj+01Xw58E2tp2JjhMUuxDfQWbBzGeqx7Yz7WZH55L6/Xm/QBi9nUnm4UcCbWInEi8CjWUvJ4bw8agPQjalI1Xhi+7mB5DWvFOBlbdfa72DiXd5D5iJ441g12WQ+3pXf3ZH1EkIKERIVaJIpYB7FNTfGRr20rn7y7rqK6clPlflMbyibVEIsd3tP9Y0DNhDLK41Df2E4yCWOGxRlZaTt3Y4bFaWjqYFRljIOnVHD3C009Pc1Qy2YuiW3YnuQXsD3l7nuJ48hunMRT2CGkHcDarCvcWys9zx67BxtvsQTbUG3BxlL8PMPz1AKXYhumH6Zd9xkyj4/oq4ZclGHh51zgDKwb4DfYERjrBuk1srEZC10H0DkYsruV2A7TNDoD2jz6DkrNWDAIsK6STcCxWMtRT5/lU8BHsFamQTmSREFCokJBoggkoS0cAFlfXzFtz8bKmtGbK2bUtMRHZDUActzwGKceNpyyOOxph9qXWmhosh3Tp19r5V0HD3vr/PbmJCfPruKZDa1MHlXG22fYQT/PbGjltYb2oXuTnSZmeb+LsH7wZVjz/7NYVjoR23PPdPhnugfC5/gL1g+/Evs83xve9nCWtazH+t3nYP3tO7EN8QHYAL1tYV2j6X1cRy3WhF9DZ2ioxQYXZhofkV7Dqdie9htYX3+ursACze3YgNJMYyl68/bw3zFYUHs7toFe0c/n+To2bqIBmxukAvucp2MDM+/Hup1+hbUWDMeONtlD5pE9C7Ht+L+wEHoWFg5eCm9fDxyNHa3RiP39fowFutuwsSL1wP5YuLiUzF1WGSlISFRMcV2A9E8S3myJDV//ZvmkHZsr9ivfWFk9aVv5lFkdsbLZZH9oZBc7mpPc9XwTFWUxaiaUcez+Vdy30sZCrK7fw+r6zpb7WRNtR6xueztnHDWCe1Y0QQxOPXQ4f352N825ziyQvWyDxFpsg3IF9sM+HduALif7uQuSWH//1djGejK2F/wImfeAe/IHrPn/Qaw15FPAy9je/P9g4zDWAOfTezhJjZN4g85xG7XYNqe2jxpuxMZRLMO6I07ENoi5+A1wHbbXnqunu10+Hdubn9nP5/kF1l3wZSw4NGHzjFwf3t4BfDC83+PYe74UG4+Sqf4GbNDkIiyYrMD+fqnWlkVYMFmBBZNZ4fMeG9ZwLzaO5lWsBSOrMRHdxZLJ/I4+EslJkFiGZrYsSKkZIHfFR2/cWrFva11lzfBNFTNm7CobO+TjWk45eBiNrR08tq7roPuqcjjt8OHc92Iz40fEOWpaBXevsN/i0w4bxrMb29iQn1aJik8cPXLoI4sUq7cBz2BdHE+6LSUztUhIVAzW6HYZgCTsSg2A3FwxI1ZXWTOuvnzfWXvilbnOADkwMSiL7f3VmFddycrNbexqTTJhBMTT7hKP5/XLVE7usypK6fkg1mrxEtbi8T2sZeophzX1SUFCokJBIs/SBkDuqquortpUWT21oWxiDbFYPtdheMucGRVsaGhnV2uSijKYNbGcqaPjPLi6a2vsvmPijB0W59G11kqxdVcHY4bHmTGujBgwdlicrbvydgSHfmOlP0Zj3Vv7Yetp1GJzSRR014G+5BIVChJDpHMA5LgtWyqmtddV1ozZXDE96wGQ+TKsIsZ/HFDF8IoYre3QsLuDB1e3sHF7ZxdFWQyOrqni4TUtb/3yNrUl+ef6Vo6ZaYMtH1vfSlNb3n6X9Rsr/fFr+jempSBojIREQ5B4htzmys+srBIOXgBTDoaqkbBjE7zwN9gezibs+T0/bv0T8MK9dn7/Y2D/f7fzax6Fdf/svN+YqfBvH4SHb4SOwm3dTtoo7cFaUEjStMUq96887asDOepApOApLUtUDH6LxFHvgzFTYPlfoXkHTD8S3nEOLL0BWnbCA9/rev+x02D+R6EuPOpr9GSYvQCeWGyX538Utq6FnVus3CM9eP7egg4RADFrTpUhUJlszfssWCL5ptU/JSoG97saL4eph8LKB2HbK7D7TXjpIfu3Jjw4pGVX19OU2dD4Bmx71W4fNQl2bIY31ttpxxYYGR7xN+sdsLMe3sjnnDdSgAo7RYoMgsH8cV5P1yk3u1+OqivpXOI2k5nYYJh5fdyv0C3A3kc2M/JFWyxuw/fbu/3Ot7fBhP32vn9ZBUw7HF5LGzy9MwwOw8bA8LEwaoItJDV8HMycBy/eP6RvQSJBXUZS9LINElOwaU7XYBNWvA7cg02Aksl84CcDqm5vV9L3Rn2wLcLmhk+5BVunfTAcjy2w8jq2AV84SM+bq0exGSTfyPL+SeBDQ1dOF1nP+56V9lZ48zU46DioGg3ErGtj/IzwcjfTjoBYGWxIWzOocSusWmLdIUd/HFYuseuOOBVW1cKEajjus3D8BTYOQ0pNG56vFgkpetmMkZiJzY62E5uudTkWQE7G1rHPNH1r91XooqqRzGvdD9QoLBgNZKRuHBs/MBiz67TS89K9Q62SvpfxzTbcZO+Zv8BRp8O7vggdHbCjDja+AGN7mI27eg5sXg2tu7te/+pTdkqZFh4ZuXUtLLgIHv0lEIN/Xwi1P9778VLMXPxfEsm7bFokUq0K87A13Vdhc6xfDxzVy+PW07VrYyy2wMsWLJQspWtXwEJsg30ytnHdha0aNyvt9q8Dh2N7wul78BcAq7FpRLdii+BkCkmLsQCUcnX4XMekXfcacE54/ko6W0GuBD4JeGk1LEh7XA02X/pubErSUzLUkHI3Ni3uHfS+VGy6hdjndFpYVyu2cmAldvzxhvD1n8Dmlk/nYX+/Zmze/I+G72FmePsCunZtjMWmmN0SPmYt8MXwtvXhv7eHj0ldBptC9snwMeuAa8L6SHvslcDN2BSvt2bxvgc/SOx+E/75a7j3WljyQ3jkZuvy2P1m1/uNmQLjpnXt1uhJxXA7CuT5u2HcDNi1zVooGuvt/Ljpg/4WpKApSEhJ6CtITMAWffkxPe+VN2T5OjFsZbLp2Ipx/4ZtyJbQdTGmKqzV49PAO7G53lMb/duwJVJXhY/ZN7xuXljfVXQup3pvL7XU0nXjvwALH6nrDiTz6nSLsDD1QFoN6UvCXoOt4Pc2bEO+GGt1GGzDsMV9LgAOw+Z9/yXWBfMx4AhsfvU76Txkshqbsz0Ir/sR8J0+Xudq4Ejsb3Yw9nd5PbxtfvjvZ7DPIXX5PVgwuB4LfZ/Guj++2e25v4TNxz8PC1N92ZrFfXLT3gYtjVA+DPY5ADat6np79RwLF1v7GDh52Cl2aGjTdojFLJSkxMu6XpZSUOe6AJF86Ktr40AsBPS2yls2TsRWTNsHW6gEbEN4Ora8a2qDVo6thJf6JV+E7bXGwsc1YqOg05N+NdZ68VespeMVrPslk1psVbp9sVXl5mOL0ZyELcG6gMyr0zWGdbTQ897G97GNN9jG8RPh+85lxbnelGHLDqfmXj8AOBtrWQgPKeB6bH36C4DPA5/DWhS+FN6+Cls46ZpeXqcGm5r18fDyK2m3pbquGuj6WXwNWyTnl+HlNdiiMv8PW6wmNXHJUvoOMukGf+9u0v62wW98A0aOh0PeZS0IG9K+PvFy665Y+1jvzzVxFozaB5aHf/6GjTBqIkyebd/ekROh4fVen0KKjlokpCT0FSQG69j9udiqcd3HTQzDNoIpLXSGCLA12SuB8djypz25H9vArcO6NO7D9rwzLYWaWpVuQVjPGqxlw8dWT1tA36vTZZI2Eu+t9eQn5/hcvdmDLeSSMgf7W3Vf1rYKa/UBOARrJUn3rz5e56dYt8tc7HO+EwsAvZmLLVv71bTr4tjKc1Pp3Etb1sfzdDf4W+GKYXDwiXbURVsTbFoJq/4OybRepmmH28RVrz2T+Xni5TbA8uk/8lZOatkJz90NR54KxOC5wFo9pJSoRUJKQl9B4iXsl/FQ4E8DeJ04tqTtcT3ctiPtfPcRzqm9197ahHdiG9LjsTEJl2PN6PPp3Jh3txRrJdmCjcNYjzWdz8e6By7v5fV6k36oVza156qFroMr4+HrzWfvw82ayN09WKvEqViXUYCNifhUL4+JY91Mt/dwW3qQ7O9RGIMfJOpWdE4ulcmG5V1bKHrSsQeW9nCA0uvP2klKlVokpCT0tZHbhu3lf4Ge+/rHZfk6T2GHkHZga9unn7Zk+RxgAwvLerh+D7bnfTk2AHQk1q+fSS0WJBbQ2fpQi/X3Zxof0VcNLj2NtUhMZe/PN7UBTo1HSHd0Fs+9FRtwuRA4DxtsWhXe1sben8VTWOtH9zpeZmCT8/TU1SRSyNQiISUhm73li7CN1DLgw9igu0OwPvdsd7cewA4h/Qu2dzsLG0x5FT23UmSyHttDnoMdWVCFBYaLsQGcNdhgw9H0Pq6jFhv/cTRdg8Q5ZB4fkV7DEdjnMAnrDsnVKGwMxduxv0V1eD7TIbWZrMYGON6CDWzcHwsNlwFnhve5AetGWoTVfiY2fgIyryz3DeAM4CCsVepMbJxFarnF9VhLxVSs+yn1mI+F/x6BfVc+RP/GQ/TkVTS5j0SLwq+UhGyCxFpsw30/dnjhs9je//uBz2b5OknscMUlwI3YOIjfYxu0TN0PPfkDdsjkg1gz+dnYYL8zsLCyEtt4ng883MvzpMZJrKazub0W6+qp7aOGG7GQsix87LH9qL+7eVhrwtPYGIKrwvPfyOG5PoUNcPwO9v7uwrp7UgMkXwH+E/u7LceWpr0qvK05w3O2YIMxl2NBcDQ2QDblUqxl57WwbrAWLC+8/vHw9H/pHASaG89vZe8xICKFqh19X6VEaPXP0nYxFlrGUeDr3QMQJG7BulZECt0LeP4RrosQyQcd2F5aLsK6c2ZhrTk+1h1S+CHCPOO6AJEs9TF7mUjx0DLipeVAbH6LiVj/7Q3k1o3iytN930WkIOi7KiVDQaK0XBKeouoZ1wWIZEktElIy1LUh0eH527GJx0QKWRKFXikhChISNc+4LkCkD2vD0CtSEhQkJGr6mtZbxLUn+76LSPFQkJCoucd1ASJ9+JvrAkTySUFCosXzn0UzBkrhSmKT5omUDAUJiSK1SkihegrP12JdUlIUJCSKtMcnhSpwXYBIvilISBQ9gK3CKlJo7nJdgEi+KUhI9Hh+I/CQ6zJEutmMLeYnUlIUJCSq1L0hheYePD8q69aIDBoFCYmqPxGdxcakNNzpugARFxQkJJo8fz02VkKkELyBxkdIiVKQkCi70XUBIqHf4vkaACwlSUFCouzPwBbXRYgAN7kuQMQVBQmJLs9vA37lugwpeU/i+ctdFyHiioKERN0vXBcgJe8nrgsQcUlBQqLN81cDS12XISVrG/A710WIuKQgIcXg564LkJJ1M57f5LoIEZcUJKQY3AG86roIKTmtwPWuixBxTUFCos8Ou/u26zKk5NyE57/iuggR1xQkpFjcBLzuuggpGc3A1a6LECkEChJSHDy/BbjWdRlSMn6K5290XYRIIVCQkGLyc0BNzTLUGoFvuS5CpFAoSEjxsLESX3ddhhS9H+H59a6LECkUChJSbH4DvOC6CClaDcB1rosQKSQKElJcPL8D+LLrMqRoXYfnN7guQqSQKEhI8fH8e4DFrsuQorMCWOS6CJFCoyAhxepibPpikcHQAZyvpcJF9qYgIcXJ87cAl7ouQ4rGj/H8x1wXIVKIFCSkeHn+LcCDrsuQyHsVuMJ1ESKFSkFCit0FgBZVkoG4EM9vdF2ESKFSkJDi5vlrgCtdlyGRdWs4eFdEMlCQkFLwXUD929Jfm4Evui5CpNApSEjx8/x24MPAFtelSGTsAT6C5291XYhIoVOQkNLg+a8DZwHtrkuRSPgynv+Q6yJEokBBQkqH59cCl7suQwre7/D8H7guQiQqFCSktHj+dcAfXJchBes54HzXRYhEiYKElKJPAStdFyEFpwE4E8/f7boQkShRkJDS4/k7gTOBna5LkYKRBM7B8192XYhI1ChISGny/BeBM4Bmx5VIYbgMzw9cFyESRQoSUro8fwl2WGib61LEqW/h+d9zXYRIVMWSyaTrGkTcChJnAb9FwboU/QzPv9B1ESJRph9OEc+/DfgM1k8upeNW4POuixCJOgUJEQDPvxm4xHUZkjeLgU/i+R2uCxGJOgUJkRTP/yHw367LkCF3O3aEhmY5FRkEChIi6Tz/GuBLqJujWN0EfEwhQmTwaLClSE+CxEeBXwGVrkuRQZEEvobnf8t1ISLFRkFCJJMgcTI2nfZY16XIgLQAC/H8xa4LESlGChIivQkShwF3AbNclyI5eQP4AJ7/iOtCRIqVxkiI9MbzVwDvALQhip6XgXcqRIgMLQUJkb54fj1wMnCD61Ika0uAY/D8l1wXIlLs1LUh0h9B4gPYyP+JrkuRHrUCPrBIc0SI5IeChEh/BYlpwK+xVgopHCuBj+P5T7kuRKSUqGtDpL88fyNwCvAVtOBXobgBmKsQIZJ/apEQGYggMQdb8Otg16WUqHrgPDz/TteFiJQqtUiIDITtAc8BvonNVyD58zvgKIUIEbfUIiEyWILELOC7wAddl1LklgEX4/mPui5ERBQkRAafzYj5A+AIx5UUmzrgCuBXeL5+uEQKhIKEyFAIEmXA54CrgAmOq4m6FuB7wDfx/EbXxYhIVwoSIkMpSEwELgMuBMa5LSZy2oHFgI/nr3NdjIj0TEFCJB+CxGjgs8AXgRluiyl4zcAvgesUIEQKn4KESD4FiQrgbODLaAxFd1uBnwHX4/mbXBcjItlRkBBxJUicBlwKnAjEHFfj0rPAj4Bb8fxm18WISP8oSIi4FiRmAueGp4PcFpM364DbgMV4/nLXxYhI7hQkRApJkDga+AjwIaDGcTWDbSNwOxYe/um6GBEZHAoSIoXKQsUZWNfHXKDCaT25eRH4OxYgHtKKnCLFR0FCJAqCxEjgncAJwPHAO4AqpzXtrR1YDjwEPAw8jOfXuy1JRIaagoRIFAWJKixMHAscAszGxldMzFMFu4CXw9OLwCPAo3j+jjy9vogUCAUJkWISJMbTGSoOAg7EZtYcHZ5GpZ0f1sMz7MFCQkPaaQudoeEl4GU8v27o3oSIRImChEipChLlWKCIYZNANWsMg4j0l4KEiIiI5CzuugARERGJLgUJERERyZmChIiIiORMQUJERERypiAhIiIiOVOQEBERkZwpSIiIiEjOFCREREQkZwoSIiIikjMFCREREcmZgoSIiIjkTEFCREREcqYgISIiIjlTkBAREZGcKUiIiIhIzhQkREREJGcKEiIiIpIzBQkRERHJmYKEiIiI5ExBQkRERHKmICEiIiI5U5AQERGRnClIiIiISM4UJERERCRnChIiIiKSMwUJERERyZmChIiIiOTs/wMBPpIU21Z2tQAAAABJRU5ErkJggg=="
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Remember-that-for-a-client-to-be-eligible,-it-must-have-at-least-two-years-of-information-within-the-company-(even-if-it-canceled-the-product).">Remember that for a client to be eligible, it must have at least two years of information within the company (even if it canceled the product).<a class="anchor-link" href="#Remember-that-for-a-client-to-be-eligible,-it-must-have-at-least-two-years-of-information-within-the-company-(even-if-it-canceled-the-product).">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">drop_exit_nan</span><span class="p">(</span><span class="n">data</span><span class="p">):</span>
    <span class="n">years</span> <span class="o">=</span> <span class="mi">2</span>
    <span class="n">days</span> <span class="o">=</span> <span class="mi">365</span><span class="o">*</span><span class="n">years</span>
    <span class="n">data</span><span class="p">[</span><span class="s1">&#39;delivery_date&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">pd</span><span class="o">.</span><span class="n">Timestamp</span><span class="p">(</span><span class="s1">&#39;2019-11-30&#39;</span><span class="p">))</span> 
    <span class="n">data</span><span class="p">[</span><span class="s1">&#39;contract_days&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;delivery_date&#39;</span><span class="p">]</span> <span class="o">-</span> <span class="n">data</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">x</span><span class="o">.</span><span class="n">days</span><span class="p">)</span>
    <span class="n">data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="o">~</span><span class="p">((</span><span class="n">pd</span><span class="o">.</span><span class="n">isna</span><span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">]))</span> <span class="o">&amp;</span> <span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;contract_days&#39;</span><span class="p">]</span> <span class="o">&lt;</span> <span class="n">days</span><span class="p">))]</span>
    <span class="n">data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="s1">&#39;delivery_date&#39;</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">data</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">get_two_years_contracts</span><span class="p">(</span><span class="n">data</span><span class="p">):</span>
    <span class="c1"># Select clients that have contracts with a minimum duration of 2 years</span>
    <span class="n">data</span> <span class="o">=</span> <span class="n">drop_exit_nan</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>
    <span class="n">years</span> <span class="o">=</span> <span class="mi">2</span>
    <span class="n">days</span> <span class="o">=</span> <span class="mi">365</span><span class="o">*</span><span class="n">years</span>
    <span class="c1">#data[&#39;contract_days&#39;] = (data[&#39;exit_date&#39;] - data[&#39;application_date&#39;]).apply(lambda x: x.days)</span>
    <span class="n">data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;contract_days&#39;</span><span class="p">]</span> <span class="o">&gt;=</span> <span class="n">days</span><span class="p">]</span>
    <span class="n">data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="s1">&#39;contract_days&#39;</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">data</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">contracts_two_years</span> <span class="o">=</span> <span class="n">get_two_years_contracts</span><span class="p">(</span><span class="n">clients</span><span class="p">)</span>
<span class="n">num_clients_after</span> <span class="o">=</span><span class="n">contracts_two_years</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
<span class="nb">print</span><span class="p">(</span><span class="sa">f</span><span class="s2">&quot;Number of clients after filter (only by this filter): </span><span class="si">{</span><span class="n">num_clients_after</span><span class="si">}</span><span class="s2">&quot;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>C:\Users\kpam2\AppData\Local\Programs\Python\Python39\lib\site-packages\pandas\core\frame.py:4308: SettingWithCopyWarning: 
A value is trying to be set on a copy of a slice from a DataFrame

See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
  return super().drop(
</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Number of clients after filter (only by this filter): 499989
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">pie_data</span> <span class="o">=</span> <span class="p">[</span><span class="n">num_total_clients</span> <span class="o">-</span> <span class="n">num_clients_after</span><span class="p">,</span> <span class="n">contracts_two_years</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">pd</span><span class="o">.</span><span class="n">notna</span><span class="p">(</span><span class="n">contracts_two_years</span><span class="p">[</span><span class="s1">&#39;contract_days&#39;</span><span class="p">])]</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">contracts_two_years</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">pd</span><span class="o">.</span><span class="n">isna</span><span class="p">(</span><span class="n">contracts_two_years</span><span class="p">[</span><span class="s1">&#39;contract_days&#39;</span><span class="p">])]</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]]</span>
<span class="n">pie_labels</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Contracts &lt; 2 years&#39;</span><span class="p">,</span> <span class="s1">&#39;Contracts &gt; 2 years (Cancelled)&#39;</span><span class="p">,</span> <span class="s1">&#39;Contracts &gt; 2 years (Not yet cancelled)&#39;</span><span class="p">]</span>
<span class="n">pie_colors</span> <span class="o">=</span> <span class="n">sns</span><span class="o">.</span><span class="n">color_palette</span><span class="p">(</span><span class="s1">&#39;pastel&#39;</span><span class="p">)[</span><span class="mi">0</span><span class="p">:</span><span class="mi">3</span><span class="p">]</span>

<span class="n">plt</span><span class="o">.</span><span class="n">pie</span><span class="p">(</span><span class="n">pie_data</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="n">pie_labels</span><span class="p">,</span> <span class="n">colors</span> <span class="o">=</span> <span class="n">pie_colors</span><span class="p">,</span> <span class="n">autopct</span><span class="o">=</span><span class="s1">&#39;</span><span class="si">%.0f%%</span><span class="s1">&#39;</span><span class="p">,</span> <span class="n">textprops</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;color&#39;</span><span class="p">:</span> <span class="s1">&#39;White&#39;</span><span class="p">,</span><span class="s1">&#39;fontsize&#39;</span><span class="p">:</span><span class="mi">14</span><span class="p">})</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Main-Code">Main Code<a class="anchor-link" href="#Main-Code">&#182;</a></h2>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">get_elegible_population</span><span class="p">(</span><span class="n">path</span><span class="p">):</span>

    <span class="sd">&#39;&#39;&#39;</span>
<span class="sd">    Apply all filters to the clients dataset</span>

<span class="sd">    Parameters:</span>
<span class="sd">        path (str): path to data source</span>
<span class="sd">    </span>
<span class="sd">    Returns:</span>
<span class="sd">        data (Dataframe): dataframe fully filtered</span>

<span class="sd">    &#39;&#39;&#39;</span>

    <span class="n">data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="n">path</span><span class="p">)</span>
    <span class="n">data</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">]</span>  <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">])</span>
    <span class="n">data</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">]</span>         <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">])</span>
    <span class="n">data</span><span class="p">[</span><span class="s1">&#39;birth_date&#39;</span><span class="p">]</span>        <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;birth_date&#39;</span><span class="p">])</span>
    <span class="n">total_clients</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>

    <span class="n">data_f1</span> <span class="o">=</span> <span class="n">get_data_from_year</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="mi">2015</span><span class="p">)</span>
    <span class="c1">#print(data_f1.shape[0])</span>

    <span class="n">data_f2</span> <span class="o">=</span> <span class="n">dismiss_country</span><span class="p">(</span><span class="n">data_f1</span><span class="p">,</span> <span class="s1">&#39;Italy&#39;</span><span class="p">)</span>
    <span class="c1">#print(data_f2.shape[0])</span>

    <span class="n">data_f3</span> <span class="o">=</span> <span class="n">dismiss_empty_cients</span><span class="p">(</span><span class="n">data_f2</span><span class="p">,</span> <span class="mi">6</span><span class="p">)</span>
    <span class="c1">#print(data_f3.shape[0])</span>

    <span class="n">data_f4</span> <span class="o">=</span> <span class="n">drop_duplicates</span><span class="p">(</span><span class="n">data_f3</span><span class="p">)</span>
    <span class="c1">#print(data_f4.shape[0])</span>

    <span class="n">data_f5</span> <span class="o">=</span> <span class="n">get_two_years_contracts</span><span class="p">(</span><span class="n">data_f4</span><span class="p">)</span>
    <span class="c1">#data_f5.drop(columns=&#39;contract_days&#39;, inplace=True)</span>
    <span class="c1">#print(data_f5.shape[0])</span>

    <span class="k">return</span> <span class="n">data_f4</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clean_data</span> <span class="o">=</span> <span class="n">get_elegible_population</span><span class="p">(</span><span class="n">MAIN_PATH</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>623242
487424
464075
450562
7963
</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>C:\Users\kpam2\AppData\Local\Programs\Python\Python39\lib\site-packages\pandas\core\frame.py:4308: SettingWithCopyWarning: 
A value is trying to be set on a copy of a slice from a DataFrame

See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
  return super().drop(
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clean_data</span> <span class="o">=</span> <span class="n">drop_exit_nan</span><span class="p">(</span><span class="n">clean_data</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>C:\Users\kpam2\AppData\Local\Programs\Python\Python39\lib\site-packages\pandas\core\frame.py:4308: SettingWithCopyWarning: 
A value is trying to be set on a copy of a slice from a DataFrame

See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
  return super().drop(
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Obtain-relevant-variables">Obtain relevant variables<a class="anchor-link" href="#Obtain-relevant-variables">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">drop_unwanted_population</span><span class="p">(</span><span class="n">data</span><span class="p">,</span> <span class="n">unique_values</span><span class="p">):</span>
    <span class="sd">&#39;&#39;&#39;</span>
<span class="sd">    Select desired population (the ones that remain in clients dataset)</span>

<span class="sd">    Parameters:</span>
<span class="sd">        data (Dataframe)        : data source</span>
<span class="sd">        unique_values (array)   : clients from Clients dataset </span>
<span class="sd">    </span>
<span class="sd">    Returns:</span>
<span class="sd">        data (Dataframe): filtered dataframe   </span>

<span class="sd">    &#39;&#39;&#39;</span>
    <span class="n">data</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;CustomerId&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">isin</span><span class="p">(</span><span class="n">unique_values</span><span class="p">)]</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>
    <span class="k">return</span> <span class="n">data</span>

<span class="k">global</span> <span class="n">product_table</span>
<span class="k">global</span> <span class="n">transaction_table</span>
<span class="k">global</span> <span class="n">credit_table</span>

<span class="n">unique_values</span> <span class="o">=</span> <span class="n">clean_data</span><span class="o">.</span><span class="n">CustomerId</span><span class="o">.</span><span class="n">unique</span><span class="p">()</span>

<span class="n">product_table</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;data/products_table.txt&#39;</span><span class="p">)</span>
<span class="n">transaction_table</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;data/transactions_table.txt&#39;</span><span class="p">)</span>
<span class="n">credit_table</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;data/credit_score_table.txt&#39;</span><span class="p">)</span>


<span class="n">product_table</span> <span class="o">=</span> <span class="n">drop_unwanted_population</span><span class="p">(</span><span class="n">product_table</span><span class="p">,</span> <span class="n">unique_values</span><span class="p">)</span>
<span class="n">transaction_table</span> <span class="o">=</span> <span class="n">drop_unwanted_population</span><span class="p">(</span><span class="n">transaction_table</span><span class="p">,</span> <span class="n">unique_values</span><span class="p">)</span>
<span class="n">credit_table</span> <span class="o">=</span> <span class="n">drop_unwanted_population</span><span class="p">(</span><span class="n">credit_table</span><span class="p">,</span> <span class="n">unique_values</span><span class="p">)</span>

<span class="n">transaction_table</span> <span class="o">=</span> <span class="n">transaction_table</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">transaction_table</span><span class="p">[</span><span class="s1">&#39;Transaction&#39;</span><span class="p">]</span><span class="o">==</span><span class="s1">&#39;trans_1&#39;</span><span class="p">]</span>
<span class="n">credit_table</span><span class="p">[</span><span class="s1">&#39;Date&#39;</span><span class="p">]</span>  <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">credit_table</span><span class="p">[</span><span class="s1">&#39;Date&#39;</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">get_num_products</span><span class="p">(</span><span class="n">customer_id</span><span class="p">):</span>
    <span class="c1"># Get number of products per client at the moment of application</span>
    <span class="k">return</span> <span class="nb">len</span><span class="p">((</span><span class="n">product_table</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">product_table</span><span class="o">.</span><span class="n">CustomerId</span> <span class="o">==</span> <span class="n">customer_id</span><span class="p">])</span><span class="o">.</span><span class="n">index</span><span class="p">)</span>

<span class="k">def</span> <span class="nf">get_balance</span><span class="p">(</span><span class="n">customer_id</span><span class="p">):</span>
    <span class="c1"># Get clients bank account balance at the moment of application</span>
    <span class="k">return</span> <span class="n">transaction_table</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">transaction_table</span><span class="o">.</span><span class="n">CustomerId</span> <span class="o">==</span> <span class="n">customer_id</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">Value</span>

<span class="k">def</span> <span class="nf">get_credit_score</span><span class="p">(</span><span class="n">customer_id</span><span class="p">,</span> <span class="n">date</span><span class="p">):</span>
    <span class="c1"># Get score of the credit bureau at the moment of application</span>
    <span class="k">return</span> <span class="n">credit_table</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">credit_table</span><span class="p">[</span><span class="s1">&#39;CustomerId&#39;</span><span class="p">]</span><span class="o">==</span><span class="n">customer_id</span><span class="p">]</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">by</span><span class="o">=</span><span class="s1">&#39;Date&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="mi">6</span><span class="p">][</span><span class="s1">&#39;Score&#39;</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;ProductsAtApplication&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">clean_data</span><span class="o">.</span><span class="n">CustomerId</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="n">get_num_products</span><span class="p">)</span>
<span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;BalanceAtApplication&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">clean_data</span><span class="o">.</span><span class="n">CustomerId</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="n">get_balance</span><span class="p">)</span>
<span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;CreditAtApplication&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">clean_data</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">get_credit_score</span><span class="p">(</span><span class="n">x</span><span class="p">[</span><span class="s1">&#39;CustomerId&#39;</span><span class="p">],</span> <span class="n">x</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">replace</span><span class="p">(</span><span class="n">day</span><span class="o">=</span><span class="mi">1</span><span class="p">)),</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;Age&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">]</span> <span class="o">-</span> <span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;birth_date&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="nb">int</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">days</span> <span class="o">/</span><span class="mi">365</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clean_data</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CustomerId</th>
      <th>Surname</th>
      <th>Geography</th>
      <th>Gender</th>
      <th>HasCrCard</th>
      <th>IsActiveMember</th>
      <th>EstimatedSalary</th>
      <th>application_date</th>
      <th>exit_date</th>
      <th>birth_date</th>
      <th>ProductsAtApplication</th>
      <th>BalanceAtApplication</th>
      <th>CreditAtApplication</th>
      <th>Age</th>
      <th>Churn</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7</th>
      <td>14523468</td>
      <td>LASKOSKI</td>
      <td>Spain</td>
      <td>Female</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>158161.23</td>
      <td>2017-12-28</td>
      <td>2018-11-19</td>
      <td>1972-10-30</td>
      <td>4</td>
      <td>1112.22</td>
      <td>630</td>
      <td>45</td>
      <td>1</td>
    </tr>
    <tr>
      <th>14</th>
      <td>15165393</td>
      <td>LABIANCA</td>
      <td>Spain</td>
      <td>Male</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>2612.65</td>
      <td>2018-02-22</td>
      <td>2019-06-11</td>
      <td>1974-07-11</td>
      <td>1</td>
      <td>4452.42</td>
      <td>487</td>
      <td>43</td>
      <td>1</td>
    </tr>
    <tr>
      <th>20</th>
      <td>15982728</td>
      <td>GOUDEAU</td>
      <td>France</td>
      <td>Male</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>66465.09</td>
      <td>2018-02-02</td>
      <td>2019-06-01</td>
      <td>1972-12-18</td>
      <td>1</td>
      <td>1437.83</td>
      <td>595</td>
      <td>45</td>
      <td>1</td>
    </tr>
    <tr>
      <th>29</th>
      <td>15893706</td>
      <td>FRIESENHAHN</td>
      <td>Germany</td>
      <td>Male</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>60959.43</td>
      <td>2019-01-10</td>
      <td>2019-10-21</td>
      <td>1988-12-10</td>
      <td>3</td>
      <td>4992.45</td>
      <td>571</td>
      <td>30</td>
      <td>1</td>
    </tr>
    <tr>
      <th>41</th>
      <td>15898769</td>
      <td>ALCOCK</td>
      <td>Germany</td>
      <td>Female</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>197095.28</td>
      <td>2018-06-09</td>
      <td>2019-06-16</td>
      <td>1998-05-14</td>
      <td>1</td>
      <td>2497.72</td>
      <td>532</td>
      <td>20</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Descriptive-variables">Descriptive variables<a class="anchor-link" href="#Descriptive-variables">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#clean_data = pd.read_csv(&#39;data/clients_new_variable.txt&#39;)</span>
<span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">]</span>  <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">])</span>
<span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">]</span>         <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">])</span>
<span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;birth_date&#39;</span><span class="p">]</span>        <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_datetime</span><span class="p">(</span><span class="n">clean_data</span><span class="p">[</span><span class="s1">&#39;birth_date&#39;</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clean_data</span><span class="p">[[</span><span class="s1">&#39;ProductsAtApplication&#39;</span><span class="p">,</span> <span class="s1">&#39;BalanceAtApplication&#39;</span><span class="p">,</span> <span class="s1">&#39;CreditAtApplication&#39;</span><span class="p">,</span> <span class="s1">&#39;Age&#39;</span><span class="p">]]</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span><span class="o">.</span><span class="n">T</span><span class="p">[[</span><span class="s1">&#39;mean&#39;</span><span class="p">,</span> <span class="s1">&#39;std&#39;</span><span class="p">,</span> <span class="s1">&#39;min&#39;</span><span class="p">,</span> <span class="s1">&#39;max&#39;</span><span class="p">]]</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>mean</th>
      <th>std</th>
      <th>min</th>
      <th>max</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>ProductsAtApplication</th>
      <td>2.403552</td>
      <td>1.116477</td>
      <td>1.00</td>
      <td>4.00</td>
    </tr>
    <tr>
      <th>BalanceAtApplication</th>
      <td>3000.452857</td>
      <td>1158.263243</td>
      <td>1000.07</td>
      <td>4999.99</td>
    </tr>
    <tr>
      <th>CreditAtApplication</th>
      <td>650.044786</td>
      <td>96.710461</td>
      <td>174.00</td>
      <td>1000.00</td>
    </tr>
    <tr>
      <th>Age</th>
      <td>38.517257</td>
      <td>10.277852</td>
      <td>18.00</td>
      <td>92.00</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Feature-engineering">Feature engineering<a class="anchor-link" href="#Feature-engineering">&#182;</a></h3>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Class 0 : contract &gt; 2 years <br>
Class 1 : contract &lt; 2 years</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">set_label</span><span class="p">(</span><span class="n">data</span><span class="p">):</span>
    <span class="n">years</span> <span class="o">=</span> <span class="mi">2</span>
    <span class="n">days</span> <span class="o">=</span> <span class="mi">365</span><span class="o">*</span><span class="n">years</span> 
    <span class="n">data</span><span class="p">[</span><span class="s1">&#39;Churn&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="mi">1</span>
    <span class="n">data</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="n">pd</span><span class="o">.</span><span class="n">Timestamp</span><span class="p">(</span><span class="s1">&#39;2019-11-30&#39;</span><span class="p">))</span>
    <span class="n">data</span><span class="p">[</span><span class="s1">&#39;contract_days&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;exit_date&#39;</span><span class="p">]</span> <span class="o">-</span> <span class="n">data</span><span class="p">[</span><span class="s1">&#39;application_date&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">x</span><span class="o">.</span><span class="n">days</span><span class="p">)</span>
    <span class="n">data</span><span class="p">[</span><span class="s1">&#39;Churn&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">loc</span><span class="p">[(</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;contract_days&#39;</span><span class="p">]</span> <span class="o">&gt;=</span> <span class="n">days</span><span class="p">)</span> <span class="o">|</span> <span class="p">(</span><span class="n">pd</span><span class="o">.</span><span class="n">isna</span><span class="p">(</span><span class="n">data</span><span class="p">[</span><span class="s1">&#39;contract_days&#39;</span><span class="p">]))]</span> <span class="o">=</span> <span class="mi">0</span>
    <span class="n">data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="s1">&#39;contract_days&#39;</span><span class="p">,</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
    <span class="k">return</span> <span class="n">data</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clean_data</span> <span class="o">=</span> <span class="n">set_label</span><span class="p">(</span><span class="n">clean_data</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>C:\Users\kpam2\AppData\Local\Programs\Python\Python39\lib\site-packages\pandas\core\indexing.py:1637: SettingWithCopyWarning: 
A value is trying to be set on a copy of a slice from a DataFrame

See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
  self._setitem_single_block(indexer, value, name)
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">clean_data</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;clean_clients.txt&#39;</span><span class="p">,</span> <span class="n">index_col</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Drop not influential columns</span>
<span class="n">features</span> <span class="o">=</span> <span class="n">clean_data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;CustomerId&#39;</span><span class="p">,</span> <span class="s1">&#39;Surname&#39;</span><span class="p">,</span> <span class="s1">&#39;application_date&#39;</span><span class="p">,</span> <span class="s1">&#39;exit_date&#39;</span><span class="p">,</span> <span class="s1">&#39;birth_date&#39;</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4>Relation analysis between each variable and Churn rate: <br><br></h4>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h5>Categorical : Geography, Gender, HasCrCard, IsActiveMember, ProductsAtApplication <br></h5>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">fig</span><span class="p">,</span> <span class="n">axs</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="mi">3</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">set_figheight</span><span class="p">(</span><span class="mi">12</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">set_figwidth</span><span class="p">(</span><span class="mi">20</span><span class="p">)</span>
<span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Geography&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Gender&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;HasCrCard&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">2</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;IsActiveMember&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;ProductsAtApplication&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>


<span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by geography&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by gender&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">2</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by hasCrCard&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by isActiveMember&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by products at application&#39;</span><span class="p">)</span>

<span class="k">for</span> <span class="n">ax</span> <span class="ow">in</span> <span class="n">axs</span><span class="o">.</span><span class="n">flat</span><span class="p">:</span>
    <span class="n">ax</span><span class="o">.</span><span class="n">set</span><span class="p">(</span><span class="n">xlabel</span><span class="o">=</span><span class="s1">&#39;x-label&#39;</span><span class="p">,</span> <span class="n">ylabel</span><span class="o">=</span><span class="s1">&#39;y-label&#39;</span><span class="p">)</span>

<span class="c1"># Hide x labels and tick labels for top plots and y ticks for right plots.</span>
<span class="k">for</span> <span class="n">ax</span> <span class="ow">in</span> <span class="n">axs</span><span class="o">.</span><span class="n">flat</span><span class="p">:</span>
    <span class="n">ax</span><span class="o">.</span><span class="n">label_outer</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h5 id="Numerical:-EstimatedSalary,-BalanceAtApplication,-CreditAtApplication,-Age">Numerical: EstimatedSalary, BalanceAtApplication, CreditAtApplication, Age<a class="anchor-link" href="#Numerical:-EstimatedSalary,-BalanceAtApplication,-CreditAtApplication,-Age">&#182;</a></h5>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">fig</span><span class="p">,</span> <span class="n">axs</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">set_figheight</span><span class="p">(</span><span class="mi">12</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">set_figwidth</span><span class="p">(</span><span class="mi">20</span><span class="p">)</span>
<span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;EstimatedSalary&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;EstimatedSalary&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Churn&#39;</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;BalanceAtApplication&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;BalanceAtApplication&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Churn&#39;</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;CreditAtApplication&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;CreditAtApplication&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Churn&#39;</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Age&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Age&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;Churn&#39;</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>

<span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by estimated salary&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by balance at application&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by credit score at application&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by age&#39;</span><span class="p">)</span>

<span class="k">for</span> <span class="n">ax</span> <span class="ow">in</span> <span class="n">axs</span><span class="o">.</span><span class="n">flat</span><span class="p">:</span>
    <span class="n">ax</span><span class="o">.</span><span class="n">set</span><span class="p">(</span><span class="n">xlabel</span><span class="o">=</span><span class="s1">&#39;x-label&#39;</span><span class="p">,</span> <span class="n">ylabel</span><span class="o">=</span><span class="s1">&#39;y-label&#39;</span><span class="p">)</span>

<span class="c1"># Hide x labels and tick labels for top plots and y ticks for right plots.</span>
<span class="k">for</span> <span class="n">ax</span> <span class="ow">in</span> <span class="n">axs</span><span class="o">.</span><span class="n">flat</span><span class="p">:</span>
    <span class="n">ax</span><span class="o">.</span><span class="n">label_outer</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">fig</span><span class="p">,</span> <span class="n">axs</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">subplots</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">set_figheight</span><span class="p">(</span><span class="mi">12</span><span class="p">)</span>
<span class="n">fig</span><span class="o">.</span><span class="n">set_figwidth</span><span class="p">(</span><span class="mi">20</span><span class="p">)</span>
<span class="n">features</span><span class="o">.</span><span class="n">pivot</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="s1">&#39;Churn&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">EstimatedSalary</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span> <span class="o">=</span> <span class="s1">&#39;hist&#39;</span><span class="p">,</span> <span class="n">stacked</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">pivot</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="s1">&#39;Churn&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">BalanceAtApplication</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span> <span class="o">=</span> <span class="s1">&#39;hist&#39;</span><span class="p">,</span> <span class="n">stacked</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">pivot</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="s1">&#39;Churn&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">CreditAtApplication</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span> <span class="o">=</span> <span class="s1">&#39;hist&#39;</span><span class="p">,</span> <span class="n">stacked</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span><span class="mi">0</span><span class="p">])</span>
<span class="n">features</span><span class="o">.</span><span class="n">pivot</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="s1">&#39;Churn&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Age</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span> <span class="o">=</span> <span class="s1">&#39;hist&#39;</span><span class="p">,</span> <span class="n">stacked</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">ax</span> <span class="o">=</span> <span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>

<span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by estimated salary&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by balance at application&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by credit score at application&#39;</span><span class="p">)</span>
<span class="n">axs</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s1">&#39;Churn rate by age&#39;</span><span class="p">)</span>

<span class="c1">#for ax in axs.flat:</span>
<span class="c1">#    ax.set(xlabel=&#39;x-label&#39;, ylabel=&#39;y-label&#39;)</span>

<span class="c1"># Hide x labels and tick labels for top plots and y ticks for right plots.</span>
<span class="c1">#for ax in axs.flat:</span>
<span class="c1">#    ax.label_outer()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>Text(0.5, 1.0, &#39;Churn rate by age&#39;)</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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O9fSpUuHHYYkSerJ5Zdf/uOqWjTsOPQL5l+SJM19E+Vg867wtHTpUlauXDnsMCRJUk+SfH/YMeihzL8kSZr7JsrBvNROkiRJkiRJvbDwJEmSJEmSpF5YeJIkSZIkSVIv5t0YT5IkacPuu+8+1qxZw9133z3sUCa0cOFClixZwpZbbjnsUCRJkjbbKORfsPE5mIUnSZL0MGvWrGHbbbdl6dKlJBl2OA9TVdx6662sWbOGPfbYY9jhSJIkbbbZnn/BpuVgXmonSZIe5u6772annXaatUlPEnbaaadZ/42gJEnSVM32/As2LQez8CRJksY1m5MemP3xSZIkbaxRyG82NkYLT5IkSZIkSeqFhSdJkrRRfvSjH3HUUUfxpCc9if3224/DDz+c0047jec///nDDk1AkoVJLk3yH0muTnJKa98jyTeSrEry6SRbtfat2/NVbf7SgW29sbV/N8mhA+3LW9uqJCfNeCclSZqHRjUHs/AkSZKmrKp44QtfyEEHHcT3vvc9Lr/8ct7xjndw8803b9Z277///mmKUMA9wMFV9XRgH2B5kgOBdwHvraonA7cDx7XljwNub+3vbcuRZC/gKGBvYDnwoSRbJNkC+CBwGLAXcHRbVpIk9WSUczALT5IkacouvvhittxyS17zmtc82Pb0pz+dZz/72dx111286EUv4ilPeQovfelLqSoAli5dyo9//GMAVq5cyUEHHQTAihUrOOaYY3jWs57FMcccw4oVK3jVq17FQQcdxBOf+EROPfXUGe/fXFCdu9rTLdujgIOBc1v7GcCRbfqI9pw2/7npBm84Aji7qu6pqhuAVcD+7bGqqq6vqnuBs9uykiSpJ6Ocg1l4kiRJU3bVVVex3377jTvvW9/6Fu973/u45ppruP766/m3f/u3DW7vmmuu4ctf/jJnnXUWAN/5zne48MILufTSSznllFO47777pjX++aKdmXQFcAtwEfA94CdVNfa15hpgcZteDNwI0ObfAew02L7eOhO1rx/D8UlWJlm5bt26aeqZJEnz0yjnYAumbUuSNBut2G7YEWyaFXcMOwJpo+2///4sWbIEgH322YfVq1fz67/+65Ou84IXvIBtttnmwefPe97z2Hrrrdl666157GMfy8033/zgNjV1VfUAsE+S7YHPA08ZQgynAacBLFu2rGZ6/+qRn62SNKvM9hzMM54k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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h5 id="Analyze-data-imbalance">Analyze data imbalance<a class="anchor-link" href="#Analyze-data-imbalance">&#182;</a></h5>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ax</span> <span class="o">=</span> <span class="n">features</span><span class="p">[</span><span class="s1">&#39;Churn&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;turquoise&#39;</span><span class="p">,</span> <span class="s1">&#39;gold&#39;</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Samples per class&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>As it can be seen in the graph above, there exists a great imbalance in our data. So let's apply under-sampling to balance our data</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">class_count_1</span><span class="p">,</span> <span class="n">class_count_0</span> <span class="o">=</span> <span class="n">features</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
<span class="n">class_1</span> <span class="o">=</span> <span class="n">features</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">features</span><span class="o">.</span><span class="n">Churn</span> <span class="o">==</span> <span class="mi">1</span><span class="p">]</span>
<span class="n">class_0</span> <span class="o">=</span> <span class="n">features</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">features</span><span class="o">.</span><span class="n">Churn</span> <span class="o">==</span> <span class="mi">0</span><span class="p">]</span>
<span class="n">class_1_under</span> <span class="o">=</span> <span class="n">class_1</span><span class="o">.</span><span class="n">sample</span><span class="p">(</span><span class="n">class_count_0</span><span class="p">)</span>

<span class="n">features</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">class_1_under</span><span class="p">,</span> <span class="n">class_0</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="n">ax</span> <span class="o">=</span> <span class="n">features</span><span class="p">[</span><span class="s1">&#39;Churn&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">color</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;turquoise&#39;</span><span class="p">,</span> <span class="s1">&#39;gold&#39;</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Samples per class (under-sampling)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Apply-clustering-algorithms-to-clients-age">Apply clustering algorithms to clients age<a class="anchor-link" href="#Apply-clustering-algorithms-to-clients-age">&#182;</a></h4>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">distortions</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">K</span> <span class="o">=</span> <span class="nb">range</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">10</span><span class="p">)</span>
<span class="k">for</span> <span class="n">k</span> <span class="ow">in</span> <span class="n">K</span><span class="p">:</span>
    <span class="n">kmeanModel</span> <span class="o">=</span> <span class="n">KMeans</span><span class="p">(</span><span class="n">n_clusters</span><span class="o">=</span><span class="n">k</span><span class="p">)</span>
    <span class="n">kmeanModel</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">features</span><span class="p">[[</span><span class="s1">&#39;Age&#39;</span><span class="p">]])</span>
    <span class="n">distortions</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">kmeanModel</span><span class="o">.</span><span class="n">inertia_</span><span class="p">)</span>

<span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">5</span><span class="p">))</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">K</span><span class="p">,</span> <span class="n">distortions</span><span class="p">,</span> <span class="s1">&#39;bx-&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;k&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Distortion&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;The Elbow Method (Age)&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.cluster</span> <span class="kn">import</span> <span class="n">KMeans</span>
<span class="n">kmeans</span> <span class="o">=</span> <span class="n">KMeans</span><span class="p">(</span><span class="n">n_clusters</span><span class="o">=</span><span class="mi">6</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">features</span><span class="p">[[</span><span class="s1">&#39;Age&#39;</span><span class="p">]])</span>
<span class="n">features</span><span class="p">[</span><span class="s1">&#39;age_cluster&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">kmeans</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">features</span><span class="p">[[</span><span class="s1">&#39;Age&#39;</span><span class="p">]])</span>

<span class="n">d</span> <span class="o">=</span> <span class="n">features</span><span class="o">.</span><span class="n">groupby</span><span class="p">(</span><span class="s1">&#39;Age&#39;</span><span class="p">)</span><span class="o">.</span><span class="n">Churn</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span><span class="o">.</span><span class="n">to_dict</span><span class="p">()</span>
<span class="n">features</span><span class="p">[</span><span class="s1">&#39;churn_prob_age&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">features</span><span class="p">[</span><span class="s1">&#39;Age&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">map</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="n">d</span><span class="p">[</span><span class="n">x</span><span class="p">])</span>

<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="n">sns</span><span class="o">.</span><span class="n">scatterplot</span><span class="p">(</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;Age&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;churn_prob_age&#39;</span><span class="p">,</span> <span class="n">hue</span><span class="o">=</span><span class="s1">&#39;age_cluster&#39;</span> <span class="p">,</span> <span class="n">data</span><span class="o">=</span><span class="n">features</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Prepare-features">Prepare features<a class="anchor-link" href="#Prepare-features">&#182;</a></h4>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">LabelEncoder</span>

<span class="n">encoder</span> <span class="o">=</span> <span class="n">LabelEncoder</span><span class="p">()</span>
<span class="n">features</span><span class="p">[</span><span class="s2">&quot;Geography&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">encoder</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">features</span><span class="p">[</span><span class="s2">&quot;Geography&quot;</span><span class="p">])</span>
<span class="n">features</span><span class="p">[</span><span class="s2">&quot;Gender&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="n">encoder</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">features</span><span class="p">[</span><span class="s2">&quot;Gender&quot;</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">y</span> <span class="o">=</span> <span class="n">features</span><span class="p">[</span><span class="s1">&#39;Churn&#39;</span><span class="p">]</span>
<span class="n">X</span> <span class="o">=</span> <span class="n">features</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;Churn&#39;</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">train_test_split</span>
<span class="n">X_train</span><span class="p">,</span> <span class="n">X_test</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">y_test</span> <span class="o">=</span> <span class="n">train_test_split</span><span class="p">(</span><span class="n">X</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">test_size</span><span class="o">=</span><span class="mf">0.3</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">42</span><span class="p">,</span> <span class="n">shuffle</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">MinMaxScaler</span>
<span class="n">columns</span> <span class="o">=</span> <span class="n">X_train</span><span class="o">.</span><span class="n">columns</span><span class="o">.</span><span class="n">values</span>
<span class="n">scaler</span> <span class="o">=</span> <span class="n">MinMaxScaler</span><span class="p">(</span><span class="n">feature_range</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">))</span>
<span class="n">scaler</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">)</span>
<span class="n">X_train</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">scaler</span><span class="o">.</span><span class="n">transform</span><span class="p">(</span><span class="n">X_train</span><span class="p">))</span>
<span class="n">X_test</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">scaler</span><span class="o">.</span><span class="n">transform</span><span class="p">(</span><span class="n">X_test</span><span class="p">))</span>
<span class="n">X_train</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="n">columns</span>
<span class="n">X_test</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="n">columns</span>
<span class="c1">#X.head()</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Statistical-model">Statistical model<a class="anchor-link" href="#Statistical-model">&#182;</a></h3>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Model 1: Logistic Regression</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.linear_model</span> <span class="kn">import</span> <span class="n">LogisticRegression</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">accuracy_score</span><span class="p">,</span> <span class="n">plot_confusion_matrix</span><span class="p">,</span> <span class="n">classification_report</span>
<span class="n">logreg</span><span class="o">=</span><span class="n">LogisticRegression</span><span class="p">()</span>
<span class="n">logreg</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span><span class="n">y_train</span><span class="p">)</span>
<span class="n">prediction_logreg</span><span class="o">=</span><span class="n">logreg</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">prediction_logreg</span><span class="p">,</span> <span class="n">target_names</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;No churn&#39;</span><span class="p">,</span> <span class="s1">&#39;Churn&#39;</span><span class="p">]))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

    No churn       0.72      0.80      0.76      2380
       Churn       0.78      0.70      0.74      2398

    accuracy                           0.75      4778
   macro avg       0.75      0.75      0.75      4778
weighted avg       0.75      0.75      0.75      4778

</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plot_confusion_matrix</span><span class="p">(</span><span class="n">logreg</span><span class="p">,</span> <span class="n">X_test</span><span class="p">,</span> <span class="n">y_test</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Model 2: XGBoost</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">xgboost</span> <span class="kn">import</span> <span class="n">XGBClassifier</span>
<span class="n">xgb_model</span> <span class="o">=</span> <span class="n">XGBClassifier</span><span class="p">(</span><span class="n">max_depth</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">learning_rate</span><span class="o">=</span><span class="mf">0.08</span><span class="p">,</span> <span class="n">objective</span><span class="o">=</span><span class="s1">&#39;binary:logistic&#39;</span><span class="p">,</span> <span class="n">n_jobs</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">xgb_model</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
<span class="n">prediction_xgb</span> <span class="o">=</span> <span class="n">xgb_model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">prediction_xgb</span><span class="p">,</span> <span class="n">target_names</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;No churn&#39;</span><span class="p">,</span> <span class="s1">&#39;Churn&#39;</span><span class="p">]))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>C:\Users\kpam2\AppData\Local\Programs\Python\Python39\lib\site-packages\xgboost\sklearn.py:1224: UserWarning: The use of label encoder in XGBClassifier is deprecated and will be removed in a future release. To remove this warning, do the following: 1) Pass option use_label_encoder=False when constructing XGBClassifier object; and 2) Encode your labels (y) as integers starting with 0, i.e. 0, 1, 2, ..., [num_class - 1].
  warnings.warn(label_encoder_deprecation_msg, UserWarning)
</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>[19:40:45] WARNING: C:/Users/Administrator/workspace/xgboost-win64_release_1.5.1/src/learner.cc:1115: Starting in XGBoost 1.3.0, the default evaluation metric used with the objective &#39;binary:logistic&#39; was changed from &#39;error&#39; to &#39;logloss&#39;. Explicitly set eval_metric if you&#39;d like to restore the old behavior.
              precision    recall  f1-score   support

    No churn       0.76      0.92      0.83      2380
       Churn       0.89      0.72      0.80      2398

    accuracy                           0.82      4778
   macro avg       0.83      0.82      0.81      4778
weighted avg       0.83      0.82      0.81      4778

</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plot_confusion_matrix</span><span class="p">(</span><span class="n">xgb_model</span><span class="p">,</span> <span class="n">X_test</span><span class="p">,</span> <span class="n">y_test</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Model 3: Random Forest</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">RandomForestClassifier</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">RandomizedSearchCV</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>

<span class="n">rf_c</span><span class="o">=</span><span class="n">RandomForestClassifier</span><span class="p">(</span><span class="n">max_depth</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="n">rf_c</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
<span class="n">prediction_rf</span> <span class="o">=</span> <span class="n">rf_c</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">prediction_rf</span><span class="p">,</span> <span class="n">target_names</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;No churn&#39;</span><span class="p">,</span> <span class="s1">&#39;Churn&#39;</span><span class="p">]))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

    No churn       0.75      0.92      0.83      2380
       Churn       0.90      0.70      0.79      2398

    accuracy                           0.81      4778
   macro avg       0.82      0.81      0.81      4778
weighted avg       0.82      0.81      0.81      4778

</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plot_confusion_matrix</span><span class="p">(</span><span class="n">rf_c</span><span class="p">,</span> <span class="n">X_test</span><span class="p">,</span> <span class="n">y_test</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAT8AAAEGCAYAAAAT05LOAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjMuMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/Il7ecAAAACXBIWXMAAAsTAAALEwEAmpwYAAAf1ElEQVR4nO3deZgdVZ3/8fenO+mELJCEhEzIYgBDMhElQkRERBCEwKCIwyjoICKrwLihDjoqDvzwcUYBxwWQJQOobIqR4LCF6PwSnWFJIEASCAlrEgIhCwlk6fTynT+qOtwk3bdvdfdN3771eT1PPV117qlT53ae/uacOlXnKCIwM8ubmu6ugJlZd3DwM7NccvAzs1xy8DOzXHLwM7Nc6tXdFSg0dEhtjB3du7urYRk8+2S/7q6CZbCZDWyJenWmjGOO6B+r1zSVlHfuk/X3R8SUzlyvXCoq+I0d3ZtH7h/d3dWwDI7Zc1J3V8EyeDhmdrqM1WuaeOT+MSXlrR2xeGinL1gmFRX8zKzyBdBMc3dXo9Mc/MwskyBoiNK6vZXMwc/MMnPLz8xyJwiaquC1WAc/M8usGQc/M8uZAJoc/Mwsj9zyM7PcCaDB9/zMLG+CcLfXzHIooKnnxz4HPzPLJnnDo+dz8DOzjEQTnZoboSI4+JlZJsmAh4OfmeVM8pyfg5+Z5VCzW35mljfV0vLzNPZmlkkgmqgpaStG0mhJf5a0UNICSV9O04dImiFpcfpzcJouST+VtETSk5IOKCjrtDT/YkmnlfI9HPzMLLPmUElbOxqBCyNiInAwcL6kicBFwMyIGAfMTI8BjgXGpdvZwNWQBEvgYuD9wEHAxS0BsxgHPzPLJBBborakrWg5ESsi4rF0/03gaWAkcAJwU5rtJuAT6f4JwM2ReAgYJGkEcAwwIyLWRMRaYAbQ7rohvudnZpkkDzmX3G4aKmlOwfG1EXHt9pkkjQXeCzwMDI+IFelHrwLD0/2RwNKC05alaW2lF+XgZ2aZZRjwWBURk4tlkDQAuBP4SkSsl94uOyJCUllepnO318wyiRBNUVPS1h5JvUkC328i4vdp8mtpd5b058o0fTlQuLzjqDStrfSiHPzMLLNmVNJWjJIm3g3A0xFxRcFH04GWEdvTgLsK0j+XjvoeDKxLu8f3A0dLGpwOdBydphXlbq+ZZZIMeHRJ6PggcCrwlKR5adq3gR8Cd0g6A3gJ+FT62T3AccASYCNwOkBErJF0KfBomu+SiFjT3sUd/Mwsk4wDHm2XE/EXaLN5eGQr+QM4v42ypgJTs1zfwc/MMmvy621mljctb3j0dA5+ZpZZcwkjuZXOwc/MMkkmNnDwM7OcCURDO6+u9QQOfmaWSQQlPcBc6Rz8zCyj9h9g7gkc/Mwsk8AtPzPLKQ94mFnuBCVNVFrxHPzMLJNk6cqeHzp6/jcws53Mi5abWQ4FfsPDzHLKLT8zy50IueVnZvmTDHj49TYzyx35IWczy59kwKPn3/Pr+eHbzHa6JmpK2tojaaqklZLmF6TdLmleur3Ysr6HpLGSNhV8dk3BOQdKekrSEkk/VeH6l21wy8/MMuniNzxuBH4O3Ly1/IhPt+xLuhxYV5D/uYiY1Eo5VwNnkSx6fg8wBbi32IXd8jOzzJqpKWlrT0TMAlpdaS1tvX0KuLVYGenavrtGxEPpIkc3A59o79pu+ZlZJhHQ0Fxyu2mopDkFx9dGxLUlnvsh4LWIWFyQtpekx4H1wHciYjYwElhWkGdZmlaUg5+ZZZJ0e0sOfqsiYnIHL3UK27b6VgBjImK1pAOBP0h6VwfLdvAzs+zK/YaHpF7AJ4EDW9Iioh6oT/fnSnoO2BdYDowqOH1UmlaU7/l1wMrlvfnGSftw1ocncNbh45l2/VAAZt29G2cdPp4pI/fn2Sd22Zq/sQF+9OUxnPOR8Zx52ARu+9keWz97a10tl541ljM+NIEzD5vAwjn9dvr3yZuvXfEytz+5gF/+adHWtL0nbuLK6Yu5ZuYi/vWmF+g3oGmbc4aN3MIfFj/FSeeu3NnVrTgtj7qUsnXCUcAzEbG1OytpmKTadH9vYBzwfESsANZLOji9T/g54K72LlDW4CdpiqRF6fDzReW81s5U2ys4+3uvcN3/f4b/+ONi7r5xKC8924exEzbzvetf5N0Hb9gm/6y7B9FQL375p0X8/L5F3POroby6tA6Aq783ksmHr+eG2c9w9YOLGDOuvju+Uq48cPsQ/uWze22T9pUfL2XqD0Zw7pHj+eu9u3LSF7cNcudc/AqP/mngzqxmBUu6vaVs7ZYk3Qr8LzBe0jJJZ6QfncyOAx2HAU+mj778Djg3IloGS84DrgeWAM/RzkgvlLHbm0boXwAfJbkB+aik6RGxsFzX3Fl2H97I7sMbAeg3oJnR76xn1YreHPjht1rNL8HmjTU0NcKWzTX0qmum34AmNqyv4amH+vP1n7wMQO+6oHddU6tlWNeZ//AAho/ask3aqL3reeqh/gA8Pmsgl93yPDf/aAQAH5iyjleX1rF5oztKLbpqDY+IOKWN9M+3knYncGcb+ecA+2W5djn/NQ8ClkTE8xGxBbgNOKGM1+sWry6t47n5uzDhgI1t5vnQ8W/Qt18zp0zaj39830ROOvd1dh3cxKsv92G33Ru5/KtjOO+j+3LlhaP9B9ZNXnq2Lx+Ysh6ADx2/jmF7NgDQt18TnzpvJb++fHh3Vq+iJKO9tSVtlaycf2kjgaUFx60OP0s6W9IcSXNeX92zWj2bNtRw6ZljOfeS5fQf2NxmvkWP96emNrjl8fnc/PDT3HnNMFa8VEdTEyx5qh/Hf24VV814lr79mrn953u0WY6VzxVfG83HTlvFz+97ll0GNNG4JWnZnPr115h23TA2b6zsP+SdqeUh5zLf8yu7bh/tTZ/5uRZg8v59o5urU7LGBrj0zLF85JNrOfS4dUXz/nnaICYf8Sa9esOgoY1MfN8Gnn2iH+8++C2GjWjY2mo89Pg3uMPBr1ssXdKXb5+yDwAj967n/UcmrcAJ793IoX/3Bmd85xUG7NpENIst9TVM/8+h3VndbuelK4tbDowuOC5p+LkniIArLhzD6HH1/P05r7ebf9jIBub9ZQBHnbSWzRtreOax/px41usM2aORoXtuYemSPox+Zz3zZg/0gEc32W33Btat7o0UfObLr/HHX+0OwIUnvnNrnn+88FU2b3Dgq5aJDcoZ/B4FxknaiyTonQx8pozX22kWPNKfmb8bwl5/u4kvHjUegNO/9QoNW2q46jsjWbe6F989dW/2edcmfnDr83z89FVc/tUxnHX4eAhx9KdXs/fEzQCc//+W828XvIPGBvE3Y7Zw4ZUvd+dXy4WLrnqJ93zgLXYb0siv5yzkV5cPZ5d+zXzs86sA+Ou9u/HAbUO6uZaVrRomM1XyKlyZCpeOA34C1AJTI+KyYvkn7983Hrl/dLEsVmGO2XNSd1fBMng4ZrI+1nSq2TZ4wh7xkaknlZT39x+8em4n3vAoq7Le84uIe0hmWDCzKuJur5nlju/5mVluOfiZWe508WSm3cbBz8wy83N+ZpY7EdBY+mSmFcvBz8wyc7fXzHLH9/zMLLfCwc/M8sgDHmaWOxG+52dmuSSaqmC0t+d/AzPb6SJU0tYeSVMlrZQ0vyDt+5KWS5qXbscVfPatdE2gRZKOKUjPvF6Qg5+ZZdLFq7fdCExpJf3KiJiUbvcASJpIMjXeu9JzrpJUW7Be0LHAROCUNG9R7vaaWTaR3PfrkqIiZkkaW2L2E4Db0vV7X5C0hGStIEjXCwKQ1LJeUNHF0tzyM7PMmlFJGzC0ZY2edDu7xEtcIOnJtFs8OE1ra12gktYL2p5bfmaWSWQb8FjVgclMrwYuJelhXwpcDnwhYxntcvAzs8zKOAE8EfFay76k64A/pofF1gXKvF6Qu71mlllXjfa2RtKIgsMTgZaR4OnAyZL6pGsDjQMeoWC9IEl1JIMi09u7jlt+ZpZJRNe93ibpVuBwknuDy4CLgcMlTSLp9r4InJNcNxZIuoNkIKMROD8imtJyLgDu5+31gha0d20HPzPLrKve8IiIU1pJvqFI/suAHRZC68h6QQ5+ZpZZOe/57SwOfmaWSSCaq+D1Ngc/M8usChp+Dn5mllEXDnh0Jwc/M8uuCpp+Dn5mlllVt/wk/Ywi8T0ivlSWGplZRQugubmKgx8wZ6fVwsx6jgCqueUXETcVHkvqFxEby18lM6t01fCcX7sP60j6gKSFwDPp8f6Srip7zcysckWJWwUr5UnFnwDHAKsBIuIJ4LAy1snMKlppkxpU+qBISaO9EbFU2uaLNJWnOmbWI1R4q64UpQS/pZIOAUJSb+DLwNPlrZaZVayAqILR3lK6vecC55NMC/0KMCk9NrPcUolb5Wq35RcRq4DP7oS6mFlPUQXd3lJGe/eWdLek19P1Ne+StPfOqJyZVaicjPbeAtwBjAD2BH4L3FrOSplZBWt5yLmUrYKVEvz6RcSvIqIx3X4N9C13xcysckWUtlWyNoOfpCGShgD3SrpI0lhJ75D0TTJOF21mVaZZpW3tSNflXSlpfkHajyQ9k67bO03SoDR9rKRNkual2zUF5xwo6SlJSyT9VNs9m9eaYgMec0kauC2FnFPwWQDfavebmVlVUte16m4Efg7cXJA2A/hWRDRK+jeSWPPP6WfPRcSkVsq5GjgLeJikcTYFuLfYhYu927tXiZU3szzpwsGMiJglaex2aQ8UHD4EnFSsjHSpy10j4qH0+GbgE3Q0+G1X+H7ARAru9UXEzW2fYWbVa6cOZnwBuL3geC9JjwPrge9ExGySZ5CXFeRZlqYV1W7wk3QxybqaE0mak8cCf2HbZqqZ5UnpLb+hkgqnx7s2Iq4t5URJ/0KyPu9v0qQVwJiIWC3pQOAPkt5Vck22U0rL7yRgf+DxiDhd0nDg1x29oJlVgeaSc66KiMlZi5f0eeB44MiIZNw4IuqB+nR/rqTngH2B5cCogtNHpWlFlfKoy6aIaAYaJe0KrARGZ/geZlZNyvycn6QpwDeBjxfOISppmKTadH9vYBzwfESsANZLOjgd5f0ccFd71yml5TcnHWq+jmQE+C3gfzN+HzOrIl012ivpVpLbakMlLQMuJhnd7QPMSJ9YeSgiziWZSu8SSQ0kbc9zI2JNWtR5JCPHu5AMdBQd7IDS3u09L929RtJ9JKMqT5b87cys+nTdaO8prSTf0EbeO4E72/hsDrBflmsXW8DogGKfRcRjWS5kZlZJirX8Li/yWQAf6eK68MzSYRz6pXPaz2gVY+z/LOruKlgGvU+v7ZJyuvAh525T7CHnI3ZmRcyshwhKenWt0nnRcjPLrppbfmZmbanqbq+ZWZuqIPiVMpOzJP2jpO+lx2MkHVT+qplZxcrJTM5XAR8AWp7HeRP4RdlqZGYVTVH6VslK6fa+PyIOSGdSICLWSqorc73MrJLlZLS3IX2fLiB5v44srzWbWdWp9FZdKUrp9v4UmAbsIekykumsflDWWplZZauCe36lvNv7G0lzgSNJprT/REQ8XfaamVll6gH380pRymSmY4CNwN2FaRHxcjkrZmYVLA/BD/gv3l7IqC+wF7AI6PAMqmbWs6kK7vqX0u19d+FxOtvLeW1kNzPrETK/4RERj0l6fzkqY2Y9RB66vZK+VnBYAxwAvFK2GplZZcvLgAcwsGC/keQeYKuzqZpZTlR78Esfbh4YEV/fSfUxs56gCoJfmw85S+oVEU3AB3difcyswolktLeUrd2ypKmSVkqaX5A2RNIMSYvTn4PTdEn6qaQlkp4sXGpD0mlp/sWSTivlexR7w+OR9Oc8SdMlnSrpky1bKYWbWRXq2okNbgSmbJd2ETAzIsYBM9NjgGNJlqscB5wNXA1JsCRZ9e39wEHAxS0Bs5hSXm/rC6wmWbPjeOBj6U8zy6suer0tImYBa7ZLPgG4Kd2/CfhEQfrNkXgIGCRpBHAMMCMi1kTEWmAGOwbUHRS757dHOtI7n7cfct5a5/YKNrMqVnoEGCppTsHxtRFxbTvnDE8XIgd4FRie7o8ElhbkW5amtZVeVLHgVwsMYNug18LBzyzHMjzqsioiJnf0OhERUnkerCkW/FZExCXluKiZ9XDlbf68JmlERKxIu7Ur0/TlwOiCfKPStOXA4dul/3d7Fyl2z6/nz1ZoZl0vum60tw3TgZYR29OAuwrSP5eO+h4MrEu7x/cDR0sanA50HJ2mFVWs5Xdkh6tuZtWti1p+km4labUNlbSMZNT2h8Adks4AXgI+lWa/BzgOWEIy09TpABGxRtKlwKNpvksiYvtBlB0UW7S83ZPNLJ+66i5cRJzSxkc7NL4iIoDz2yhnKjA1y7W9dKWZZVcFQ54OfmaWTQ+Yor4UDn5mlonIz6wuZmbbcPAzs3xy8DOzXHLwM7PcydFMzmZm23LwM7M8ysXSlWZm23O318zyxw85m1luOfiZWd74DQ8zyy019/zo5+BnZtn4np+Z5ZW7vWaWTw5+ZpZH1dDyK2XRcjOzbXXBouWSxkuaV7Ctl/QVSd+XtLwg/biCc74laYmkRZKO6cxXcMvPzLKJrnm9LSIWAZMAJNWSLEE5jWRhoisj4seF+SVNBE4G3gXsCTwoad+IaOrI9d3yM7NMWp7zK2XL4EjguYh4qUieE4DbIqI+Il4gWcXtoI5+Dwc/M8suorQtWZJyTsF2dhslngzcWnB8gaQnJU1N1+IFGAksLcizLE3rEAc/M8ssQ8tvVURMLtiu3aEsqQ74OPDbNOlqYB+SLvEK4PJyfAff8+uk0Xu8wSWfn7n1eM+h67n+nsmseqM/Xzh2Lu8YvpazLj+RRUuHAdCrtolvfHo2E8a8ToT4jzsP4fEle3ZX9XPjzcs2Uv/XBmoGiyG/2XVr+qbf1rPpznqohbpDejPg/F3YfP8WNt6yeWuepiXNDP7PAfTatxebH9zCxps2Q/Pb+XOn6x9yPhZ4LCJeA2j5CSDpOuCP6eFyYHTBeaPStA4pW/CTNBU4HlgZEfuV6zrdbenKQZz+738PQI2amXbpb5j1xFj61jXy7Rs+yjc/PXub/B8/5BkATvvhPzBowCYu/+K9nPnjE4nQTq97nvQ5ro6+J9Xx5iUbt6ZtmdtA/ewGBt88ENWJ5jXJXfy+x9TR95g6ABqfa2LdP2+g1769aF7XzIZfbGLw1IHUDK5h/aUb2DKngbrJvbvlO3WnLp7P7xQKurySRkTEivTwRGB+uj8duEXSFSQDHuOARzp60XJ2e28EppSx/Ipz4PhXWL5qV15bO5CXXhvM0pWDdsgz9m/W8tjipKX3xlu78ObGOiaMfn0n1zR/6t7bi5pdt/0PZvO0LfQ7tQ+qS9Jrhuz457B5xhb6HpUEt6blzdSOqqVmcJKvbnJv6v/cUOaaVyY1l7a1W47UH/go8PuC5H+X9JSkJ4EjgK8CRMQC4A5gIXAfcH5HR3qhjMEvImYBa8pVfiU66oAlPDh3n6J5lizfnUP3e4nammZGDFnP+NGr2GPwWzuphlaocWkTDU80svbMN3njvDdpWNi4Q576Bxvo89GkFVg7qoaml5toWtFENAb1sxtoXlkFUxpnFWQZ8CheVMSGiNg9ItYVpJ0aEe+OiPdExMcLWoFExGURsU9EjI+IezvzNbr9nl86+nM2QF2/Qd1bmU7oVdvEB/d7iWvuLj7y/l8Pjecdw9dy/den8eraAcx/YTjNzR536haN0Lw+GHTdABqfbmL9dzcy5HcDkZKWYMOCRtQXeu1TC0DNrjUM+EY/1n93Iwh6v7sXTcs73PDo0arhDY9uD37p6M+1AAOGjO6xv9KDJy7l2WVDWftmv6L5mppr+Nm0Q7YeX/3Vu1j6+m7lrp61omaPGvp8uDeS6D2xFwjijUCDk+BX2Opr0efQ3vQ5NOkGb/pDMlCSSz32L/VtbnJ0kaTL+8528/Xp3UjfuuQ+0eTxy2hqEi++Orids6wc+hzWm4bHkq5u48tN0BhoUBL4ojmon/n2/b4WLYMizeub2TStnr4f2zY45kGZHnLe6bq95VcN+tY18L4Jy/nR7YdtTTvsPS/wlZP+h0EDNvGjc+5j8fLdufDq4xg8cBNXfPEemkOsWtefS391RDfWPD/Wf28DDY830vxGsPqEdfQ7sy99j6/jzcs2suaz61FvMfA7/d7u8s5rpGZ4DbUjt23avfWTTTQuSbq6/U7vS68xOWz6RVTFZKaKEm5Kdqhg6VbgcGAo8BpwcUTcUOycAUNGx3uO+nJZ6mPlMfZri7q7CpbB/af/gdVPv96p56oGDhoV7z2stL/T2Xd/c25ETO7M9cqlbC2/iDilXGWbWfeq9C5tKdztNbNsAqiCbq+Dn5ll1/Njn4OfmWXnbq+Z5VI1jPY6+JlZNl660szyKHnIuedHPwc/M8uuCuZzcPAzs8zc8jOz/PE9PzPLp+p4t9fBz8yyc7fXzHKnixYt726ez8/MsuuiaewlvZiu1zFP0pw0bYikGZIWpz8Hp+mS9FNJS9I1fQ/ozFdw8DOz7KLErTRHRMSkgqmvLgJmRsQ4YGZ6DMkSl+PS7WyS9X07zMHPzDJTc3NJWwedANyU7t8EfKIg/eZIPAQMkjSioxdx8DOzbILkIedSNhgqaU7BdnYrpT0gaW7BZ8MLVmx7FRie7o8ElhacuyxN6xAPeJhZJiKyPOS8qp2ZnA+NiOWS9gBmSHqm8MOICKk8c8i45Wdm2XXdur3L058rgWnAQcBrLd3Z9OfKNPtyYHTB6aPStA5x8DOz7Log+EnqL2lgyz5wNDAfmA6clmY7Dbgr3Z8OfC4d9T0YWFe4oHlW7vaaWTYt9/w6bzgwLV0xrxdwS0TcJ+lR4A5JZwAvAZ9K898DHAcsATYCp3fm4g5+ZpZZJ0Zyt4qI54H9W0lfDRzZSnoA53f6wikHPzPLqLT7eZXOwc/Msgkc/Mwsp6rg3V4HPzPLzJOZmlk+OfiZWe5EQFPP7/c6+JlZdm75mVkuOfiZWe4E4DU8zCx/AsL3/MwsbwIPeJhZTvmen5nlkoOfmeWPJzYwszwKoAumtOpuDn5mlp1bfmaWP369zczyKCD8nJ+Z5VIVvOHh1dvMLLuuWb1ttKQ/S1ooaYGkL6fp35e0XNK8dDuu4JxvSVoiaZGkYzrzFdzyM7NsIrpqtLcRuDAiHkuXsJwraUb62ZUR8ePCzJImAicD7wL2BB6UtG9ENHXk4m75mVl2XdDyi4gVEfFYuv8m8DQwssgpJwC3RUR9RLxAsoTlQR39Cg5+ZpZREE1NJW3AUElzCrazWytR0ljgvcDDadIFkp6UNFXS4DRtJLC04LRlFA+WRTn4mVk2LVNalbLBqoiYXLBdu31xkgYAdwJfiYj1wNXAPsAkYAVweTm+hu/5mVl2XfSoi6TeJIHvNxHxe4CIeK3g8+uAP6aHy4HRBaePStM6xC0/M8skgGiOkrZiJAm4AXg6Iq4oSB9RkO1EYH66Px04WVIfSXsB44BHOvo93PIzs2yiyyYz/SBwKvCUpHlp2reBUyRNIomzLwLnJJeNBZLuABaSjBSf39GRXnDwM7MOSAczOldGxF8AtfLRPUXOuQy4rNMXBxQV9IKypNeBl7q7HmUwFFjV3ZWwTKr13+wdETGsMwVIuo/k91OKVRExpTPXK5eKCn7VStKciJjc3fWw0vnfrPp5wMPMcsnBz8xyycFv59jhwU6reP43q3K+52dmueSWn5nlkoOfmeWSg18ZSZqSTrq4RNJF3V0fa186i8hKSfPbz209mYNfmUiqBX4BHAtMJHllZ2L31spKcCNQkQ/lWtdy8Cufg4AlEfF8RGwBbiOZjNEqWETMAtZ0dz2s/Bz8yqdLJ140s67l4GdmueTgVz5dOvGimXUtB7/yeRQYJ2kvSXUkq05N7+Y6mVnKwa9MIqIRuAC4n2RVqjsiYkH31sraI+lW4H+B8ZKWSTqju+tk5eHX28wsl9zyM7NccvAzs1xy8DOzXHLwM7NccvAzs1xy8OtBJDVJmidpvqTfSurXibJulHRSun99sUkXJB0u6ZAOXONFSTus8tVW+nZ53sp4re9L+nrWOlp+Ofj1LJsiYlJE7AdsAc4t/FBSh9ZhjogzI2JhkSyHA5mDn1klc/DruWYD70xbZbMlTQcWSqqV9CNJj0p6UtI5AEr8PJ1f8EFgj5aCJP23pMnp/hRJj0l6QtJMSWNJguxX01bnhyQNk3Rneo1HJX0wPXd3SQ9IWiDpelpfkHobkv4gaW56ztnbfXZlmj5T0rA0bR9J96XnzJY0oUt+m5Y7HWopWPdKW3jHAvelSQcA+0XEC2kAWRcR75PUB/irpAeA9wLjSeYWHA4sBKZuV+4w4DrgsLSsIRGxRtI1wFsR8eM03y3AlRHxF0ljSN5i+VvgYuAvEXGJpL8DSnk74gvpNXYBHpV0Z0SsBvoDcyLiq5K+l5Z9AcnCQudGxGJJ7weuAj7SgV+j5ZyDX8+yi6R56f5s4AaS7ugjEfFCmn408J6W+3nAbsA44DDg1ohoAl6R9KdWyj8YmNVSVkS0Na/dUcBEaWvDbldJA9JrfDI9978krS3hO31J0onp/ui0rquBZuD2NP3XwO/TaxwC/Lbg2n1KuIbZDhz8epZNETGpMCENAhsKk4B/ioj7t8t3XBfWowY4OCI2t1KXkkk6nCSQfiAiNkr6b6BvG9kjve4b2/8OzDrC9/yqz/3AFyX1BpC0r6T+wCzg0+k9wRHAEa2c+xBwmKS90nOHpOlvAgML8j0A/FPLgaRJ6e4s4DNp2rHA4HbquhuwNg18E0hani1qgJbW62dIutPrgRck/UN6DUnav51rmLXKwa/6XE9yP++xdBGeX5K08KcBi9PPbiaZuWQbEfE6cDZJF/MJ3u523g2c2DLgAXwJmJwOqCzk7VHnfyUJngtIur8vt1PX+4Bekp4GfkgSfFtsAA5Kv8NHgEvS9M8CZ6T1W4CXBrAO8qwuZpZLbvmZWS45+JlZLjn4mVkuOfiZWS45+JlZLjn4mVkuOfiZWS79Hyvp+0pH8MfJAAAAAElFTkSuQmCC"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Model-4:-KNN">Model 4: KNN<a class="anchor-link" href="#Model-4:-KNN">&#182;</a></h4>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.neighbors</span> <span class="kn">import</span> <span class="n">KNeighborsClassifier</span>
<span class="n">neigh</span> <span class="o">=</span> <span class="n">KNeighborsClassifier</span><span class="p">(</span><span class="n">n_neighbors</span><span class="o">=</span><span class="mi">2</span><span class="p">)</span>
<span class="n">neigh</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
<span class="n">prediction_neigh</span> <span class="o">=</span> <span class="n">neigh</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">prediction_neigh</span><span class="p">,</span> <span class="n">target_names</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;No churn&#39;</span><span class="p">,</span> <span class="s1">&#39;Churn&#39;</span><span class="p">]))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

    No churn       0.68      0.90      0.77      2380
       Churn       0.85      0.58      0.69      2398

    accuracy                           0.74      4778
   macro avg       0.76      0.74      0.73      4778
weighted avg       0.76      0.74      0.73      4778

</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plot_confusion_matrix</span><span class="p">(</span><span class="n">neigh</span><span class="p">,</span> <span class="n">X_test</span><span class="p">,</span> <span class="n">y_test</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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"
>
</div>

</div>

</div>

</div>

</div>
</body>







</html>
```
