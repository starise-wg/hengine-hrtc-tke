# srs-tke-template

![](http://ossrs.net/gif/v1/sls.gif?site=github.com&path=/tmpl/k8s/tke/ossrs/srs-tke-template)
[![](https://github.com/ossrs/srs-tke-template/actions/workflows/tencent.yml/badge.svg)](https://github.com/ossrs/srs-tke-template/actions/workflows/tencent.yml)

Template repository for deploying SRS to [TKE(Tencent Kubernetes Engine)](https://cloud.tencent.com/document/product/457/6759).

## Usage

**Step 1:** Create TKE cluster and user:

1. Create a K8s cluster by [TKE](https://console.cloud.tencent.com/tke2/cluster?rid=8), check by command `kubectl get namespace`
1. Create a new [CAM user](https://console.cloud.tencent.com/cam), with access <kbd>AdministratorAccess</kbd>

**Step 2:** Click the <kbd>Use this template</kbd> to create your repository, then set the [secrets](https://github.com/ossrs/srs-tke-template/settings/secrets/actions):

1. `TENCENT_CLOUD_SECRET_ID` is the SecretId of [CAM user](https://console.cloud.tencent.com/cam).
1. `TENCENT_CLOUD_SECRET_KEY` is the SecretKey of [CAM user](https://console.cloud.tencent.com/cam).
1. `TKE_CLUSTER_ID` is the TKE K8s cluster ID at <kbd>TKE</kbd> > <kbd>Basic Information</kbd>.
1. `TKE_REGION` is the region of cluster, for example, `ap-beijing`

**Step 3:** Run <kbd>Actions</kbd> to deploy to your K8s, for example, if your external IP is `49.233.120.79`:

* Website is http://49.233.120.79:8080
* Publish RTMP to rtmp://49.233.120.79/live/livestream
* Play RTMP from rtmp://49.233.120.79/live/livestream
* Play HTTP-FLV from http://49.233.120.79:8080/live/livestream.flv
* Play HLS from http://49.233.120.79:8080/live/livestream.m3u8

Try to motify the [srs.yaml](srs.yaml), then push to your repository, your K8s will be updated automatically.

