# Online Convenience Store
Docker in a SQLi Box

## Introduction

A simple docker application using Ubuntu 16.04 xenial, apache2 httpd (2.4), php (7.0) and mariadb (10). The only problem is it has a problem. Time to practice some SQL injection. 

## Installation

The application is packaged as a Docker application. Clone and download a copy for the application

    git clone [https://github.com/ngchianglin/VulnerableMamaShop.git](https://github.com/kabarton62/sqliStore.git)

Change into the directory and build using docker

    cd sqliStore
    docker build -t store .

## Running the Docker Application

To run it detached mode

    docker run -itd --rm -p 8505:80 store

This will make sqliStore available at http://localhost:8505 or http://[ip address]:8505

Do not expose sqliStore to the internet, it is an insecure application and can lead to a system or network compromise. 
Use it in an isolated test lab environment meant for security testing and learning. 
 
Note the mariadb database is restored each time the docker container is started up.     

## Source signature
Gpg Signed commits are used for committing the source files. 

> Look at the repository commits tab for the verified label for each commit, or refer to [https://www.nighthour.sg/git-gpg.html](https://www.nighthour.sg/git-gpg.html) for instructions on verifying the git commit. 
>
> A userful link on how to verify gpg signature is availabe here [https://github.com/blog/2144-gpg-signature-verification](https://github.com/blog/2144-gpg-signature-verification)




