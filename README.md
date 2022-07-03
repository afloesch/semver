# SemVer

Go lib for simple semantic version parsing and comparisons. Augments semantic version strings with comparison operators for fine grained version comparison rules.

Semantic version parsing is implemented to the https://semver.org specification.

## Install

```shell
go get -u github.com/afloesch/semver
```

## Basic Usage

Semver comparisons can return an integer or boolean result.

```go
package main

import "github.com/afloesch/semver"

func main() {
  v := semver.String(">=v1.0.0").Get()
  v2 := semver.String("v1.1.0").Get()
  
  // Version.Compare returns an integer of 1, -1, or 0.
  fmt.Println(v.Compare(v2) == -1)

  // Version.OpCompare returns true or false.
  // Note: try this without the '>=' in v.
  fmt.Println(v.OpCompare(v2) == true)
}
```

## Testing

Semver has complete code coverage.

```
go test . -v -cover
```
