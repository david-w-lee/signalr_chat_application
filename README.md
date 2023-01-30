# signalr_chat_application



## Summary

* This project is practice of https://docs.microsoft.com/en-us/aspnet/core/tutorials/signalr?view=aspnetcore-5.0&tabs=visual-studio



## Concepts

* SignalR is baiscally a broadcasting system which send messages from server to client.
* When SignalR is running in servers behind a load balancer, the connections can be synchronized via a backplane like Redis.



## Authentication

* If you are using SignalR for the same domain as your website, your existing user credentials will be used for SignalR connections. No additional configuration is needed. You just need to set attribute(such as Authorize or Role) on top of your Hub class or methods.
* Cookie authentication is only for browser clients. If you are using non-browser client, you will need to set cookie manually or use something like Bearer token authentication(recommended).
* WebSockets or Server-Sent Events don't allow custom header, so you need to transmit it using query string parameter. WebSocket doesn't have spec for authentication. Use the guide here: https://docs.microsoft.com/en-us/aspnet/core/signalr/authn-and-authz?view=aspnetcore-5.0
* Once WebSocket connection is established(and authentication is done), no further authentication is done until the next reconnection.



## Separating out SignalR server

* You can follow this guide if you want to separate out your SignalR server: https://stackoverflow.com/questions/56196661/signalr-client-connect-to-different-server
* Basically, you just have to call the dedicated SignalR server in the client side. It seems like the solution for authentication is also in place.





## Ref

* https://docs.microsoft.com/en-us/aspnet/core/tutorials/signalr?view=aspnetcore-5.0&tabs=visual-studio
* https://seangrimes.dev/post/load-balance-signalr-no-sticky-sessions/
* https://devblogs.microsoft.com/aspnet/signalr-and-user-identity-authentication-and-authorization/
* https://stackoverflow.com/questions/60692656/how-to-get-identity-of-signalr-connected-users-which-are-using-client-mvc-applic
* https://stackoverflow.com/questions/47495817/how-can-i-authenticate-a-websocket-connection-where-client-and-server-reside-on
* https://stackoverflow.com/questions/48378073/signalr-core-not-working-with-cookie-authentication





