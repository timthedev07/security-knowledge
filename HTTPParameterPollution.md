# HTTP Parameter Pollution
What happens when you send a request with the same parameter multiple times but different values?
```
users.com/?name=Chad&name=Henry
```

The outcome depends on the backend server.

*On Google, this search `https://www.google.com/search?q=hello&q=world` would concatenate the two queries together*
![img](assets/google-q-param.png)

*On Yahoo, this search `https://search.yahoo.com/search?p=apple&p=mango` would return the last paremeter*
![img](assets/yahoo-q-param.png)

**Caveat: Different frameworks have different implementations, and there isn't a standard way of accepting multiple values for the same parameter.

## Example

Say you made a post on `somesocialnetwork.com` with the title being `&u=hacker.com`

And assume the share link on Facebook is formatted as the following:
```
facebook.com/sharer.php?u=[LINK]
```

The result of sharing this to facebook would be something like(without having the `u` parameter percent-coded):
```
facebook.com/sharer.php?u=somesocialnetwork.com/post?title=&u=hacker.com
```

This is a big security flaw as the user would be redirected to hacker.com instead of somesocialnetwork.com given that the PHP framework Apache uses takes the value of the last occurence of the parameter:
```
facebook.com/sharer.php?u=hacker.com
```
