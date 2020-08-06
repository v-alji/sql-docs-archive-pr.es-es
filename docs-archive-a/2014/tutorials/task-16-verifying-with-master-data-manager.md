---
title: 'Tarea 16: comprobación con Master Data Manager | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 57ad9d3e-8f95-4df6-af01-c291ccf49164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d1649582f97e9e08691726745e4ba14b2f8226bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746065"
---
# <a name="task-16-verifying-with-master-data-manager"></a><span data-ttu-id="bb48e-102">Tarea 16: Comprobación con Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="bb48e-102">Task 16: Verifying with Master Data Manager</span></span>
  <span data-ttu-id="bb48e-103">En esta tarea, comprobará el estado del trabajo por lotes enviado por el paquete de SSIS y comprobará que los datos se cargaron en el servidor de MDS con Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="bb48e-103">In this task, you check the status of the batch job submitted by the SSIS package and verify that the data was uploaded to MDS server by using Master Data Manager.</span></span>  
  
1.  <span data-ttu-id="bb48e-104">Inicie **Master Data Manager** ( `http://localhost/MDS` ).</span><span class="sxs-lookup"><span data-stu-id="bb48e-104">Launch **Master Data Manager** (`http://localhost/MDS`).</span></span> <span data-ttu-id="bb48e-105">Si ya está abierto, haga clic en **Microsoft SQL Server Master Data Services** en la parte superior para cambiar a la **Página principal**.</span><span class="sxs-lookup"><span data-stu-id="bb48e-105">If it is already open, click **Microsoft SQL Server Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="bb48e-106">Haga clic en **Administración de integraciones**.</span><span class="sxs-lookup"><span data-stu-id="bb48e-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="bb48e-107">Observe que hay un lote con el nombre **EIMBatch** que envió en la lista.</span><span class="sxs-lookup"><span data-stu-id="bb48e-107">Notice that there is a batch with named **EIMBatch** that you submitted in the list.</span></span> <span data-ttu-id="bb48e-108">Haga clic en **importar datos** en la barra de menús si no ve la pantalla siguiente.</span><span class="sxs-lookup"><span data-stu-id="bb48e-108">Click **Import Data** on the menu bar if you do not see the following screen.</span></span>  
  
     <span data-ttu-id="bb48e-109">![Lote EIM](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "Lote EIM")</span><span class="sxs-lookup"><span data-stu-id="bb48e-109">![EIM Batch](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "EIM Batch")</span></span>  
  
4.  <span data-ttu-id="bb48e-110">Vuelva a la Página principal haciendo clic en **SQL Server 2012 Master Data Services** en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="bb48e-110">Switch back to the home page by click **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
5.  <span data-ttu-id="bb48e-111">Asegúrese de que el modelo **proveedores** está seleccionado para **modelo** y **VERSION_1** está seleccionado para **versión**y haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="bb48e-111">Make sure that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**, and click **Explorer**.</span></span>  
  
6.  <span data-ttu-id="bb48e-112">Puede ver el paquete de datos de SSIS importado en MDS.</span><span class="sxs-lookup"><span data-stu-id="bb48e-112">You can see the data SSIS package imported into MDS.</span></span> <span data-ttu-id="bb48e-113">Los datos deben limpiarse y no tener valores de **código** duplicados (Nota: la columna **IdProveedor** en Excel corresponde al atributo **code** de la entidad proveedor en MDS).</span><span class="sxs-lookup"><span data-stu-id="bb48e-113">The data should be cleansed and have no duplicates **Code** values (Note: **SupplierID** column in Excel corresponds to **Code** attribute of Supplier entity in MDS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="bb48e-114">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="bb48e-114">Next Step</span></span>  
 [<span data-ttu-id="bb48e-115">Tarea 17: Revisión del proyecto de limpieza de DQS creado por el paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="bb48e-115">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>](../../2014/tutorials/task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package.md)  
  
  
