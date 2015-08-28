# pifhem

Simple bash script to setup fhem on Raspberry Pi

## Hints

**CAUTION!** This script is currently meant to create a raspberry pi fhem server from scratch. It does the following additional steps:

 - Removing the raspbian desktop

## Upcoming Changes

In order to address the above issues, I will extend the number of optional parameters in order to let you decide if you want to execute the above mentioned steps.

## Usage

First of all get a Raspberry Pi running the latest version of the Raspbian os or any other debian based system for the Raspberry Pi. Connect to your pi via ssh or acess it directly and login as **root**. Switch to the temp dir:

    [root@pi]$ cd /tmp

Download the latest version of *pifhem* from the git repository:

    [root@pi]$ git clone https://github.com/Avedo/pifhem

Switch into the downloaded directory and run the *pifhem* script with the -h option to see all possible options:

    [root@pi]$ ./pifhem -h

This should prompt the following:

    Usage: pifhem [-hvdUcn] [-V <fhem_version>] [-H <hostname>] [-u <username>] [-p <user_password>] [-r <root_password>]

    -h|--help:
      Displays this help.
    -v|--version
      Displays the current version of this script.
    -V|--fhem-version
      Fhem version to be used.
    -H|--hostname
      The hostname to be used.
    -u|--username
      Name of the fhem user.
    -p|--password
      Password of the fhem user.
    -r|--root
      Password of the root user.
    -d|--delete
      Delete default pi user.
    -U|--update
      Update base system.
    -c|--cleanup
      Cleanup old kernels.
    -n|--ntp
      Setup ntp as datetime server.

To install fhem version *5.6*, change the hostname to *pifhem*, create an *fhem* user with password *s3cr37* and change the root password to *v3rys3cr37* you can run the follwing command:

    [root@pi]$ ./pifhem -V 5.6 -H pifhem -u fhem -p s3cr37 -r v3rys3cr37

And that's it. You should now be able to go to *<raspberry_ip>:8083* to see your fhem web interface.

## License

The *pifhem* bash script is licensed under the terms of the Apache License 2.0.

[![License](http://img.shields.io/badge/license-Apache--2.0-blue.svg?style=flat)](LICENSE)
