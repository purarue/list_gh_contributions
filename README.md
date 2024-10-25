## list_gh_contributions

Script to list all of the repositories you've contributed to on Github. Includes your own repositories and any repositories you've contributed to (a commit, PR or issue)

## Installation

Requires `python3.6+`

To install with pip, run:

    pip install 'git+https://github.com/purarue/list_gh_contributions'

---

## Usage

Go to Github Developer Settings and create a 'Personal Access Token' (https://github.com/settings/tokens).

The only scopes this requires is `repo`

Put the generated token in a text file on the first line

Usage:

```
Usage: list_gh_contributions [OPTIONS]

  Prints results to STDOUT

Options:
  --github-token PATH  Text file which contains your Github token  [required]
  --fetch-schema       indicate if we want to fetch the schema from the
                       transport using an introspection query

  --to-csv             Convert output to CSV instead
  --help               Show this message and exit.
```

By default, this prints JSON blobs to STDOUT, to export to CSV:

```
python3 -m list_gh_contributions --github_token ./token.txt --to-csv > repos.csv
```

...

```csv
"name","updatedAt","url"
"list_gh_contributions","2021-01-17T04:57:34Z","https://github.com/purarue/list_gh_contributions"
"mal-id-cache","2021-01-17T02:56:59Z","https://github.com/purarue/mal-id-cache"
"chomp","2021-01-17T02:22:05Z","https://github.com/purarue/chomp"
"newest","2021-01-17T02:21:56Z","https://github.com/purarue/newest"
"exobrain","2021-01-15T10:42:04Z","https://github.com/purarue/exobrain"
"HPI","2021-01-15T10:41:56Z","https://github.com/purarue/HPI"
"mint","2021-01-14T23:21:27Z","https://github.com/purarue/mint"
"dotfiles","2021-01-12T03:43:22Z","https://github.com/purarue/dotfiles"
"plaintext-playlist","2021-01-07T07:41:29Z","https://github.com/purarue/plaintext-playlist"
```

Note: You probably shouldn't have to use `--fetch-schema`, but if you get a 'null graphql' error, try that and see if it fixes the issue for you. See [#3](https://github.com/purarue/list_gh_contributions/issues/3)
