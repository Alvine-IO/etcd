# Etcd client library for PHP

etcd is a distributed configuration system, part of the coreos project.

This repository provides a client library for etcd for PHP applications.

## Installing and running etcd

```bash
wget http://download.alvine.io/alvine.infrastructure.coreos-<version>.phar
wget http://download.alvine.io/alvine.infrastructure.coreos-<version>.phar.pubkey
````

## Usage

### The client

```php
    $uri = new \Alvine\Net\Resource\URI('http://localhost:4001/');
    $client = new \Alvine\Infrastructure\CoreOS\Etcd\Client($uri);
    
    // Optional: Verbindung über über Proxy
    // $client->setProxy('localhost', 8888);

    $client->setValue('/foo', 'bar');
    // with ttl
    $client->setValue('/foo', 'bar', 10)
    // get value
    echo $client->getValue('/foo');
    
    // Delete value
    $client->deleteValue('/foo);
    
```
