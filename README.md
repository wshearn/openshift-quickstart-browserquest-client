openshift-quickstart-browserquest-client
========================================

Mozillas Browser Quest Client for OpenShift

Quickstart
==========

1) Setup the server directions are here https://github.com/wshearn/openshift-quickstart-browserquest-server/blob/master/README.md

2) Create a PHP application:

    rhc app create -a bqclient -t php-5.3

3) Add this upstream repo

    cd bqserver
    git remote add upstream -m master git://github.com/wshearn/openshift-quickstart-browserquest-client.git
    git pull -s recursive -X theirs upstream master

4) Edit the config files

    cp php/config/config_build.json-dist php/config/config_build.json
    cp php/config/config_build.json-dist php/config/config_local.json

Edit those 2 new files and set the server URL to the one you created in step 1

5) Then commit the changes and push the repo upstream

    git add -A ; git commit -m "Set server URL" ; git push

5) That's it, you can check it out at http://bqclient-$namespace.rhcloud.com.


