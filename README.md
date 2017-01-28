# stack_master-docker
Dockerfile to build container with [stack_master](https://github.com/envato/stack_master) tool. Simplifies it's usage for non Linux/Mac users or for those of you, who don't want to pollute main system or deal with bundler.

#How to use it

## To run it once:

```bash
docker run --rm -v $HOME/.aws:/root/.aws:ro -v $(pwd):/conf zeldigas/stack_master <your stack master command here>
```
This will 
1. mount your .aws directory with credentials
2. mount current directory to container workdir
3. execute stack master with passed arguments

## To run it on daily basis

Create shell function and enable it your rc/profile

```bash
#bash version below
function stack_master(){
 docker run --rm -v $HOME/.aws:/root/.aws:ro -v $(pwd):/conf zeldigas/stack_master "$@"
}
```

Run it as a regular command

```bash
stack_master <your stack master command here>
```
