# WPScan meets Docker

This is a simple Docker container for [WPScan](http://wpscan.org/).  
It runs on Debian Sid because latest WPScan version requires `ruby > 2.1.9` and Debian Jessie has `2.1.5`. Also the installation installs (`redundancy check: ✓`) a couple of packages missing in their docs.

## How to ...?

If you prefer to build the container yourself

```bash
$ git clone https://github.com/lvm/docker-wpscan
$ cd docker-wpscan
$ docker build -t wpscan .
```

If you *trust me* and prefer to download it directly from Docker Hub

```bash
$ docker pull lvm23/docker-wpscan
```

either way, then you can run it by executing

```bash
$ docker run -it wpscan --url http://my.wp.blog
```

Notes:  

1/ `wpscan` is the name of given to the image. YMMV
2/ This will run `ruby wpscan.rb` within the container as if it were installed on your system (thanks to the magic of `ENTRYPOINT ...` in the [Dockerfile](Dockerfile))

## LICENSE

See [LICENSE](LICENSE).
