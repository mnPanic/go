# go

## Project structure

[Standard Go Project Layout]

## Design

- [Understanding Go Interfaces - Google](https://www.youtube.com/watch?v=F4wUrj6pmSI&t=1642s)
- [Package oriented design - Ardan Labs](https://www.ardanlabs.com/blog/2017/02/package-oriented-design.html)

## Writing code

- [Uber Style Guide] for a general-purpose style guide
- [CodeReviewComments] for common mistakes
- [Go Proverbs]
- [Effective Go]
- [Practical Go](https://dave.cheney.net/practical-go/presentations/qcon-china.html)

- Don't panic.
  - https://github.com/uber-go/guide/blob/master/style.md#dont-panic
  - https://github.com/golang/go/wiki/CodeReviewComments#dont-panic
  - https://golang.org/doc/effective_go#errors
  - https://eli.thegreenplace.net/2018/on-the-uses-and-misuses-of-panics-in-go/#id4
  - En general, don't panic. Solo en inicialización
  - Si querés paniquear, dejalo en el package's boundaries, nunca exponerlo hacia
    afuera.

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

Add the directory `$GOPATH/bin` to PATH

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
