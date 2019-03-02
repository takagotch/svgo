### svgo
---
https://github.com/ajstarks/svgo

```go
package main

import (
  "github.com/ajstarks/svgo"
  "os"
)

func main() {
  width := 500
  height := 500
  canvas := svg.New(os.Stdout)
  canvas.Start(width, height)
  canvas.Circle(width/2, height/2, 100)
  canvas.Text(width/2, height/2, "Hello, SVG", "text-anchor:middle;font-size:30px;fill:white")
  canvas.End()
}



package main

import (
  "log"
  "github.com/ajstarks/svgo"
  "net/http"
)

func main() {
  http.Handle("/circle", http.HandlerFunc(circle))
  err := http.listenAndServe(":2003", nil)
  if err != nil {
    log.Fatal("ListenAndServe:", err)
  }
}

func circle(w http.ResponseWriter, req *http.Request) {
  w.Header().Set("Content-Type", "image/svg+xml")
  s := svg.New(w)
  s.Start(500, 500)
  s.Circle(250, 250, 125, "fill:none;stroke:black")
  s.End()
}

type SVG struct {
  Writer io.Writer
}

type Offcolor struct {
  Offset uint8
  Color string
  Opacity float64
}

type Filterspec struct {
  In string
  In2 string
  Result string
}

New() *SVG
```

```
go get github.com/ajstarks/svgo
go install github.com/ajstarks/svgo/...
go doc github.com/ajstarks/svgo

svgplay
curl http://localhost:1999/
```

```
```


