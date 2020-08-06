---
title: Editor de origen de SAP BW (página Salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6e23b0c-949a-46d1-8424-4dc3d9035e79
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a4ad2d02d3f5ec5c1a786019e18fa01665fdc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744225"
---
# <a name="sap-bw-source-editor-error-output-page"></a><span data-ttu-id="8067c-102">Editor de origen de SAP BW (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="8067c-102">SAP BW Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="8067c-103">Utilice la página **Salida de error** del **Editor de origen de SAP BW** para seleccionar las opciones de control de errores y para establecer las propiedades en las columnas de salida de errores.</span><span class="sxs-lookup"><span data-stu-id="8067c-103">Use the **Error Output** page of the **SAP BW Source Editor** to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="8067c-104">Para obtener más información sobre el componente de origen de SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Origen de SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="8067c-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8067c-105">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8067c-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="8067c-106">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="8067c-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8067c-107">La extracción de datos de SAP Netweaver BW requiere una licencia SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="8067c-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="8067c-108">Póngase en contacto con SAP para comprobar estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="8067c-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="8067c-109">**Para abrir la página Salida de error**</span><span class="sxs-lookup"><span data-stu-id="8067c-109">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="8067c-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8067c-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="8067c-111">En la pestaña **Flujo de datos** , haga doble clic en el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8067c-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="8067c-112">En **Editor de origen de SAP BW**, haga clic en **Salida de error** para abrir la página **Salida de error** del editor.</span><span class="sxs-lookup"><span data-stu-id="8067c-112">In the **SAP BW Source Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8067c-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="8067c-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8067c-114">Si no conoce todos los valores necesarios para configurar el origen, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="8067c-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="8067c-115">**Entrada o salida**</span><span class="sxs-lookup"><span data-stu-id="8067c-115">**Input or Output**</span></span>  
 <span data-ttu-id="8067c-116">Muestra el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8067c-116">View the name of the data source.</span></span>  
  
 <span data-ttu-id="8067c-117">**Columna**</span><span class="sxs-lookup"><span data-stu-id="8067c-117">**Column**</span></span>  
 <span data-ttu-id="8067c-118">Muestra las columnas externas (origen) que se han seleccionado en la página **Columnas** del cuadro de diálogo **Editor de origen de SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="8067c-118">View the external (source) columns that you selected on the **Columns** page of the **SAP BW Source Editor** dialog box.</span></span> <span data-ttu-id="8067c-119">Para obtener más información sobre este cuadro de diálogo, vea [Editor de origen de SAP BW &#40;página Columnas&#41;](sap-bw-source-editor-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="8067c-119">For more information about this dialog box, see [SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md).</span></span>  
  
 <span data-ttu-id="8067c-120">**Error**</span><span class="sxs-lookup"><span data-stu-id="8067c-120">**Error**</span></span>  
 <span data-ttu-id="8067c-121">Permite especificar lo que debe hacer el componente de origen de SAP BW cuando se produzca un error: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="8067c-121">Specify what the SAP BW source component should do when there is an error: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="8067c-122">**Truncamiento**</span><span class="sxs-lookup"><span data-stu-id="8067c-122">**Truncation**</span></span>  
 <span data-ttu-id="8067c-123">Permite especificar lo que debe hacer el componente de origen de SAP BW cuando se produzca un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="8067c-123">Specify what the SAP BW source component should do when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="8067c-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8067c-124">**Description**</span></span>  
 <span data-ttu-id="8067c-125">Muestra la descripción del error.</span><span class="sxs-lookup"><span data-stu-id="8067c-125">View the description of the error.</span></span>  
  
 <span data-ttu-id="8067c-126">**Establecer este valor en las celdas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="8067c-126">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="8067c-127">Permite especificar qué debe hacer el componente de origen de SAP BW en todas las celdas seleccionadas cuando se produce un error o un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="8067c-127">Specify what the SAP BW source component should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="8067c-128">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="8067c-128">**Apply**</span></span>  
 <span data-ttu-id="8067c-129">Aplica la opción de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="8067c-129">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8067c-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8067c-130">See Also</span></span>  
 <span data-ttu-id="8067c-131">[Editor de origen de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="8067c-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="8067c-132">[Editor de origen de SAP BW &#40;página Columnas&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="8067c-132">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="8067c-133">[Editor de origen de SAP BW &#40;página Opciones avanzadas&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="8067c-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="8067c-134">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="8067c-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
