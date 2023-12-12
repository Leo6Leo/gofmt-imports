I don't know what's wrong with my IDEs, they are always messing up my go file format and go imports.... As I have been manually run gofmt and goimports everytime on every single file that is changed. So just make this tool to help me out and make my life easier. Hopefully it will help some other people who have the same problem as I do.
# gofmt+goimports Combo

This script is designed to automatically format Go files in a Git repository using `go fmt` and `goimports`. It identifies modified Go files and formats them, except for files or directories explicitly excluded.

## Prerequisites

Before running this script, ensure you have the following installed:
- Git
- Go
- `goimports` tool (installable via `go get golang.org/x/tools/cmd/goimports`)

## Installation

To use this script, clone or download it to your local machine:

```
git clone https://github.com/Leo6Leo/gofmt-imports
```

Make the script executable:

```
sudo chmod +x format.sh
```

## Usage

Run the script from the root of your Git repository. You can specify files or directories to exclude as arguments:

```
./format.sh [excluded file or directory] ...
```

For example, to exclude the `vendor` and `third_party` directories and a specific file `haha.go`, run:

```
./format.sh vendor third_party haha.go
```

## How It Works

- The script scans for all modified `.go` files using `git diff`.
- It excludes any files or directories specified as command-line arguments.
- Each non-excluded, modified Go file is then formatted using `go fmt` and `goimports`.
