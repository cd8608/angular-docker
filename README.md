# angular-docker

Play angular just through docker and without installing any angular and node software on your computer

## create angular project

create a new angular project called ``demo`` and located on ``/Users/penxiao/tmp/angular-docker`` through docker volume.

```
$ docker run --rm -it -v /Users/penxiao/tmp/angular-docker:/app xiaopeng163/angular-docker ng new demo
```

## build and serve angular project

for example, our angular project is demo in ``/Users/penxiao/tmp/angular-docker/demo``

```
$ docker run -d --rm --name=angular-demo -it -v /Users/penxiao/tmp/angular-docker/demo:/app -p 4200:4200 xiaopeng163/angular-docker ng serve --host=0.0.0.0
b6c0b0b3a19325f7e42b5c7ec86d6ddef5b1822d70419e0361acf6f2b294c86d
```

check logs

```
$ docker logs angular-demo -f
** Angular Live Development Server is listening on 0.0.0.0:4200, open your browser on http://localhost:4200/ **

Date: 2018-05-21T06:10:59.583Z
Hash: c81cc3c9f7977164505e
Time: 14041ms
chunk {main} main.js, main.js.map (main) 10.6 kB [initial] [rendered]
chunk {polyfills} polyfills.js, polyfills.js.map (polyfills) 227 kB [initial] [rendered]
chunk {runtime} runtime.js, runtime.js.map (runtime) 5.22 kB [entry] [rendered]
chunk {styles} styles.js, styles.js.map (styles) 15.6 kB [initial] [rendered]
chunk {vendor} vendor.js, vendor.js.map (vendor) 3.37 MB [initial] [rendered]
ℹ ｢wdm｣: Compiled successfully.

```

open browser on localhost:   http://127.0.0.1:4200/

![image](demo.png)
