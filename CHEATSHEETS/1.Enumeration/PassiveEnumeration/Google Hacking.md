Limit the search `site` operator:
```
site:megacorpone.com
```

Add some operator to search for `filetype` for example:
```shell
site:megacorpone.com filetype:txt # Can find robots.txt
```

It's possible to remove operator:
```
site:megacorpone.com ext:php -filetype:html
```

Find pages that contain title and word:
```
site:megacorpone.com intitle:"index of" "parent directory"
```

https://www.exploit-db.com/google-hacking-database
https://dorksearch.com/
