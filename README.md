# Status: early development phase

# Tech stack:

Content sharing platform (educational resources)

Type of content: articles, documents, presentations, images, url's

User base: Moroccan homeschooling parents

Tools and technologies:
 * [JHipster](https://www.jhipster.tech)
 * [Java 11](https://openjdk.java.net)
 * [Spring Boot 2.1](https://spring.io/projects/spring-boot), [Spring Content](https://paulcwarren.github.io/spring-content)
 * [Angular 8](https://angular.io)
 * [MySQL 8](https://www.mysql.com)
 * [Liquibase](https://www.liquibase.org) (database version control)
 * [HikariCP](https://github.com/brettwooldridge/HikariCP) (connection pooling)
 * [Elasticsearch](https://github.com/elastic/elasticsearch)
 * [Caffeine](https://github.com/ben-manes/caffeine) (in-memory cache)
 * [Jenkins](https://jenkins.io) (automation server)
 * [Protractor](https://www.protractortest.org) (end-to-end testing)
  * [Docker](https://www.docker.com) (test & production)

# Dev env:
 * compte Github Free (répo privé, max. 3 comptes)
 * installation en local (Git, OpenJDK 11, Node.js, Eclipse) https://www.jhipster.tech/installation/
 * communication interne avec RocketChat (hébergé nous-mêmes sur VPS 2GB ram) et sur Github (issues)

# Devops flow:
 * (laptop dev) commit
 * (VPS 2 GB ram) Jenkins build déclenche dans une VM sur laptop testeur (avec SSH tunnel ouvert), à cause de la compilation Angular besoin >4GB ram, c'est lourd
 * envoi statut build vers Github + Dockerhub push (gratuit)
 * (VM sur laptop testeur) Watchtower > update container en cours
 * (optionnel, VM sur laptop testeur) app temporairement public via le VPS (avec SSH tunnel ouvert)
