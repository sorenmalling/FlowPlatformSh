# Platform.sh for Flow Framework made easy

Flow framework utility package to parse Platform.sh variables

## How to use ?

Create a file ```.platform.env``` in your distribution directory:

    DATABASE_HOST = database.0.host
    DATABASE_PORT = database.0.port
    DATABASE_NAME = database.0.path
    DATABASE_USER = database.0.username
    DATABASE_PASSWORD = database.0.password
    
    REDIS_HOST = redis.0.host
    REDIS_PORT = redis.0.port

    REDIS_ALTERNATIVE_HOST = redis.1.host
    REDIS_ALTERNATIVE_PORT = redis.1.port
    
    ELASTICSEARCH_HOST = elasticsearch.0.host
    ELASTICSEARCH_PORT = elasticsearch.0.port
    
Based on this configuration, this package will create env variables from ```PLATFORM_RELATIONSHIPS```. 

Then you can edit your ```Settings.yaml``` to use the new env variables:

    Neos:
      Flow:
        persistence:
          backendOptions:
            driver: pdo_pgsql
            dbname: '%env:DATABASE_NAME%'
            port: '%env:DATABASE_PORT%'
            user: '%env:DATABASE_USER%'
            password: '%env:DATABASE_PASSWORD%'
            host: '%env:DATABASE_HOST%'
            
## Acknowledgments

Development sponsored by [ttree ltd - neos solution provider](http://ttree.ch).

We try our best to craft this package with a lots of love, we are open to sponsoring, support request, ... just contact us.

## License

The MIT License (MIT). Please see [LICENSE](LICENSE) for more information.