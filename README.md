# selinux-docker-sock

## Usage

Make sure you have the prerequisite SELinux utilities:

    yum install selinux-policy-devel

Then as root, just do

    make -f /usr/share/selinux/devel/Makefile dockersock.pp

to install SELinux policy module

    semodule -i dockersock.pp

to reload SELinux policy module
    
    semodule -R

Should you ever wish to remove the module, do

    semodule -r dockersock


## Example

    docker run -d --security-opt label:type:container_sock_t --name centos centos sleep infinity

## License

MIT(https://github.com/stone-payments/selinux-docker-sock/blob/master/LICENSE)
