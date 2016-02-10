## Node web server to help provide meta data for bloginator generated meta data

#### Building the docker image using packer

##### For Mac users add `TMPDIR=~/tmp`

`TMPDIR=~/tmp /usr/local/packer/packer build -var 'source_code_fld=/Users/mario/Documents/hevnly/meta-spa' -var 'tag=<tagName>' -var 'docker_repo_imgName=hevnly/hevnlify' packerImage.json`

##### For linux users remove


Once you have the docker image, either by building it or pulling it from the docker hub, run it by setting the ports:

`docker run -d -p 3000:8080 <imageName>:<tag> http-server --cors -p 8080`

In the browser go to:

`$(docker-machine ip default):3000`

Or if linux user:

`localhost:3000`