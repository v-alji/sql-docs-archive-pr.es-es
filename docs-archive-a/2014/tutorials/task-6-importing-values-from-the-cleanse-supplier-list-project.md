---
title: 'Tarea 6: importar valores del proyecto limpiar lista de proveedores | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fec0deef-a729-4ff1-b709-72d2b3f407ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b674cfb42ddf31c3b903a465d1be1b04e9a355ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663849"
---
# <a name="task-6-importing-values-from-the-cleanse-supplier-list-project"></a><span data-ttu-id="f369c-102">Tarea 6: Importación de valores del proyecto Limpiar lista de proveedores</span><span class="sxs-lookup"><span data-stu-id="f369c-102">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>
  <span data-ttu-id="f369c-103">En esta tarea, importará el conocimiento de calidad de datos obtenido durante el proceso de limpieza.</span><span class="sxs-lookup"><span data-stu-id="f369c-103">In this task, you import the data quality knowledge gathered during the cleansing process.</span></span> <span data-ttu-id="f369c-104">Consulte [el tema importar valores de proyecto de limpieza en un dominio](https://msdn.microsoft.com/library/hh479581.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="f369c-104">See [Importing Cleansing Project Values into a Domain](https://msdn.microsoft.com/library/hh479581.aspx) topic for more details.</span></span> <span data-ttu-id="f369c-105">También exportará la base de conocimiento en un archivo DQS antes de publicar la base de conocimiento de **proveedores** actualizada.</span><span class="sxs-lookup"><span data-stu-id="f369c-105">You also export the knowledge base into a DQS file before publishing the updated **Suppliers** knowledge base.</span></span>  
  
1.  <span data-ttu-id="f369c-106">En la Página principal del **cliente DQS**, haga clic en la **flecha derecha** junto a **proveedores** en **bases de conocimiento recientes** y haga clic en **Administración de dominios**.</span><span class="sxs-lookup"><span data-stu-id="f369c-106">In the main page of **DQS Client**, click **right-arrow** next to **Suppliers** under **Recent Knowledge Bases** and click **Domain Management**.</span></span>  
  
2.  <span data-ttu-id="f369c-107">Haga clic en **correo electrónico de contacto** en la lista de dominios y cambie a la pestaña **valores del dominio** en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="f369c-107">Click **Contact Email** in the list of domains, and switch to the **Domain Values** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="f369c-108">Haga clic en la **flecha abajo** situada junto al icono **importar valores** de la barra de herramientas y haga clic en **importar valores de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f369c-108">Click **down arrow** next to the **Import Values** icon on the toolbar and click **Import Project Values**.</span></span>  
  
     <span data-ttu-id="f369c-109">![Botón de la barra de herramientas Importar valores de proyecto](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Botón de la barra de herramientas Importar valores de proyecto")</span><span class="sxs-lookup"><span data-stu-id="f369c-109">![Import Project Values Toolbar Button](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Import Project Values Toolbar Button")</span></span>  
  
4.  <span data-ttu-id="f369c-110">En el cuadro de diálogo **importar valores de proyecto** , seleccione el proyecto **limpiar lista de proveedores** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f369c-110">In the **Import Project Values** dialog box, select the **Cleanse Supplier List** project, and click **OK**.</span></span>  
  
5.  <span data-ttu-id="f369c-111">Observe que se importan todas las direcciones de correo electrónico junto con las dos correcciones que hizo durante la limpieza interactiva.</span><span class="sxs-lookup"><span data-stu-id="f369c-111">Notice that all the emails are imported along with the two corrections you did during interactive cleansing.</span></span> <span data-ttu-id="f369c-112">Desplácese para ver las dos correcciones.</span><span class="sxs-lookup"><span data-stu-id="f369c-112">Scroll to see the two corrections.</span></span>  
  
    |<span data-ttu-id="f369c-113">Value</span><span class="sxs-lookup"><span data-stu-id="f369c-113">Value</span></span>|<span data-ttu-id="f369c-114">Corregir a</span><span class="sxs-lookup"><span data-stu-id="f369c-114">Correct To</span></span>|  
    |-----------|----------------|  
    |bobby0@adventure-work.com|bobby0@adventure-works.com|  
    |tad0@adventure-work.com|tad0@adventure-works.com|  
  
6.  <span data-ttu-id="f369c-115">Repita el paso anterior de importación de valores de proyecto para el dominio **Country** y observe que se ha agregado una nueva entrada para corregir el **Estado de United State** en **Estados Unidos** (con ' es ').</span><span class="sxs-lookup"><span data-stu-id="f369c-115">Repeat the previous step of importing project values for the **Country** domain and notice that a new entry is added for correcting **United State** to **United States** (with 's').</span></span>  
  
    |<span data-ttu-id="f369c-116">Value</span><span class="sxs-lookup"><span data-stu-id="f369c-116">Value</span></span>|<span data-ttu-id="f369c-117">Corregir a</span><span class="sxs-lookup"><span data-stu-id="f369c-117">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="f369c-118">United State</span><span class="sxs-lookup"><span data-stu-id="f369c-118">United State</span></span>|<span data-ttu-id="f369c-119">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="f369c-119">United States</span></span>|  
  
7.  <span data-ttu-id="f369c-120">Para ver los valores de dominio antiguos, desactive la casilla **Mostrar solo nuevo** .</span><span class="sxs-lookup"><span data-stu-id="f369c-120">To see the old domain values, clear **Show Only New** checkbox.</span></span>  
  
8.  <span data-ttu-id="f369c-121">Repita el paso anterior de importación de valores de proyecto para el dominio de **nombre de proveedor** .</span><span class="sxs-lookup"><span data-stu-id="f369c-121">Repeat the previous step of importing project values for the **Supplier Name** domain.</span></span> <span data-ttu-id="f369c-122">De forma predeterminada, después de la importación, solo verá los nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="f369c-122">By default, after importing, you will only see the new values.</span></span> <span data-ttu-id="f369c-123">Para ver todos los valores, desactive la casilla **Mostrar solo nuevo** .</span><span class="sxs-lookup"><span data-stu-id="f369c-123">To see all the values, clear **Show Only New** check box.</span></span> <span data-ttu-id="f369c-124">Ha enriquecido la base de conocimiento **proveedores** con lo que ha aprendido en la actividad de limpieza.</span><span class="sxs-lookup"><span data-stu-id="f369c-124">You have enriched the **Suppliers** knowledge base with what you learned from the cleansing activity.</span></span> <span data-ttu-id="f369c-125">Cuanto más sólida sea la base de conocimiento, mejores resultados obtendrá la limpieza.</span><span class="sxs-lookup"><span data-stu-id="f369c-125">The stronger the knowledge base is, the better the cleansing results are.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f369c-126">No es posible importar valores de un dominio compuesto.</span><span class="sxs-lookup"><span data-stu-id="f369c-126">It is not possible import values for a composite domain.</span></span>  
  
9. <span data-ttu-id="f369c-127">En la barra de herramientas, haga clic en el icono **exportar base de conocimiento** y, a continuación, en **exportar base de conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="f369c-127">Click **Export Knowledge Base** icon on the toolbar and then click **Export Knowledge Base**.</span></span>  
  
     <span data-ttu-id="f369c-128">![Exportar menú de base de conocimiento](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Exportar menú de base de conocimiento")</span><span class="sxs-lookup"><span data-stu-id="f369c-128">![Export Knowledge Base Menu](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Export Knowledge Base Menu")</span></span>  
  
10. <span data-ttu-id="f369c-129">Vaya a la carpeta tutorial, escriba **Suppliers. DQS** como **nombre de archivo**y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f369c-129">Navigate to the Tutorial folder, type **Suppliers.dqs** for the **file name**, and click **Save**.</span></span> <span data-ttu-id="f369c-130">Puede usar este archivo de DQS para crear una nueva base de conocimiento a partir de él.</span><span class="sxs-lookup"><span data-stu-id="f369c-130">You can use this DQS file to create a new knowledge base based on it.</span></span>  
  
11. <span data-ttu-id="f369c-131">Haga clic en **Aceptar** para cerrar el cuadro de mensaje **exportar base de conocimiento-proveedores** .</span><span class="sxs-lookup"><span data-stu-id="f369c-131">Click **OK** to close the **Export Knowledge Base - Suppliers** message box.</span></span>  
  
12. <span data-ttu-id="f369c-132">Haga clic en **Finalizar** para finalizar la actividad.</span><span class="sxs-lookup"><span data-stu-id="f369c-132">Click **Finish** to finish the activity.</span></span>  
  
13. <span data-ttu-id="f369c-133">Haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f369c-133">Click **Publish**.</span></span>  
  
14. <span data-ttu-id="f369c-134">Haga clic en **Aceptar** en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f369c-134">Click **OK** on the message box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f369c-135">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="f369c-135">Next Step</span></span>  
 [<span data-ttu-id="f369c-136">Lección 3: Búsqueda de datos coincidentes para quitar duplicados de lista de proveedores</span><span class="sxs-lookup"><span data-stu-id="f369c-136">Lesson 3: Matching Data to Remove Duplicates from Supplier List</span></span>](../../2014/tutorials/lesson-3-matching-data-to-remove-duplicates-from-supplier-list.md)  
  
  
