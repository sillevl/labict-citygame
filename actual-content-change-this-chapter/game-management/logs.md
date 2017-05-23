# logs
monolog will log each request to a page \(not a file\) in the `logs/app.log` file with:

* method
* schema
* host
* port
* path
* key
* keytype

example:

```
[2017-05-17 12:05:45] slim-app.INFO: GET=>http://localhost:8080/controlpanel with key: lpVw.8eEID (master) [] {"uid":"949184e"}
```

explenation:

```
[DATE TIME] slim-app.INFO: METHOD=>SCHEME://HOST:PORT/PATH with key: KEY (KEYTYPE) [] {"uid":"PHP\_REQUEST\_ID"}
```

or this one from a api post from the game creators:  
\(this one shows the purpuse of the HOST in the log, as the same server can be accessed from multiple diffrent hosts\)

```
[2017-05-17 11:49:57] slim-app.INFO: POST=>http://330c3ac6.ngrok.io:8080/secret/creators with key:  (logout) [] {"uid":"a280451"}
```

the code responsible for this logging:

```php
/* log asked route and method //*/
$uri=$request->getUri();
$page=$uri->getScheme()."://".$uri->getHost().":".$uri->getPort().
       $uri->getPath()." with key: ".$this->key->getkey().
       " (".$this->key->getType().")";
$logger->info($request->getMethod()."=>".$page);
```

