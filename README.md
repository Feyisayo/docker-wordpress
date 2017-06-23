This is the base docker-compose set up I use for WordPress sites.

**How To Use**

- Put your wordpress files in the `src` folder
- Run `docker-compose up -d` and voila!! you're good to go
- In your browser go to http://localhost
- You can also add an entry to your hosts files (that's at `/etc/hosts` on debian-based systems) to customize the URL for the wordpress site.
- Access the mailhog app by going to http://localhost:8025

