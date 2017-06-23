This is the base docker-compose set up I use for WordPress sites. It contains images for apache-php, mysql and mailhog.

**How To Use

- Install docker-compose. See https://docs.docker.com/compose/

- Download WordPress from https://wordpress.org and put the wordpress files in the `src` folder

- In the `wp-config.php` file set up the database as follows

  `define('DB_NAME', 'wordpress');`

  `define('DB_USER', 'root');`

  `define('DB_PASSWORD', 'root');`

  `define('DB_HOST', 'mysql-server');`

- Run `docker-compose up -d` and voila!! you're good to go

- In your browser go to http://localhost

- You can also add an entry to your hosts files (that's at `/etc/hosts` on debian-based systems) to customize the URL for the wordpress site. The default friendly name is `wordpress.local`. You can change this from the apache configuration file at `includes/000-default.conf`

- Access the mailhog app by going to http://localhost:8025

