[![GoDoc](https://godoc.org/github.com/s3pt3mb3r/lineatgo?status.svg)](https://godoc.org/github.com/s3pt3mb3r/lineatgo)
# lineatgo
This is a unofficial LINE@ API that was implemented in pure go

## installation
```
go get github.com/s3pt3mb3r/lineatgo
```

## warning
This library doesn't handle errors yet.
I'll do it in a few days.

## Usage
```go
package main

import (
    "github.com/s3pt3mb3r/lineatgo"
    "log"
    "fmt"
)

func main()  {
    api := lineatgo.NewApi("personium85@gmail.com", "Am4ne5262521")
    bot, err := api.NewBot("@xur2140w")
    if err != nil {
        log.Println(err)
    }
    fmt.Println(bot.GetAuthURL())
    for _, u := range bot.AuthUserList.Users {
        if u.Name == "林田 周" {
            u.Delete()
            break
        }
    }
}
```

## Todo
- [ ] Fix DeletePostAll function
- [ ] Enable to select authority type in getAuth function
- [ ] Enable to Delete paymaster user's clearance
- [ ] Enable to Post to time line

### At last
Probably, being overlook some factors, I can't code Login() function without web driver

So If it's possible, please make Login() function more better and send pull request:)