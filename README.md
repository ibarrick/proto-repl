# Proto REPL

Proto REPL is a Clojure development environment and REPL for [Atom](https://atom.io). See the [features](#features) and [installation instructions](#installation).

![A screenshot of Proto REPL](https://github.com/jasongilman/proto-repl/raw/master/front_image.png)

## Features

* An interactive REPL driven development environment.
* Evaluate blocks of code or selected code with a keystroke.
* Easily run tests in a namespace or the whole project.
* View documentation and code from linked Clojure libraries.
* [Atom Tool Bar](https://atom.io/packages/tool-bar) integration that allows controlling the REPL.

## Running the REPL

Proto REPL currently only works with projects using [Leiningen](http://leiningen.org).

1. Open your Clojure project in Atom. (See [the Leiningen tutorial](https://github.com/technomancy/leiningen/blob/stable/doc/TUTORIAL.md#creating-a-project) for help creating a new project.)
2. Start the REPL using one of the following methods.


* Use the keyboard shortcut - cmd-alt-L
* Select the menu item "Packages" -> "proto-repl" -> "Start REPL"
* Bring up the Command Palette (cmd-alt-p) and select "Proto REPL: Toggle"

### About the REPL

The REPL in Proto REPL is not a typical REPL. It's more of a text editor that is the target for output from REPL execution. You can type anywhere and modify any of the displayed text. Commands are not sent by typing in the REPL and pressing enter. They are sent through keyboard shortcuts. (See the [key bindings](#keybindings-and-events) for executing blocks or selected text below.) You will typically type Clojure forms in one text editor and send them to the REPL for evaluation. You continue the cycle of code modification and REPL evaluation until it does what you want it to do.

### Limitations

These are known current limitations of Proto REPL. They may be addressed in the future.

* Currently only works with Leiningen projects.
* You can only start one REPL per Atom window.

## Installation

`apm install proto-repl` or go to your Atom settings, select "+ Install" and search for "proto-repl".

### Dependencies

* [Java](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
* [Leiningen](http://leiningen.org)

### Tool Bar Integration

Proto REPL integrates with the [Atom Tool Bar package](https://atom.io/packages/tool-bar) to provide buttons for common REPL actions. Install tool-bar and then restart Proto REPL to get quick access to actions like refreshing namespaces, pretty printing, and toggling REPL scrolling.

### Recommend Atom Settings

Change the "Non Word Characters" setting in Atom to

```
()\"':,;<>~#$%^&*|+=`…
```

Doing this allows you to select namespaces with var definitions in Clojure as a single word.

### Recommended Additional Packages

These packages go well with Proto REPL.

* [tool-bar](https://atom.io/packages/tool-bar)
* [lisp-paredit](https://atom.io/packages/lisp-paredit)

## Keybindings and Events

| Keybinding        | Event                                 | Action                                                                                                                                   |
|-------------------|---------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| `cmd-alt-L`       | `proto-repl:toggle`                   | Starts the REPL                                                                                                                          |
| `ctrl-L`          | `proto-repl:clear-repl`               | Clears REPL Output                                                                                                                       |
| `ctrl-d`          | `proto-repl:exit-repl`                | Exits the REPL                                                                                                                           |
| `cmd-alt-shift-s` | `proto-repl:toggle-auto-scroll`       | Enables/Disables autoscrolling the REPL                                                                                                  |
| `cmd-alt-b`       | `proto-repl:execute-block`            | Sends the current block of Clojure code to the REPL for execution.                                                                       |
| `cmd-alt-s`       | `proto-repl:execute-selected-text`    | Sends the selected text to the REPL for execution.                                                                                       |
| `cmd-alt-shift-f` | `proto-repl:load-current-file`        | Loads the current file in the repl.                                                                                                      |
| `cmd-alt-r`       | `proto-repl:refresh-namespaces`       | Runs the `user/reset` function. See [My Clojure Workflow, Reloaded](http://thinkrelevance.com/blog/2013/06/04/clojure-workflow-reloaded) |
| `cmd-alt-shift-r` | `proto-repl:super-refresh-namespaces` | Clears all loaded namespaces using `clojure.tools.namespace` the runs the `user/reset` function.                                         |
| `cmd-alt-p`       | `proto-repl:pretty-print`             | Pretty prints the last value returned at the REPL.                                                                                       |
| `cmd-alt-x`       | `proto-repl:run-tests-in-namespace`   | Runs all the tests in the current namespace.                                                                                             |
| `cmd-alt-t`       | `proto-repl:run-selected-test`        | Runs the test that's selected.                                                                                                           |
| `cmd-alt-a`       | `proto-repl:run-all-tests`            | Runs all the test in the current project.                                                                                                |
| `cmd-alt-d`       | `proto-repl:print-var-documentation`  | Prints the documentation with the current selected var.                                                                                  |
| `cmd-alt-c`       | `proto-repl:print-var-code`           | Prints out the code of the current selected var.                                                                                         |
| `cmd-alt-o`       | `proto-repl:open-file-containing-var` | Opens the code of the current selected var or namespace. This works even with vars defined in libraries.                                 |
| `cmd-alt-n`       | `proto-repl:list-ns-vars`             | Lists the vars in the selected namespace.                                                                                                |
| `cmd-alt-shift-n` | `proto-repl:list-ns-vars-with-docs`   | Lists the vars in the selected namespace with documentation.                                                                             |


## Potential Future Enhancements

* Ability to connect to existing Clojure processes using nrepl.
* Visualize function call graph.
