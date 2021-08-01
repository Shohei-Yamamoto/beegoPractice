# beegoPractice
My Practice Repository for beego

# beego Home
[Homepage - beego: simple & powerful Go app framework](https://beego.me/)

# setup

1. `go get github.com/beego/bee/v2`


# tips

## Error: too many open files

1. check your settings `launchctl limit`
1. `sudo vi /Library/LaunchDaemons/limit.maxfiles.plist`

```xml
<?xml version="1.0" encoding="UTF-8"?>  
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">  
  <dict>
    <key>Label</key>
    <string>limit.maxfiles</string>
    <key>ProgramArguments</key>
    <array>
      <string>launchctl</string>
      <string>limit</string>
      <string>maxfiles</string>
      <string>524288</string>
      <string>524288</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>ServiceIPC</key>
    <false/>
  </dict>
</plist>  
```

1. `sudo launchctl load -w /Library/LaunchDaemons/limit.maxfiles.plist`
1. `launchctl limit`


* [Macの「Too many open files」エラーを解消 - Qiita](https://qiita.com/sou_lab/items/1ca051a1f3b906a23dc8)

# MemoForFirst

## create new web applications

`bee new myproject`

## create new API applications

`bee api myproject`
