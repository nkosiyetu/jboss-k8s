# Trying to make this happen

This file will be deleted, but this is how we are currently running it:

1. Clone the repo 
1. download jboss-eap-6.4.zip
1. Add your configuration files 'jboss-eap-6.4/standalone/configurations'
1. Add the modules. In this case: 'jboss-eap-6.4/modules/system/layers/base/com'
1. Zip jboss-eap-6.4 folder
1. Put your Docker hub account:

    ```
    export DOCKERHUB_ACCOUNT=brusmx
    ```

1. Build the image

    ```
    docker build -t $DOCKERHUB_ACCOUNT/jboss-myapp .
    ```

1. Now lets run it:

    ```
    sudo docker run -p 8080:8080 -p 9990:9990 -p 9999:9999 -it $DOCKERHUB_ACCOUNT/jboss-myapp
    ```

1. You can now go to `http://0.0.0.0:8080/jboss-as-helloworld/HelloWorld`and confirm it works.
