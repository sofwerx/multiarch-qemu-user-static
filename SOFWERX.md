# qemu-user-static

This is a SOFWERX fork of qemu-user-static to allow running our own multiarch style docker images on a ppc64le host.

The manual steps used here:

1. Build and run the `sofwerx/qemu-user-static:ppc64le-register` docker image:

    docker-compose up qemu-user-static-register

2. Use docker container to publish the qemu static tarballs under a github release:

    export GITHUB_TOKEN={github personal token with repo publish permission}
    docker-compose up qemu-user-static-publish

3. Build the `sofwerx/qemu-user-static:ppc64le-{arch}` docker images:

    ./update.sh

The `.travis.yml` build and push should work as well.

Now things are ready for the distribution specific multiarch repos (ubuntu, debian, centos, etc).

