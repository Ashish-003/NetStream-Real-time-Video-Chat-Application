# NetStream: video-chat application
> Chat application with **1 to 1** and **many to many** video functionality using [VueJS](https://vuejs.org), [Vuex](https://vuex.vuejs.org), [WebRTC](https://webrtc.org/start/), [SocketIO](https://socket.io),NodeJS and [Redis](https://github.com/NodeRedis/node_redis)

## Quick start
First of all, you need to install and run the redis in your PC. Here there is an [article](https://medium.com/@petehouston/install-and-config-redis-on-mac-os-x-via-homebrew-eb8df9a4f298) for Mac OS X. Once Redis is up and running:

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
To test out the horizontal scaling we'll create 3 different instances. Each one running a unique nodeJS process serving the FE and exposing the API

<p align="center">
  <img src="https://github.com/Ashish-003/NetStream-Real-time-Video-Chat-Application/blob/master/src/assets/local_env.png" alt="scaling" width="500" height="460"/>
</p>


```bash
# Build the images
docker-compose -f docker-compose.yml build

# Create and run the three instances
docker-compose -f docker-compose.yml up

```

The webapp will be exposed on http://localhost:3000, http://localhost:3001 and http://localhost:3002, each one with a different socket connection

