# websocket-nginx

There are many post on how to enable websocket on NGINX , see ref , however none worked for me. The diagnosis of the problem was that websocket was hosted with first handshake with http/https followed by ws . This second handshake can be to https://ws.example.com or https://example.com/ws , depending on websocket server design . This project is for https://example.com/ws, for ws.example.com please use redirect <filter> break or anyother filter based actions on NGINX

# Will this work for me?
Yes, if your websocket server behing NGNIX is directing http traffic to http://example.com and ws traffic to https://ws.example.com , in that order

Ref : 
Ngnix Official : https://www.nginx.com/blog/websocket-nginx/
