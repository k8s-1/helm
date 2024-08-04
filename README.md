# helm
* quick guide to understanding helm
* basic chart structure

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

## advanced structure
```
.
├── mychart
│   ├── charts
│   ├── Chart.yaml
│   ├── templates
│   │   ├── deployment.yaml
│   │   ├── _helpers.tpl
│   │   ├── hpa.yaml
│   │   ├── ingress.yaml
│   │   ├── NOTES.txt
│   │   ├── serviceaccount.yaml
│   │   ├── service.yaml
│   │   └── tests
│   │       └── test-connection.yaml
│   └── values.yaml
└── README.md

5 directories, 11 files
```
## mychart/templates
* NOTES.txt: The "help text" for your chart. This will be displayed to your users when they run helm install.
* deployment.yaml: A basic manifest for creating a Kubernetes deployment
* service.yaml: A basic manifest for creating a service endpoint for your deployment
* _helpers.tpl: A place to put template helpers that you can re-use throughout the chart

# installation
helm install <chart-name> <chart-path>
helm install mychart ./mychart
