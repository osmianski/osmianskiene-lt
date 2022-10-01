Source code for osmianskiene.lt

* [Developing Locally](#developing-locally)
    * [Prerequisites](#prerequisites)
    * [Installation](#installation)
    * [Running The Project](#running-the-project)
    * [Installing Plugins And Themes](#installing-plugins-and-themes)

## Developing Locally

### Prerequisites

Download and install:

* [Docker](https://docs.docker.com/get-docker/)
* [Docker Compose](https://docs.docker.com/compose/install/)

If you are working on a Mac, install [Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/install/) instead. It includes Docker and Docker Compose out of the box.

If you use Windows, install [Docker Desktop for Windows](hhttps://docs.docker.com/desktop/install/windows-install/) instead. 

### Installation

Clone the project from GitHub:

```shell
cd ~/projects
git clone git@github.com:osmianski/osmianskiene-lt.git
```

### Running The Project

Start the Docker containers for the project:

```shell
cd ~/projects/osmianskiene-lt
docker-compose up
```

Open the local copy of the website in the browser:

* [Frontend](http://127.0.0.1:8000/)
* [Admin](http://127.0.0.1:8000/wp-admin/)

### Installing Plugins And Themes

Use the WordPress Dashboard. To enable it:

1. Add the following to `wordpress/wp-config.php`:

    ```php
    /**
     * Allow installing and updating plugins and themes
     */
    define('FS_METHOD', 'direct');
    ```

2. Set directory permissions:

    ```shell
    # run on the host machine
    cd ~/projects/osmianskiene-lt
    docker exec -it osmianskiene-lt-wordpress-1 /bin/bash
   
    # run inside the container
    chown -R www-data:www-data wp-content/uploads
    ```

 
