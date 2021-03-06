---
layout: default
---

# Interfaces in Go

Go supports interfaces in a different way than other programming languages like Java does. Like a struct, an interface is created using the type keyword, followed by a name and the keyword interface.
Click [here](https://tour.golang.org/methods/10) to learn more

```go
type Shape interface {
	// area returns the Square's area by multiplying both sides.
	area() float64
}

// Now in order to "implement" this interface, 
// a type must implement the interface methods defined. For example:
type Square struct {
	x1, y1, x2, y2 float64
}

func (s *Square) area() float64 {
	return math.Abs((s.x2 - s.x1) * (s.y2 - s.y1))
}

func measure(s Shape) float64 {
	return s.area()
}

func main() {
	// create new 5x5 Square
	s := Square{0, 0, 5, 5}
	// print the Square's area via the Shape interface
	fmt.Println(measure(&s)) // 25
}

```

### Output

```bash
25
```

<a href='https://play.golang.org/p/fVjFIddO0VP' target='_blank'>Try It Out</a> | <a href='https://github.com/sagar-jadhav/go-examples/blob/master/src/interfaces.go' target='_blank'>Source code</a>

### Contributors
- <a href='https://github.com/chanceeakin' target='_blank'>Chance</a>
- <a href='https://github.com/LukaJaj' target='_blank'>Luka Jajanidze</a>
- <a href='https://github.com/aprabhat' target='_blank'>Prabhat Agarwal</a>
- <a href='https://github.com/mmichaelb' target='_blank'>Michael B.</a>

[<< Home Page](./) | [Previous << Map](./map.html) | [Next >> Struct](./struct.html)
