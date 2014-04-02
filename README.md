# In-Memory MySQL script

You may decide that you want to run mysql in memory for accelerated testing etc.  This python script ([originally found here](https://raw.github.com/ksolademi/python-dev-utils/master/mysql-ramdisk.py)) will take care of the specifics for you.

### Script Options

Description | Shorthand Option | Longhand Option | Default
--- | --- | --- | ---
Kill the ramdisk | -k | --kill-ramdisk | _none_
Path to the ramdisk | -p | --path-to-ramdisk | `/dev/disk3` on OSX or `/mnt/ramdisk` on Linux
Create the ramdisk | -c | --create-ramdisk | _none_
Ramdisk size | -s | --ramdisk-size | 128 MB
Disable Linux App Armor | -a | --disable-apparmor | _none_
Install MySQL in memory and start it | -m | --with-mysql | _none_

## Create an in-memory MySQL DB    
    ./mysql-ramdisk.py --create-ramdisk --with-mysql

## Connect to that DB
    mysql --socket=/tmp/mysql.sock
    
## Destroy the DB
    ./mysql-ramdisk.py --kill-ramdisk