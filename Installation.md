# Installing and starting Virtuoso Open Source on MacOS Montery 
I used the official docker container from Opennlink on Deocker Hub with statement:  
```
$ mkdir my_virtdb
$ cd my_virtdb
$ docker run \
    --name my_virtdb \
    --interactive \
    --tty \
    --env DBA_PASSWORD=mysecret \
    --publish 1111:1111 \
    --publish  8890:8890 \
    --volume `pwd`:/database \
    openlink/virtuoso-opensource-7:latest
```

When Virtuoso is up and running on http://localhoast:8890  

Openlink has Virtuoso publiced on [github](https://github.com/openlink/virtuoso-opensource)  
I used the latest release with the same major version number (ie 7.2) for [linux x86-64](https://github.com/openlink/virtuoso-opensource/releases/download/v7.2.10/virtuoso-opensource.x86_64-generic_glibc25-linux-gnu.tar.gz) to get all the VAD's. Copy the VAD directory into the my_virtdb directory. Go to http://localhoast:8890 click on **Conductor** en login with userid: **dba** and **DBA_PASSWORD** used in the docker command (**mysecret** in this example). Go to **System Admin** tab and then the **Packages** tab. Change the Package path: with the **change** button above the package list and choose **Server-side file** and browse to the copied VAD directory and choose **select** button. Now you can select which packages you want to install.
