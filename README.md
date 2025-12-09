# community-cloud-storage-ui

This is a user interface for [community-cloud-storage]. It is a static web page that is
served up by nginx and, which talks to a running IPFS Cluster and IPFS APIs.
The interface allows you to upload, list and view files that have been added to
the cluster. It is designed to run within the privacy of the cluster's
Tailscale virtual private mesh network.

![shiftedstorage-ui screenshot](https://github.com/historypin/community-cloud-storage-ui/blob/main/screenshot.png?raw=true)

Instead of using this Docker image directly you will likely want to be using
the docker compose configuration that shiftedstorage creates for you. 
Typically you would need to ensure that the `CLUSTER_REST_URL` and
`IPFS_REST_URL` environment variables are set. However this is something that
shiftedstorage will do for you when starting up services.

## Publish

To publish the Docker image you will need to:

```bash
docker build --platform linux/amd64 --tag edsu/community-cloud-ui .
docker push edsu/community-cloud-storage-ui
```

[community-cloud-storage]: https://github.com/historypin/community-cloud-storage
