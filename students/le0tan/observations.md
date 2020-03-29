### Project: Hugo / MyPy

[Hugo](https://github.com/gohugoio/hugo) is a static-site generator written in Go. It's most famous for its performance (under one second build time for most websites, claim to be the world's fastest website engine). My personal favorite feature of Hugo is [shortcodes](https://gohugo.io/content-management/shortcodes/#readout), which combines the simplicity and ease-of-use of Markdown and flexibility of templates.

**Links to contributor documentations of Hugo**

- [CONTRIBUTING.md](https://github.com/gohugoio/hugo/blob/master/CONTRIBUTING.md)
- [Contributors' forum](https://discourse.gohugo.io/)
- [Developer's Guide](https://gohugo.io/contribute/development/)
- [Documentation Guide](https://gohugo.io/contribute/documentation/)

### My Contributions

I have two merged PRs for Hugo:

- [Allow multiple arguments in ne/ge/gt/le/lt functions](https://github.com/gohugoio/hugo/pull/6775)
- [Add languageDirection to language configuration](https://github.com/gohugoio/hugo/pull/7038)

And two merged documentation PRs for MyPy and ZeroMQ respectively:

- [Update common issues to include __init__ without arguments](https://github.com/python/mypy/pull/8303)
- [Problem: minor typo in hello_world c/cpp examples](https://github.com/zeromq/zeromq.org/pull/73)

### My Observations

#### Babysitter-like Contribution Guide

Hugo's contribution guide is for anyone who's willing to contribute even if he/she doesn't have any experience in Go, GitHub or how Hugo works in specific. The content is written in a tutorial-like fashion with each step explicitly explained. It includes a ton of introductory learning resources for newcomers to refer to and takes different development environments into consideration (Mac/Windows/Linux).

It covers the following key points that are common for any type of contribution:
- how to build and live-test the modified version
- how to run the test suite and auto-formatter
- how to amend/squash commits such that the contribution follows the guide

While it is true that people can easily search for solutions online (e.g. various methods for changing the Git history), including these information in the exact order of build -> test -> format -> cleanup commits would not only make the contributors' life easier, but also avoid many non-standardized pull requests for the reviewers to spend time on. It's a huge waste of time when the PR is generally OK with minor non-compliance here and there.

#### Forum for Discussion

While GitHub issues can be used as a forum, sometimes it's not ideal for people to create an issue simply because they don't know how certain functionality works (an extreme example is the issue tracker for [Flutter](https://github.com/flutter/flutter/issues). Most of the issues are questions that should be asked on StackOverFlow or issues for third-party plugins). On the other hand, Hugo has its own [forum](https://discourse.gohugo.io/) for discussions about community-contributed templates and site-building techniques. Separating questions/complaints/ask-for-helps from bug reports and feature requests is extremely beneficial for large OSS projects, especially those with no company support.

#### Self-sufficient Pull Requests

PRs for Hugo must be self-sufficient to be merged, which means bug fixes must come with extended tests, feature implementations must come with inline documentation, user documentation and unit tests.

#### Lack of Developer's Guide

The maintainer (especially [the founder](https://github.com/bep)) is rather particular about the naming conventions of the project - which becomes extremely important as the project grows larger and larger as newcomers need to search for file/function names to locate a small area to set breakpoints and investigate on. So long as the functions that do similar things are named similarly, pinpointing related codes would become much easier. However, this approach still doesn't cover the fact that Hugo lacks comprehensive documentation of its architecture and inner workings. And the organization of source code is rather flat (i.e. there are few nested folders to show hierarchy), which makes even more difficult for newbies to grasp an idea of how data flows through the generator.

#### Miscellaneous Points

1. **Separate source code from documentation**: Hugo has two separate repositories for documentation website and source code. For projects that are more like a [platform](https://nus-cs2103-ay1920s2.github.io/website/se-book-adapted/chapters/reuse.html#platforms), it makes more sense to separate the documentation from the source code as its usage is meant to be extended by the community's creativity (i.e. it's not limited to be used as it is).
1. **Testing for multiple platforms**: Hugo makes use of AppVeyor to test on Windows.
1. **Official template gallery**: as mentioned in a previous point, a platform-like project should have a place for the community to showoff their creativity.

### Insights for Internal Projects

Hugo has similar audience and use cases as [MarkBind](https://markbind.org/), here are some of the insights we can get from observing how Hugo project operates:

1. MarkBind could benefit from a more welcoming contributor's guide - the current developer's guide is more like documentation instead of a guide. And the contributor's guide and developer's guide can be more easily accessible from the official website - currently there's no easy way of locating two essential pieces of documentation from [markbind.org](https://markbind.org/).
1. In the [Project Structure](https://markbind.org/devdocs/devGuide/index.html#project-structure) section of the developer guide, it briefly mentioned how MarkBind rendering pipeline works. However as the project evolves, this part is not updated timely and the current approach is more complicated than what's described in the guide. It would be best if there is a dedicated blog post about the inner workings of MarkBind at a certain version for newcomers (especially future CS3281/2 students) to refer to.
1. The documentation for MarkBind can be separated from the main repo as 1) a large portion of MarkBind's functionality is in VueStrap, which is already outside of the main repo, 2) MarkBind has the potential to develop a community of templates and plugins in the future, and a separate documentation repo would make the management easier.

 