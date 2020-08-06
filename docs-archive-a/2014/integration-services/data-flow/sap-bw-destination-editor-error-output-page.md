---
title: Editor de destino de SAP BW (página Salida de error) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a543d811-0bd2-4890-a0d3-f5fdcd4524b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ffd58580865a71626252aa2d177530e41156537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744229"
---
# <a name="sap-bw-destination-editor-error-output-page"></a><span data-ttu-id="3b0ad-102">Editor de destino de SAP BW (página Salida de error)</span><span class="sxs-lookup"><span data-stu-id="3b0ad-102">SAP BW Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="3b0ad-103">Use la página **Salida de error** del cuadro de diálogo **Editor de destino de SAP BW** para especificar las opciones de control de errores.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-103">Use the **Error Output** page of the **SAP BW Destination Editor** to specify error handling options.</span></span>  
  
 <span data-ttu-id="3b0ad-104">Para obtener más información sobre el destino SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Destino de SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="3b0ad-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3b0ad-105">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="3b0ad-106">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="3b0ad-107">**Para abrir la página Salida de error**</span><span class="sxs-lookup"><span data-stu-id="3b0ad-107">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="3b0ad-108">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="3b0ad-109">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="3b0ad-110">En **Editor de destino de SAP BW**, haga clic en **Salida de error** para abrir la página **Salida de error** del editor.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-110">In the **SAP BW Destination Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3b0ad-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="3b0ad-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b0ad-112">Si no conoce todos los valores necesarios para configurar el destino, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="3b0ad-113">**Entrada o salida**</span><span class="sxs-lookup"><span data-stu-id="3b0ad-113">**Input or Output**</span></span>  
 <span data-ttu-id="3b0ad-114">Muestra el nombre de la entrada.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-114">View the name of the input.</span></span>  
  
 <span data-ttu-id="3b0ad-115">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3b0ad-115">**Column**</span></span>  
 <span data-ttu-id="3b0ad-116">Esta opción no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-116">This option is not used.</span></span>  
  
 <span data-ttu-id="3b0ad-117">**Error**</span><span class="sxs-lookup"><span data-stu-id="3b0ad-117">**Error**</span></span>  
 <span data-ttu-id="3b0ad-118">Permite especificar lo que debe hacer el destino cuando se produzca un error: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-118">Specify what the destination should do when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="3b0ad-119">**Truncamiento**</span><span class="sxs-lookup"><span data-stu-id="3b0ad-119">**Truncation**</span></span>  
 <span data-ttu-id="3b0ad-120">Esta opción no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-120">This option is not used.</span></span>  
  
 <span data-ttu-id="3b0ad-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3b0ad-121">**Description**</span></span>  
 <span data-ttu-id="3b0ad-122">Muestra la descripción de la operación.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-122">View the description of the operation.</span></span>  
  
 <span data-ttu-id="3b0ad-123">**Establecer este valor en las celdas seleccionadas**</span><span class="sxs-lookup"><span data-stu-id="3b0ad-123">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="3b0ad-124">Permite especificar lo que debe hacer el destino en todas las celdas seleccionadas cuando se produce un error o un truncamiento: omitir el error, redirigir la fila o hacer que el componente no funcione.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-124">Specify what the destination should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="3b0ad-125">**Aplicar**</span><span class="sxs-lookup"><span data-stu-id="3b0ad-125">**Apply**</span></span>  
 <span data-ttu-id="3b0ad-126">Aplica la opción de control de errores a las celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="3b0ad-126">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b0ad-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b0ad-127">See Also</span></span>  
 <span data-ttu-id="3b0ad-128">[Editor de destino de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="3b0ad-128">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="3b0ad-129">[Editor de destino de SAP BW &#40;página Asignaciones&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="3b0ad-129">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="3b0ad-130">[Editor de destino de SAP BW &#40;página Opciones avanzadas&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="3b0ad-130">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="3b0ad-131">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="3b0ad-131">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
