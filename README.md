
# etcd browser
 etcd browser with role based access

## To build/run as a Docker container:

(adjust options as necessary - to run it as a daemon, remove "--rm", "-t", "-i" and add "-D")

    cd <repository>
    sudo docker build -t etcd-browser .
    sudo docker run --rm --name etcd-browser -p 0.0.0.0:8000:8000 --env ETCD_HOST=10.10.0.1 ADMIN_USER=admin --env ADMIN_PASS=test1234 --env VIEW_USER=viewer --env VIEW_PASS=test4321 -t -i etcd-browser

### Configuration
You can configure the builtin server using environment variables:

 * AUTH_USER: Username for http basic auth (skip to disable auth)
 * AUTH_PASS: Password for http basic auth
 * VIEW_USER: Viewer for http basic auth
 * VIEW_PASS: Viewer password
 * ETCD_HOST: IP of the etcd host the internal proxy should use [172.17.42.1]
 * ETCD_PORT: Port of the etcd daemon [4001]
 * SERVER_PORT: Port of builtin server
 
If you use a secured etcd:
 * ETCDCTL_CA_FILE
 * ETCDCTL_KEY_FILE
 * ETCDCTL_CERT_FILE
