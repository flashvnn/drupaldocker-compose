# drupaldocker-compose
Drupal docker compose 

## Steps to start drupal docker for local development

- Download this repo to local
- Open console at repo directory and run command: docker-compose up -d
- Open hosts file
    * For Windows: C:\Windows\System32\drivers\etc\hosts
    * For MAC: /etc/hosts
- Add these line at end of file:
    ```bash
      127.0.0.1       domain1.com
      127.0.0.1       domain2.com
    ```
- Open domain1.com and domain2.com you will see content Web 1 amd Web 2
- Location for domain1.com is docroot/web1 and for domain2.com is docroot/web2
- Default database root account has username root and password is root
- To access database host in web1 and web2 you must use "db" as hosting name
- PHPMYADMIN: Open url http://localhost:8001 for managed database

## How to use difference domain for development

- Run command to stop docker compose: docker-compose kill
- Update file ginx/nginx.conf
    * Find and replace domain1.com with your domain name you want, example: drupal8.test
    * Open hosts file and append this line:
    ```bash
      127.0.0.1       drupal8.test
    ```
- Start docker compose again with : docker-compose up -d
- Open url http://drupal8.test and check result