### Project: Babel

[Babel](https://github.com/babel/babel) lets you use next-generation JavaScript while still supporting older browsers. Babel will compile your JavaScript into JavaScript that all of your targeted environments support.

### My Contributions

These are my merged PRs:

- [Fix scope of function body when var redeclares param](https://github.com/babel/babel/pull/11158)
- [Allow redeclaration of loop variable in body](https://github.com/babel/babel/pull/11088)

Compiling certain features such as default parameters and for-of loops to 'old' JavaScript that doesn't have such features result in many edge cases that are unaccounted for. I helped to fix these bugs.


### My Observations

#### Comprehensive contributing guide
Babel's [contributing](https://github.com/babel/babel/blob/master/CONTRIBUTING.md) guide lists all the steps needed to build and test Babel in an easy to follow manner. Also, it lists where to get help (their Slack channel), how to submit PRs, and lots of other important information.
#### Poor documentation
Even big projects like Babel can be lacking in documentation. It was difficult to get started with Babel, since the project was so huge and it took many hours of trial and error to figure out where to even start. They had some small guides on their Abstract Syntax Tree and how to write plugins, but that was it. This unfortunately seems to be an issue with many projects as I faced the same difficulty when first starting out with MarkBind. Nonetheless, it would be great for these projects (and other projects too) to have better documentation. Not just so that it would be easier for new contributers like myself to submit PRs, but also for all maintainers to know why a certain thing was written that way a few years down the road.
#### Precise specification
In contrast with its lacking documentation (i.e. how to implement a feature), it was comparatively easy to know what that feature should do. Babel tries to implement the latest [ECMAScript specification](https://tc39.es/ecma262/), and the specification provides a very detailed explanation of exactly how a language feature (e.g. default parameters) should work. This is why bugs reported in Babel can be determined to be legitimate objectively and quickly: reference the specification and that's it! 

This aspect is very different as compared to other compiler projects out there (inclduing MarkBind). MarkBind, React, Vue, etc are all projects where their specification is also a part of the project, and so when a legitimate bug is reported  with regards to the syntax, the bug could either be a bug in the specification (but implementation correctly follows the specification), a bug in the implementation (does not correctly follow the specification), or maybe even both. 

Should MarkBind have a formal specification? It currently uses a mix of several different syntax, so unless a custom MarkBind parser is written we probably have no reason to do so.
#### Easy testing
The nature of Babel (compiling JavaScript into JavaScript) nicely gives rise to its test suite: One folder for each test, with each folder containing 2 files, `input.js` and `output.js`. `input.js` contains the code to be transpiled, and `output.js` contains the expected output. Adding and updating files are therefore really easy. Of course, there are other tests in Babel, but the one I described is the most commonly used. In a way, Babel is very similar to MarkBind, in that they are both compilers.

MarkBind currently tests Markbind snippets via the use of test sites, where there are a few test sites with many `.md` files that make up a full site. Then, the expected HTML output of all these files are stored in a separate folder. This makes it hard to compare the input and output, since location-wise the source MarkBind file and the output HTML file are quite far apart. It might be feasible for us to introduce this method of testing, or even rewrite our current test suite. Then test updates would also be more modular, as all additions would be entirely confined to an new folder, resulting in easier code reviews as well!
#### Easily reproducible bug reports
You can easily share a code snippet on the [Babel playground](https://babeljs.io/repl). You can choose between many different configuration options, plugins, and versions, and also share the link to the exact state of your REPL. This makes it an ideal way to submit bug reports, where anyone can read the issue and then click on the link that reproduces the issue exactly. This would eliminate many "unable to reproduce" bugs in practice, since the reporter can verify bugs on the playground itself before reporting.
MarkBind might be able to implement this to a certain degree, such as self-contained MarkBind syntax that does not reference other files. This would allow easier verification of bugs, since developers can simply click on a link and see the bug in action instead of having to copy the offending code over and then building the site. However, we wouldn't be able to call this a true "MarkBind playground" since it does not include all features of MarkBind. 
