# NetStream: video-chat application
> Chat application with **1 to 1** and **many to many** video functionality.
>  Uses [VueJS](https://vuejs.org),  [WebRTC](https://webrtc.org/start/),  [SocketIO](https://socket.io), [Vuex](https://vuex.vuejs.org),NodeJS and [Redis](https://github.com/NodeRedis/node_redis)

## Quick start
You must first install and use Redis on your computer. For Mac OS X, click [this](https://medium.com/@petehouston/install-and-config-redis-on-mac-os-x-via-homebrew-eb8df9a4f298). After Redis is operational:

```bash
# Clone the repo
git clone https://github.com/Ashish-003/NetStream-Real-time-Video-Chat-Application.git
# Change into the repo directory
cd video-chat

# install
npm install 

# Start the FE in dev mode
npm run serve

# Start the server
npm run run:server

```
Then visit http://localhost:8080 in your browser

## Horizontal scaling
We will establish three distinct instances in order to verify the horizontal scaling. Every individual operating a distinct nodeJS process that serves the FE and exposes the API

<p align="center">
  <img src="https://github.com/Ashish-003/NetStream-Real-time-Video-Chat-Application/blob/master/src/assets/local_env.png" alt="scaling" width="500" height="460"/>
</p>


```bash
# Build the images
docker-compose -f docker-compose.yml build

# Create and run the three instances
docker-compose -f docker-compose.yml up

```

The webapp will be available at http://localhost:3000, http://localhost:3001, and http://localhost:3002, each with its own socket connection.

