# Installing the OpenShift Serverless Operator

This procedure describes how to install and subscribe to the OpenShift Serverless Operator from the OperatorHub using the OpenShift Container Platform web console.

**Procedure**

1. In the OpenShift Container Platform web console, navigate to the **Operators** → **OperatorHub** page.
2. Scroll, or type they keyword **Serverless** into the **Filter by keyword box** to find the OpenShift Serverless Operator. [![OpenShift Serverless Operator in the OpenShift Container Platform web console](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/ce5abba257ad3e4c3778b9c83e9fddb4/serverless-search.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/ce5abba257ad3e4c3778b9c83e9fddb4/serverless-search.png)
3. Review the information about the Operator and click **Install**.[![OpenShift Serverless Operator information](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/ee8cf92b3b3e391bf32df6fcb0e32441/serverless-operator.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/ee8cf92b3b3e391bf32df6fcb0e32441/serverless-operator.png)
4. On the **Create Operator Subscription** page: [![Create Operator Subscription page](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/12640b38901766ba2f8099592cafd83c/serverless-create-sub.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/12640b38901766ba2f8099592cafd83c/serverless-create-sub.png)
   1. The **Installation Mode** is **All namespaces on the cluster \(default\)**. This mode installs the Operator in the default `openshift-operators` namespace to watch and be made available to all namespaces in the cluster.
   2. The **Installed Namespace** will be `openshift-operators`.
   3. Select an **Update Channel**.
      1. The **4.3** channel will enable installation of the latest stable release of the OpenShift Serverless Operator.
      2. The **preview-4.3** channel enables installation of the latest preview version of the OpenShift Serverless Operator, which may contain features that are not yet available from the **4.3** update channel.
   4. Select **Automatic** or **Manual** approval strategy.
5. Click **Subscribe** to make the Operator available to the selected namespaces on this OpenShift Container Platform cluster.
6. From the **Catalog** → **Operator Management** page, you can monitor the OpenShift Serverless Operator subscription’s installation and upgrade progress.
   1. If you selected a **Manual** approval strategy, the subscription’s upgrade status will remain **Upgrading** until you review and approve its install plan. After approving on the **Install Plan** page, the subscription upgrade status moves to **Up to date**.
   2. If you selected an **Automatic** approval strategy, the upgrade status should resolve to **Up to date** without intervention.

**Verification steps**

After the Subscription’s upgrade status is **Up to date**, select **Catalog** → **Installed Operators** to verify that the OpenShift Serverless Operator eventually shows up and its **Status** ultimately resolves to **InstallSucceeded** in the relevant namespace.  
[![Installed Operators page](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/fa19efa9851ddd26fd1604468aaad202/serverless-installed-operator.png)](https://access.redhat.com/webassets/avalon/d/OpenShift_Container_Platform-4.3-Serverless_applications-en-US/images/fa19efa9851ddd26fd1604468aaad202/serverless-installed-operator.png)

If it does not:

1. Switch to the **Catalog** → **Operator Management** page and inspect the **Operator Subscriptions** and **Install Plans** tabs for any failure or errors under **Status**.
2. Check the logs in any pods in the `openshift-operators` project on the **Workloads** → **Pods** page that are reporting issues to troubleshoot further.

