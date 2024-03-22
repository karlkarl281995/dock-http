
---

## dock-http

A simple web application using Docker container and Apache HTTP.

This project is designed for a macOS environment. While some commands may be macOS-specific, you can adapt them for your local environment on Windows or Linux.

For Docker and Git installations, you can simply follow the respective OS installer download links.

### Key Takeaways:

**Branch Specification:** Ensure to choose the appropriate branch specifier (e.g., Master or Main) depending on the configuration of your local repository. This ensures smooth synchronization between your local and remote repositories.

If you have issues troubleshooting GIT and your local repo, refer to the [🔑 Secure GitHub Connection Guide] at the bottom of this document.

---

### Section I

1. **Fork the repository into your GitHub account:** [dock-http](https://github.com/karlkarl281995/dock-http).

2. **Clone the repository into your local environment:**
   
    ```bash
    git clone https://github.com/karlkarl281995/dock-http.git
    ```

    ![Git Clone](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/git%20clone.png)

3. **Change directory to `dock-http`:**
   
    ```bash
    cd dock-http
    ```

---

### Section II

1. **Download Docker Desktop from [here](https://docs.docker.com/desktop/install/mac-install/). Choose Docker Desktop for Mac with an Intel chip.**

2. **After setting up Docker Desktop, open Terminal and sign in:**
   
    ```bash
    docker login <username>
    ```

3. **Check Docker version:**
   
    ```bash
    docker -v
    ```

    ![Docker Version](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/Screen%20Shot%202024-03-13%20at%202.09.34%20PM.png)

4. **Create a Dockerfile:**
   
    ```bash
    vi Dockerfile
    ```

    Paste the following content:

    ```Dockerfile
    FROM httpd:2.4
    COPY . /usr/local/apache2/htdocs/
    ```

    Save and exit (`:wq!`).

    ![Vi Dockerfile](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/vi%20dockerfile.png)

---

### Section III

7. **Build the Docker image:**
   
    ```bash
    docker build -t dock-http:v1 .
    ```

    ![Docker Build](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/dock%20build%20.png)

8. **Check if the image is created:**
   
    ```bash
    docker images
    ```

    ![Docker Image](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/dock%20image%20http.png)

9. **Run the Docker container:**
   
    ```bash
    docker run -d --rm --name karlvalcourtweb -p 90:80 dock-http:v1
    ```

    ![Docker Run](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/docker%20run%20for%20container%20.png)

    Alternatively, you can start the container using Docker Desktop.

    ![Docker Desktop](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/dock-http%20image.png)

10. **Access the web server in your browser:**
    - Type `localhost:90` in the address bar.
    ![Localhost 90](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/localhost%2C90.png)
    - Or check the ports section in Docker Desktop.
    ![Start Browser](https://github.com/karlkarl281995/dock-http/blob/main/dock-http%20w%3A%20pictures/start%20browser%20from%20play%20button%20.png)

11. **Congratulations!** You have successfully deployed your Apache Webserver using Docker.

---

The last important thing to add is to push your changes from your local repo to your repository:

```bash
git add . 
git commit -m "Dockerfile"
git push origin main
```

### 🔑 Secure GitHub Connection Guide

**Step-by-Step Setup:**

1. **Navigate to Settings:** Go to your GitHub account settings, then select "Developer Settings."

2. **Generate Key Pair Token:** Under "Developer Settings," locate the option to generate a key pair token (classic).

3. **Select First Box:** Ensure to check the first box of each line to grant appropriate permissions.

4. **Save Token:** Once generated, save the token key pair securely, either in a clipboard or a notes file. It's crucial not to lose this token.

5. **Usage during Git Push:** When prompted during a Git push operation, enter this token into the password field.

**Success:** You're all set! Your GitHub connection is now secured using the generated token.

---

Feel free to let me know if you need further adjustments or have any other requests!
