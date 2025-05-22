### Description

Here we containerize PRQL compiler `prqlc`[its original repo  is here](https://github.com/PRQL/prql/tree/main/prqlc/prqlc).
This project is inspired by [prql-query project](https://github.com/PRQL/prql-query)


### How to use it

- build & install 
```bash
    # 1 build prqlc locally
    $./build_locally.sh

    # 2 (optionally) create alias to command invoking prqlc image
    $ alias pq="docker run --rm -it -v $(pwd):/data -e HOME=/tmp -u $(id -u):$(id -g) prqlc"

```    
```bash
    # or pull it from the docker hub
    $ docker pull sajonaro/prqlc-in-container:debian

    # 2 (optionally) create alias to command invoking prqlc image
    $ alias pq="docker run --rm -it -v $(pwd):/data -e HOME=/tmp -u $(id -u):$(id -g) sajonaro/prqlc-in-container:debian"

```    
- example usage:
```bash
    # use directly
    $ pq --help

    # or pipe the transpiled sql into database
    # e.g. select top 5 records from `countries`table
    $ pq "from countries | take 5" | psql postgresql://username:password@host:port/database
```