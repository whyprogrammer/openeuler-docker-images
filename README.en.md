# openEuler official container images

#### Introduction

Dockerfiles for openEuler official container images, include openEuler basic image and appliaction images.


#### openEuler Basic Container Image

openEuler basic image is published by openEuler community in [openEuler repo](https://repo.openeuler.org)


"openeuler:latest" is current stable avalible image.

After offcial images published, we will push to every remote container images hub:

- name: `openeuler/openeuler`
- Download: `docker pull [Remote repo URL]openeuler/openeuler[:tags]`
- Support arch: amd64, arm64
- Tags:
    - [21.09](https://repo.openeuler.org/openEuler-21.09/docker_img/)
    - [20.09](https://repo.openeuler.org/openEuler-20.09/docker_img/)
    - [20.03-lts](https://repo.openeuler.org/openEuler-20.03-LTS/)
    - [20.03-lts-sp1, 20.03](https://repo.openeuler.org/openEuler-20.03-LTS-SP1/docker_img/)
    - [20.03-lts-sp2](https://repo.openeuler.org/openEuler-20.03-LTS-SP2/docker_img/)
    - [20.03-lts-sp3](https://repo.openeuler.org/openEuler-20.03-LTS-SP3/docker_img/)
    - [21.03](https://repo.openeuler.org/openEuler-21.03/docker_img/)
    - [22.03-lts, 22.03, latest](https://repo.openeuler.org/openEuler-22.03-LTS/docker_img/)
- Path rule：`openeuler/[openEuler version]/Dockerfile`,
such as: openEuler 21.09 Dockerfile is under `openeuler/21.09/Dockerfile` path.

#### openEuler Application Container Image

Dockerfiles for various popular application implementations based on openEuler basic image.

- Path rule：`[Application name]/[Application version]/[openEuler version]/Dockerfile`,
such as, the nginx 1.20.1 based on openEuler 20.03 LTS SP1 is under `nginx/1.20.1/20.03-lts-sp1/Dockerfile`.
- The container images would be published after Dockerfile merged under `openeuler`,
such as: `openeuler/nginx:1.20.1-20.03-lts-sp1`.

Every openEuler application images contains the README (such as nginx/README.md), included:

- Desciption for container images build.
- openEuler, container service (like Docker, iSula) and application version info.

The container images would be published under `openeuler` after Dockerfile merged. We use `docker buildx` to build the container image for amd64 and arm64 platforms.
The build steps are as follows:
- go into directory of `[Application name]/[Application version]/[openEuler version]`
- execute the command `docker buildx build -t tag_name --platform linux/amd64,linux/arm64 .`

#### Avalible Container Repo

- Hub oepkgs: https://hub.oepkgs.net/

- AtomHub: https://atomhub.org/


#### Contributions

Welcome to submit your idea, issue and pull request.
