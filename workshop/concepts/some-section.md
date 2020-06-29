# Getting Started with OpenShift Serverless

OpenShift Serverless simplifies the process of delivering code from development into production by reducing the need for infrastructure set up or back-end development by developers.

## How OpenShift Serverless works

Developers on OpenShift Serverless can use the provided Kubernetes native APIs, as well as familiar languages and frameworks, to deploy applications and container workloads.

OpenShift Serverless on OpenShift Container Platform enables stateless serverless workloads to all run on a single multi-cloud container platform with automated operations. Developers can use a single platform for hosting their microservices, legacy, and serverless applications.

OpenShift Serverless is based on the open source Knative project, which provides portability and consistency across hybrid and multi-cloud environments by enabling an enterprise-grade serverless platform.

## Supported Configurations

The set of supported features, configurations, and integrations for OpenShift Serverless \(current and past versions\) are available at the [Supported Configurations page](https://access.redhat.com/articles/4912821).

## OpenShift Serverless components

This section describes the components of OpenShift Serverless.

### Knative Serving

Knative Serving on OpenShift Container Platform builds on Kubernetes and Kourier to support deploying and managing serverless applications.

It creates a set of Kubernetes custom resource definitions \(CRDs\) that are used to define and control the behavior of serverless workloads on an OpenShift Container Platform cluster.

These CRDs are building blocks to address complex use cases, for example:

* Rapidly deploying serverless containers.
* Automatically scaling pods.
* Viewing point-in-time snapshots of deployed code and configurations.

### Knative Eventing

Knative Eventing on OpenShift Container Platform enables developers to more easily declare how components of their system communicate, using an event-driven architecture for serverless applications. Event-driven architecture is based on the concept of decoupled relationships between event producers and event consumers.

For more information about event-driven architecture, see [What is event-driven architecture?](https://www.redhat.com/en/topics/integration/what-is-event-driven-architecture)

{% hint style="warning" %}
**IMPORTANT**

Knative Eventing is a Technology Preview feature only. Technology Preview features are not supported with Red Hat production service level agreements \(SLAs\) and might not be functionally complete. Red Hat does not recommend using them in production. These features provide early access to upcoming product features, enabling customers to test functionality and provide feedback during the development process.
{% endhint %}

For more information about the support scope of Red Hat Technology Preview features, see [https://access.redhat.com/support/offerings/techpreview/](https://access.redhat.com/support/offerings/techpreview/)  


