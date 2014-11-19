gantree-docker
==============

Docker environment for Gantree deploys. The container is preloaded with Gantree and all tools needed for deployment.

Your repo should be mounted as a volume named `/deploy` on the container.
This allows the container to be used to deploy any repo.
However, Gantree currently emits a warning if the name of the working directory doesn't match the repo name;
it is ok to ignore this.

Example usage:

```
docker run --rm -t -i --name gantree -v ~/src/pistyll:/deploy -e AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY sillypog/gantree gantree deploy stag-pistyll-app-s1
```
