#### Code style

Comments should be generally avoided. If the code would not be understood without comments, consider re-writing the code to make it self-explanatory.

##### Backend
Coding style is given by linter [standard](https://standardjs.com/)

##### Frontend
We will follow [angular style guide](https://angular.io/guide/styleguide) and ... (to be complete).

#### Documentation
Code should be annotated with [closure annotations](https://github.com/google/closure-compiler/wiki/Annotating-JavaScript-for-the-Closure-Compiler) and every entrypoint should be documented: function, classes, http url, websocket events etc

Project documentation should be a reminder for future development, so it should describe architectural or relevant or critial cases and should be essential but precise, ignoring common or trivial project parts.

#### Commit Messages

Commit should accomplish only one job and commit messages should follow the [semantic commit messages format](https://seesparkbox.com/foundry/semantic_commit_messages).

#### Tools
Recommended IDE is [Visual Studio Code](https://code.visualstudio.com/).

##### Backend
Add extension `vscode-standardjs` to Visual Studio Code to enable live linter checking and auto code formatting (follow extension instruction to install).

##### Frontend
(todo)

#### Git
We adopt [git flow](https://datasift.github.io/gitflow/IntroducingGitFlow.html).

### Data types
JSON schema  
**proposal** use `avro`  
https://github.com/mtth/avsc  
example in `/w7-microservice-auth/models/schema/User.js`  
**features**: define types, custom validation, compression in transmission

#### TODO

- Git Hooks  
are we going to use git hooks? (test and linter)

- Tests  
are we going to do tests?

- Code review  
are we going to do code review?
