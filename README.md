# minishift

## Setting Up the hyperkit Driver on MacOS  

To install the hyperkit driver, you need to download and install the docker-machine-driver-hyperkit binary and place  
it in a directory which is on your PATH environment variable. The directory /usr/local/bin is a good choice, since  
it is the default installation directory for Docker Machine binaries.  

The following steps explain the installation of the docker-machine-driver-hyperkit binary to the  
/usr/local/bin/ directory:  


Download the docker-machine-driver-hyperkit binary using:  

`$ sudo curl -L  https://github.com/machine-drivers/docker-machine-driver-hyperkit/releases/download/v1.0.0/docker-machine-driver-hyperkit -o /usr/local/bin/docker-machine-driver-hyperkit`  

Enable root access for the docker-machine-driver-hyperkit binary and add it to the default wheel group:

`$ sudo chown root:wheel /usr/local/bin/docker-machine-driver-hyperkit`  

Set owner User ID (SUID) for the binary as follows:

`$ sudo chmod u+s,+x /usr/local/bin/docker-machine-driver-hyperkit`  

The prereqs.sh can help with the above.  

## Installing minishift

1. Download the archive for your operating system from the Minishift Releases page and extract its contents.  
1. Copy the contents of the directory to your preferred location.  
1. Add the minishift binary to your PATH environment variable.  


## Starting MiniShift

`$ minishift start --vm-driver hyperkit`  

After several minutes it will output to the console something like:

The server is accessible via web console at:  
    https://192.168.64.2:8443  

You are logged in as:  
    User:     developer  
    Password: <any value>  
  
To login as administrator:  
    oc login -u system:admin  


`$ minishift stop`  

`$ minishift delete`  