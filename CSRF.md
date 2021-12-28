# Cross-Site Request Forgery(CSRF)

## Cross Domain Access Controls
The `iframe` tag in HTML allows you to embed a webpage inside of another.

But a security feature called `Same Origin Policy` prevents you from accessing any arbitrary webpage.

It only allows you to embed a page when all of the following conditions are met:
 - Same Domain
 - Same Port
 - Same Protocol(e.g. http/https)
