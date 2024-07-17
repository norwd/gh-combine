# gh-combine

GitHub CLI extenion to combine multiple Pull Requests together into one PR and close all the individual PRs.

This is particularly useful for cleaning up @dependabot PRs.

```sh
gh combine --title "Update all dependencies" $(gh pr list --author app/dependabot --json number --jq '.[].number')
```

<img src="https://raw.githubusercontent.com/norwd/human/b1bc793d7085ed4532349a4125a5d3d171f6c568/docs/automatic-logo.svg" height="50" />

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
