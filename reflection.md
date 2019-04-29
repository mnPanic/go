# Reflection

## Useful links

- [Reflect package](https://golang.org/pkg/reflect/)
- [Laws of Reflection](https://blog.golang.org/laws-of-reflection)
- [Setting fields of a struct](https://stackoverflow.com/questions/6395076/using-reflect-how-do-you-set-the-value-of-a-struct-field?rq=1)

## Reflection example

```go
package main

import (
	"fmt"
	"reflect"
)

type Foo struct {
	FirstName string `tag_name:"tag 1"`
	LastName  string `tag_name:"tag 2"`
	Age       int    `tag_name:"tag 3"`
}

func (f *Foo) reflect() {
	val := reflect.ValueOf(f).Elem()

	for i := 0; i < val.NumField(); i++ {
		valueField := val.Field(i)
		typeField := val.Type().Field(i)
		tag := typeField.Tag

		fmt.Printf("Field Name: %s,\t Field Value: %v,\t Tag Value: %s\n", typeField.Name, valueField.Interface(), tag.Get("tag_name"))
	}
}

func main() {
	f := &Foo{
		FirstName: "Drew",
		LastName:  "Olson",
		Age:       30,
	}

	f.reflect()
}
```

[Source](https://gist.github.com/drewolson/4771479)

