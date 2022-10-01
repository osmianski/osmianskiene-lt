Source code for osmianskiene.lt

* [Developing Locally](#developing-locally)
    * [Prerequisites](#prerequisites)
    * [Installation](#installation)
    * [Run The Project](#run-the-project)

## Developing Locally

### Prerequisites

1. Install [PHP, Composer, Docker](https://laravel.com/docs/9.x).

### Installation

Clone the project from GitHub:

```shell
cd ~/projects
git clone git@github.com:osmianskiene/osmianskiene.git
```

### Installing plugins and themes.

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

### Run The Project

Start the Docker containers for the project:

```shell
cd ~/projects/osmianskiene-lt
docker-compose up
```

Open the local copy of the website in the browser:

* [Frontend](http://127.0.0.1:8000/)
* [Admin](http://127.0.0.1:8000/wp-admin/)
 
