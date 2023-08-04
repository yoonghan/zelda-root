# Microfrontend container shell

This project is the shell to expose all the routes to control all hosted microfrontend (framework agnostic).

## Usage

1. To run the root

```
npm run start
``` 

## Adding new frameworks/engines

1. Edit src/index.ejs and add the libraries that are unique into 'script type="systemjs-importmap"'. Example for React, we added react and react-dom library. Take note this is an optional step, but it's a relevant topic to reduce shared library being loaded > once.

2. Add your project into index.js to register the project below @zelda-root/root-config. E.g. added "@walcron/zelda-auth-react". To know your project configuration, start the host project with the command 'npm start -- --port 8500', and browse the page with http://localhost:8500 and the instruction will be there.

3. Configured into shared systemjs-importmap as well for public hosted site for Step 2. This is because the codes are only valid or runs for local configuration only.

4. Update the route in src/microfrontend-layout.html, to point to your projects based on different path. TAKE NOTE: The path are passed into routers of host project, e.g. path /app will be passed to the route project when navigated to /app. Hence the host projects cannot rely on root path!
