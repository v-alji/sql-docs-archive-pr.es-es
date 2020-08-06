---
title: 'Tarea 17: revisar el proyecto de limpieza de DQS creado por el paquete SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fc6cc258-72f5-4593-8edb-9f5bc66de9db
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0876a0b727e810f8834fcf5445958bf9884a87f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743702"
---
# <a name="task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package"></a><span data-ttu-id="b3b6c-102">Tarea 17: Revisión del proyecto de limpieza de DQS creado por el paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="b3b6c-102">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>
  <span data-ttu-id="b3b6c-103">En esta tarea, abrirá el proyecto de DQS creado por el paquete SSIS en el Cliente DQS, revisará los resultados del proceso de limpieza y, opcionalmente, realizará una limpieza interactiva y exportará los resultados.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-103">In this task, you open the DQS project created by the SSIS package in DQS Client, review the results from the cleansing process, and optionally perform interactive cleansing and export the results.</span></span>  
  
1.  <span data-ttu-id="b3b6c-104">Inicie **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-104">Launch **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="b3b6c-105">Haga clic en **supervisión de actividades** en el panel **Administración** .</span><span class="sxs-lookup"><span data-stu-id="b3b6c-105">Click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
3.  <span data-ttu-id="b3b6c-106">Ordene la lista en función de la **hora de inicio** de la actividad para ver el registro más reciente.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-106">Sort the list based on **Activity Start Time** to see the latest record.</span></span>  
  
4.  <span data-ttu-id="b3b6c-107">Tenga en cuenta que verá un nombre del proyecto con el siguiente formato: **CleanseAndCurate. cleane Supplier Data. GUID**.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-107">Notice that you see a name of the project in the following format: **CleanseAndCurate.Cleanse Supplier Data.GUID**.</span></span>  
  
     <span data-ttu-id="b3b6c-108">![Proyecto de limpieza de DQS creado por el paquete SSIS](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "Proyecto de limpieza de DQS creado por el paquete SSIS")</span><span class="sxs-lookup"><span data-stu-id="b3b6c-108">![DQS Cleansing Project Created by SSIS Package](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "DQS Cleansing Project Created by SSIS Package")</span></span>  
  
5.  <span data-ttu-id="b3b6c-109">Observe que el valor del campo **es activo** está **activo**.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-109">Notice that the value in the **Is Active** field is **Active**.</span></span>  
  
6.  <span data-ttu-id="b3b6c-110">Haga clic en la pestaña **generador de perfiles** en el panel inferior para ver las estadísticas del generador de perfiles para la actividad de limpieza realizada por el paquete SSIS.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-110">Click **Profiler** tab in the bottom pane to see profiler statistics for the Cleansing activity that the SSIS package performed.</span></span>  
  
7.  <span data-ttu-id="b3b6c-111">Haga clic en **cerrar** para cerrar la pantalla de **Administración** .</span><span class="sxs-lookup"><span data-stu-id="b3b6c-111">Click **Close** to close the **Administration** screen.</span></span>  
  
8.  <span data-ttu-id="b3b6c-112">En la Página principal del **cliente DQS**, haga clic en **Abrir proyecto de calidad de datos** en el panel **proyectos de calidad de datos** .</span><span class="sxs-lookup"><span data-stu-id="b3b6c-112">In the main page of **DQS Client**, click **Open Data Quality Project** in the **Data Quality Projects** pane.</span></span>  
  
9. <span data-ttu-id="b3b6c-113">En la lista de proyectos, seleccione el proyecto creado por el componente Limpieza de DQS de SSIS.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-113">In the list of projects, select the project created by SSIS DQS Cleansing component.</span></span> <span data-ttu-id="b3b6c-114">El nombre del proyecto debe tener el formato: **CleanseAndCurate. cleane Supplier Data. GUID (en color rojo)**.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-114">The name of the project should be in format:  **CleanseAndCurate.Cleanse Supplier Data.GUID (in red color)**.</span></span> <span data-ttu-id="b3b6c-115">Es posible que tenga que ordenar la lista en función de la columna **fecha de creación** y buscar el registro más reciente.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-115">You may need to sort the list based on **Date Created** column and look for the latest record.</span></span>  
  
10. <span data-ttu-id="b3b6c-116">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-116">Click **Next**.</span></span>  
  
11. <span data-ttu-id="b3b6c-117">La página **administrar y ver resultados** debe ser familiar desde la limpieza interactiva que hizo anteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-117">The **Manage and View Results** page should be familiar to you from the interactive cleansing you did earlier in this tutorial.</span></span>  
  
12. <span data-ttu-id="b3b6c-118">Revise los resultados de la limpieza.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-118">Review the cleansing results.</span></span> <span data-ttu-id="b3b6c-119">También puede hacer una limpieza interactiva y exportar los resultados a un archivo de Excel o a una base de datos en la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-119">You can also perform interactive cleansing and export results to an Excel file or to a database in the next page.</span></span>  
  
13. <span data-ttu-id="b3b6c-120">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-120">Click **Next**.</span></span> <span data-ttu-id="b3b6c-121">En esta página **exportar** , puede exportar los resultados a un archivo de Excel, a un archivo CSV o a una base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-121">In this **Export** page, you can export results to an excel file, CSV file, or to a SQL database.</span></span>  
  
14. <span data-ttu-id="b3b6c-122">Haga clic en **Finalizar** para finalizar la actividad.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-122">Click **Finish** to finish the activity.</span></span>  
  
15. <span data-ttu-id="b3b6c-123">En la Página principal del **cliente DQS**, haga clic en **supervisión de actividades** en el panel **Administración** .</span><span class="sxs-lookup"><span data-stu-id="b3b6c-123">In the main page of **DQS Client**, click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
16. <span data-ttu-id="b3b6c-124">Observe que el valor del campo **isActive** del proyecto ha **finalizado** ahora.</span><span class="sxs-lookup"><span data-stu-id="b3b6c-124">Notice that the value of **IsActive** field for the project is **Ended** now.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="b3b6c-125">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="b3b6c-125">Next Step</span></span>  
 [<span data-ttu-id="b3b6c-126">Conclusión</span><span class="sxs-lookup"><span data-stu-id="b3b6c-126">Conclusion</span></span>](../../2014/tutorials/conclusion.md)  
  
  
