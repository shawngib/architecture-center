---
title: "Adopting Azure: Foundational" 
description: Describes the basic level of knowledge that an enterprise requires to adopt Azure
author: petertay
---

# Adopting Microsoft Azure: Foundational

For an organization that is new to cloud technologies, it can be difficult to decide on the right place to begin their adoption journey. The goal of the foundational adoption stage is to provide a starting point. Once individuals within the organization have worked through this stage they will have all the knowledge and skills necessary to deploy the compute resources for a simple workload to Azure. 

> [!NOTE]
> This guide does not cover application development. For more information about developing applications on Azure, see the [Azure Application Architecture Guide](/azure/architecture/guide/).

The audience for this stage of the guide is the following personas within your organization:

- *Finance:* owner of the financial commitment to Azure, responsible for developing policies and procedures for tracking resource consumption costs including billing and chargeback.
- *Central IT:* responsible for governing your organization's cloud resources including resource management and access, and workload health and monitoring.
- *Workload owners:* all development roles that are involved in deploying workloads to Azure, including developers, testers, and build engineers.

## Step 1: Understand Azure internals

This introductory step is intended for the *finance* and *central IT* personas. The focus of this section is acquiring a basic understanding of how Azure works in preparation for learning about the concept of cloud governance. It may also be useful for the *workload owners* in your organization to review this content to help them understand how resource access is managed.

- [How does Azure work?](./azure-explainer.md)
- [What is cloud resource governance?](./governance-explainer.md)

## Step 2: Understand Azure resource access governance

After you understand how Azure works and the basics of cloud goverance, your first step in adopting Azure is learning about resource access management in Azure. This article describes the Azure services for making resource access requests and the controls used to validate those requests.

The next step is learning how to design a governance model for a single team. This article describes how to configure the resource access management services and controls you learned about earlier.

- [Understanding resource access management in Azure](./azure-resource-access.md)
- [Azure governance design guide](./governance-how-to.md)

## Step 3: Deploy a basic workload architecture to Azure

The audience for this section is the *workload owner* persona. *Workload owners* define the compute and networking requirements for their workloads, select the correct resources to meet those requirements, and deploy them to Azure. 

For the foundational adoption stage, the workload owner can select either a basic web application or a virtual network (VNet) and virtual machine (VM). For more information about these different types of compute options in Azure, review the [overview of Azure compute options](/azure/architecture/guide/technology-choices/compute-overview?toc=/azure/architecture/cloud-adoption-guide/toc.json).

Regardless of which compute option is selected, each of these deployments requires a **resource group**. Your **workload owner** must [create the resource group](/azure/azure-resource-manager/vs-azure-tools-resource-groups-deployment-projects-create-deploy). As part of the deployment, the **workload owner** specifies a name for the resource group. This name will be used in the following sections.

### Basic web application (PaaS)

For a basic web application, select one of the 5-minute quickstarts from the [web apps documentation](/azure/app-service?toc=/azure/architecture/cloud-adoption-guide/toc.json) and follow the steps. 

> [!NOTE]
> Some of the quickstarts will deploy a resource group by default. In this case, the **workload owner** does not need to create a resource group explicitly. Otherwise, deploy the web application to the resource group created above.

Once your simple workload has been deployed, you can learn more about the proven practices for deploying a [basic web application](/azure/architecture/reference-architectures/app-service-web-app/basic-web-app?toc=/azure/architecture/cloud-adoption-guide/toc.json) to Azure.

### Single Windows or Linux VM (IaaS)

For a simple workload that runs on a virtual machine, the first step is to deploy a virtual network. All IaaS resources in Azure such as virtual machines, load balancers, and gateways require a virtual network. Learn about [Azure virtual networks](/azure/virtual-network/virtual-networks-overview?toc=/azure/architecture/cloud-adoption-guide/toc.json), and then follow the steps to [deploy a Virtual Network to Azure using the portal](/azure/virtual-network/quick-create-portal?toc=/azure/architecture/cloud-adoption-guide/toc.json). When you specify the settings for the virtual network in the Azure portal, specify the name of the resource group created above.

The next step is to decide whether to deploy a single Windows or Linux VM. For a Windows VM, follow the steps to [deploy a Windows VM to Azure with the portal](/azure/virtual-machines/windows/quick-create-portal?toc=/azure/architecture/cloud-adoption-guide/toc.json). Again, when you specify the settings for the virtual machine in the Azure portal, specify the name of the resource group created above.

Once you've followed the steps and deployed the VM, you can learn about [proven practices for running a Windows VM on Azure](/azure/architecture/reference-architectures/virtual-machines-windows/single-vm?toc=/azure/architecture/cloud-adoption-guide/toc.json). For a Linux VM, follow the steps to [deploy a Linux VM to Azure with the portal](/azure/virtual-machines/linux/quick-create-portal?toc=/azure/architecture/cloud-adoption-guide/toc.json). You can also learn more about [proven practices for running a Linux VM on Azure](/azure/architecture/reference-architectures/virtual-machines-linux/single-vm?toc=/azure/architecture/cloud-adoption-guide/toc.json).

## Next steps

The next stage in cloud readiness is the [**intermediate stage**](../intermediate-stage/overview.md). In the intermediate stage, you will learn about extending your on-premises network running multiple workloads and governance models for multiple teams.