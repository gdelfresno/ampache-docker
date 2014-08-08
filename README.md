ampache-docker
==============

Ampache build using docker

The Ampache server will listen on port 80. Please set up a reverse proxy using Nginx or Apache if you would like to use SSL. There are currently three volumes set up. One is /var/www/config for the Ampache configuration files, one  is /var/www/themes for your ampache themes, and the other is for your media at /media. I recommend copying the default ampache themes from the main tarball found at https://github.com/ampache/ampache/releases into the themes directory you mounted.

MYSQL database is required and is not included in the base image. This can be added however through a docker link to a mysql container.

Audio transcoding is working and has been tested. Video transcoding should work, but has not been tested.

Example to start and serve on port 80 on your local machine:

docker run -d --name ampache -v /my/media:/media -v /my/config:/var/www/config -v /my/themes:/var/www/themes -p 80:80 --link mysql:mysql velocity303/ampache-docker

Happy Listening!
