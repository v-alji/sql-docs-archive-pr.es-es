---
title: Editor de destino de SAP BW (página Asignaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dfa1f1d6-6b64-4331-bdc5-eaa8b7aa41a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c4c2803be3e2649f7425a2974dae8ac0a80fae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744228"
---
# <a name="sap-bw-destination-editor-mappings-page"></a><span data-ttu-id="888bd-102">Editor de destino de SAP BW (página Asignaciones)</span><span class="sxs-lookup"><span data-stu-id="888bd-102">SAP BW Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="888bd-103">Use la página **Asignaciones** del cuadro de diálogo **Editor de destino de SAP BW** para asignar columnas de entrada a columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="888bd-103">Use the **Mappings** page of the **SAP BW Destination Editor** to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="888bd-104">Para obtener más información sobre el destino SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Destino de SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="888bd-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="888bd-105">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="888bd-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="888bd-106">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="888bd-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="888bd-107">**Para abrir la página Asignaciones**</span><span class="sxs-lookup"><span data-stu-id="888bd-107">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="888bd-108">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="888bd-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="888bd-109">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="888bd-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="888bd-110">En **Editor de destino de SAP BW**, haga clic en **Asignaciones** para abrir la página **Asignaciones** del editor.</span><span class="sxs-lookup"><span data-stu-id="888bd-110">In the **SAP BW Destination Editor**, click **Mappings** to open the **Mappings** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="888bd-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="888bd-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="888bd-112">Si no conoce todos los valores necesarios para configurar el destino, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="888bd-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="888bd-113">La página **Asignaciones** del **Editor de destino de SAP BW** consta de dos secciones:</span><span class="sxs-lookup"><span data-stu-id="888bd-113">The **Mappings** page of the **SAP BW Destination Editor consists** of two sections:</span></span>  
  
-   <span data-ttu-id="888bd-114">En la sección superior aparecen las columnas de entrada y de destino disponibles y permite crear asignaciones entre estos dos tipos de columnas.</span><span class="sxs-lookup"><span data-stu-id="888bd-114">The upper section shows the available input and destination columns and lets you create mappings between these two types of columns.</span></span>  
  
-   <span data-ttu-id="888bd-115">En la sección inferior hay una tabla que indica las columnas de entrada que se han asignado y a qué columnas de salida.</span><span class="sxs-lookup"><span data-stu-id="888bd-115">The lower section is a table that lists which input columns have been mapped to which output columns.</span></span>  
  
### <a name="upper-section-options"></a><span data-ttu-id="888bd-116">Opciones de la sección superior</span><span class="sxs-lookup"><span data-stu-id="888bd-116">Upper Section Options</span></span>  
 <span data-ttu-id="888bd-117">La sección superior presenta las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="888bd-117">The upper section has the following options:</span></span>  
  
 <span data-ttu-id="888bd-118">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="888bd-118">**Available Input Columns**</span></span>  
 <span data-ttu-id="888bd-119">Muestra la lista de columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="888bd-119">View the list of available input columns.</span></span>  
  
 <span data-ttu-id="888bd-120">Para asignar una columna de entrada a una columna de destino, arrastre una columna desde la lista **Columnas de entrada disponibles** y colóquela en la lista **Columnas de destino disponibles** .</span><span class="sxs-lookup"><span data-stu-id="888bd-120">To map an input column to a destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="888bd-121">**Columnas de destino disponibles**</span><span class="sxs-lookup"><span data-stu-id="888bd-121">**Available Destination Columns**</span></span>  
 <span data-ttu-id="888bd-122">Muestra la lista de columnas de destino disponibles.</span><span class="sxs-lookup"><span data-stu-id="888bd-122">View the list of available destination columns.</span></span>  
  
 <span data-ttu-id="888bd-123">Para asignar una columna de entrada a una columna de destino, arrastre una columna desde la lista **Columnas de entrada disponibles** y colóquela en la lista **Columnas de destino disponibles** .</span><span class="sxs-lookup"><span data-stu-id="888bd-123">To map an input column to destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="888bd-124">La sección superior dispone también de un menú contextual que se abre si hace clic con el botón secundario en el fondo.</span><span class="sxs-lookup"><span data-stu-id="888bd-124">The upper section also has a context menu that you can open by right-clicking on the background.</span></span> <span data-ttu-id="888bd-125">Este menú contextual contiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="888bd-125">This context menu contains the following options:</span></span>  
  
-   <span data-ttu-id="888bd-126">**Seleccionar todas las asignaciones**</span><span class="sxs-lookup"><span data-stu-id="888bd-126">**Select All Mappings**</span></span>  
  
-   <span data-ttu-id="888bd-127">**Eliminar asignaciones seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="888bd-127">**Delete Selected Mappings**</span></span>  
  
-   <span data-ttu-id="888bd-128">**Asignar elementos por coincidencia de nombres**</span><span class="sxs-lookup"><span data-stu-id="888bd-128">**Map Items by Matching Names**</span></span>  
  
### <a name="lower-section-columns"></a><span data-ttu-id="888bd-129">Columnas de la sección inferior</span><span class="sxs-lookup"><span data-stu-id="888bd-129">Lower Section Columns</span></span>  
 <span data-ttu-id="888bd-130">La sección inferior presenta una tabla con las asignaciones y tiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="888bd-130">The lower section is a table of the mappings, and has the following columns:</span></span>  
  
 <span data-ttu-id="888bd-131">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="888bd-131">**Input Column**</span></span>  
 <span data-ttu-id="888bd-132">Permite ver las columnas de entrada que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="888bd-132">View the input columns that you have selected.</span></span>  
  
 <span data-ttu-id="888bd-133">Para asignar una columna de entrada a la misma columna de destino, seleccione una columna de entrada diferente de la lista.</span><span class="sxs-lookup"><span data-stu-id="888bd-133">To map a different input column to the same destination column, select a different input column in the list.</span></span> <span data-ttu-id="888bd-134">Para quitar una asignación, seleccione **\<ignore>** con el fin de excluir la columna de entrada de la salida.</span><span class="sxs-lookup"><span data-stu-id="888bd-134">To remove a mapping, select **\<ignore>** to exclude the input column from the output.</span></span>  
  
 <span data-ttu-id="888bd-135">**Columna de destino**</span><span class="sxs-lookup"><span data-stu-id="888bd-135">**Destination Column**</span></span>  
 <span data-ttu-id="888bd-136">Permite ver todas las columnas de destino disponibles, tanto si las columnas están asignadas como si no lo están.</span><span class="sxs-lookup"><span data-stu-id="888bd-136">View each available destination column, regardless of whether that column is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="888bd-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="888bd-137">See Also</span></span>  
 <span data-ttu-id="888bd-138">[Editor de destino de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="888bd-138">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="888bd-139">[Editor de destino de SAP BW &#40;página Salida de error&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="888bd-139">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="888bd-140">[Editor de destino de SAP BW &#40;página Opciones avanzadas&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="888bd-140">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="888bd-141">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="888bd-141">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
