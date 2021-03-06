# StorjMonitor
Node.js script for publishing data from local Storj nodes to https://Storjstat.com


# Install Instructions

## Windows

The monitor can easily be started by running "storjMonitor.bat", by download the whole project you also download a NodeJS portable client. The only change you need to do is in "storjMonitor.js" and change line 10 (var token = "YOUR-TOKEN-HERE") to be your api token to communicate with Storjstat.com API.

## Linux

1. Clone/Copy this Repo to your local storage. Eg. `git clone https://github.com/calxibe/StorjMonitor.git `
2. Change into the directory. `cd StorjMonitor/`
3. Modify the install Script to executable. `chmod +x storjMonitor-install.sh`
4. Run the Script! `./storjMonitor-install.sh`
5. Enter your API Key from the website into the line 10 in storjMonitor.js (var token = "YOUR-TOKEN-HERE").
6. Execute the Monitor Script. `./storjMonitor.sh` or via seperate screen `screen -dmS StorjMonitor ./storjMonitor.sh`

## Docker

1. Pull the Docker image from docker hub. `docker pull calxibe/StorjMonitor`
2. Run the Docker container.`docker run -e TOKEN=MY-TOKEN -e STORJ_DAEMON=1.2.3.4 --name StorjMonitor calxibe/StorjMonitor`
   * 3 variables exists:
     * `TOKEN`: the API key from the website
     * `STORJ_DAEMON`: the host of Storj daemon (`storj` per default)
     * `STORJ_PORT`: the port of Storj daemon (`45015` per default)

If Storj daemon is running also on a docker, the simplest is to make a link at
run time. (let's say that the container of Storj Daemon is `MyStorjContainer`):

`docker run -e TOKEN=MY-TOKEN --link MyStorjContainer:storj --name StorjMonitor calxibe/StorjMonitor:latest`

## Troubleshooting

In case the Linux Install Script is throwing issues you may need to install some dependencies first:
```
sudo apt-get install -y nodejs-legacy
sudo apt-get install -y build-essential
```
