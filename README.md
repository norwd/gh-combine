# gh-combine

GitHub CLI extenion to combine multiple Pull Requests together into one PR and close all the individual PRs.

This is particularly useful for cleaning up @dependabot PRs.

```sh
gh combine --title "Update all dependencies" $(gh pr list --author app/dependabot --json number --jq '.[].number')
```

<img src="https://codeberg.org/norwd/human/raw/branch/main/docs/automatic-logo.svg" height="50" />

## Installation

```sh
gh extension install norwd/gh-combine

```

### Building locally

```sh
gh repo clone norwd/gh-combine
cd gh-combine
# optionally make edits or changes
gh extension install .
```

## Usage

*USAGE*

    gh combine [-h|--help]
    gh combine [--base BRANCH] [-b|--branch BRANCH] [-t|--title TITLE] PR ...

*FLAGS*

	  -h, --help:             Show help for command"
	  --base BRANCH:          Use specified base BRANCH"
	  -b, --branch BRANCH:    Use specified BRANCH name"
	  -t, --title TITLE:      Use specified Pull Request TITLE"

*ARGUMENTS*

    Trailing arguments are parsed as the pull requests to combine.

*EXAMPLES*

    $ gh combine 1 2 3
    $ gh combine -b combine-1-2-and-3 -t "Combine PRs #1 #2 and #3" 1 2 3 
    $ gh combine --base dependencies --branch all-new-dependencies --title "Update all dependencies" $(gh pr list --author app/dependabot --json number --jq '.[].number')

# I'm Using GitHub Under Protest

My projects are currently hosted on GitHub.
This is not ideal; GitHub is a proprietary, trade-secret system that is not Free and Open Source Software (FOSS).
I am deeply concerned about using a proprietary system like GitHub to develop my FOSS projects.
I have an [open discussion][Leaving GitHub Discussion] where I am planning how to move away from GitHub in the long term.
I urge you to read about the [Give up GitHub] campaign from the [Software Freedom Conservancy] to understand some of the reasons why GitHub is not a good place to host FOSS projects.

If you are a contributor who personally has already quit using GitHub, please [check this resource][Leaving GitHub Discussion] for how to send in contributions without using GitHub directly.

Any use of my projects' code by GitHub Copilot, past or present, is done without my permission.
I do not consent to GitHub's use of any of my projects' code in Copilot.

![Logo of the GiveUpGitHub campaign](https://sfconservancy.org/static/img/GiveUpGitHub.png)

[Leaving GitHub Discussion]: https://github.com/norwd/norwd/discussions/7
[Give up GitHub]: https://GiveUpGitHub.org
[Software Freedom Conservancy]: https://sfconservancy.org
