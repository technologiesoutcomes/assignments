## Kubernetes, Docker, Containerisation and Virtualisation



## Linux administration and shell scripting



## CICD, Git, GitHub, GitHub Action, Infrastructure as as Code (IaC), Terraform, Packer and Ansible
1. You create a repository in GitHub called <b>myfirstrepo</b>. You then clone this repository on your local laptop. On your laptop how would you check its remote address? How would you go about changing the remote address so that it points to repository called <b>mysecondrepo</b>?
2. You have a workflow running on GitHub Action that has the following code;
```
jobs:
  deploy_to_production:
    runs-on: ubuntu-latest
    name: deploy to production with soruce code
    steps:
      - name: Checkout GitHub Action
        uses: actions/checkout@v2

      - name: Login via Azure CLI
        uses: azure/login@v1
        with:
          creds: ${{ secrets.AZURE_CREDENTIALS }}

      - name: deploy to production step with soruce code
        uses: azure/spring-cloud-deploy@v1
        with:
          azure-subscription: ${{ env.AZURE_SUBSCRIPTION }}
          action: deploy
          service-name: <service instance name>
          app-name: <app name>
          use-staging-deployment: false
          package: ${{ env.ASC_PACKAGE_PATH }}
```
Describe what you think this code is doing.



## System Architecture and Application Design, Cloud Computing (AWS)
1. You have worked thus far with systems that you have had to download and install on your local laptop as well as systems hosted remotely on some external cloud. Describe in details the features and capabilities of all the systems (local and remote) that you have worked with thus far on this training. Draw a solution architecture diagram depicting these systems and where they fit in your solution landscape.
2. For all the systems that you have installed locally, write a manual for its installation and configuration.



## Site Reliability Engineering (SRE), Troubleshooting, Observability




## DevOps and Agile Transformation principles and methodology
