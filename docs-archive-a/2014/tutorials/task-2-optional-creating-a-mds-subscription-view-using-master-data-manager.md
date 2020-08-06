---
title: 'Tarea 2 (opcional): creación de una vista de suscripciones de MDS con Master Data Manager | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3da8219-e0cb-4848-95ca-285a76ec1ba9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 998436734ba5c3cf09cfe88f266a0908c0550abc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747757"
---
# <a name="task-2-optional-creating-a-mds-subscription-view-using-master-data-manager"></a><span data-ttu-id="8d4aa-102">Tarea 2 (opcional): Creación de una vista de suscripciones de MDS con Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="8d4aa-102">Task 2 (Optional): Creating a MDS Subscription View using Master Data Manager</span></span>
  <span data-ttu-id="8d4aa-103">En esta tarea, creará una vista de suscripciones para exponer la entidad **proveedor** del modelo **proveedores** a otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-103">In this task, you create a subscription view to expose the **Supplier** entity in the **Suppliers** model to other applications.</span></span> <span data-ttu-id="8d4aa-104">No use esta vista en la versión actual del tutorial.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-104">You do not consume this view in the current version of the tutorial.</span></span>  
  
1.  <span data-ttu-id="8d4aa-105">Cambie a la Página principal de **Master Data Manager** ( `http://localhost/MDS` ) haciendo clic en **SQL Server 2012 Master Data Services** en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-105">Switch to the main page of **Master Data Manager** (`http://localhost/MDS`) by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
2.  <span data-ttu-id="8d4aa-106">Haga clic en **Administración de integraciones**.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="8d4aa-107">Haga clic en **crear vistas** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-107">Click **Create Views** on the menu bar.</span></span>  
  
     <span data-ttu-id="8d4aa-108">![Botón Agregar una nueva vista de suscripción](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Botón Agregar una nueva vista de suscripción")</span><span class="sxs-lookup"><span data-stu-id="8d4aa-108">![Add a New Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Add a New Subscription View Button")</span></span>  
  
4.  <span data-ttu-id="8d4aa-109">Haga clic en el icono **+ (más)** de la barra de herramientas para crear una vista de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-109">Click **+ (Plus)** icon on the toolbar to create a subscription view.</span></span>  
  
5.  <span data-ttu-id="8d4aa-110">En el panel **crear vista de suscripciones** , escriba **proveedores** de **nombre de vista de suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-110">In the **Create Subscription View** pane, type **Suppliers** for **Subscription view name**.</span></span>  
  
6.  <span data-ttu-id="8d4aa-111">Seleccione **Proveedores** en **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-111">Select **Suppliers** for **Model**.</span></span>  
  
7.  <span data-ttu-id="8d4aa-112">Seleccione **VERSION_1** en **Versión**.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-112">Select **VERSION_1** for **Version**.</span></span>  
  
8.  <span data-ttu-id="8d4aa-113">Seleccione **proveedor** para **entidad**.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-113">Select **Supplier** for **Entity**.</span></span>  
  
9. <span data-ttu-id="8d4aa-114">Seleccione **los miembros hoja** para el **formato**.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-114">Select **Leaf members** for **Format**.</span></span>  
  
     <span data-ttu-id="8d4aa-115">![Botón Guardar vista de suscripción](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Botón Guardar vista de suscripción")</span><span class="sxs-lookup"><span data-stu-id="8d4aa-115">![Save Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Save Subscription View Button")</span></span>  
  
10. <span data-ttu-id="8d4aa-116">Haga clic en **Guardar** en la barra de herramientas para guardar la vista de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-116">Click **Save** on the toolbar to save the subscription view.</span></span> <span data-ttu-id="8d4aa-117">Esta acción crea una vista en SQL Server **proveedores**con nombre.</span><span class="sxs-lookup"><span data-stu-id="8d4aa-117">This action creates a view in SQL Server named **Suppliers**.</span></span> <span data-ttu-id="8d4aa-118">Puede comprobarlo con SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="8d4aa-118">You can verify this using SQL Server Management Studio (SSMS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8d4aa-119">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="8d4aa-119">Next Step</span></span>  
 [<span data-ttu-id="8d4aa-120">Tarea 3 &#40;&#41; opcional: revisar las vistas de suscripciones</span><span class="sxs-lookup"><span data-stu-id="8d4aa-120">Task 3 &#40;Optional&#41;: Reviewing the Subscription Views</span></span>](task-3-optional-reviewing-the-subscription-views.md)  
  
  
