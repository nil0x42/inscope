# inscope
Quickly filter in-scope domains &amp; urls for bug bounty

## Install
```sh
git clone https://github.com/nil0x42/inscope
cp inscope/inscope ~/bin
```
_**inscope** depends on Python3_

## help
```
usage: inscope [-h] [-s <file or expr>] [-r]

Filter in-scope subdomains & URLs from input

optional arguments:
  -h, --help            show this help message and exit
  -s <file or expr>, --scope <file or expr>
                        scope file or expression (defaults to `./SCOPE` file)
  -r, --reverse         reverse match: only show out-of-scope items

usage examples:
  cat urls.txt | inscope > inscope-urls.txt
  cat domains.txt | inscope -r > domains-NOT-in-scope.txt
  cat urls.txt | inscope -s '*.gov|*.mil' > us-gov-urls.txt

configuration:
  if not specified with '-s', scope is taken from ./SCOPE file
  in nearest parent directory.

scope file syntax example:
  ----------
  # this is a comment
  # in-scope items:
  *.target.com
  www.target.io
  # out-of-scope items start with '!'
  ! excluded.target.com
  ----------
```
