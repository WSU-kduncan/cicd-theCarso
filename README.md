# Project 6

## Part 1:
- Clone Repo: `git clone git@github.com:WSU-kduncan/cicd-theCarso.git`
- Installed Docker from: `https://docs.docker.com/desktop/windows/install/`
    - In Settings > Resources > WSL: Enable Ubuntu-20.04
- Grab an Image: `docker pull httpd`
- Created a Dockerfile that builds the image.
- Build Container: In directory with website folder...
    - `docker build -t myapache:1.0 .`
- Run Container:
    - `docker run -dit -p 80:80 --name testname myapache:1.0`
- View Project:
    - Go to `localhost` or `130.108.238.27` in a browser.
    - OR just `curl <address>` with the IP above.


## Part 2:
- Create DockerHub Repo: `https://hub.docker.com/repositories`
    - Repo Link: `https://hub.docker.com/r/ctm21/project6`
    - Click 'Create Repository' button. Input name, select public, click create.
- Docker CLI:
    - Settings > Security > New Access Token > Read, Write, Delete
    - `docker login -u ctm21`
    - For Password: Type access code from 2 steps ago.
- GitHub Secrets:
    - Credentials needed are Username and Access Token
    - In GitHub Repo: Settings > Secrets > New Repository Secret
    - DOCKER_USERNAME = ctm21
    - DOCKER_PASSWORD = DockerHub token
- Configure Workflow:
    - Replace DOCKER_HUB_REPO with ctm21/project6
    - Add condition for when pushed to master:
        - `push:`
            - `branches: [master]`

## Part 3:
- Installation: (From https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)
    - `sudo apt install apt-transport-https ca-certificates curl software-properties-common`
    - `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`
    - `sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"`
    - `sudo apt install docker-ce`
    
- Login:
    - `sudo docker login` then use Username: ctm21 and Password: {token}
- Pull:
    - `sudo docker pull ctm21/project6`
- Run:
    - `sudo docker run -dit -p 80:80 ctm21/project6`
