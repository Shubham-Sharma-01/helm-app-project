# helm-app-project
this is for the project - manage deployments using helm
This project has a helm chart, a helm file and two environments dev and stage as follows : 

Project structure:
.
├── README.md
├── helm-app
│   ├── Chart.yaml
│   ├── charts
│   ├── environments
│   │   ├── values-dev.yaml
│   │   └── values-stage.yaml
│   └── templates
│       ├── _helpers.tpl
│       ├── deployment.yaml
│       ├── service.yaml
│       ├── serviceaccount.yaml
│       └── tests
└── helmfile.yaml


To manage the release using helmfile use the following commands : 

# To Push
**For development environment**
helmfile -e dev sync

**For staging environment**
helmfile -e stage sync

# To Manage

**To see what changes will be made**
helmfile -e dev diff

**To see the status of your releases**
helmfile -e dev status

**To delete a release**
helmfile -e dev delete

**To check the releasee created** 
helm list --all-namespaces

**To check what all resources are created using that particular release use the following command:**
helm get manifest <releaese_name> | kubectl get -f -

