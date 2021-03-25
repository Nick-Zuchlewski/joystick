# joystick

Go Joystick API

Package joystick implements a Polled API to read the state of an attached joystick.
Windows, Linux & OSX are supported.
Package requires no external dependencies to be installed.

Mac OSX code developed by:  [ledyba](https://github.com/ledyba)

Forked from: [simulatedsimian/joystick](https://github.com/simulatedsimian/joystick)

## Installation

```bash
go get github.com/simulatedsimian/joystick/...
```

## Sample Program

```bash
go install github.com/simulatedsimian/joystick/joysticktest
joysticktest 0
```

Displays the state of the specified joystick

## Example

```go
import "github.com/Nick-Zuchlewski/joystick"

js, err := joystick.Open(jsid)
if err != nil {
  panic(err)
}

fmt.Printf("Joystick Name: %s", js.Name())
fmt.Printf("   Axis Count: %d", js.AxisCount())
fmt.Printf(" Button Count: %d", js.ButtonCount())

state, err := joystick.Read()
if err != nil {
  panic(err)
}

fmt.Printf("Axis Data: %v", state.AxisData)
js.Close()
```
