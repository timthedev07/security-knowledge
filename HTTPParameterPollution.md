# HTTP Parameter Pollution
What happens when you send a request with the same parameter multiple times but different values?
```
users.com/?name=Chad&name=Henry
```

The outcome depends on the backend server.

*On Google, this search `https://www.google.com/search?q=hello&q=world` would concatenate the two queries together*
