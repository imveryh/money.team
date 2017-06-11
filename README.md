# MONEY.TEAM forum nginx config ([forum link](https://forums.money.team))
This is how I've setup MONEY.TEAM's nginx config and I use this setup for most of my other sites.<br>
Feel free to use it as I haven't made it all myself, majority if not 80% is taken from [H5BP's config](https://github.com/h5bp/server-configs-nginx/)<br>
There are however a few minor tweaks I've added myself<br>

## Tweaks
  * [Only allow cloudflare to connect to the site](https://github.com/stugmi/money.team-forum-nginx/blob/master/sites-available/default.conf#L4)
  * [Force real IPs from CF](https://github.com/stugmi/money.team-forum-nginx/blob/master/money/cloudflare-realip.conf)
  * [php config in one file](https://github.com/stugmi/money.team-forum-nginx/blob/master/money/php.conf)

## Notice
Remember to change [php.conf](https://github.com/stugmi/money.team-forum-nginx/blob/master/money/php.conf) based on what you have installed.<br>
This install is based around [php-fpm](https://www.nginx.com/resources/wiki/start/topics/examples/phpfcgi/), specically php7.0-fpm which I highly recommend, it's blazing fast.

## Installing
Installing should be pretty straigh forward, just place all the files inside your `/etc/nginx` folder.<br>
It's important you always backup your insallation if you're dealing with something new, so backup that nginx fold right now.<br>

To activate your vhost create a symlink `sites-avaliable/default.conf` into `sites-enabled/<domain-name>`.<br>
To do so simply run this command:<br> `ln -sf /etc/nginx/sites-avaliable/default.conf /etc/nginx/sites-avaliable/money.team`
