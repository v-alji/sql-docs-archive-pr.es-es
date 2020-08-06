---
title: 'Tarea 8: agregar un nuevo valor para la entidad estado en Excel | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a763d76b-06a3-4d51-9614-01fc9fb1c158
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cace99419997e48088420c331a823cdf3639a3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747280"
---
# <a name="task-8-adding-a-new-value-for-state-entity-in-excel"></a><span data-ttu-id="8ed74-102">Tarea 8: Adición de un nuevo valor para la entidad Estado en Excel</span><span class="sxs-lookup"><span data-stu-id="8ed74-102">Task 8: Adding a New Value for State Entity in Excel</span></span>
  <span data-ttu-id="8ed74-103">En esta tarea, agregará un valor para la entidad Estado en Excel y publicará el cambio en el servidor de MDS.</span><span class="sxs-lookup"><span data-stu-id="8ed74-103">In this task, you add a value for the State entity in Excel and publish the change to the MDS server.</span></span>  
  
1.  <span data-ttu-id="8ed74-104">Para agregar una **hoja de trabajo** en Excel, haga clic en la pestaña nuevo de la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="8ed74-104">Add a **work sheet** in Excel by clicking the new tab at the bottom.</span></span>  
  
     <span data-ttu-id="8ed74-105">![Excel - Pestaña Nueva hoja de cálculo](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - Pestaña Nueva hoja de cálculo")</span><span class="sxs-lookup"><span data-stu-id="8ed74-105">![Excel - New Worksheet Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - New Worksheet Tab")</span></span>  
  
2.  <span data-ttu-id="8ed74-106">En **Excel**, haga clic en la pestaña **datos maestros** del menú y, a continuación, haga clic en **Mostrar explorador** en la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="8ed74-106">In **Excel**, click the **Master Data** tab on the menu, and then click **Show Explorer** on the ribbon.</span></span>  
  
3.  <span data-ttu-id="8ed74-107">En el **Explorador de datos maestro**, seleccione **proveedores** en **modelo**.</span><span class="sxs-lookup"><span data-stu-id="8ed74-107">In the **Master Data Explorer**, select **Suppliers** for **Model**.</span></span> <span data-ttu-id="8ed74-108">Debería ver dos entidades: **proveedor** y **Estado** en la lista de entidades.</span><span class="sxs-lookup"><span data-stu-id="8ed74-108">You should see two entities: **Supplier** and **State** in the entity list.</span></span>  
  
4.  <span data-ttu-id="8ed74-109">Haga doble clic en **Estado** en la lista.</span><span class="sxs-lookup"><span data-stu-id="8ed74-109">Double-click **State** in the list.</span></span> <span data-ttu-id="8ed74-110">Todos los miembros de la entidad **State** de MDS deben mostrarse en la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="8ed74-110">All the members of the **State** entity from MDS should be displayed in the worksheet.</span></span>  
  
5.  <span data-ttu-id="8ed74-111">Ahora, agregue una fila al final con los siguientes valores: **Carolina del norte** para **nombre** y **NC** para el **código**.</span><span class="sxs-lookup"><span data-stu-id="8ed74-111">Now, add a row at the end with the following values: **North Carolina** for **Name** and **NC** for **Code**.</span></span> <span data-ttu-id="8ed74-112">La codificación de colores distingue los registros nuevos y actualizados de los demás registros.</span><span class="sxs-lookup"><span data-stu-id="8ed74-112">The color coding differentiates any new/updated records from the other records.</span></span>  
  
     <span data-ttu-id="8ed74-113">![Excel - Agregar North Carolina a Estados](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Agregar North Carolina a Estados")</span><span class="sxs-lookup"><span data-stu-id="8ed74-113">![Excel - Add North Carolina to States](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Add North Carolina to States")</span></span>  
  
6.  <span data-ttu-id="8ed74-114">Haga clic en **publicar** en la cinta de opciones para publicar el cambio en MDS.</span><span class="sxs-lookup"><span data-stu-id="8ed74-114">Click **Publish** on the ribbon to publish the change to MDS.</span></span>  
  
     <span data-ttu-id="8ed74-115">![Excel - Botón Publicar en la pestaña de datos maestros](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Botón Publicar en la pestaña de datos maestros")</span><span class="sxs-lookup"><span data-stu-id="8ed74-115">![Excel - Publish Button on Master Data Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Publish Button on Master Data Tab")</span></span>  
  
7.  <span data-ttu-id="8ed74-116">En el cuadro de diálogo **publicar y anotar** , observe que está seleccionada la opción **usar la misma anotación para todos los cambios** .</span><span class="sxs-lookup"><span data-stu-id="8ed74-116">On the **Publish and Annotate** dialog box, notice that the **Use same annotation for all changes** is selected.</span></span> <span data-ttu-id="8ed74-117">Aquí puede escribir una sola anotación para todos los cambios.</span><span class="sxs-lookup"><span data-stu-id="8ed74-117">You can enter a single annotation for all the changes here.</span></span>  
  
8.  <span data-ttu-id="8ed74-118">Seleccione la opción **Revisar cambios y proporcionar anotaciones individualmente** para proporcionar una anotación para cada cambio (en este caso, solo uno).</span><span class="sxs-lookup"><span data-stu-id="8ed74-118">Select **Review changes and provide annotations individually** option to provide annotation for each change (in this case, only one).</span></span>  
  
     <span data-ttu-id="8ed74-119">![Excel - Cuadro de diálogo Publicar y anotar](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Cuadro de diálogo Publicar y anotar")</span><span class="sxs-lookup"><span data-stu-id="8ed74-119">![Excel - Publish and Annotate Dialog Box](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Publish and Annotate Dialog Box")</span></span>  
  
9. <span data-ttu-id="8ed74-120">Haga clic en **publicar** para publicar datos en MDS.</span><span class="sxs-lookup"><span data-stu-id="8ed74-120">Click **Publish** to publish data to MDS.</span></span>  
  
10. <span data-ttu-id="8ed74-121">Observe que la **codificación de colores** de la fila con el norte de **Carolina** como el **Estado** es la misma que la de otros registros.</span><span class="sxs-lookup"><span data-stu-id="8ed74-121">Notice that **color coding** for the row with **North Carolina** as the **State** is same as other records now.</span></span>  
  
11. <span data-ttu-id="8ed74-122">**Opcional:** Compruebe que el nuevo miembro (NC) se agrega a la entidad **Estado** mediante el **Explorador** de **Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="8ed74-122">**Optional:** Verify that the new member (NC) is added to the **State** entity by using the **Explorer** in **Master Data Manager**.</span></span>  
  
12. <span data-ttu-id="8ed74-123">En Excel, haga clic con el botón secundario en la hoja de cálculo de **Estado** en la parte inferior y haga clic en **eliminar** para eliminar la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="8ed74-123">In Excel, right-click the **State** worksheet at the bottom, and click **Delete** to delete the worksheet.</span></span> <span data-ttu-id="8ed74-124">Al eliminar la hoja de cálculo no se eliminan los datos del servidor de MDS.</span><span class="sxs-lookup"><span data-stu-id="8ed74-124">Deleting the worksheet does not delete any data from the MDS server.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8ed74-125">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="8ed74-125">Next Step</span></span>  
 [<span data-ttu-id="8ed74-126">Tarea 9: Creación de una jerarquía derivada mediante Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="8ed74-126">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>](../../2014/tutorials/task-9-creating-a-derived-hierarchy-using-master-data-manager.md)  
  
  
