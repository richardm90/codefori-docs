
## Project Scope

As of 2023, the Code for IBM i project has grown quite large. While Code for IBM i can generally mean many extensions, it actually refers to vscode-ibmi. The vscode-ibmi is the Code for IBM i extension which is the base for many other extensions.

![](../../assets/scope.png)

## Code for IBM i

vscode-ibmi generally provides the base user experience for application development on IBM i, this includes:

* Manage connections and maintain the connection for the user
* Opening and browsing objects/files in QSYS.LIB or the IFS
* Maintain and executing Actions to run commands on the server, usually to compile source code and show compile errors
* Maintain the user library list, current library and Profiles that will be used when Actions are run
* Provide a UI to the IBM i Debugger for ILE and OPM objects

vscode-ibmi manages the connection, but provides an API to which other extensions can utilise to do many things:

* Run ILE or pase commands on the connection server
* Parse and display EVFEVENT file results from the majority of ILE compilers (C, C++, COBOL, RPGLE, etc)
* Running SQL queries on the server
* List directories in multiple file systems (including QSYS.LIB and the IFS) as well as download/upload files and/or manage their content

**vscode-ibmi is not supposed to** provide tools for a specific language, runtime or feature. All the current functionality is generic as possible while keeping a lightweight experience.

## What if I want to add a new feature?

Consider where your feature really belongs.

* Are you building a feature for a specific language? Perhaps it belongs in one of the many language extensions (vscode-rpgle, vscode-clle, etc)
* Are you building a database UX feature? Then it likely belongs in the vscode-db2i extension
* Do you want to be able to view the contents of an object like a `BNDDIR`, `MSGF`, etc? Then it likely belongs in the vscode-ibmi-fs extension.
* Do you want to fix a bug in the base, or add a feature that is generic to IBM i and applies to all languages? Then perhaps it belongs in the base (vscode-ibmi)