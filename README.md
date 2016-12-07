# mvn-site-github-pages

This is a *template* project to integrate [GitHub Pages](https://help.github.com/articles/what-is-github-pages/) with [Maven Site](https://github.github.com/maven-plugins/site-plugin/project.html#)

## Usage

1. Clone the repository
2. Create a new home for the repository in GitHub.com or GitHub Enterprise
3. Change the `pom.xml` section to point to your new repository location (2 sections)
4. Generate a personal access token with `user` and `repo` permissions
5. Fill in the `server` section in your `~/.m2/settings` with GitHub username and token:

```
<server>
   <id>github</id>
    <username>YOUR_USERNAME</username>
    <password>YOUR_TOKEN generate in step 4</password>
</server>

```

Run `mvn site` and see the content being uploaded to your project's `gh-pages` branch. Expected sample output:

```
> mvn site       
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building site-testing 1.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] 
[INFO] --- maven-site-plugin:3.3:site (default-site) @ site-testing ---
[WARNING] Report plugin org.apache.maven.plugins:maven-project-info-reports-plugin has an empty version.
[WARNING] 
[WARNING] It is highly recommended to fix these problems because they threaten the stability of your build.
[WARNING] 
[WARNING] For this reason, future Maven versions might no longer support building such malformed projects.
[INFO] configuring report plugin org.apache.maven.plugins:maven-project-info-reports-plugin:2.9
[INFO] Relativizing decoration links with respect to project URL: https://github.com/bitoiu/mvn-site-github-pages
[INFO] Rendering site with org.apache.maven.skins:maven-default-skin:jar:1.0 skin.
[INFO] Generating "Dependencies" report    --- maven-project-info-reports-plugin:2.9
[INFO] Generating "Dependency Convergence" report    --- maven-project-info-reports-plugin:2.9
[INFO] Generating "Dependency Information" report    --- maven-project-info-reports-plugin:2.9
[INFO] Generating "About" report    --- maven-project-info-reports-plugin:2.9
[INFO] Generating "Plugin Management" report    --- maven-project-info-reports-plugin:2.9
[INFO] Generating "Plugins" report    --- maven-project-info-reports-plugin:2.9
[INFO] Generating "Source Code Management" report    --- maven-project-info-reports-plugin:2.9
[INFO] Generating "Summary" report    --- maven-project-info-reports-plugin:2.9
[INFO] 
[INFO] --- site-maven-plugin:0.12:site (default) @ site-testing ---
[INFO] Creating 25 blobs
[INFO] Creating tree with 25 blob entries
[INFO] Merging with tree 29461b509796af89d455d240f497f5f05a2f4ea8
[INFO] Creating commit with SHA-1: 3e7725d27b0c638fe39b136f851598d5a6cbda0f
[INFO] Updating reference refs/heads/gh-pages from e8f77156784fe92cb4b37e3e8b27351e14213da2 to 3e7725d27b0c638fe39b136f851598d5a6cbda0f
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 01:32 min
[INFO] Finished at: 2016-12-06T10:51:22+00:00
[INFO] Final Memory: 24M/310M
[INFO] ------------------------------------------------------------------------
```

## Usage in a CI Server

If you're trying to automate the site generation and deployment in CI make sure access to the build agents' `.m2/settings.xml` is well protected. For additional security you might want to look at [Maven's password encryption](https://maven.apache.org/guides/mini/guide-encryption.html).

## Help needed

If you have any issues check [Maven Site's GitHub Plugin docs](https://github.github.com/maven-plugins/site-plugin/project.html#).

## Found a bug in this template

Please open a PR with the changes and I'll take a look as soon as possible.

:octocat::heart:
