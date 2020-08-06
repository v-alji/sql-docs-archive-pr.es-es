---
title: Tarea de creación de clúster de Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpcreatecltask.f1
- sql11.dts.designer.afpcreatecltask.f1
ms.assetid: a8ec413a-38d3-45df-887e-6f5f4d9f8465
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4029e3a01cbcfe04be5f2879a9b60866bfc867a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744813"
---
# <a name="azure-hdinsight-create-cluster-task"></a><span data-ttu-id="3efba-102">Tarea de creación de clúster de HDInsight de Azure</span><span class="sxs-lookup"><span data-stu-id="3efba-102">Azure HDInsight Create Cluster Task</span></span>
<span data-ttu-id="3efba-103">La **tarea de creación de clúster de Azure HDInsight** permite que un paquete SSIS cree un clúster de Azure HDInsight en la suscripción de Azure y el grupo de recursos especificados.</span><span class="sxs-lookup"><span data-stu-id="3efba-103">The **Azure HDInsight Create Cluster Task** enables an SSIS package to create an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]  
> - <span data-ttu-id="3efba-104">La creación de un nuevo clúster de HDInsight puede tardar entre 10 y 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="3efba-104">Creating a new HDInsight cluster may take 10~20 minutes.</span></span>  
> - <span data-ttu-id="3efba-105">Hay un costo asociado con la creación y ejecución de un clúster de Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3efba-105">There is a cost associated with creating and running an Azure HDInsight cluster.</span></span> <span data-ttu-id="3efba-106">Vea el tema [Precios de HDInsight](https://azure.microsoft.com/pricing/details/hdinsight/) para más información.</span><span class="sxs-lookup"><span data-stu-id="3efba-106">See [HDInsight Pricing](https://azure.microsoft.com/pricing/details/hdinsight/) for details.</span></span>  
  
<span data-ttu-id="3efba-107">Para agregar una **tarea de creación de clúster de HDInsight de Azure**, arrástrela y colóquela en el Diseñador SSIS y haga doble clic (o haga clic con el botón derecho y, después, haga clic en **Editar** ) para ver el siguiente cuadro de diálogo del **Editor de la tarea de creación de clúster de HDInsight de Azure** .</span><span class="sxs-lookup"><span data-stu-id="3efba-107">To add an **Azure HDInsight Create Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Create Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="3efba-108">En la tabla siguiente se proporciona una descripción de los campos de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3efba-108">The following table provides a description of the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3efba-109">**Campo**</span><span class="sxs-lookup"><span data-stu-id="3efba-109">**Field**</span></span>|<span data-ttu-id="3efba-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3efba-110">**Description**</span></span>|  
|<span data-ttu-id="3efba-111">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="3efba-111">AzureResourceManagerConnection</span></span>|<span data-ttu-id="3efba-112">Seleccione un administrador de conexiones de Azure Resource Manager o cree uno nuevo que se usará para crear el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3efba-112">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to create the HDInsight cluster.</span></span>|  
|<span data-ttu-id="3efba-113">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="3efba-113">AzureStorageConnection</span></span>|<span data-ttu-id="3efba-114">Seleccione un administrador de conexiones de almacenamiento de Azure existente o cree uno que haga referencia a una cuenta de almacenamiento de Azure que se asociará con el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3efba-114">Select an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account that will be associated with the HDInsight cluster.</span></span>|
|<span data-ttu-id="3efba-115">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="3efba-115">SubscriptionId</span></span>|<span data-ttu-id="3efba-116">Especifique el identificador de la suscripción en la que se creará el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3efba-116">Specify the ID of the subscription the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="3efba-117">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="3efba-117">ResourceGroup</span></span>|<span data-ttu-id="3efba-118">Especifique el grupo de recursos de Azure en el que se creará el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3efba-118">Specify the Azure resource group the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="3efba-119">Location</span><span class="sxs-lookup"><span data-stu-id="3efba-119">Location</span></span>|<span data-ttu-id="3efba-120">Especifique la ubicación del clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3efba-120">Specify the location of the HDInsight cluster.</span></span> <span data-ttu-id="3efba-121">El clúster debe crearse en la misma ubicación que la cuenta de Azure Storage especificada.</span><span class="sxs-lookup"><span data-stu-id="3efba-121">The cluster must be created in the same location as the Azure Storage Account specified.</span></span>|  
|<span data-ttu-id="3efba-122">ClusterName</span><span class="sxs-lookup"><span data-stu-id="3efba-122">ClusterName</span></span>|<span data-ttu-id="3efba-123">Especifique un nombre para el clúster de HDInsight que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="3efba-123">Specify a name for the HDInsight cluster to be created.</span></span>|  
|<span data-ttu-id="3efba-124">clusterSize</span><span class="sxs-lookup"><span data-stu-id="3efba-124">ClusterSize</span></span>|<span data-ttu-id="3efba-125">Especifique el número de nodos que quiere crear en el clúster.</span><span class="sxs-lookup"><span data-stu-id="3efba-125">Specify the number of nodes to create in the cluster.</span></span>|  
|<span data-ttu-id="3efba-126">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="3efba-126">BlobContainer</span></span>|<span data-ttu-id="3efba-127">Especifique el nombre del contenedor de almacenamiento predeterminado que quiere asociar con el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3efba-127">Specify the name of the default storage container to be associated with the HDInsight cluster.</span></span>|  
|<span data-ttu-id="3efba-128">UserName</span><span class="sxs-lookup"><span data-stu-id="3efba-128">UserName</span></span>|<span data-ttu-id="3efba-129">Especifique el nombre de usuario que se usará para conectarse al clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3efba-129">Specify the user name to be used for connecting to the HDInsight cluster.</span></span>|  
|<span data-ttu-id="3efba-130">Contraseña</span><span class="sxs-lookup"><span data-stu-id="3efba-130">Password</span></span>|<span data-ttu-id="3efba-131">Especifique la contraseña que se usará para conectarse al clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="3efba-131">Specify the password to be used for connecting to the HDInsight cluster.</span></span>|
|<span data-ttu-id="3efba-132">SshUserName</span><span class="sxs-lookup"><span data-stu-id="3efba-132">SshUserName</span></span>|<span data-ttu-id="3efba-133">Especifique el nombre de usuario que se usa para acceder de forma remota al clúster de HDInsight con SSH.</span><span class="sxs-lookup"><span data-stu-id="3efba-133">Specify the user name used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="3efba-134">SshPassword</span><span class="sxs-lookup"><span data-stu-id="3efba-134">SshPassword</span></span>|<span data-ttu-id="3efba-135">Especifique la contraseña usada para acceder de forma remota al clúster de HDInsight con SSH.</span><span class="sxs-lookup"><span data-stu-id="3efba-135">Specify the password used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="3efba-136">FailIfExists</span><span class="sxs-lookup"><span data-stu-id="3efba-136">FailIfExists</span></span>|<span data-ttu-id="3efba-137">Especifique si la tarea debe generar un error si el clúster ya existe.</span><span class="sxs-lookup"><span data-stu-id="3efba-137">Specify whether the task should fail if the cluster already exists.</span></span>|  
  
> [!NOTE]  
> <span data-ttu-id="3efba-138">Las ubicaciones del clúster de HDInsight y de la cuenta de Azure Storage deben ser la misma.</span><span class="sxs-lookup"><span data-stu-id="3efba-138">The locations of the HDInsight cluster and the Azure Storage Account must be the same.</span></span>
