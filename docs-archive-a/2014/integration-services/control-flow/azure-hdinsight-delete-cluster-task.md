---
title: Tarea de eliminación de clúster de Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpdelcltask.f1
- sql11.dts.designer.afpdelcltask.f1
ms.assetid: e298776e-d18a-4393-a8e6-65ee3d555749
author: chugugrace
ms.author: chugu
ms.openlocfilehash: db0a15aaea37c6d18c1d3c2136e0fd0c94eb7506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676128"
---
# <a name="azure-hdinsight-delete-cluster-task"></a><span data-ttu-id="89048-102">Tarea de eliminación de clúster de HDInsight de Azure</span><span class="sxs-lookup"><span data-stu-id="89048-102">Azure HDInsight Delete Cluster Task</span></span>
<span data-ttu-id="89048-103">La **tarea de eliminación de clúster de Azure HDInsight** permite que un paquete SSIS elimine un clúster de Azure HDInsight del grupo de recursos y la suscripción de Azure especificados.</span><span class="sxs-lookup"><span data-stu-id="89048-103">The **Azure HDInsight Delete Cluster Task** enables an SSIS package to delete an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89048-104">La eliminación de un clúster de HDInsight puede tardar entre 10 y 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="89048-104">Deleting an HDInsight cluster may take 10~20 minutes.</span></span>  
  
<span data-ttu-id="89048-105">Para agregar una **tarea de eliminación de clúster de HDInsight de Azure**, arrástrela y suéltela en el Diseñador SSIS y haga doble clic o haga clic con el botón derecho y luego haga clic en **Editar** para ver el siguiente cuadro de diálogo: **Azure HDInsight Delete Cluster Task Editor** (Editor de tareas de eliminación de clúster de HDInsight de Azure).</span><span class="sxs-lookup"><span data-stu-id="89048-105">To add an **Azure HDInsight Delete Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Delete Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="89048-106">En la tabla siguiente se proporciona una descripción de los campos del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="89048-106">The following table provides a description for the fields in the dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="89048-107">**Campo**</span><span class="sxs-lookup"><span data-stu-id="89048-107">**Field**</span></span>|<span data-ttu-id="89048-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="89048-108">**Description**</span></span>|  
|<span data-ttu-id="89048-109">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="89048-109">AzureResourceManagerConnection</span></span>|<span data-ttu-id="89048-110">Seleccione un administrador de conexiones de Azure Resource Manager existente o cree uno nuevo que se usará para eliminar el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="89048-110">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to delete the HDInsight cluster.</span></span>|
|<span data-ttu-id="89048-111">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="89048-111">SubscriptionId</span></span>|<span data-ttu-id="89048-112">Especifique el identificador de la suscripción en la que se encuentra el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="89048-112">Specify the ID of the subscription the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="89048-113">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="89048-113">ResourceGroup</span></span>|<span data-ttu-id="89048-114">Especifique el grupo de recursos de Azure en el que se encuentra el clúster de HDInsight.</span><span class="sxs-lookup"><span data-stu-id="89048-114">Specify the Azure resource group the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="89048-115">ClusterName</span><span class="sxs-lookup"><span data-stu-id="89048-115">ClusterName</span></span>|<span data-ttu-id="89048-116">Especifique el nombre del clúster que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="89048-116">Specify the name of the cluster to be deleted.</span></span>|  
|<span data-ttu-id="89048-117">FailIfNotExists</span><span class="sxs-lookup"><span data-stu-id="89048-117">FailIfNotExists</span></span>|<span data-ttu-id="89048-118">Especifique si la tarea debe generar un error si no existe el clúster.</span><span class="sxs-lookup"><span data-stu-id="89048-118">Specify whether the task should fail if the cluster does not exist.</span></span>|
