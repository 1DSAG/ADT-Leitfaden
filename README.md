# ADT-Leitfaden

#### Installation Steps Docker Container

Install the following programs:

* [Visual Studio Code](https://code.visualstudio.com/)
* [Remote Containers Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
* [Docker](https://code.visualstudio.com/docs/remote/containers)

Clone the repository with the command _[Remote-Containers: Clone Repository in Container Volume...](https://code.visualstudio.com/docs/remote/containers-advanced#_use-clone-repository-in-container-volume)_

This will

* Clone the Repository in a Container Volume
* Build the Docker Image
* Start the Docker Container and map the required ports
* Mount the created Container Volume
* Install the required npm packages
* Install the required ruby gems

The only thing left to do is open the console in Visual Studio Code (it is attached to the running Development Container), navigate into the docs folder and start the Development Server:

```shell
cd docs
bundle exec jekyll serve --livereload
```
