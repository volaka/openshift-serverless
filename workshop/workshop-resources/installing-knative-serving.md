# Installing Knative Serving

After you install the OpenShift Serverless Operator, you can install Knative Serving by following the procedures described in this guide.

This guide provides information about installing Knative Serving using the default settings. However, you can configure more advanced settings in the KnativeServing custom resource definition.

For more information about configuration options for the KnativeServing custom resource definition, see [Advanced installation configuration options](https://access.redhat.com/documentation/en-us/openshift_container_platform/4.3/html-single/installing_serverless/#serverless-install-config-options).

## Creating the `knative-serving` namespace

When you create the `knative-serving` namespace, a `knative-serving` project will also be created.

{% hint style="warning" %}
**IMPORTANT**

You must complete this procedure before installing Knative Serving
{% endhint %}

If the `KnativeServing` object created during Knative Serving’s installation is not created in the `knative-serving` namespace, it will be ignored.

### **Prerequisites**

* An OpenShift Container Platform account with cluster administrator access
* Installed OpenShift Serverless Operator

## **Creating the knative-serving namespace using the web console**

### **Procedure**

1. In the OpenShift Container Platform web console, navigate to **Administration** → **Namespaces**.[![Namespaces page](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/1aeaa8015ccbbf3acdbdbc8cf89e27cd/serverless-create-namespaces.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/1aeaa8015ccbbf3acdbdbc8cf89e27cd/serverless-create-namespaces.png)
2. Enter `knative-serving` as the **Name** for the project. The other fields are optional.[![Creating the \`knative-eventing\` namespace](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/ddcf320ac617fa4660516363166023f8/create-serving-namespace.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/ddcf320ac617fa4660516363166023f8/create-serving-namespace.png)
3. Click **Create**.

## Installing Knative Serving using the web console

### **Procedure**

1. In the **Administrator** perspective of the OpenShift Container Platform web console, navigate to **Operators** → **Installed Operators**.
2. Check that the **Project** dropdown at the top of the page is set to **Project: knative-serving**.
3. Click **Knative Serving** in the list of **Provided APIs** for the OpenShift Serverless Operator to go to the **Knative Serving** tab. [![Installed Operators page](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/8df8058ab00b71f4dc5d4f4442624b0a/serving-installed-operator.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/8df8058ab00b71f4dc5d4f4442624b0a/serving-installed-operator.png)
4. Click the **Create Knative Serving** button. [![Knative Serving tab](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/6038bddad81f68eb84cdfdbf0b366af4/serverless-create-serving.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/6038bddad81f68eb84cdfdbf0b366af4/serverless-create-serving.png)
5. In the **Create Knative Serving** page, you can install Knative Serving using the default settings by clicking **Create**.

   You can also modify settings for the Knative Serving installation by editing the `KnativeServing` object using either the form provided, or by editing the YAML.

   * Using the form is recommended for simpler configurations that do not require full control of `KnativeServing` object creation.
   * Editing the YAML is recommended for more complex configurations that require full control of `KnativeServing` object creation. You can access the YAML by clicking the **edit YAML** link in the top right of the **Create Knative Serving** page.

     After you complete the form, or have finished modifying the YAML, click **Create**.NOTE

     For more information about configuration options for the KnativeServing custom resource definition, see the documentation on _Advanced installation configuration options_.[![Create Knative Serving in Form View](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/9c21f24ecf6eace56ea2bb3020cbef39/serving-form-view.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/9c21f24ecf6eace56ea2bb3020cbef39/serving-form-view.png)[![Create Knative Serving in YAML view](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/a8a4119d1a43f11973ff5ac17fa77258/serverless-create-serving-yaml.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/a8a4119d1a43f11973ff5ac17fa77258/serverless-create-serving-yaml.png)

6. After you have installed Knative Serving, the `KnativeServing` object is created, and you will be automically directed to the **Knative Serving** tab.  
   [![Installed Operators page](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/bdcc9f62ad23a7402fce1704405ae26b/serving-tab-created.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/bdcc9f62ad23a7402fce1704405ae26b/serving-tab-created.png)

   You will see `knative-serving` in the list of resources.

### **Verification steps**

1. Click on `knative-serving` in the **Knative Serving** tab.
2. You will be automatically directed to the **Knative Serving Overview** page.[![Installed Operators page](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/3ed1652f80a56fe6c9182082483ad9b1/serving-overview.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/3ed1652f80a56fe6c9182082483ad9b1/serving-overview.png)
3. Scroll down to look at the list of **Conditions**.
4. You should see a list of conditions with a status of **True**, as shown in the example image.[![Conditions](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/e5be0610a44bce96d329b9917a29eeeb/serving-conditions-true.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/e5be0610a44bce96d329b9917a29eeeb/serving-conditions-true.png)

   It may take a few seconds for the Knative Serving resources to be created. You can check their status in the **Resources** tab.

5. If the conditions have a status of **Unknown** or **False**, wait a few moments and then check again after you have confirmed that the resources have been created.

