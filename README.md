# monitoring-framework

# monitoring-frontend

Steps to run this repository -

1. Make sure you have npm installed in your system
2. Run `npm install`
3. Replace the server array contents in endpoints.js with the actual endpoints of the servers you want to monitor
4. Run `npm start` and the server should be up at - http://localhost:3000

Steps to obtain metrics -

1. Make sure the server is up and running
2. Run `npm install -g lighthouse`
3. Run `lighthouse http://localhost:3000`. This will create an HTML file with the metrics dashboard.
4. To obtain the react flamegraph metrics, follow this guide - https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi

# monitoring-backend

This is a client-side back-end monitoring application written in Python using the Flask framework. It utilizes the psutil library along with other metrics libraries to gather system data, and use HTTP GET requests to send them in the form of JSON response bodies.

The steps to setup the application are as follows:

1. After cloning the repo, cd into the folder and run this command: 'sudo docker image build -t flask_docker .'
2. The docker build command takes two environment variables, PORT (Defaults to 5009) and CONFIG (Defaults to log_config.txt, already included in the repo).
3. After installing the required dependencies, run the command 'sudo docker run flask_docker' to run the server in command line
4. After the server begins running, localtunnel will display the internet-facing URL of the server, which you can copy, and then replace it in the front-end dashboard

The log_config.txt file can be changed by appending the absolute path to the desired log as a key-value pair in the [Logs] section.
Additionally, the modules /network_info (hostname=), /process_info (length=), and /logs_info (length=) take optional URL parameters.
