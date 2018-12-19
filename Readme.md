# AppInsights.Log4NetAppender

Fork of Microsoft.ApplicationInsights.Log4NetAppender that adds support for sending custom events

## Develop

To build and run tests you can use:
* the dotnet cli tool
* any IDE/editor that understands MSBuild eg Visual Studio or Visual Studio Code

**Recommended workflow**

* Develop on a feature branch created from master:
    * create a branch from *master* named *feature/xxx* eg `feature/cool-feature` 
    * commits pushed from this branch will trigger a limited CI build (compile and test only)
* When ready to publish the nuget package to production:
    * merge *master* into your branch, then run tests locally (eg `dotnet test src/CcAcca.AppInsights.Log4NetAppender.Tests`)
    * merge your *feature* branch to *master*
    * on the *master* branch, bump the version number in [CcAcca.AppInsights.Log4NetAppender.csproj](src/CcAcca.AppInsights.Log4NetAppender/CcAcca.AppInsights.Log4NetAppender.csproj); follow [semver](https://semver.org/)
    * on the master branch `git push`

## CI server

Azure Devops (formally vsts) is used to run the dotnet cli tool to perform the build and test. See the [yam build definition](azure-pipelines.yml) for details.

Notes:
* The CI build is configured to run on every commit to any branch
* Commits to master will also publish the nuget package for CcAcca.AppInsights.Log4NetAppender to the nuget.org