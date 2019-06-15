# Docker image for `pycodestyle`

[![Build Status](https://travis-ci.com/cytopia/docker-pycodestyle.svg?branch=master)](https://travis-ci.com/cytopia/docker-pycodestyle)
[![Tag](https://img.shields.io/github/tag/cytopia/docker-pycodestyle.svg)](https://github.com/cytopia/docker-pycodestyle/releases)
[![](https://images.microbadger.com/badges/version/cytopia/pycodestyle:latest.svg)](https://microbadger.com/images/cytopia/pycodestyle:latest "pycodestyle")
[![](https://images.microbadger.com/badges/image/cytopia/pycodestyle:latest.svg)](https://microbadger.com/images/cytopia/pycodestyle:latest "pycodestyle")
[![](https://img.shields.io/badge/github-cytopia%2Fdocker--pycodestyle-red.svg)](https://github.com/cytopia/docker-pycodestyle "github.com/cytopia/docker-pycodestyle")
[![License](https://img.shields.io/badge/license-MIT-%233DA639.svg)](https://opensource.org/licenses/MIT)

> #### All awesome CI images
>
> [ansible](https://github.com/cytopia/docker-ansible) |
> [ansible-lint](https://github.com/cytopia/docker-pycodestyle-lint) |
> [awesome-ci](https://github.com/cytopia/awesome-ci) |
> [eslint](https://github.com/cytopia/docker-eslint) |
> [jsonlint](https://github.com/cytopia/docker-jsonlint) |
> [pycodestyle](https://github.com/cytopia/docker-pycodestyle) |
> [terraform-docs](https://github.com/cytopia/docker-terraform-docs) |
> [yamllint](https://github.com/cytopia/docker-yamllint)


View **[Dockerfile](https://github.com/cytopia/docker-pycodestyle/blob/master/Dockerfile)** on GitHub.

[![Docker hub](http://dockeri.co/image/cytopia/pycodestyle)](https://hub.docker.com/r/cytopia/pycodestyle)

Tiny Alpine-based multistage-build dockerized version of [pycodestyle](https://github.com/PyCQA/pycodestyle)<sup>[1]</sup>.
The image is built nightly against multiple stable versions and pushed to Dockerhub.

<sup>[1] Official project: https://github.com/PyCQA/pycodestyle</sup>


## Available Docker image versions

| Docker tag | Build from |
|------------|------------|
| `latest`   | Latest stable pycodestyle version |


## Docker mounts

The working directory inside the Docker container is **`/data/`** and should be mounted locally to
the root of your project where your `setup.cfg` or `tox.ini` config file is.


## Usage

```bash
docker run --rm -v $(pwd):/data cytopia/pycodestyle .
```


## License

**[MIT License](LICENSE)**

Copyright (c) 2019 [cytopia](https://github.com/cytopia)
