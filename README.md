# OpenShift Pipelines-as-Code example

This example will show how to use OpenShift Pipelines-as-Code (PAC) to create a continuous integration process. This will require the use of the tkn-pac command line utility which can be downloaded from [here] (https://github.com/openshift-pipelines/pipelines-as-code/blob/main/docs/content/docs/guide/cli.md#install).

If this application is used on demolab there may be an issue regarding the pulling of container images from remote sources. When using demolab it is best to create the container images in local image streams within the namespace and then have tasks reference images from the namespace. This demonstration is configured to work with the celeron cluster on demolab.

To cache the images use the commands :

oc import-image node-js --from=registry.redhat.io/rhel9/nodejs-18:latest --confirm
oc import-image origin-cli --from=quay.io/openshift/origin-cli:latest --confirm
oc import-image buildah --from=registry.redhat.io/rhel8/buildah:latest --confirm
