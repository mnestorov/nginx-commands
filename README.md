# Ubuntu with Nginx useful commands

## Switch between PHP versions on Ubuntu with Nginx

Please use to below command:

`sudo update-alternatives --config php`

After run above command select the PHP version that you need to use.

**Note:** *Press to keep the current choice '*', or type selection number: For example 2*

After switching below command used to restart the PHP and Nginx server.

`sudo service nginx restart`

`sudo service php7.1-fpm or php7.2-fpm  restart`
