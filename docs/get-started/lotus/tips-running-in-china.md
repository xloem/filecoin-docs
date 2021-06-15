---
title: 'Lotus: tips when running in China'
description: 'This guide provides a few tips for users in China to get around some of the bandwidth issues or slowness they can suffer when building and running Lotus.'
breadcrumb: 'Tips when running in China'
---

# {{ $frontmatter.title }}

{{ $frontmatter.description }}

## Issues with the Great Firewall

The government of China uses a combination of legislative actions and technologies enforced by the People's Republic of China to regulate the Internet within it's borders. This is known as _The Great Firewall_ (GFW). The GFW makes sustained data streaming into and out of China incredibly difficult. 

Limited connections into and out of China is not a Filecoin specific issue. You can find out more about the [GFW on Wikipedia](https://en.wikipedia.org/wiki/Great_Firewall).

## Tips

Here are a few tips for users in China to get around some of the bandwidth issues or slowness they can suffer when building and running Lotus.

### Speed up proof parameter download for first boot

Running Lotus requires the download of chain's _proof parameters_ which are large files which by default are hosted outside of China and very slow to download there. To get around that, users should set the following environment variable when running either of `lotus`, `lotus-miner` and `lotus-worker`:

```shell
export IPFS_GATEWAY=https://proof-parameters.s3.cn-south-1.jdcloud-oss.com/ipfs/
```

### Speed up Go module download during builds

Building Lotus requires downloading a few Go modules. These are usually hosted on Github, which has very low bandwidth from China. To fix this use a local proxy by setting the following variable **before** running Lotus:

```shell
export GOPROXY=https://goproxy.cn
```
