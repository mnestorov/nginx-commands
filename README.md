# Ubuntu with Nginx useful commands

## Start Nginx

`service nginx start`

If you're using a systemd based version such as Ubuntu Linux 16.04 LTS and above, use systemctl within the command, like so:

`systemctl start nginx`

## Stop Nginx

Stopping Nginx will kill all system processes quickly. This will terminate Nginx even if there are open connections. 
In order to do so, run one of the following commands:

`service nginx stop`

`systemctl stop nginx`

This command can still, however, take some time on busy servers. Therefore, if you want Nginx to stop even faster, you can also use:

`killall -9 nginx`

## Quit Nginx

Quitting Nginx is very similar to stopping it however it does so gracefully which means it will finish serving open connections before shutting down. To quit Nginx, use one of the following commands:

`service nginx quit`

`systemctl quit nginx`

## Restart Nginx

Restarting Nginx basically performs a stop then a start. Use one of the following commands to run an Nginx restart:

`service nginx restart`

`systemctl restart nginx`

## Reload Nginx

Reload is a bit different from restart in that, again, it is more gracefully. According to Nginx, reload is defined as "start the new worker process with a new configuration, gracefully shut down old worker processes.". You can reload Nginx by using one of the following commands:

`service nginx reload`

`systemctl reload nginx`

## View server status

Check what the current status of your Nginx web server is with one of the following commands:

`service nginx status`

`systemctl status nginx`

## Test Nginx configuration

You can test your Nginx server's configuration file before restarting or reloading it completely.

`nginx -t`

## Check Nginx version

`service nginx -v`

`systemctl -v nginx`

## Show command help

`service nginx -h`

`systemctl -h nginx`

## Switch between PHP versions on Ubuntu with Nginx

Please use the below command:

`sudo update-alternatives --config php`

After run above command select the PHP version that you need to use.

**Note:** *Press to keep the current choice *, or type selection number: For example 2*

After switching below command used to restart the PHP and Nginx server.

`sudo service nginx restart`

`sudo service php7.1-fpm or php7.2-fpm  restart`
