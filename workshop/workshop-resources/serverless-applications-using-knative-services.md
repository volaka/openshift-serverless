# Serverless applications using Knative services

To deploy a serverless application using OpenShift Serverless, you must create a _Knative service_. Knative services are Kubernetes services, defined by a route and a configuration, and contained in a YAML file.

**Example Knative service YAML**

```text
apiVersion: serving.knative.dev/v1
kind: Service
metadata:
  name: hello
  namespace: default
spec:
  template:
    spec:
      containers:
        - image: docker.io/openshift/hello-openshift
          env:
            - name: RESPONSE
              value: "Hello Serverless!"
```

1. The name of the application.
2. The namespace the application will use.
3. The image of the application.
4. The environment variable printed out by the sample application.

You can create a serverless application by using one of the following methods:

* Create a Knative service from the OpenShift Container Platform web console.
* Create a Knative service using the `kn` CLI.
* Create and apply a YAML file.

## Creating serverless applications using the OpenShift Container Platform web console

You can create a serverless application using either the **Developer** or **Administrator** perspective in the OpenShift Container Platform web console.

### Creating serverless applications using the Administrator perspective

#### **Prerequisites**

To create serverless applications using the **Administrator** perspective, ensure that you have completed the following steps.

* The OpenShift Serverless Operator and Knative Serving are installed.
* You have logged in to the web console and are in the **Administrator** perspective.

#### **Procedure**

1. Navigate to the **Serverless** → **Services** page. ![Services page](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/d0f57e5a7201b4eec376cec363ba6281/serverless-create-service-admin.png)
2. Click **Create Service**.
3. Manually enter YAML or JSON definitions, or by dragging and dropping a file into the editor.![Text editor](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/c84f8f0767b88f2888bb65bc1760cd83/service-yaml-admin.png)
4. Click **Create**.

## Verifying your serverless application deployment

To verify that your serverless application has been deployed successfully, you must get the application URL created by Knative, and then send a request to that URL and observe the output.

{% hint style="info" %}
**NOTE**

OpenShift Serverless supports the use of both HTTP and HTTPS URLs, however the output from `oc get ksvc <SERVICE-NAME>` will always print URLs using the `http://` format.
{% endhint %}

### **Procedure**

1. Find the application URL by entering:

   ```text
   $ oc get ksvc hello
   ```

   **Example output**

   ```text
   NAME            URL                                        LATESTCREATED         LATESTREADY           READY   REASON
   hello   http://hello-default.example.com   hello-4wsd2   hello-4wsd2   True
   ```

2. Make a request to your cluster and observe the output.

   **Example HTTP request**

   ```text
   $ curl http://hello-default.example.com
   Hello Serverless!
   ```

   **Example HTTPS request**

   ```text
   $ curl https://hello-default.example.com
   Hello Serverless!
   ```

3. Optional. If you receive an error relating to a self-signed certificate in the certificate chain, you can add the `--insecure` flag to the curl command to ignore the error.IMPORTANT

   Self-signed certificates must not be used in a production deployment. This method is only for testing purposes.

   **Example**

   ```text
   $ curl https://hello-default.example.com --insecure
   Hello Serverless!
   ```

4. Optional. If your OpenShift Container Platform cluster is configured with a certificate that is signed by a certificate authority \(CA\) but not yet globally configured for your system, you can specify this with the curl command. The path to the certificate can be passed to the curl command by using the `--cacert` flag.

   **Example**

   ```text
   $ curl https://hello-default.example.com --cacert <file>
   Hello Serverless!
   ```

