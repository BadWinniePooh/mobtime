# mobtime

A websocket powered, collaborative mobbing timer, for desktop and mobile.

## Deploying to a server

The current version is available at [Docker Hub](https://hub.docker.com/r/badwinniepooh/mobtime-app). Please have a look at the documentation over there on how to run your own instance of a mob timer.

### Create a production image

```sh
npm run start:prod
docker image tag mobtime-app:latest badwinniepooh/mobtime-app:{version}
docker push badwinniepooh/mobtime-app:{version}
docker image tag badwinniepooh/mobtime-app:{version} badwinniepooh/mobtime-app:latest
docker push badwinniepooh/mobtime-app:latest
```

## Running Locally

### With Docker/Docker Compose

This is probably the preferred way, so you don't need to global install redis or even a specific node version.

 - `npm install`
 - `npm run tailwind`
 - `npm run start:dev`

### On your system

I'd only use this if you are using `nvm` or similar for node version management, and are okay with running a local redis server.

 - Install NodeJS LTS (>= v16.x officially, 12.x may still work though)
 - Install and run redis server
     - OSX+homebrew: `brew install redis`
     - Ubuntu: `sudo apt install redis-server`
     - Or google for your operating system's install instructions
 - `npm install`
 - `npm run tailwind`
 - `npm run start:dev`

### Configuration with .env

See [.env.example](./.env.example) for information on environment variables.

## Tips for running in production

 - Ensure `NODE_ENV` is set to production
 - Use `npm start` rather than `npm run start:dev`
 - Surprise find: If you are using phusion passenger to run your node application, you cannot use clustering

## Contributing

Bug reports and suggestions are welcome, just create an issue. PRs are welcome, too.

## License

It's under [MIT](./LICENSE.md).
