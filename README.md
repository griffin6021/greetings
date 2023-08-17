# greetings
prints a simple greeting when code is run

the code (i think:)
# go.mod
module example.com/hello

go 1.20

replace example.com/greetings => ../greetings

require example.com/greetings v0.0.0-00010101000000-000000000000

# go.mod_g
module example.com/greetings

go 1.20

# greetings.go
package greetings

import "fmt"

// Hello returns a greeting for the named person.
func Hello(name string) string {
    // Return a greeting that embeds the name in a message.
    message := fmt.Sprintf("Hi, %v. Welcome!", name)
    return message
}

# hello.go
package main

import (
    "fmt"

    "example.com/greetings"
)

func main() {
    // Get a greeting message and print it.
    message := greetings.Hello("Elliott")
    fmt.Println(message)
}
