
Docker Steps To Step 

(for image build)

docker build -t image-name

docker images

(for docker container with port location)

docker run -d -p 3000:3000 --name car-cafe-app react-webimage

docker ps

[For inside the docker container location /app]

docker exec -it car-cafe-app bash
{example 
root@0061fe0ae967:/app# ls
README.md  node_modules  package-lock.json  package.json  public  src
}

cd /src

cat app.js=>{print file in unix}

For Update in app and refelect on web

docker run -e CHOKIDAR_USEPOLLING=true -v ${pwd}\src:/app/src -d -p 3000:3000 --name car-cafe-app react-webimage

Read only Project For spesific Sequerty Resion 

 docker run -e CHOKIDAR_USEPOLLING=true -v ${pwd}\src:/app/src:ro -d -p 3000:3000 --name car-cafe-app react-webimage 



docker run --env-file ./.env -v ${pwd}\src:/app/src -d -p 3000:3000 --name car-cafe-app react-webimage



 docker-compose up -d

 docker-compose down
 
 
if run this blow command first change in docker-compose.yml file as blow 


docker run -it --env-file ./.env -v ${pwd}\src:/app/src -d -p 3000:3000 --name car-cafe-app react-webimage

* docker-compose.yml

version: "3"
services:
  react-app:
    stdin_open: true
    tty: true
    build: .
    ports:
      - "3000:3000"
    volumes:
      - ./src:/app/src
    environment:
      - REACT_APP_NAME=NARENDRA KUMAR
      - CHOKIDAR_USEPOLLING=true
    #env_file:
    #   - ./.env

*


docker-compose -f docker-compose.yml -f docker-compose-prod.yml up  -d --build

docker-compose -f docker-compose.yml -f docker-compose-dev.yml up  -d --build













# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
