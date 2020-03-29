### Project: [OpenRefine](http://openrefine.org)

OpenRefine (previously known as Google Refine) is a powerful tool for working with messy data. The tool is capable of cleaning data, transforming it from one format into another, and extending it with web services and external data.

The server-side of OpenRefine is implemented in Java as a single servlet which is executed by the [Jetty](http://jetty.codehaus.org/jetty/) web server + servlet container. The client-side is implemented in HTML, CSS, Javascript and libraries such as [jQuery](http://jquery.com/), [Recurser jquery-i18n](https://github.com/recurser/jquery-i18n).

### Project Documents

- [Contribution Guidelines](https://github.com/OpenRefine/OpenRefine/blob/master/CONTRIBUTING.md)
- [Code of Conduct](https://github.com/OpenRefine/OpenRefine/blob/master/CODE_OF_CONDUCT.md)
- [User Guide](https://github.com/OpenRefine/OpenRefine/wiki/Documentation-For-Users)
- [Project README](https://github.com/OpenRefine/OpenRefine/blob/master/README.md)

### My Contributions

The following are my merged PRs for OpenRefine:
1. [Translate Sort link to the language of the UI](https://github.com/OpenRefine/OpenRefine/pull/2275)
2. [Standardise 'edit' cell dialogue with 'toNumber()' when parsing String to Number](https://github.com/OpenRefine/OpenRefine/pull/2274)
3. [[#2220] Add facet for blank values/records per column](https://github.com/OpenRefine/OpenRefine/pull/2297)
4. [[#2280] Add fill down and blank down operations for all columns](https://github.com/OpenRefine/OpenRefine/pull/2296)

My contributions for the project starts off with mainly bug fixes (PR 1 & 2) to ease my understanding to the large existing codebase. After having a deeper understanding of the existing codebase, I added some new features (PR 3 and 4) that provide more value and simplifies the effort of the user.

### My Observations

1. **Motivation for new contributors**. OpenRefine provides a good starting point for new contributors in the form of their [Contribution Guidelines](https://github.com/OpenRefine/OpenRefine/blob/master/CONTRIBUTING.md). The guidelines cover multiple ways to contribute (in the form of PRs, feature requests, bug reports, documentation) as well as things to take note before contributing. Several first timer issues and second timer issues were also offered to ensure that new contributors can ease their way through the codebase with simple features/fixes. 
2. **Having good documentation is crucial for developers to get started with the project**. Initially it was very daunting for me to start working on such as large codebase that are built with some technologies that I was not familiar with. OpenRefine's developer guide did not help me much either, as it only describes the application architecture on a high level, the content was not structured well, there's even missing info about several components. I had to take quite some time and dive deep into the code to figure out how the components tie with one another. 
3. **Specific issue templates**. The issue templates have clear and concise structure which allows the developers to know all information about the bug/feature requests. This reduces potential confusion and the need to clarify and ask for more information, while forcing contributors to be more clear and specific when describing the issue. Issue templates are not set up on RepoSense and I believe it will greatly improve the quality of our submitted issues.
4. **Every feature addition requires multiple tests to go with it**. This is because OpenRefine's code coverage is rather low and having a higher coverage will increase the confidence in thoroughness of testing. 
5. **Support for multiple languages is important**. OpenRefine is available in more than 15 languages. The front-end of the application is localized using the [Wikimedia's jquery-i18n plugin](https://github.com/wikimedia/jquery.i18n). This is done to accommodate with the wide range of users that OpenRefine has. So whenever adding a new feature involves displaying texts, the corresponding translation for the other languages should also be added.
6. **Good and effective code reviews**. Even though OpenRefine has only two active reviewers, they keep up with the pull requests very efficiently and will review usually in a day or two. The code reviews that I have gotten were complete, clear and concise. The reviewers know that I'm a new contributor and thus providing more information about how a certain component works while correcting some mistakes in my solution. The code reviews are also done in a positive, motivating tone which really helps new contributors to feel less daunting. 

### Project: [Video Hub App](https://videohubapp.com)

Video Hub App is an application that provides a fast way to browse and search for videos on your computer. It is like a YouTube for videos on your computer that allows browsing, searching and previewing. 

The application is build with tools such as [Angular](https://github.com/angular/angular) and [Electron](https://github.com/electron/electron).

### Project Documents

- [Project README](https://github.com/whyboris/Video-Hub-App/blob/master/README.md)
- [Code of Conduct](https://github.com/whyboris/Video-Hub-App/blob/master/CODE_OF_CONDUCT.md)

### My Contributions

The following are my merged PRs for Video Hub App:
1. [[#332] Fix bug of tags that persists after switching hubs](https://github.com/whyboris/Video-Hub-App/pull/334)
2. [[#324] Fix scrolling bug after switching from text view](https://github.com/whyboris/Video-Hub-App/pull/329)

Submitted Issues:
1. [Adding tags to videos does not update tag tray if open](https://github.com/whyboris/Video-Hub-App/issues/336)

My contributions for the project mainly consists of fixing and detecting bugs that exist in the application.

### My Observations

Video Hub App is a rather small and new application, with only two active developers working on features while other small bug fixes/features are open to external contributors. 

1. **Simple contribution guidelines**. There's no format or procedures to follow in order to contribute to the project, there are no code styles to follow as well. I think it is fine at this stage, but I think in the future when the codebase increases in size, there needs to be a certain code style to follow so that code consistency is achieved, which makes code check ins and reviews easier.  
2. **There's no developer guide**. This is perhaps due to the developers not having enough time to document their work, as I believe they are focused on churning out as much features as possible in a short amount of time. However, this decreases the willingness of external contributors to contribute to the project, as they would not know where and how to start working on the existing codebase. 


### Suggestions for Internal Project

1. **Can consider to set up issue templates**. It is common that contributors who submitted issues without providing full information. Issue templates allows contributors to submit their issues in a systematic and specific way, while helping to save the time and effort for developers to clarify about the issue.
2. **Provide more first timer issues**. There are existing first timer issues in RepoSense, but those are mainly targeted towards the back end of the application. Perhaps we can provide more first timer issues targeted towards the front end of the application, since the front end part was the harder part to grasp. This will invite more external contributors to work on the front end of the application, easing their way towards understanding how the front end ties together.
3. **Can include more people in the level 2 reviewers**. The number of pull requests are increasing constantly, while the reviewing progress of the stage 2 reviewers are slightly behind. Perhaps we can include current students/developers as stage 2 reviewers.
4. **User Interface changes should be decided before starting to work on them**. There are a lot of instances where developers contribute PRs that involves UI addition/changes, but require multiple changes due to opinions of different reviewers. This causes a lot of unnecessary rework and effort. Perhaps we can have a discussion in the issue on the UI changes, stating the reasons why the UI should be implemented in this way etc. Once we have a general consensus, the need to change the implementation of UI would be less likely.
5. **Utilise Github Actions for general housekeeping tasks**. Currently, we are manually doing housekeeping tasks such as reminding contributors to follow our contributing guidelines, fixing the CI checks before continuing, reminding contributors about their stale PRs etc. These housekeeping tasks can be automated using Github Actions, so that us developers can focus on solely reviewing the code.
6. **RepoSense requires more robust front end tests**. There were a lot of merged PRs that caused regressions in the front end of the RepoSense dashboard. A big part of this is due to our front end tests not being robust enough.  
