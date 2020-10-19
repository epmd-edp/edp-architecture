# EDP Components List

This page provides the list of EDP source code repositories that are used during the development process, as well as the corresponding descriptions of their purposes. 
For details, inspect the Table 1 below.

_Table 1. EDP Source Code Repositories._

|№| Repository Name  | Description  | 
|---|---|---|
|1|[edp4edp-cicd](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp4edp-cicd) DEPRECATED| It contains all Jenkins pipelines that are used for the EDP development. |
|2| [edp](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp) | It contains EDP installation script, EDP installation OpenShift template, CI/CD tools installation templates, EDP Jenkins pipelines recommended for Business applications. |
|3| [edp-base](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-base) | It contains the Golang code with a base layer of EDP installation (cluster-wide tools like Keycloak, Monitoring tool, Logging tool, etc.). |
|4| [admin-console-operator](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/admin-console-operator) | It deploys the Admin Console component on a cluster by using AdminConsole CR, which contains all necessary data. |
|5| [edp-admin-console](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-admin-console) | It contains the Golang code for the Admin Console application that is used for managing the EDP project. |
|6| [edp-cockpit](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-cockpit) DEPRECATED | A control panel of EDP inside OpenShift that allows an EDP user to do the following: add a project to EDP environment, add an application, check the overall status of EDP health. |
|7| [edp-install-wizard](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-install-wizard) | It contains the install wizard that is used for the EDP installation. | 
|8| [edp-library-pipelines](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-library-pipelines) | A Jenkins shared-library for the reference EDP pipelines. |
|9| [edp-library-stages](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-library-stages) | A Jenkins shared-library for the reference EDP stages. |
|10| [codebase-operator](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/codebase-operator) | It prepares codebase repositories in order to use them in CI/CD process. |
|11| [cd-pipeline-operator](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/cd-pipeline-operator) | It contains a set of controllers that are reconciled into EDP entities (e.g. Gerrit repository, Jenkins pipelines, etc.). |
|12| [reconciler](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/reconciler) | It monitors all events, which happen with all CRs, and saves their representation into DB. |
|13| [gerrit-operator](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/gerrit-operator) | It installs the Gerrit EDP Component in order to use it as GitProvider and store codebases code.|
|14| [jenkins-operator](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/jenkins-operator) |It creates, deploys, and manages the EDP Jenkins instance on Kubernetes and OpenShift. In addition, the Jenkins instance is equipped with the necessary plugins. There is also the ability to customize the Jenkins instance as well as to check the changes during the application creation.|
|15| [keycloak-operator](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/keycloak-operator) | It is responsible for establishing a connection to provided Keycloak Server, reconciling realms, and clients according to the created CRs. |
|16| [nexus-operator](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/nexus-operator) | It installs the Nexus EDP Component on a cluster to store/manage artifacts of codebases. It also exposes configuration that allows Nexus to perform with other EDP components.  |
|17| [sonar-operator](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/sonar-operator) | It installs the Sonar EDP Component on a cluster for continuous inspection of a codebase code quality. |
|18| [custom-pipelines](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/custom-pipelines)| It contains the adapted EDP4EDP pipelines and stages that are used for EDP development. |
|19| [edp-base](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-base) | It is responsible for the installation of the cluster-wide components. | 
|20| [edp-component-operator](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-component-operator) | It contains the API of EDP component that is necessary for the registry of the installed components. The Admin Console UI consists of several single components. | 
|21| [edp-install](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-install) | It contains Ansible Playbook that has the custom resource code and installs the main configuration (e.g. database registration, the creation of a user in a database, etc.), which cannot be subsumed to the corresponding operator or allotted to the repository. |
|22| [edp-jenkins](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-jenkins) | It contains the Dockerfile with a detailed description of how to build Jenkins including additional plugins and components installation. |
|23| [edp-admin-console](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-admin-console)| It contains a backup for EDP Admin Console. |
|24| javascript-npm-react| The application template for the "create" strategy with the JavaScript code language, the React framework, and the NPM build tool. | 


|  | [terraform-core](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/terraform-core) | It is a core repository with Terraform code that is used for deploying infrastructure on OpenShift cluster in AWS. |
|19| [terraform-aws-vpc](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/terraform-aws-vpc) | It contains Terraform code for VPC module as a part of Terraform AWS core that is used for provisioning and configuration VPC on a top of AWS. |
|20| [terraform-aws-openshift](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/terraform-aws-openshift) | It contains Terraform code for OpenShift module as a part of Terraform AWS core that is used for provisioning and configuration EC2 infrastructure on top of AWS. |
|21| [terraform-aws-init](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/terraform-aws-init) | It contains a Terraform code for the Init module as a part of Terraform AWS core that is used for the initialization of the backend for the Terraform state file. |
|22| [terraform-aws-dns](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/terraform-aws-dns) | It contains a Terraform code for the DNS module as a part of Terraform AWS core that is used for provisioning and configuration of the Route53 service in AWS. |
|23| [terraform-aws-bastion](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/terraform-aws-bastion) | It contains a Terraform code for the Bastion module as a part of Terraform AWS core that is used for provisioning Bastion host for external access to infrastructure in AWS. |
|24| [edp-architecture](https://gerrit-edp-cicd-delivery.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-architecture) | It contains the general architecture of EPAM Delivery Platform. |
|25| [edp-autotests](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/edp-autotests)] | It contains all autotests necessary for the EDP verification. |
|26| [All-EDP-Projects](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/All-EDP-Projects), [All-Operators](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/All-Operators), [All-Projects](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/All-Projects), [All-Terraform](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/All-Terraform), [All-Users](https://gerrit-oc-green-edp-cicd.delivery.aws.main.edp.projects.epam.com/#/admin/projects/All-Users)| These are empty repositories without code where RBAC policy is set, i.e. some resources, groups or users have access and all their rights are applied to other child repositories. |
|27|  |  |
|  |  |  |






![postgres](../readme-resource/postgres.png "postgres")

