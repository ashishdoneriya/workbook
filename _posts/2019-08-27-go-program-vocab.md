---
title: "Go program for vocabulary"
date: 2019-08-27T22:10:00+05:30
lastmod: 2019-08-27T22:10:00+05:30
draft: false
tags: ["programming"]
categories: ["programming"]
summary: ""
---

```golang
package main

import (
  "fmt"
  "io/ioutil"
  "strings"
  "time"

  "github.com/gen2brain/beeep"
)

func main() {
  b, err := ioutil.ReadFile("vocabulary.txt") // just pass the file name
  if err != nil {
    fmt.Print(err)
  }

  content := string(b) // convert content to a 'string'

  groups := strings.Split(content, "\n\n")

  for {
    for _, group := range groups {
      index := strings.Index(group, "\n")
      heading := group[:index]
      content := group[index+1 : len(group)]

      err := beeep.Notify(heading, content, "assets/information.png")
      if err != nil {
        panic(err)
      }
      
      time.Sleep(90 * time.Second)
      
      err = beeep.Notify(heading, content, "assets/information.png")
      if err != nil {
        panic(err)
      }
      time.Sleep(90 * time.Second)
    }
  }
}
```
