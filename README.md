# Software Architecture Subject Labs

Labs for the Software Architecture subject at the National University of Colombia.

> The files in this repository where provided by the teacher of the subject.

## Group members

- Sebastian Garnica Quiroz - sgarnicaq@unal.edu.co
- David Esteban Hernandez Gomez - davhernandezgo@unal.edu.co

## Setup and run

### Requirements

- [Docker](https://docs.docker.com/install/) 🐳
- [Docker Compose](https://docs.docker.com/compose/install/) 🐙

### Run

Clone the repository then run the following command

```sh
docker-compose up -d --build
```

> This will build the images and run the containers in the background.

## Container list for each lab

### Lab 1 - Data

| Container name  | Ports     | Technologies                                 |
| --------------- | --------- | -------------------------------------------- |
| swarch2022ii_db | 3306:3306 | [MySQL](https://www.mysql.com/) 🐬           |
| db_client       | 8081:80   | [PHPMyAdmin](https://www.phpmyadmin.net/) 🐘 |

### Lab 2 - Logic, Part 1

| Container name  | Ports     | Technologies                                                                |
| --------------- | --------- | --------------------------------------------------------------------------- |
| swarch2022ii_ms | 4000:4000 | Language: [Python](https://www.python.org/) 🐍                              |
|                 |           | Framework: [Flask](https://flask.palletsprojects.com/en/1.1.x/) 🌶️          |
|                 |           | API Architecture: [REST](https://en.wikipedia.org/wiki/Representational) 🌐 |

### Lab 3 - Logic, Part 2

| Container name  | Ports     | Technologies                                           |
| --------------- | --------- | ------------------------------------------------------ |
| swarch2022ii_ag | 5000:5000 | Language: [JavaScript](https://www.javascript.com/) 📜 |
|                 |           | Framework: [Koa](https://koajs.com/) 🌲                |
|                 |           | API Architecture: [GraphQL](https://graphql.org/) 🌐   |

### Lab 4 - Presentation

---

### Lab 5 - Security

| Container name     | Ports    | Technologies                                     |
| ------------------ | -------- | ------------------------------------------------ |
| swarch2022ii_ldap  | 389:389  | [OpenLDAP](https://www.openldap.org/) 📚         |
| ldap_client        | 6443:443 | [PHPLDAPadmin](https://www.phpldapadmin.org/) 📖 |
| swarch2022ii_proxy | 80:80    | [Nginx](https://www.nginx.com/) 📦               |

### Lab 6 - Interoperability

| Container name | Ports     | Technologies                                    |
| -------------- | --------- | ----------------------------------------------- |
| sa_bank_ss_db  | 3308:3306 | [MySQL](https://www.mysql.com/) 🐬              |
| sa_bank_ss     | 3000:3000 | Language: [Ruby](https://www.ruby-lang.org/) 💎 |
| sa_user_ss_db  | 3310:3306 | [MySQL](https://www.mysql.com/) 🐬              |
| sa_user_ss     | 3010:3000 | Language: [Ruby](https://www.ruby-lang.org/) 💎 |

To populate the databases there is a script in each container folder named
`init.sql` it may be runned however you want.

### Tests

There are some test files to try using the [VSCode REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) extension.

Each folder contains a `requests.http` file with the requests to test the API.

To test the proxy you may use the same file as the API gateway, but you must remove the port from the URL using the @baseUrl variable in the file.
In the response headers you should see the `Server` header with the nginx version which means that the proxy is working
