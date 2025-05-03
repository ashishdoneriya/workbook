---
title: "Go program for vocabulary"
date: 2019-08-27T22:10:00+05:30
lastmod: 2019-09-01T22:10:00+05:30
tags:
  - programming
categories:
  - programming
description: ""
url: /go-program-vocab.html
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
  for {
    // just pass the file name
    b, err := ioutil.ReadFile("vocabulary.txt")
    if err != nil {
      fmt.Print(err)
    }

    // convert content to a 'string'
    content := string(b)

    groups := strings.Split(content, "\n\n")

    for _, group := range groups {
      index := strings.Index(group, "\n")
      var content string
      var heading string
      if index != -1 {
        heading = group[:index]
        content = group[index+1 : len(group)]
      } else {
        heading = group
        content = ""
      }

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
