# Serenity/JS Cucumber Protractor Template

[![Build Status](https://github.com/serenity-js/serenity-js-cucumber-protractor-template/workflows/build/badge.svg)](https://github.com/serenity-js/serenity-js-cucumber-protractor-template/actions)

Use this [template repository](https://help.github.com/en/articles/creating-a-repository-from-a-template)
to get started with acceptance testing your web applications using [Serenity/JS](https://serenity-js.org), [Cucumber](https://github.com/cucumber/cucumber-js) and [Protractor](http://www.protractortest.org/). 

Learn more:
- [Serenity BDD reports for this project](https://serenity-js.github.io/serenity-js-cucumber-protractor-template/)
- [Serenity/JS Website](https://serenity-js.org)
- [Serenity/JS Tutorial](https://serenity-js.org/handbook/thinking-in-serenity-js/index.html)
- [Serenity/JS API Docs](https://serenity-js.org/modules)

> **Note**
>
> ## Serenity/JS v3 is coming soon!
>
> The default [`main` branch](https://github.com/serenity-js/serenity-js-cucumber-protractor-template/tree/main) of this Serenity/JS repository contains code for the upcoming Serenity/JS v3 release.
>
> All the public Serenity/JS APIs are now stable and unlikely to change much before the final release. You're welcome to go through the [v3 migration guide](https://serenity-js.org/handbook/release-notes/serenity-js-3.html), experiment with the new version, and ask any questions you might have about the migration on the [Serenity/JS Community Gitter Chat](https://gitter.im/serenity-js/Lobby).
>
> ## Stay up to date!
>
> - To get notified when Serenity/JS v3 is available and when new tutorials are released, follow [Serenity/JS on LinkedIn](https://www.linkedin.com/company/serenity-js) and subscribe to [@serenity-js on YouTube](https://www.youtube.com/@serenity-js)!
> - To find out more about what's left to do for the v3 launch, check out our [project board](https://github.com/serenity-js/serenity-js/milestone/1).
>
> And if you find Serenity/JS useful, learn how becoming a [GitHub Sponsor](https://github.com/sponsors/serenity-js) can help both you and this project!
>
> ## Where's Serenity/JS v2 codebase?
> Check out the [`2.x` branch](https://github.com/serenity-js/serenity-js-cucumber-protractor-template/tree/2.x)

## Prerequisites

To use this project, you'll need:
- Node.js, a Long-Term Support (LTS) release version 12 or later - [download](https://nodejs.org/en/)
- Java Runtime Environment (JRE) or a Java Development Kit (JDK) version 8 or later - [download](https://adoptopenjdk.net/)
- Chrome web browser - [download](https://www.google.co.uk/chrome/)

Follow the [installation instructions](https://serenity-js.org/handbook/integration/runtime-dependencies.html) to help you verify your setup.

## Usage

This repository is a GitHub template. You can use it to [create a new GitHub repository](https://help.github.com/en/articles/creating-a-repository-from-a-template), [clone it to your computer](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/cloning-a-repository).

You can also launch it in a virtual Gitpod workspace without having to install anything on your machine:

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/from-referrer/)

### Installation

Once you have the code on your computer, use your computer terminal to run the following command in the directory where you've cloned the project:
```
npm ci
```

Running [`npm ci`](https://docs.npmjs.com/cli/v6/commands/npm-ci) downloads the [Node modules](https://docs.npmjs.com/about-packages-and-modules) this project depends on, as well as the latest version of [`chromedriver`](https://www.npmjs.com/package/chromedriver) and the [Serenity BDD CLI](https://github.com/serenity-bdd/serenity-cli) reporter jar. 

### Corporate networks

If your network administrators require you to use proxy servers or an internal artifact registry (Artifactory, Nexus, etc.), your development environment might require some additional configuration.

The easiest way to do it is to create an [`.npmrc` file](https://docs.npmjs.com/cli/v6/configuring-npm/npmrc) in your home directory: 

```
proxy=http://user:password@host.mycompany.com:8080/
https-proxy=http://user:password@host.mycompany.com:8080/
strict-ssl=false
registry=https://artifactory.mycompany.com/artifactory/
```

If you encounter issues downloading the Serenity BDD CLI jar, please follow the [detailed instructions in the Serenity/JS Handbook](https://serenity-js.org/modules/serenity-bdd/#downloading-the-serenity-bdd-reporting-cli).

Similar instructions are available for the [`chromedriver` module](https://www.npmjs.com/package/chromedriver).

### Execution

The project provides several [NPM scripts](https://docs.npmjs.com/cli/v6/using-npm/scripts) defined in [`package.json`](package.json):

```
npm run lint            # runs the code linter
npm run clean           # removes reports from any previous test run
npm test                # executes the example test suite
                        # and generates the report under ./target/site/serenity
npm start               # starts a mini HTTP server and serves the test reports
                        # at http://localhost:8080
```

#### Running individual scenarios by name

To execute only those scenarios which names match a given pattern, run:

```
npm run test:execute -- --cucumberOpts.name="Adding numbers"
``` 

Note that this technique works with partial matches, i.e. specifying `--cucumberOpts.name="numbers"` would match both scenarios in the [example `.feature` file](features/super_calculator.feature).

#### Running scenarios by tag

You can limit the number of scenarios to execute using [Cucumber tags](https://cucumber.io/docs/cucumber/api/#tags) and [tag expressions](https://cucumber.io/docs/cucumber/api/#tag-expressions), for example:

```
npm run test:execute -- --cucumberOpts.tags="@smoke-test and @fast"
``` 

#### Running scenarios by file name and line number

You can also run a single scenario by specifying its exact `file:line` location, for example
```
npm run test:execute -- --specs=features/super_calculator.feature:24
```

## Your feedback matters!

Do you find Serenity/JS useful? [Give it a star](https://github.com/serenity-js/serenity-js)! &#9733;

Found a bug? Need a feature? Raise [an issue](https://github.com/serenity-js/serenity-js/issues?state=open)
or submit a pull request.

Have feedback? Let me know on Twitter: [@JanMolak](https://twitter.com/JanMolak)

If you'd like to chat with fellow users of Serenity/JS, join us on [Serenity/JS Community Chat](https://gitter.im/serenity-js/Lobby).

And if Serenity/JS has made your life a little bit easier, please consider [sponsoring its ongoing development](https://github.com/sponsors/serenity-js)

New tutorials and videos are coming soon, follow us on [LinkedIn](https://www.linkedin.com/company/serenity-js) and subscribe to [Serenity/JS YouTube channel](https://www.youtube.com/channel/UC0RdeVPyjtJopVHvlLrXd1Q) to get notified when they're available!

[![LinkedIn Follow](https://img.shields.io/badge/Serenity%2FJS-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/serenity-js)
[![YouTube Follow](https://img.shields.io/badge/@serenity&#8212;JS-FA120F?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@serenity-js)
