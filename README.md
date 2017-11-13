# docker-plumber

example on how to create a rest api with r using [plumber](https://www.rplumber.io) and run it in a box

## build

```bash
# build with url
docker build -t crazycapivara/plumber-datasets \
	github.com/crazycapivara/docker-plumber

# build with path (first pull repository)
docker build -t crazycapivara/plumber-datasets .
```

## run

```bash
docker run -p 8000:8000 -d crazycapivara/plumber-datasets
```

## browse

```bash
# use "jq" for pretty output and filters
$ curl -s localhost:8000/dataset/iris | jq
$ curl -s localhost:8000/dataset/airquality?limit=5 | jq
$ curl -s localhost:8000/dataset/quakes?limit=6 | jq '.[] | select(.mag > 4.2)'

# feel free to query any dataset from the r-base packages ...
```

