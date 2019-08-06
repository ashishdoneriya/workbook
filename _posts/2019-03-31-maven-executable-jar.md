---
title: "How to create executable jar in maven"
date: 2019-03-31T03:17:00+05:30
date: 2019-03-31T03:17:00+05:30
draft: false
tags: ["java", "maven"]
categories: ["java"]
toc: false
autoCollapseToc: false
summary: "Snippet code to create an executable jar in maven"
---

### Termiologies

```xml
<build>
    <plugins>
      <plugin>
        <artifactId>maven-assembly-plugin</artifactId>
        <configuration>
          <archive>
            <manifest>
              <mainClass>io.github.ashishdoneriya.Test</mainClass>
            </manifest>
          </archive>
          <descriptorRefs>
            <descriptorRef>jar-with-dependencies</descriptorRef>
          </descriptorRefs>
        </configuration>
        <executions>
          <execution>
            <id>make-assembly</id> <!-- this is used for inheritance merges -->
            <phase>package</phase> <!-- bind to the packaging phase -->
            <goals>
              <goal>single</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
    </plugins>
  </build>
```
