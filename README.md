An example implementation of web sockets on svelte/node.js 

- run NPM INSTALL in both the client and server directories
- run the server with `node index.js`
- run the client with `npm run dev`

### Whats happening here?

A web socket server is running and monitoring any inbound connections.  A connection is being made when the client runs its `onMount` life cycle hook.  When the user presses the bid button, a WS message event happens, which gets recieved by the WS server `message` event.  The response then sends a message, which is recieved by the clients `message` event. 