---
title: Tarea de Hive de Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afphivetask.f1
- sql11.dts.designer.afphivetask.f1
ms.assetid: e1896c73-128a-4128-9814-3e01f7dfe19b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5905dee4a7a195a16d217b28b59cc10bb74dd9a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676126"
---
# <a name="azure-hdinsight-hive-task"></a><span data-ttu-id="b8a89-102">Tarea de Hive de HDInsight de Azure</span><span class="sxs-lookup"><span data-stu-id="b8a89-102">Azure HDInsight Hive Task</span></span>
<span data-ttu-id="b8a89-103">Utilice la **tarea de Hive de HDInsight** para ejecutar el script de Hive en un clúster de HDInsight de Azure.</span><span class="sxs-lookup"><span data-stu-id="b8a89-103">Use the **Azure HDInsight Hive Task** to run Hive script on an Azure HDInsight cluster.</span></span>
     
<span data-ttu-id="b8a89-104">Para agregar una **tarea de Hive de HDInsight de Azure**, arrástrela al Diseñador de SSIS y haga doble clic o haga clic con el botón derecho y haga clic en **Editar** para ver el siguiente cuadro de diálogo: **Azure HDInsight Hive Task Editor** (Editor de tareas de Hive de HDInsight de Azure).</span><span class="sxs-lookup"><span data-stu-id="b8a89-104">To add an **Azure HDInsight Hive Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Hive Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="b8a89-105">La lista siguiente describe los campos de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b8a89-105">The following list describes fields in this dialog box.</span></span>  
  
1.  <span data-ttu-id="b8a89-106">Para el campo **HDInsightConnection**, seleccione un Administrador de conexiones de Azure HDInsight existente o cree uno nuevo que haga referencia al clúster de Azure que se usó para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="b8a89-106">For the **HDInsightConnection** field, select an existing Azure HDInsight Connection Manager or create a new one that refers to the Azure HDInsight cluster used to execute the script.</span></span>
  
2.  <span data-ttu-id="b8a89-107">Para el campo **AzureStorageConnection**, seleccione un Administrador de conexiones de Azure Storage existente o cree uno nuevo que haga referencia a una cuenta de Azure Storage asociada con el clúster.</span><span class="sxs-lookup"><span data-stu-id="b8a89-107">For the **AzureStorageConnection** field, select an existing Azure Storage Connection Manager or create a new one that refers to the Azure Storage Account associated with the cluster.</span></span> <span data-ttu-id="b8a89-108">Esto solo es necesario si quiere descargar los registros de error y la salida de ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="b8a89-108">This is only necessary if you want to download the script execution output and error logs.</span></span>
 
3.  <span data-ttu-id="b8a89-109">Para el campo **BlobContainer**, especifique el nombre del contenedor de almacenamiento asociado con el clúster.</span><span class="sxs-lookup"><span data-stu-id="b8a89-109">For the **BlobContainer** field, specify the storage container name associated with the cluster.</span></span> <span data-ttu-id="b8a89-110">Esto solo es necesario si quiere descargar los registros de error y la salida de ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="b8a89-110">This is only necessary if you want to download the script execution output and error logs.</span></span>
  
4.  <span data-ttu-id="b8a89-111">Para el campo **LocalLogFolder**, especifique la carpeta en la que se descargarán los registros de error y la salida de ejecución de script.</span><span class="sxs-lookup"><span data-stu-id="b8a89-111">For the **LocalLogFolder** field, specify the folder to which the script execution output and error logs will be downloaded to.</span></span> <span data-ttu-id="b8a89-112">Esto solo es necesario si quiere descargar los registros de error y la salida de ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="b8a89-112">This is only necessary if you want to download the script execution output and error logs.</span></span>   
  
5.  <span data-ttu-id="b8a89-113">Hay dos maneras de especificar el script de Hive que se va a ejecutar:</span><span class="sxs-lookup"><span data-stu-id="b8a89-113">There are two ways to specify the Hive script to execute:</span></span>
  
    1.  <span data-ttu-id="b8a89-114">**Script en línea**: especifique el campo **Script** escribiendo en línea el script que quiere ejecutar en el cuadro de diálogo **Escriba el script**.</span><span class="sxs-lookup"><span data-stu-id="b8a89-114">**In-line script**: Specify the **Script** field by typing in-line the script to execute in the **Enter Script** dialog box.</span></span>
  
    2.  <span data-ttu-id="b8a89-115">**Archivo de script**: cargue el archivo de script en Azure Blob Storage y especifique el campo **BlobName**.</span><span class="sxs-lookup"><span data-stu-id="b8a89-115">**Script file**: Upload the script file to Azure Blob Storage and specify the **BlobName** field.</span></span> <span data-ttu-id="b8a89-116">Si el blob no está en el contenedor ni en la cuenta de almacenamiento predeterminados asociados con el clúster de HDInsight, deben especificarse los campos **ExternalStorageAccountName** y **ExternalBlobContainer**.</span><span class="sxs-lookup"><span data-stu-id="b8a89-116">If the blob is not in the default storage account or container associated with the HDInsight cluster, the **ExternalStorageAccountName** and **ExternalBlobContainer** fields must be specified.</span></span> <span data-ttu-id="b8a89-117">Para un blob externo, asegúrese de que está configurado como accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="b8a89-117">For an external blob, make sure that it is configured as publicly accessible.</span></span>  
  
     <span data-ttu-id="b8a89-118">Si se especifican ambos, se usará el archivo de script y se omitirá el script en línea.</span><span class="sxs-lookup"><span data-stu-id="b8a89-118">If both are specified, script file will be used and the in-line script will be ignored.</span></span>
