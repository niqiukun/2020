### Project: [React Bootstrap](https://react-bootstrap.github.io/)

React-Bootstrap is a open source library of Bootstrap 4 components re-built with React, to be used with React.

**Links to documentation of project workflow:**

- [Contributing](https://github.com/react-bootstrap/react-bootstrap/blob/master/CONTRIBUTING.md)
- [Maintaining](https://github.com/react-bootstrap/react-bootstrap/blob/master/MAINTAINING.md)

### My Contributions

- [docs(Navs): Add missing documentation for NavDropdown on website #5041](https://github.com/react-bootstrap/react-bootstrap/pull/5041)
- [Make FormLabel support `as` prop #5044](https://github.com/react-bootstrap/react-bootstrap/pull/5044)

### My Observations

1. The use of a **sandbox environment with an intergrated editor**, particulary via codesandbox.io makes it easier to report bugs. One just needs to paste the corresponding source code, and the rendered output can be seen on the other half of the screen. Bug reporters would also give brief instructions, such as steps for reproduction or state what to focus on. The sandbox environment makes it easy for developers to see what bug is being reporting, and reproduce issues easily and quickly. It seems that for now, sandboxes in sandbox.io can be configured for popular libraries (such as Vue, React, Angular), it would be extremely nice to investigate how to configure one for MarkBind. Be it by talking to the developers of codesandbox.io or by building our own code playground ourselves.

1. Writing documentation comments on the attributes in javascript comment (in React terms, `props`), **automatically generates documentation** in the form of a table. This is acheived via the use of a [function/component](https://github.com/react-bootstrap/react-bootstrap/blob/master/www/src/components/ComponentApi.js) they made themselves. This makes the documentation and code always in sync, and also decreasing the number of places to update from the 2 places (the code, and the docs), to just 1 place (the code). This is easy for the project to implement because each React-Bootstrap component is isolated in its own React Javascript file. The closest thing we have similar in MarkBind would be vue-strap components. Unfortunately, it seems more difficult to do the same for MarkBind syntax, especially elements that use `markdown-it-attrs`.

1. The project encouraged **Test Driven Development**, which provided me a straightforward and pleasant experience when working on an enhancement. First, I add small unit test like the code block below representing my intended behavior. Then, I will code until I pass the test case. In MarkBind, I would have my own test site and add all the components and attributes I want to test for in the markdown file. While coding a feature, I would `serve` the test site and visually check if I have implemented my intended behavior. It works but is slightly a more clunky experience, and visual inspection is not always reliable. Why I did not use the existing snapshot-like testing tool MarkBind had, i.e. `npm run testwin`, is something worth further reflection/discussion with the MarkBind team. I know for sure, one thing I appreciated in React-Bootstrap, was that their **testing framework gave feedback via a delightful UI**, showing specific headings stating which component and what behavior is currently being tested. One could consider my observation a small nit, but in my opinion, it goes a long way in encouraging test driven development.

  ```js{heading="Adding an as prop with legend value should turn the DOM type to a legend"}
  it("accepts as prop", () => {
    mount(<FormLabel as="legend">body</FormLabel>).assertSingle("legend");
  });
  ```

4. **Public communication channels** are important for both users and developers of open source libraries. React-Bootstrap has a public Discord as an open channel for contributors, new and old, to come and discuss, or ask quick questions, regarding the project/workflow. I learnt from one of the maintainers in the channel that discussions over the project take place both in Github issues as well as in the Discord channel. To my knowledge, MarkBind has a Slack, but it seems to be invite only. Should MarkBind want to open up to public contributors, it should consider providing and promoting a public channel as well. When it comes to usage of the library, React-Bootstrap directs such questions to Stack Overflow with questions tagged `react-bootstrap`, or a different channel in their Discord suited for "How do I use X" type of queries.

1. **Code coverage** is a major issue for the project, starting June 11 2019 and almost completed. To organise efforts to increase the coverage of tests, a central hub was created in the form of a pinned Github issue. In it, was a checkbox list of links to a code coverage site (codecov.io) that detailed coverage per file, mostly those of the major components. From that page, interested contributors can indicate their interest to add tests for a specific component, preventing contributors from doing overlapping work.

1. The use of **Prettier** reduced the possibiliy of dealing with coding style nits, both as a contributor as well as a reviewer. Speeding the time taken to have a successful PR. Which can and had been suggested for MarkBind before.

1. These two observations are things worth taking note when a library/project matures. One of the issue raised was regarding adding **blog for future releases**, which is useful for users of the library to reference to when migrating to a newer release. MarkBind is still relatively young. But in the far future, when we might go to v3, we need to take not of having a point of reference for migrators. Another issue raised asked **what organisations are using React-Bootstrap**. Even though React-Bootstrap is `Used by` 198172 repos, even such a widely use library does not know if it's used by any major organisation. Unfortunately, only 2 organisations replied to that issue, which is now buried past the first page of issues. 

1. React-Bootstrap has a **repo of examples**. Which is useful for users to reference to. Beyond the 2 templates for Markbind, we can consider adding templates showing more in depth usage, or suited to a particular use case. For example, a 'portfolio site' template, or a 'module site' template.

1. **Lack of Triaging is not the end of the world** to a project. While exploring projects before React-Bootstrap, I realised that even the `good first issue` label isn't exactly useful. If anything, it's rarely utilised effectively/appropriately in most projects I've seen, or very quickly taken up. From my observations, if you have active maintainers commenting on issues, it does alot to encourage new contributors to take up tickets. There are better way to judge whether a project is in good health, such as by seeing that new PRs are merged to close to a day to day basis, as opposed to how colorful their issues are labelled.