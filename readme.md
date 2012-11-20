# fail

A failure detector is a tracker that receives events from multiple TCP connections and manages timeouts locally so that failed servers are detected - works with multiple connections.

## API

- `.connecting(to)`: if you are the initiating party, call this; sets a timeout on the connection
- `.connected(to)`: call this when the connection is established (either on the client, or on the server)
- `.receive(from)`: call this for each message received from the other party (request or response)
- `.ungracefulDisconnectFn(from)`: returns a function that you can pass to .on('close'); triggers a disconnect if this occurs unexpectedly
- `.disconnect(from)`: call this for a graceful disconnect
- `.timeouts()`: run the timeout interval manually
