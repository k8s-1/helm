# helm
* quick guide to understanding helm
* chart structure

.
├── mychart
│   ├── charts
│   ├── Chart.yaml
│   ├── templates
│   └── values.yaml
└── README.md

* charts/ can contain other charts a.k.a. "subcharts"
* Chart.yaml contains the chart description
* templates/ is rendered by templating engine into k8s manifests
* values.yaml contains default values for a chart (can be overridden during helm install)

## create new chart
```sh
helm create mychart
```
