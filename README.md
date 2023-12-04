# Initialize your project:
If you haven't already created a package.json file for your project, you can initialize it by running the following command in your project directory:

`npm init -y`
This command will generate a basic package.json file with default values.

# Install json-server:
Install json-server globally by running the following command:
`npm install -g json-server`
This will install json-server as a global package so that you can use it from the command line.


# Start the JSON server:
To start the JSON server with your stations.json file, use the following command:

`json-server --watch stations.json`
The --watch flag tells json-server to watch for changes in the stations.json file and update the API accordingly.

# Access your API:
Your JSON server should now be running, and you can access your API at http://localhost:3000. For example, if you have a resource named "posts," you can access it at http://localhost:3000/stations.

You can now make GET, POST, PUT, and DELETE requests to interact with your JSON API. For example, you can use tools like curl, Postman, or programming libraries like axios in JavaScript to interact with your JSON server.

Remember to customize the JSON data and routes in your stations.json file to match your specific application's requirements.


# How to run a JSON Server in the Terminal using Process Manager

## Install PM2
`npm install pm2@latest -g`

## Create a server.js file
`import pkg from 'json-server';
const { create, router: _router, defaults } = pkg;

const server = create();
const router = _router('./data/db.json');
const middlewares = defaults();

server.use(middlewares);
server.use(router);

const PORT = 3000; // Change the port if needed

server.listen(PORT, () => {
  console.log(`JSON Server is running on port ${PORT}`);
});`

## Start the JSON Server with PM2
`pm2 start server.js --watch ./data/db.json --name json-server`

## Access the JSON Server
`pm2 list` List all PM2 processes
`pm2 save json-server` To save the JSON server process
`pm2 stop json-server` To stop the JSON server process
`pm2 start json-server` To start the JSON server process if it's stopped
`pm2 restart json-server` To restart the JSON server process
`pm2 delete json-server` To delete the JSON server process from pm2


