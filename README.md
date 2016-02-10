## Node web server to help provide meta data for bloginator generated meta data

This web server uses npm module [http-server](https://www.npmjs.com/package/http-server) as its base.

The main objective of this repo is to create a docker image using the _http server_ from the above mentioned npm module that can be used with other repo's.

#### Building the [docker](https://www.docker.com/) image using [packer](https://www.packer.io/).

##### For Mac users add `TMPDIR=~/tmp`

`TMPDIR=~/tmp /usr/local/packer/packer build -var 'source_code_fld=/Users/mario/Documents/hevnly/meta-spa' -var 'tag=<tagName>' -var 'docker_repo_imgName=hevnly/hevnlify' packerImage.json`

##### For linux users remove `TMPDIR=~/tmp`

Once you have the docker image, either by building it or pulling it from the docker hub, run it by setting the ports:

`docker run -d -p 3000:8080 <imageName>:<tag> http-server --cors -p 8080`

If using Mac, in the browser go to:

`$(docker-machine ip default):3000`

Or if linux user:

`localhost:3000`