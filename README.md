# dock-http
A simple web application using Docker container and HTTP. 

This project is designed for a macOS environment. While some commands may be macOS-specific, you can adapt them for your local environment on Windows or Linux.

For Docker and Git installations, you can simply follow the respective OS installer download links.


**Section I**

1. Fork the repository into your GitHub account: [dock-http](https://github.com/karlkarl281995/dock-http).



2. Clone the repository into your local environment:
    
    git clone https://github.com/karlkarl281995/dock-http.git

![](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/git%20clone.png)


3. Change directory to `dock-http`:
    
    cd dock-http

**Section II**

1. Download Docker Desktop from [here](https://docs.docker.com/desktop/install/mac-install/). Choose Docker Desktop for Mac with an Intel chip.

2. After setting up Docker Desktop, open Terminal and sign in:
 
   docker login <username>
   

3. Check Docker version:

    docker -v
    
![](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/Screen%20Shot%202024-03-13%20at%202.09.34%20PM.png)


4. Create a Dockerfile:
    
    vi Dockerfile
   

    Paste the following content:
    
    FROM httpd:2.4
    COPY . /usr/local/apache2/htdocs/
   

    Save and exit (`:wq!`).

![](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/vi%20dockerfile.png)

**Section III**

7. Build the Docker image:
   
    docker build -t dock-http:v1 .
![](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/dock%20build%20.png)
   

8. Check if the image is created:
  
    docker images
    
![](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/dock%20image%20http.png)
9. Run the Docker container:
   
    docker run -d --rm --name karlvalcourtweb -p 90:80 dock-http:v1

![](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/docker%20run%20for%20container%20.png)

    Alternatively, you can start the container using Docker Desktop.

https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/dock-http%20image.png

10. Access the web server in your browser:
    - Type `localhost:90` in the address bar.
![](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/localhost%2C90.png)
    - Or check the ports section in Docker Desktop.

![](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/start%20browser%20from%20play%20button%20.png)

11. Congratulations! You have successfully deployed your Apache Webserver using Docker. 

Feel free to let me know if you need further adjustments or have any other requests!
