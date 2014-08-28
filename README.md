# msed

this correctly parses:

```
msed2 "

many ( spaces | choice (match a) 
                       (match test) 
                       (match is) 
                       (match this)
    ) 
| eof" <<< "this is a test"
```

and this correctly fails to parse:

```
msed2 "

many ( spaces | choice (match a) 
                       (match test) 
                       (match is) 
                       (match this)
    ) 
| eof" <<< "this is NOT a test"
```
