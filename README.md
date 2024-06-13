
# Docker Compose for PHP7

This repository provides a Docker Compose setup for PHP 7 development, including the most common PHP extensions and a MySQL database. It's designed to help you quickly set up a local development environment.

## Containers Included

- **PHP 7**
  - Dockerfile: `./etc/docker/dockerfile_php_7`
  - Common PHP extensions included
  - Apache server configuration
- **MySQL 5.7**
  - Official MySQL image

## Getting Started

### Prerequisites

Make sure you have Docker and Docker Compose installed on your machine. If not, you can follow the instructions on the official [Docker documentation](https://docs.docker.com/get-docker/) to install Docker and [Docker Compose documentation](https://docs.docker.com/compose/install/) for Docker Compose.

### Setup

1. **Clone the repository:**

    ```bash
    git clone https://github.com/yourusername/php7-docker-compose.git
    cd php7-docker-compose
    ```

2. **Build and start the containers:**

    ```bash
    docker-compose up -d
    ```

3. **Access the application:**

    - The PHP application will be available at `http://localhost`.
    - The MySQL database will be accessible on port `3306`.

### Configuration

- **PHP:**
  - The PHP configuration files are located in `./etc/php`.
  - Custom Apache configurations are in `./etc/apache2`.

- **MySQL:**
  - MySQL configuration files are located in `./etc/mysql`.
  - The initial database setup script can be placed in `./etc/mysql`.

### Volumes

- `./sites:/var/www/html`: PHP application files.
- `./etc/php:/usr/local/etc/php`: PHP configuration.
- `./etc/apache2/apache2.conf:/etc/apache2/conf-enabled/apache2.conf`: Apache main configuration.
- `./etc/apache2/hosts.conf:/etc/apache2/sites-enabled/hosts.conf`: Apache virtual hosts configuration.
- `./etc/php/php-mail.conf:/usr/local/etc/php/conf.d/mail.ini`: PHP mail configuration.
- `./etc/php/php.ini:/usr/local/etc/php/php.ini`: PHP main configuration.
- `./etc/logs:/var/log`: Log files.
- `./etc/mysql:/docker-entrypoint-initdb.d`: MySQL initialization scripts.
- `./etc/mysql/my.cnf:/etc/mysql/my.cnf`: MySQL configuration.
- `./etc/mysql/data:/var/lib/mysql-files`: MySQL data files.

### Environment Variables

- `MYSQL_ROOT_PASSWORD`: The root password for MySQL.
- `MYSQL_DATABASE`: The name of the default database.

### Stopping the Containers

To stop the containers, run:

```bash
docker-compose down
```

## Contributing

Feel free to use, fork, or contribute to this repository. Any contributions that improve the setup or documentation are welcome.

## License

This project is licensed under the MIT License.

## Contact

If you have any questions or suggestions, please open an issue on GitHub.

Happy coding!