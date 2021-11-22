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
