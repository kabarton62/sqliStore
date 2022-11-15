# Online Convenience Store
Docker in a SQLi Box

## Introduction

A simple docker application using Ubuntu 16.04 xenial, apache2 httpd (2.4), php (7.0) and mariadb (10). The only problem is it has a problem. Time to practice some SQL injection. 

## Installation

The application is packaged as a Docker application. Clone and download a copy for the application

    git clone https://github.com/ngchianglin/VulnerableMamaShop.git

Change into the directory and build using docker

    cd VulnerableMamaShop
    docker build -t mamashop .

## Running the Docker Application

To run it interactively

    docker run -it --rm -p 8000:80 mamashop

This will make Mamashop available at http://localhost:8000 or http://[ip address]:8000

Do not expose Vulnerable Mama Shop to the internet, it is an insecure application and can lead to a system or network compromise. 
Use it in an isolated test lab environment meant for security testing and learning. 
 
To run Vulnerable Mama Shop in detached mode

    docker run -d --rm -p 8000:80 mamashop
    
Note the mariadb database is restored each time the docker container is started up.     

## Finding the SQL Injection Flaw

A intercepting proxy like OWASP ZAP or Blurpsuite can be used to inspect and alter the traffic between the browser and Mama Shop. 
Mama Shop is deliberately kept simple, it should be relatively easy to find the SQL injection flaw. 

See if you can dump out the list of customers in Mama Shop. To gain the most understanding, it is advised that the user 
do this systematically, step by step. Find out where the SQL vulnerability is and proceed to gather information on the database. 
and finally dump out the customer list. 

For a more detailed walkthrough, refer to the article [https://www.nighthour.sg/articles/2018/learning-sql-injection-using-vulnerable-mama-shop.html](https://www.nighthour.sg/articles/2018/learning-sql-injection-using-vulnerable-mama-shop.html)



## Source signature
Gpg Signed commits are used for committing the source files. 

> Look at the repository commits tab for the verified label for each commit, or refer to [https://www.nighthour.sg/git-gpg.html](https://www.nighthour.sg/git-gpg.html) for instructions on verifying the git commit. 
>
> A userful link on how to verify gpg signature is availabe here [https://github.com/blog/2144-gpg-signature-verification](https://github.com/blog/2144-gpg-signature-verification)




