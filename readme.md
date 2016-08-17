# Sublime Terminal

My personal fork of the great [sublime_terminal by Will Bond](https://github.com/wbond/sublime_terminal). (Many, many thanks Will!)

When working with Sublime Text I constantly use Will's plugin to open terminal windows, both `cmd.exe` and `git-bash.exe`. (Yes, I'm a Windows user...)

Due to the fact that the `terminal` setting could only be set once in the user settings file, I finally choose `cmd.exe` as my default. This resulted in having a spare `cmd` floating in my desktop every time I opened a `bash` window from ST, as the `bash` window was called from the default `cmd`.

After some settings tweaking I could avoid the effect in one of my computers, but when trying to do it by memory on another computer I couldn't remember the *trick*. So, I decided to go the long path... modifying the plugin so it works the way I expect.

What I wanted was to be able to specify a different `terminal` for every one of my keyboard shortcuts, so I can choose amongst a couple more CLIs.

This README only adds specifics about my changes, and complements the [original README](https://github.com/wbond/sublime_terminal/blob/master/readme.md). Please read it before reading this document.

## Features (fork)

 - Allows setting a different `terminal` for different keyboard combinations.

## Installation (fork)

The easiest way to go is:

* Make sure you have [Package Control](https://packagecontrol.io) installed.
* Install the original [Terminal](https://packagecontrol.io/packages/Terminal) using Package Control.
* Download a ZIP version of this repo
* Manually replace the contents of your `packages/terminal` folder.

If you prefer to do it the *git way*, you should already know how to do it. (sorry if you don't)

### Examples (fork)

I will use my own configuration as an example.

Note that I'm leaving the configuration on `terminal.sublime-settings` empty and set all preferences in my keyboard shortcuts.

The contents of `terminal.sublime-settings` for all examples is:
```js
{
  "terminal": "",
  "parameters": [ ]
}
```

#### cmd.exe

`default.sublime.keymap`
```js
    {
      "keys": ["ctrl+shift+t"],
      "command": "open_terminal",
      "args": {
        "terminal": "cmd.exe",
        "parameters": [ "/K", "mode con: cols=200" ]
      }
   },
```

#### git-bash.exe

`default.sublime.keymap`
```js
    {
      "keys": ["ctrl+alt+t"],
      "command": "open_terminal",
      "args": {
        "terminal": "git-bash.exe",
        "parameters": [ "-a" ]
      }
    },
```

#### python console

`default.sublime.keymap`
```js
    {
      "keys": ["ctrl+alt+p"],
      "command": "open_terminal",
      "args": {
        "terminal": "python.exe",
        "parameters": [ ]
      }
    },
```

#### Node.JS console

`default.sublime.keymap`
```js
    {
      "keys": ["ctrl+alt+n"],
      "command": "open_terminal",
      "args": {
        "terminal": "node.exe",
        "parameters": [ ]
      }
    },
```

## Custom Parameters (fork)

The only thing modified in this fork is that the `terminal` setting in `terminal.sublime-settings` can now be overriden in `default.sublime.keymap`.
