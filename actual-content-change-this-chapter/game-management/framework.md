# Slim Framework

We use [Slim Framework 3](https://www.slimframework.com/) as a framework for our project,  
Slim is a PHP micro framework that helps you quickly write simple yet powerful web applications and APIs.  
Slim also support extensions, we used the following:

* [slim-controller](https://packagist.org/packages/martynbiz/slim3-controller)
  Provides controller functionality to Slim Framework v3.
* [slim/twig-view](https://packagist.org/packages/slim/twig-view)
  Slim Framework 3 view helper built on top of the Twig 2 templating component
* [monolog](https://packagist.org/packages/monolog/monolog)
  Sends your logs to files, sockets, inboxes, databases and various web services
* [slim-session](https://packagist.org/packages/bryanjhv/slim-session)
  Session middleware and helper for Slim framework 3.
* [mongodb/mongodb](https://packagist.org/packages/mongodb/mongodb)
  MongoDB driver library
* [vlucas/phpdotenv](https://packagist.org/packages/vlucas/phpdotenv)
  Loads environment variables from `.env` to `getenv()`, `$_ENV` and `$_SERVER` automagically.
* [phpmailer/phpmailer](https://packagist.org/packages/phpmailer/phpmailer)
  PHPMailer is a full-featured email creation and transfer class for PHP
* [webmozart/json](https://packagist.org/packages/webmozart/json)
  A robust JSON decoder/encoder with support for schema validation.

We also added a own implementation around the mongodb/mongodb library for a easier to use database access.  
And the slim-session is used in our key class and middleware to automaticly log users in without having to do it in each route.  


