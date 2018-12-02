# Build a Simple REST API in PHP

This example shows how to build a simple REST API in core PHP and secure it with Okta using OAuth 2.0 Client Credentials Flow.

Please read <article placeholder> to see how this application was built.

**Prerequisites:** PHP, Composer, MySQL, [Okta developer account](https://developer.okta.com/)

> [Okta](https://developer.okta.com) has Authentication and User Management APIs that reduce development time with instant-on, scalable user infrastructure. Okta's intuitive API and expert support make it easy for developers to authenticate, manage, and secure users and roles in any application.

## Getting Started

Sign up for an [Okta developer account](https://developer.okta.com) and create a new application. Make note of the Client ID and Issuer values for your application.

Clone this project using the following commands:

```
git@github.com:oktadeveloper/okta-php-core-rest-api-example.git
cd okta-php-core-rest-api-example
```

### Configure the application

Create the database and user for the project:

```
mysql -uroot -p
CREATE DATABASE api_example CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'api_user'@'localhost' identified by 'api_password';
GRANT ALL on api_example.* to 'api_user'@'localhost';
quit
```

Copy and edit the `.env` file and enter your database details and Okta details there:

```
cp .env.example .env
```

Install the project dependencies and start the PHP server:

```
composer install
cd public
php -S 127.0.0.1:8000
```

Loading [127.0.0.1:8000/person](127.0.0.1:8000/person) should return a 401 Unauthorized response now.

NOTE: if using a virtual machine and NAT, you might need to run the server as `php -S 0.0.0.0:8000 -t public` instead.

### Run the client application

In the public directory, simply run:

```
php client.php
```

If you see 'Obtaining token...success!' on the first line then Okta authentication is working correctly. After that, you should see the client app execute some API requests and dump the output.

## Help

Please post any questions as comments on the <article link>, or visit our [Okta Developer Forums](https://devforum.okta.com/). You can also email developers@okta.com if would like to create a support ticket.

## License

Apache 2.0, see [LICENSE](LICENSE).