---
title: Feature Pack de Azure | Microsoft Docs
ms.custom: ''
ms.date: 08/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL11.SSIS.AZURE.F1
- SQL12.SSIS.AZURE.F1
ms.assetid: 31de555f-ae62-4f2f-a6a6-77fea1fa8189
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8bca2b4d3ce91f6010fbe01da836efd8a67ca6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744285"
---
# <a name="azure-feature-pack"></a><span data-ttu-id="29735-102">Feature Pack de Azure</span><span class="sxs-lookup"><span data-stu-id="29735-102">Azure Feature Pack</span></span>
<span data-ttu-id="29735-103">Feature Pack de SQL Server Integration Services (SSIS) para Azure es una extensión que proporciona los componentes que se muestran en esta página para que SSIS se conecte a los servicios de Azure, para transferir datos entre Azure y orígenes de datos locales, y para procesar los datos almacenados en Azure.</span><span class="sxs-lookup"><span data-stu-id="29735-103">SQL Server Integration Services (SSIS) Feature Pack for Azure is an extension that provides the components listed on this page for SSIS to connect to Azure services, transfer data between Azure and on-premises data sources, and process data stored in Azure.</span></span>

## <a name="components-in-the-feature-pack"></a><span data-ttu-id="29735-104">Componentes de Feature Pack</span><span class="sxs-lookup"><span data-stu-id="29735-104">Components in the Feature Pack</span></span>
  
-   <span data-ttu-id="29735-105">Administradores de conexión</span><span class="sxs-lookup"><span data-stu-id="29735-105">Connection Managers</span></span>  
  
    -   [<span data-ttu-id="29735-106">Administrador de conexiones de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="29735-106">Azure Storage Connection Manager</span></span>](connection-manager/azure-storage-connection-manager.md)  
  
    -   [<span data-ttu-id="29735-107">Administrador de conexiones de suscripción de Azure</span><span class="sxs-lookup"><span data-stu-id="29735-107">Azure Subscription Connection Manager</span></span>](connection-manager/azure-subscription-connection-manager.md)  
    
    -   [<span data-ttu-id="29735-108">Administrador de conexiones de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="29735-108">Azure Data Lake Store Connection Manager</span></span>](../../2014/integration-services/azure-data-lake-store-connection-manager.md)
    
    -   [<span data-ttu-id="29735-109">Administrador de conexiones de Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="29735-109">Azure Resource Manager Connection Manager</span></span>](../../2014/integration-services/azure-resource-manager-connection-manager.md)
    
    -   [<span data-ttu-id="29735-110">Administrador de conexiones de Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="29735-110">Azure HDInsight Connection Manager</span></span>](../../2014/integration-services/azure-hdinsight-connection-manager.md)
  
-   <span data-ttu-id="29735-111">Tareas</span><span class="sxs-lookup"><span data-stu-id="29735-111">Tasks</span></span>  
  
    -   [<span data-ttu-id="29735-112">Tarea de carga de blobs de Azure</span><span class="sxs-lookup"><span data-stu-id="29735-112">Azure Blob Upload Task</span></span>](control-flow/azure-blob-upload-task.md)  
  
    -   [<span data-ttu-id="29735-113">Tarea de descarga de blobs de Azure</span><span class="sxs-lookup"><span data-stu-id="29735-113">Azure Blob Download Task</span></span>](control-flow/azure-blob-download-task.md)  
  
    -   [<span data-ttu-id="29735-114">Tarea de Hive de Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="29735-114">Azure HDInsight Hive Task</span></span>](control-flow/azure-hdinsight-hive-task.md)  
  
    -   <span data-ttu-id="29735-115">[Tarea de Pig de Azure HDInsight](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="29735-115">[Azure HDInsight Pig Task](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span></span>
  
    -   [<span data-ttu-id="29735-116">Tarea de creación de clúster de HDInsight de Azure</span><span class="sxs-lookup"><span data-stu-id="29735-116">Azure HDInsight Create Cluster Task</span></span>](control-flow/azure-hdinsight-create-cluster-task.md)  
  
    -   [<span data-ttu-id="29735-117">Tarea de eliminación de clúster de HDInsight de Azure</span><span class="sxs-lookup"><span data-stu-id="29735-117">Azure HDInsight Delete Cluster Task</span></span>](control-flow/azure-hdinsight-delete-cluster-task.md)
    
    -   [<span data-ttu-id="29735-118">Tarea de carga de Azure SQL DW</span><span class="sxs-lookup"><span data-stu-id="29735-118">Azure SQL DW Upload Task</span></span>](../../2014/integration-services/azure-sql-dw-upload-task.md)    
    
    -   [<span data-ttu-id="29735-119">Tarea Sistema de archivos de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="29735-119">Azure Data Lake Store File System Task</span></span>](control-flow/file-system-task.md)    
  
-   <span data-ttu-id="29735-120">Componentes de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="29735-120">Data Flow Components</span></span>  
  
    -   <span data-ttu-id="29735-121">[Origen de blobs de Azure](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="29735-121">[Azure Blob Source](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span></span>  
  
    -   [<span data-ttu-id="29735-122">Destino de blobs de Azure</span><span class="sxs-lookup"><span data-stu-id="29735-122">Azure Blob Destination</span></span>](data-flow/azure-blob-destination.md)  
    
    -   [<span data-ttu-id="29735-123">Origen de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="29735-123">Azure Data Lake Store Source</span></span>](../../2014/integration-services/azure-data-lake-store-source.md)
    
    -   [<span data-ttu-id="29735-124">Destino de Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="29735-124">Azure Data Lake Store Destination</span></span>](../../2014/integration-services/azure-data-lake-store-destination.md)
  
-   <span data-ttu-id="29735-125">Enumerador de blobs de Azure & enumerador de archivos ADLS.</span><span class="sxs-lookup"><span data-stu-id="29735-125">Azure Blob Enumerator & ADLS File Enumerator.</span></span> <span data-ttu-id="29735-126">Vea [contenedor de bucles foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="29735-126">See [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 
## <a name="download-the-feature-pack"></a><span data-ttu-id="29735-127">Descarga del Feature Pack</span><span class="sxs-lookup"><span data-stu-id="29735-127">Download the Feature Pack</span></span>  
<span data-ttu-id="29735-128">Descargue Feature Pack de SQL Server Integration Services (SSIS) para Azure.</span><span class="sxs-lookup"><span data-stu-id="29735-128">Download the SQL Server Integration Services (SSIS) Feature Pack for Azure.</span></span>  
  
-   [<span data-ttu-id="29735-129">Feature Pack de Microsoft SQL Server 2014 Integration Services para Azure</span><span class="sxs-lookup"><span data-stu-id="29735-129">Microsoft SQL Server 2014 Integration Services Feature Pack for Azure</span></span>](https://www.microsoft.com/download/details.aspx?id=47366)  

## <a name="prerequisites"></a><span data-ttu-id="29735-130">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="29735-130">Prerequisites</span></span>  
<span data-ttu-id="29735-131">Necesita instalar los siguientes requisitos previos antes de instalar este Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="29735-131">You must install the following prerequisites before installing this feature pack.</span></span>  
  
-   <span data-ttu-id="29735-132">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="29735-132">SQL Server Integration Services</span></span>  
-   <span data-ttu-id="29735-133">.Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="29735-133">.Net Framework 4.5</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="29735-134">Escenarios</span><span class="sxs-lookup"><span data-stu-id="29735-134">Scenarios</span></span>  
  
### <a name="big-data-processing"></a><span data-ttu-id="29735-135">Procesamiento de macrodatos</span><span class="sxs-lookup"><span data-stu-id="29735-135">Big Data Processing</span></span>  
 <span data-ttu-id="29735-136">Use el Conector Azure para completar el trabajo de procesamiento de macrodatos siguiente:</span><span class="sxs-lookup"><span data-stu-id="29735-136">Use Azure Connector to complete following big data processing work:</span></span>  
  
1.  <span data-ttu-id="29735-137">Utilice la tarea de carga de blobs de Azure para cargar datos de entrada en el almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="29735-137">Use the Azure Blob Upload Task to upload input data to Azure Blob Storage.</span></span>  
  
2.  <span data-ttu-id="29735-138">Utilice la tarea de creación de clúster de HDInsight de Azure para crear un clúster de HDInsight de Azure.</span><span class="sxs-lookup"><span data-stu-id="29735-138">Use the Azure HDInsight Create Cluster Task to create an Azure HDInsight cluster.</span></span> <span data-ttu-id="29735-139">Este paso es opcional si quiere utilizar su propio clúster.</span><span class="sxs-lookup"><span data-stu-id="29735-139">This step is optional if you want to use your own cluster.</span></span>  
  
3.  <span data-ttu-id="29735-140">Utilice la tarea de Hive de HDInsight de Azure o la tarea de Pig de HDInsight de Azure para invocar un trabajo de Pig o Hive en el clúster de HDInsight de Azure.</span><span class="sxs-lookup"><span data-stu-id="29735-140">Use the Azure HDInsight Hive Task or Azure HDInsight Pig Task to invoke a Pig or Hive job on the Azure HDInsight cluster.</span></span>  
  
4.  <span data-ttu-id="29735-141">Utilice la tarea de eliminación de clúster de HDInsight de Azure para eliminar el clúster de HDInsight tras su uso si creó un clúster de HDInsight a petición en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="29735-141">Use the Azure HDInsight Delete Cluster Task to delete the HDInsight Cluster after use if you have created an on-demand HDInsight cluster in step #2.</span></span>  
  
5.  <span data-ttu-id="29735-142">Utilice la tarea de descarga de blobs de HDInsight de Azure para descargar los datos de salida de Pig o Hive del almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="29735-142">Use the Azure HDInsight Blob Download Task to download the Pig/Hive output data from the Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="29735-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span><span class="sxs-lookup"><span data-stu-id="29735-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span></span>  
  
### <a name="cloud-data-archiving"></a><span data-ttu-id="29735-144">Archivado de datos en la nube</span><span class="sxs-lookup"><span data-stu-id="29735-144">Cloud Data Archiving</span></span>  
 <span data-ttu-id="29735-145">Use el destino de blobs de Azure en un paquete de SSIS para escribir los datos de salida en un almacenamiento de blobs de Azure o para utilizar el origen de blobs de Azure para leer datos desde un almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="29735-145">Use the Azure Blob Destination in an SSIS package to write output data to an Azure Blob Storage, or use the Azure Blob Source to read data from an Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="29735-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span><span class="sxs-lookup"><span data-stu-id="29735-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span></span>  
  
 <span data-ttu-id="29735-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span><span class="sxs-lookup"><span data-stu-id="29735-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span></span>  
  
 <span data-ttu-id="29735-148">Y utilice el contenedor de bucles Foreach con el enumerador de blobs de Azure para procesar los datos de varios archivos de blob.</span><span class="sxs-lookup"><span data-stu-id="29735-148">And use the Foreach Loop Container with Azure Blob Enumerator to process data in multiple bob files.</span></span>  
  
 <span data-ttu-id="29735-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span><span class="sxs-lookup"><span data-stu-id="29735-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span></span>  
  
  
