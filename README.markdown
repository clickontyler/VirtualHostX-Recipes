# Custom Server Recipes

Beginning with [VirtualHostX](http://clickontyler.com/virtualhostx/) 2.8, you can create custom server recipes that let VirtualHostX work with alternative Apache servers such as [Zend Server CE](http://www.zend.com/en/products/server-ce/), [BitNami](http://bitnami.org/), and [Acquia Drupal](http://acquia.com/products-services/acquia-drupal) just to name a few. This is in addition to the servers that VHX has built-in support for &mdash; [MAMP](http://bitbob.com/mac-web-development-made-easy), [XAMPP](http://www.apachefriends.org/en/xampp.html), and Apple's built-in Apache.

**To install a server recipe someone has given you**, just double-click the file. VirtualHostX will automatically open and confirm if you'd like to install the recipe.

**To create a custom server recipe of your own**, choose "Custom" as your Default Web Server in VirtualHostX's Preferences, and fill in the appropriate settings for the web server you are using. Each setting is described below.

## httpd.conf

The full path to your Apache httpd.conf file.

## vhosts.conf

The full path to the conf file you would like VirtualHostX to save your virtualhost containers to. This can be any file on your Mac as long as you have modified your httpd.conf file to include it.

To ensure Apache loads your virtual hosts, make sure your httpd.conf file includes it by adding a line similar to:

    Include /private/etc/apache2/extra/httpd-vhosts.conf

## Start, Stop, and Restart Commands


This is the full path and arguments to the commands you use to start, stop, and restart your web server. This can be a shell script, an executable file, anything. For example, the following command will start Zend Server CE's Apache server:

    /usr/local/zend/apache2/bin/httpd -k start

## Notes

 * Type the command as you would in a terminal shell. 
 * If the executable name or an argument contains a space, escape the space by prepending it with a backslash "\" character. There is no need to escape the spaces between arguments. Also, do not use quotation marks to escape spaces.
 * Do not prefix your command with "sudo". VirtualHostX will automatically execute your command with administrator privileges.
 * If you leave the restart command blank VirtualHostX will instead execute the stop and start commands in order.

## Contributing

If you'd like to contribute your own VirtualHostX recipe, feel free to fork this project, add your recipe, and send me a pull request. Or, you're welcome to email the recipe file to me directly at [support@clickontyler.com](mailto:support@clickontyler.com). You can also contact me if there's a server you need helping creating a recipe for.