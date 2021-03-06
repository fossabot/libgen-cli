## libgen-cli [![Build Status](https://github.com/ciehanski/libgen-cli/workflows/build/badge.svg)](https://github.com/ciehanski/libgen-cli/actions) [![Go Report Card](https://goreportcard.com/badge/github.com/ciehanski/libgen-cli)](https://goreportcard.com/report/github.com/ciehanski/libgen-cli)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fciehanski%2Flibgen-cli.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fciehanski%2Flibgen-cli?ref=badge_shield)

libgen-cli is a command line interface application which allows users to
quickly query the Library Genesis dataset and download any of its contents.

![Example](https://github.com/ciehanski/libgen-cli/blob/master/resources/libgen-cli-example.gif)

## Installation

You can download the latest binary from the releases section of this repo
which can be found [here](https://github.com/ciehanski/libgen-cli/releases).

If you have Golang installed on your local machine you can use the
commands belows to install it directly into your $GOPATH.

```
go get -u github.com/ciehanski/libgen-cli
go install github.com/ciehanski/libgen-cli
```

## Commands

#### Search:

The _search_ command is the bread and butter of libgen-cli. Simply provide an
additional argument to have libgen-cli scrape the Library Genesis dataset and
provide you results available for download. See below for a few examples:

```bash
libgen search kubernetes
```

Filter the amount of results displayed:

```bash
libgen search kubernetes -r 5
```

Filter by file extension:

```bash
libgen search kubernetes -e pdf
```

Specify an output path:

```bash
libgen search kubernetes -o ~/Desktop/libgen
```

Require that the author field is listed and available for the specific search
results:
 
```bash
libgen search kubernetes -a
```

#### Download:

The _download_ command will allow you to download a specific book if already 
know the MD5 hash. See below for an example:

```bash
libgen download 2F2DBA2A621B693BB95601C16ED680F8
```

Specify an output path:

```bash
libgen download -o ~/Desktop/ 2F2DBA2A621B693BB95601C16ED680F8
```

The _download-all_ command will allow you to download all query results. See
below for an example:

```bash
libgen download-all kubernetes
```

Specify an output path:

```bash
libgen download-all -o ~/Desktop/ kubernetes
```

#### Dbdumps:

The _dbdumps_ command will list out all of the compiled database dumps of
libgen's database and allow you to download them with ease.

```bash
libgen dbdumps
```

Specify an output path:

```bash
libgen dbdumps -o ~/Desktop
```

#### Status:

The _status_ command simply pings the mirrors for Library Genesis and
returns the status [OK] or [FAIL] depending on if the mirror is responsive 
or not. See below for an example:

```bash
libgen status
```

Specify to only check the status of the download mirrors:

```bash
libgen status -m download
```

Specify to only check the status of the search mirrors:

```bash
libgen status -m search
```

## License
- Apache License 2.0

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fciehanski%2Flibgen-cli.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fciehanski%2Flibgen-cli?ref=badge_large)