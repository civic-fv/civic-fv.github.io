# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.183.0/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version: bionic, focal
ARG VARIANT="focal"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# install requisite packages
RUN sudo apt update
RUN sudo apt -y upgrade
RUN sudo apt -y install \
                ruby-full 
                git 
                build-essential 
#                python3

# get bundler gem and make sure it is upto date
RUN sudo gem install bundle
RUN sudo bundle update --bundler

# grap the website template from the template repo (only the release/master branch)
RUN git clone --single-branch --branch master github.com:osterhoutan-UofU/comweb /workspaces/comweb

# Set the origin repository (the template repo) to upsream
RUN cd /workspaces/comweb && \
        git remote rename origin upstream
# Set the upstream push URL to an error message to prevent bad pushes 
RUN cd /workspaces/comweb && \
        git remote set-url --push upstream "!! BAD_PUSH :: DO NOT TRY TO PUSH TO THE TEMPLATE REPOSITORY !!"

# install the prerequisite gems for the project
RUN cd /workspaces/comweb/site-src && sudo bundle install

# Remember to set up an ssh key in the docker, 
#  your name & email address in /workspaces/comweb/.git/config like so:
#   ```config
#   [user]
#       name = <github-username>
#       email = <github-push-associated-email-address>
#   ```
# You could also do this via command line w/ the following commands:
#   ```sh
#   # from insode the repo: `/workspaces/comweb`
#   cd /workspaces/comweb
#   git config user.name <github-username>
#   git config user.email <github-push-associated-email-address>
#   ```
# Then of course add your new remote repository so you can function
#  This dockerfile just pulls in the template repo 
#     then prevents you from accidentally pushign to it.
# To do so just run the following command:
#   ```sh
#   git remote add origin <repo-url>
#   ```
# After which make sure to push everything to get the repo up to date 
#   (if you already have things set up then pull everything instead.)
