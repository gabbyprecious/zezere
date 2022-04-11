# Zezere

[Zezere](https://en.wikipedia.org/wiki/Z%C3%AAzere_River) is a provisioning server for Fedora IoT.
It can be used for deploying Fedora IoT to devices without needing a physical console.

## Getting Started

### Running with Docker


### Running with Python

If you're using any Python virtual environment you might want to setup that
first. Using venv:

```
$ venv zezere-venv
```
$ source zezere-venv/bin/activate
```
Before you can install the python requirements you need to have Apache httpd
installed. Please follow instructions from
[mod-wsgi-httpd project documentation](https://pypi.org/project/mod-wsgi-httpd/)

After the prequisites have been met we can install required packages:

```
$ pip install -r requirements.txt
```

Before using the `zezere-manage` tool, database and models needs to be migrated
and a configuration needs to be created.

Synchronize the database state with the current set of models and migrations:

```
$ python manage.py migrate
```

Default configuration can be used as a base:

```
$ cp zezere/default.conf ./zezere.conf
```

Authentication method and secret key needs to be set in order to satisfy the
tool. Also, make sure that the allowed_hosts is what you want.

```
allowed_hosts = localhost
secret_key = very-secret
auth_method = local
```

Now we can create a superuser:

```
$ python-manage.py createsuperuser
```

After a password has been set, we are ready to run Zezere:

```
./app.sh
```

Use the admin credentials we created to login to localhost:8080

### Running Tests

## Testing Local Setup


## Contributing
