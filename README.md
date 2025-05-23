### Description

Here we containerize PRQL compiler `prqlc`[its original repo  is here](https://github.com/PRQL/prql/tree/main/prqlc/prqlc).


### How to use it

- build & install 
```bash
    # 1 build prqlc locally
    $./build_locally.sh

    # 2 (optionally) create alias to command invoking prqlc image
    $ alias prqlc="docker run -i --rm prqlc"


    # alternatively, pull it from the docker hub
    $ docker pull sajonaro/prqlc-in-container:debian
    $ alias prqlc="docker run --rm -i sajonaro/prqlc-in-container:debian"

```    
- usage example
```bash
    # use directly
    $ prqlc --help

    # or pipe the prsql query into it
    $ echo 'from employees | filter has_dog | select salary' | prqlc compile
```

