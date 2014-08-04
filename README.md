After updating to OSX 10.9, the default php shipped with OSX has been updated to 5.4. Zend.com doesn't publicly provide a zend debugger for php 5.4.x.Here are the steps to install zend debugger on Mac OSX 10.9 64bit. The files used here are offically shipped within zend server.

Step 1. Download ZendDebugger.so from https://github.com/mkb2000/zend_debugger.

Step 2. Put ZendDebugger.so at somewhere like /Library/WebServer/Documents/zend_debugger.

Step 3. Modify php.ini. The default configuration file used by Mac OS is /private/etc/php.ini. Admin permission is required to modify this file. So go /Applications/Utilities and open Terminal. Enter "sudo nano /private/etc/php.ini". Jump to the end of this file and add:
[zend_debugger]
zend_extension="/the/path/to/the/folder/you/made/in/step2/ZendDebugger.so"
zend_debugger.allow_hosts=127.0.0.1, localhost
zend_debugger.expose_remotely=always
Control+x to save this file. You'd better comment out Xdebug if it is enabled. (Here is also a full version of debug configuration available at https://github.com/mkb2000/zend_debugger/blob/master/debugger.ini which is shipped with zend server. Take a look for more details.)

Step 4. Download dummy.php from https://github.com/mkb2000/zend_debugger/blob/master/dummy.php. Put it in your web server root document fold. By default, it is /Library/WebServer/Documents. 

Step 5. Restart apache. In Terminal, enter sudo apachectl restart.


Step 6. Choose to use zend debugger in zend studio or eclipse.
