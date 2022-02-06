---
id: XGynaZczE1ZM7e7HKVE6g
title: Keybindings
desc: ''
updated: 1634236684643
created: 1634193873243
---


Keep getting overwritten by Settings Sync!


```
// Place your key bindings in this file to override the defaults
[
    {
        "key": "ctrl+;",
        "command": "workbench.action.terminal.focus"
    },
    {
        "key": "ctrl+;",
        "command": "workbench.action.focusActiveEditorGroup",
        "when": "terminalFocus"
    },
    {
        "key": "ctrl+shift+v",
        "command": "-markdown.showPreview",
        "when": "!notebookEditorFocused && editorLangId == 'markdown'"
    },
    {
        "key": "ctrl+shift+v",
        "command": "dendron.showPreviewV2",
        "when": "!notebookEditorFocused && editorLangId == 'markdown'"
    },
    {
        "key": "ctrl+k",
        "command": "dendron.insertNoteLink"
    },
    {
        "key": "ctrl+'",
        "command": "dendron.gotoNote",
        "when": "editorFocus"
    },
    {
        "key": "ctrl+enter",
        "command": "-dendron.gotoNote",
        "when": "editorFocus"
    },
    {
        "key": "ctrl+m",
        "command": "-markdown.extension.editing.toggleMath",
        "when": "editorTextFocus && !editorReadonly && editorLangId == 'markdown'"
    },
    {
        "key": "ctrl+m",
        "command": "-editor.action.toggleTabFocusMode"
    },
    {
        "key": "ctrl+m",
        "command": "dendron.moveNote",
        "when": "editorLangId == 'markdown'"

    }
]
```
