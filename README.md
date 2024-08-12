<h1><center>Docker familiarization</center></h1>
<h2 style=text-align:right>10-08-2024</h2>

Basic docker familiarization. And study of how to create ann container and move to an port.
container inspect.

<h3>Installation</h3>
<h4>1.Update your package list:</h4>sudo apt-get update

<h4>2.Install Docker Engine:</h4>sudo apt-get update<br>
sudo apt-get install docker-ce docker-ce-cli containerd.io

<h4>Verify the installation:</h4>
sudo docker --version

<h3>Build an html docker container running on port 4040</h3>

<h4>1. Create a Project Directory</h4>
mkdir html-docker<br>
cd html-docker
<h4>2. Create an HTML File</h4>
echo "Hello, Docker!"> index.html
<h4>3. Create a Dockerfile</h4>
touch Dockerfile<br>
Add the following content to the Dockerfile:
<br>

// Use an official Nginx image as the base image<br>
FROM nginx:alpine

<br>// Copy the HTML file to the default Nginx directory<br>
COPY index.html /usr/share/nginx/html/index.html<br>
<h4>4. Build the Docker Image</h4>
docker build -t html-docker .<br>
<h4>5.Run the Docker Image</h4>
sudo docker run html
<h4>6.move to the port 4040</h4>
sudo docker run -d -p4040:80 html

<h4>6.Access the Web Page</h4>

Open a web browser and go to http://localhost:4040. You should see the "Hello, Docker!" message from your index.html file.
