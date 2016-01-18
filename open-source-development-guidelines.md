# PayEx Open Source Development Guidelines

## Introduction
initiative on GitHub and will alongside its partners expose the PayEx
Payment APIs in high quality client modules and libraries. The development
of these modules and libraries should be as transparent and accessible to
the public as possible. The consequence and meaning of this will be
explained in the following chapters of this guideline.
place makes the projects governing the modules and libraries easier to
grasp and understand for new users. GitHub is the world’s most popular
developer and source code hosting platform and offers everything we need
in an easy to use package. It is therefore a great choice for hosting the
source code for the open source modules and all of their related resources.
core principles:
project. Being able to inspect the source code, read the documentation,
view potentially reported bugs and understand the development process in
an accessible and easy to understand way is critical to be able to assert
the quality of the project.
hide, underlining our confidence in the quality of what we publish, which
of course should be top notch.
to test it. The test should preferably be automated and be run on every
code check-in. The automation can be done through a language-native test
framework like NUnit, JUnit or PHPUnit and then have a continuous
integration system like Travis or TeamCity execute these tests every
time code is pushed to the repository on GitHub.
  being written in.
is whether people outside of the project’s core development group
contribute to it or not. The contributions can be everything from reported
issues to correcting typographic errors in documentation to pull requests
for minor or major code contributions.
While accessibility is an abstract term, it can be broken down into smaller
and more concrete parts that are easier to measure and understand.
outstanding features listed, who are the developers working on which features
and where do they reside? How easy is it to fork the project and make a pull
request that has a high chance of being merged?
if the project is managed in a good and orderly fashion. The following list
enumerates the most important aspects that a project should be governed by to
be perceived as accessible:
	“issues” in the project’s repository.
	to from the project’s `README` file.
	[Markdown](https://help.github.com/articles/github-flavored-markdown/)
	markup so it is easy to correct by anyone simply by using GitHub’s online
	Markdown editing features.
	1. The project should follow the norm and best practice of the language
		and environment it is written in.
		on a developer machine without installing any external services, tools
		or libraries, unless they are handled by a package manager like NuGet.
		server that labels the status of pull request accordingly. If a test
		fails, the contributor should be alerted of its failure through
		GitHub’s interface.
6.	All code contributions should be run through a public continuous integration
	server so build failures are visible to the contributor such that he or she
	can fix it without any project manager’s involvement.
	existing scheme such as [GitFlow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow/)
	or [GitHub Flow](https://guides.github.com/introduction/flow/).
		progress.
		with branch prefixes such as `feature/` and `hotfix/` should be used
enumerated in [OWASP Top 10](https://www.owasp.org/index.php/Top_10_2013-Top_10)
and [SANS 25](https://www.sans.org/top25-software-errors/). It should preferably
exist a test for each of these problems such that it is continually verified
that the code does not contain any of these problems now or in the future.
information. If such code is committed by accident, history should be
rewritten through interactive rebasing as soon as possible and force-pushed.
the [Open Source Initiative](https://opensource.org/) and preferably one that
is compatible with closed source, enterprise software. The
[MIT License](https://opensource.org/licenses/MIT) is therefore a good fit
and should be chosen when possible:
The MIT License (MIT)
copy of this software and associated documentation files (the "Software"),
to deal in the Software without restriction, including without limitation
the rights to use, copy, modify, merge, publish, distribute, sublicense,
and/or sell copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following conditions:
in all copies or substantial portions of the Software.
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL
THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.
```

repository and preferably be included as a header in all source code files
in the same repository.
between PayEx and the individual authors of the source code. This should be
stated in the above mentioned LICENSE file as well as in each individual
source code file and other metadata (such as .NET assembly information, etc.):
Copyright © PayEx and Project Contributors
or another so other people can use it. To be able to release software
efficiently, several different strategies and methodologies need to exist
and be followed. They will be described in the following chapters.
should be versioned according to [semantic versioning](http://semver.org/).
This means that whenever backward compatibility is broken, the major version
should be incremented. When a new feature is added, the minor version should
be incremented and when bug fixes and other minor changes are introduced,
the revision number should be incremented.
repository. This commit should be tagged with the version number it
represents and the commit should be in the branch corresponding with
what’s being released; stable code should be in the master branch,
while pre-release, alpha or beta code should be in the develop branch
or in a release/ prefixed branch.
epresenting that version should be tagged in Git with the value `1.2.5`
and the commit should exist in the master branch.
[GitVersion](https://github.com/GitTools/GitVersion) can be used. For
most uses, [GitVersionTask](https://www.nuget.org/packages/GitVersionTask)
performs the job perfectly. It understands
[GitFlow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow/)
and increments the version number automatically based on which branch
the code being built exists on. 

[GitFlow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow/),
[GitHub Flow](https://guides.github.com/introduction/flow/) or derivates,
so released and stable code is kept in the master branch, while unstable
and pre-released code — if such is required — is kept in the develop branch.
done directly in the develop branch; features, hotfixes and such should
preferably be done in separate branches using the GitFlow-standard branch
prefixes `feature/`, `hotfix/`, etc.
storefront for applications (or “modules”, “extensions” and what have you)
such as [Apple’s App Store](http://www.appstore.com/) or
[Google Play](https://play.google.com/store), should try to publish the
released software in these marketplaces.
[Release](https://help.github.com/articles/creating-releases/) for the
version should be created on GitHub. The GitHub Release should summarize
all changes made since the last release and highlight new features, possibly
by referring to blog entries or similar that describes them in more detail.
[GitReleaseNotes](https://github.com/GitTools/GitReleaseNotes).
Even if no tool is used, the release notes should adhere to the
[Semantic Release Notes](http://www.semanticreleasenotes.org/) specification.