# Chart.yaml layout

At TrueCharts we try to keep some files standardised, this enables us to make changes to these charts in bulk with less risk of mistakes. Chart.yaml is one of these files.
In this documentation we will explain the standardised layout options. For an example layout, please see our standard Chart.yaml [template](https://github.com/truecharts/apps/tree/master/.tools/templates/chart/Chart.yaml)


### Layout Explained

```
apiVersion: The chart API version (required)
kubeVersion: A SemVer range of compatible Kubernetes versions (optional)
name: The name of the chart (required)
version: A SemVer 2 version (required)
upstream_version: A SemVer 2 version, as used by an upstream Helm Chart source (optional)
appVersion: The version of the app that this contains (optional). Needn't be SemVer. Quotes recommended.
description: A single-sentence description of this project (optional)
type: The type of the chart (optional)
deprecated: Whether this chart is deprecated (optional, boolean)
home: The URL of this projects home page (optional)
icon: A URL to an SVG or PNG image to be used as an icon (optional).
keywords:
  - A list of keywords about this project (optional)
sources:
  - A list of URLs to source code for this project (optional)
dependencies:
  - name: The name of the chart (nginx)
    repository: The repository URL ("https://example.com/charts") or alias ("@repo-name")
    version: The version of the chart ("1.2.3")
    condition: (optional) A yaml path that resolves to a boolean, used for enabling/disabling charts (e.g. subchart1.enabled )
    tags: # (optional)
      - Tags can be used to group charts for enabling/disabling together
    import-values: # (optional)
      - ImportValues holds the mapping of source values to parent key to be imported. Each item can be a string or pair of child/parent sublist items.
    alias: (optional) Alias to be used for the chart. Useful when you have to add the same chart multiple times
maintainers: # (optional)
  - name: The maintainers name (required for each maintainer)
    email: The maintainers email (optional for each maintainer)
    url: A URL for the maintainer (optional for each maintainer)
annotations:
  example: A list of annotations keyed by name (optional).
```

##### Commenting

In the above description there are a lot of values that are not actually used. Some of those, like `deprecated`, we just set to false. While others, like `annotations` get commented out.

Please refer to our standard Chart.yaml [template](https://github.com/truecharts/apps/tree/master/.tools/templates/chart/Chart.yaml) to see which unused values needs which treatment.

##### Dependencies

We expect each chart to use our Common-Chart in some capacity, inless it's absolutely impossible to do so. This also means we expect the Common-Chart to always be the first dependency in the list. This enables us to easily update all common-chart references in bulk.

All other dependencies are expected to be listed in alphabetical order.

##### Maintainers

The first maintainer should always be TrueCharts, as the TrueCharts core team is expected to step in if the other maintainers fail to maintain their work.
An example of how to list TrueCharts as a maintainer is available in our standard Chart.yaml [template](https://github.com/truecharts/apps/tree/master/.tools/templates/chart/Chart.yaml).

While currently we primarily use the CODEOWNERS file to define maintainers. We might in the future either automate keeping track of maintainers, completely rely on the maintainers or do both. For this reason it's important to add yourself as a maintainer if you expect to maintain your work.
All other maintainers are, ofcoarse, expected to be entered in importance. With the primary maintainer under "truecharts" and secondary maintainers thereunder.
