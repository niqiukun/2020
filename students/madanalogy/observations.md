### Project: OWASP Zed-Attack-Proxy (ZAP)

[ZAP](https://www.zaproxy.org) is a flagship project from the Open Web Application Security Project ([OWASP](https://owasp.org)) that has become the world's most popular free, open source web security tool. ZAP is actively used by penetration testers and security specialists worldwide, maintained by a dedicated international team of volunteers. Under the hood, ZAP is a complex and mature Java desktop application created for web application security testing with an experienced and dedicated core of developers and maintainers.

### My Contributions

#### Enhancement: CSRF Token Regeneration in HTTP Manual Resend

I added a button to the HTTP manual resend screen in ZAP core to enable regeneration of the Anti-CSRF token if any were present. This addition was difficult as it involved code from the UI all the way to the HTTP APIs. Furthermore, extensive research on Cross Site Request Forgery (CSRF) attacks and their protection mechanisms was required to understand how to regenerate anti-csrf tokens and inject them into the HTTP request to be sent out.

Relevant PRs:
- [Add a button on the resend screen to inject a CSRF token #5828](https://github.com/zaproxy/zaproxy/pull/5828)
- [Add help message for Regenerate Anti-CSRF #301](https://github.com/zaproxy/zap-core-help/pull/301)

#### Enhancement: Passive Scan Rule for Dangerous JS Functions

I added a new passive scan rule to ZAP which would allow for the scanning of HTML and javascript responses to look for dangerous JS functions that could leave a web application vulnerable. The implementation for this was particularly difficult as the senior developers suggested I support a custom payload so that users can define their own functions to look for at runtime. On top of learning how HTML/JS is structured for effective scanning, I had to learn how to utilise a custom extension and manage dependencies in gradle.

Relevant PRs:
- [Add passive scan rule for dangerous js functions #2317](https://github.com/zaproxy/zap-extensions/pull/2317)
- [Update scanners.md for dangerous js function scanner id #5882](https://github.com/zaproxy/zaproxy/pull/5882)

### My Observations

#### External Project Workflow

ZAP has extensive documentation on contribution and development guidelines. In brief, they follow a forking workflow similar to most OSS projects, and require that PRs made be associated with issues raised. There was also a very useful blog post series outlining in detail how one can start contributing to ZAP.

Relevant Links:
- [Contributing to OWASP ZAP](https://github.com/zaproxy/zaproxy/blob/develop/CONTRIBUTING.md)
- [Development Rules & Guidelines](https://github.com/zaproxy/zaproxy/wiki/DevGuidelines)
- [Hack The ZAP Source Code](https://www.zaproxy.org/blog/2014-03-10-hacking-zap-1-why-should-you/)

#### Important Lessons Learned

I chose ZAP as my external project so that I could begin to develop expertise in both __Java__ and __Computer Security__. I learned a lot about functional interfaces, callback patterns, and method forwarding in Java. I also learned in greater depth how UI design and implementation is done in Java swing. One interesting lesson was how to operate multiple repositories in one workspace on IntelliJ. Since my external project had different git repositories interacting with each other, learning how to work with multiple modules using gradle was quite enlightening.

Equally as important was the knowledge I gained about web application security. The contributions I made to ZAP were highly non-trivial and required extensive research into security concepts. I learned a lot about the CSRF attack as well as professional defences against it in great detail. I was also exposed to a lot of application security concepts in breadth and have a much better appreciation for the topic now, with a firm grasp of the jargon involved.

Additionally, one of the most important lessons for me was learning how to ask for help. This was the first time I had to work on such a complex project that I couldn't easily understand how things worked. Learning to ask the right questions and getting over the fact that you just had no idea what was going on was a very humbling experience.

#### Suggestions for Internal Project

Currently, TEAMMATES requires a review from a "junior" developer followed by a review by a senior developer for PR merging or approval. In that sense, there exists two teams of starkly different authority over the application. The current two-tier structure limits the availability of developers with the capacity to deal with issues like stale PRs or design conflicts, and furthermore restricts the agency of the junior developer which consequently carries the potential to disincentivise them from further involvement.

One interesting practice of the external project that I feel could be adopted by TEAMMATES was the relatively flat maintainer hierarchy approach to resolving PRs and issues. In order to be merged, PRs in my external project required two approvals from the dev team. There only exists the one team, and two approvals from any member of the team suffices for resolving PRs. In that sense, each member of the dev team carried with them equal ownership over the project, which could be a very large motivating factor for continued involvement.

My suggestion is that a similar approach be taken with TEAMMATES, where either the function of the senior dev team gets expanded to allow inclusion of some junior developers or more authority is given to the junior development team (e.g. two reviews from a junior dev is equivalent to one from a senior dev). This helps provide the agency needed to sustain involvement and subsequently grow the application. The success of an open source project relies upon the developer experience, which is directly improved with a larger pool of dedicated maintainers to attend to new contributors and triage issues.
