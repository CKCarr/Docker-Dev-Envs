# Node-js_ENV

Steps to Set up Docker and run the project environment:
These steps are after you have Docker installed on your machine and in VScode have remote extension installed.

Open the Repo Docker-Dev-Envs from Github in VScode.

Check the files in the Dockerfile to make sure the enviroment is setup correctly for your project.

Check the nodeConfigs.sh file to make sure the files you want to work with I.E. package.json, babel.config.js, webpack.config.js, etc. are in the file.

Check the Makefile to ensure what you want to call the image and container are correct.(Maybe project name)

Open the terminal in VScode and run the following command to build the image: make build (This will build the image)

Run the following command to start the container: make run (This will start the container)

In vscode open your Remote Explorer and click on the container with the project name you gave it in the Makefile. You may need to click at the top left corner and select Dev Container if not already selected. Attach to current window or open new window with the container/project.
