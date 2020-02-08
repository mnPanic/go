# go

## Project structure

[Standard Go Project Layout]

## Writing code

- [Uber Style Guide] for a general-purpose style guide
- [CodeReviewComments] for common mistakes
- [Go Proverbs]
- [Effective Go]

## Tests

### Running all tests in a directory

```bash
go test ./...
```

### With coverage

```bash
go test ./... -coverprofile=cp.out
go tool -html=cp.out
rm cp.out
```

Or, with a simple `~/.bash_profile` alias

```bash
alias gocov="go test ./... --coverprofile=cp.out;go tool cover -html=cp.out;rm cp.out"
```

### Writing tests

- [Principles of unit testing](https://github.com/ghsukumar/SFDC_Best_Practices/wiki/F.I.R.S.T-Principles-of-Unit-Testing)
- [TableDrivenTests](https://github.com/golang/go/wiki/TableDrivenTests)
- [Prefer table driven tests](https://dave.cheney.net/2019/05/07/prefer-table-driven-tests)

## [Reflection](reflection.md)

## Configuration

### Add executables to `PATH`

To do so, add the directory `$GOPATH/bin` to path PATH

```bash
export PATH=$PATH:$(go env GOPATH)/bin
```

### [Dep](dep.md)

## General

- [Pass by reference or value?](http://goinbigdata.com/golang-pass-by-pointer-vs-pass-by-value/)
- [Developer Roadmap](https://github.com/Alikhll/golang-developer-roadmap)
- [How to write go code](https://golang.org/doc/code.html)
- [A Tour of Go](https://tour.golang.org/welcome/1): Learn language proper
- [Documentation page](https://golang.org/doc/#articles)
- [Functional options](https://dave.cheney.net/2014/10/17/functional-options-for-friendly-apis)

[Standard Go Project Layout]: https://github.com/golang-standards/project-layout
[Uber Style Guide]: https://github.com/uber-go/guide
[Effective Go]: https://golang.org/doc/effective_go.html
[CodeReviewComments]: https://github.com/golang/go/wiki/CodeReviewComments
[Go Proverbs]: https://go-proverbs.github.io/