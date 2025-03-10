# Introduction

![Version: 3.1.2](https://img.shields.io/badge/Version-3.1.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: auto](https://img.shields.io/badge/AppVersion-auto-informational?style=flat-square)

HandBrake is a tool for converting video from nearly any format to a selection of modern, widely supported codecs.

TrueCharts are designed to be installed as TrueNAS SCALE app only. We can not guarantee this charts works as a stand-alone helm installation.
**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/truecharts/apps/issues/new/choose)**

## Source Code

* <https://github.com/truecharts/apps/tree/master/stable/handbrake>
* <https://github.com/jlesage/docker-handbrake>
* <https://hub.docker.com/r/jlesage/handbrake/>
* <https://handbrake.fr/>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://truecharts.org/ | common | 3.5.2 |

## Installing the Chart

To install the chart with the release name `handbrake`

- Open TrueNAS SCALE
- Go to Apps
- Click "Install" for this specific Apps
- Fill out the configuration form

## Uninstalling the Chart

To uninstall the `handbrake` deployment

- Open TrueNAS SCALE
- Go to Apps
- Go to "Installed Apps"
- Expand the menu in the top-right corner of this App
- Click "Remove" for this specific Apps

The command removes all the Kubernetes components associated with the chart **including storage volumes** _(Except hostPath Storage)_ and deletes the release.

## Support

- See the [Wiki](https://truecharts.org)
- Open a [issue](https://github.com/truecharts/apps/issues/new/choose)
- Ask a [question](https://github.com/truecharts/apps/discussions)

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
All Rights Reserved - The TrueCharts Project
