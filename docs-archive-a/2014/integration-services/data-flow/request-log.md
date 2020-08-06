---
title: Registro de solicitudes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 165d3833-0493-490c-9f63-8a134a7fafb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 024012878ae94c5ba6276648e289e6e6f7c93d7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670452"
---
# <a name="request-log"></a><span data-ttu-id="118e8-102">Registro de solicitudes</span><span class="sxs-lookup"><span data-stu-id="118e8-102">Request Log</span></span>
  <span data-ttu-id="118e8-103">Use el cuadro de diálogo **Registro de solicitudes** para ver los eventos que se registran durante la solicitud que se efectúa al sistema SAP Netweaver BW sobre datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="118e8-103">Use the **Request Log** dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="118e8-104">Esta información puede ser útil si tiene que solucionar problemas en la configuración del origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="118e8-104">This information can be useful if you have to troubleshoot your configuration of the SAP BW source.</span></span>  
  
 <span data-ttu-id="118e8-105">Para obtener más información sobre el componente de origen de SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Origen de SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="118e8-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="118e8-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="118e8-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="118e8-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="118e8-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="118e8-108">La extracción de datos de SAP Netweaver BW requiere una licencia SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="118e8-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="118e8-109">Póngase en contacto con SAP para comprobar estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="118e8-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="118e8-110">**Para abrir el cuadro de diálogo Registro de solicitudes**</span><span class="sxs-lookup"><span data-stu-id="118e8-110">**To open the Request Log dialog box**</span></span>  
  
1.  <span data-ttu-id="118e8-111">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="118e8-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="118e8-112">En la pestaña **Flujo de datos** , haga doble clic en el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="118e8-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="118e8-113">En **Editor de origen de SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="118e8-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="118e8-114">Después de configurar el origen de SAP BW, haga clic en **Vista previa** para obtener una vista previa de los eventos del cuadro de diálogo **Registro de solicitudes** .</span><span class="sxs-lookup"><span data-stu-id="118e8-114">After you configure the SAP BW source, click **Preview** to preview the events in the **Request Log** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="118e8-115">Al hacer clic en **Vista previa** , también se abre el cuadro de diálogo **Vista previa** .</span><span class="sxs-lookup"><span data-stu-id="118e8-115">Clicking **Preview** also opens the **Preview** dialog box.</span></span> <span data-ttu-id="118e8-116">Para obtener más información sobre este cuadro de diálogo, vea [Preview](preview.md).</span><span class="sxs-lookup"><span data-stu-id="118e8-116">For more information about this dialog box, see [Preview](preview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="118e8-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="118e8-117">Options</span></span>  
 <span data-ttu-id="118e8-118">**Time**</span><span class="sxs-lookup"><span data-stu-id="118e8-118">**Time**</span></span>  
 <span data-ttu-id="118e8-119">Muestra la hora en la que se ha registrado el evento.</span><span class="sxs-lookup"><span data-stu-id="118e8-119">Displays the time that the event that was logged.</span></span>  
  
 <span data-ttu-id="118e8-120">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="118e8-120">**Type**</span></span>  
 <span data-ttu-id="118e8-121">Muestra el tipo de evento que se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="118e8-121">Displays the type of the event that was logged.</span></span> <span data-ttu-id="118e8-122">En la tabla siguiente se enumeran los tipos de evento posibles.</span><span class="sxs-lookup"><span data-stu-id="118e8-122">The following table lists the possible event types.</span></span>  
  
|<span data-ttu-id="118e8-123">Value</span><span class="sxs-lookup"><span data-stu-id="118e8-123">Value</span></span>|<span data-ttu-id="118e8-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="118e8-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="118e8-125">S</span><span class="sxs-lookup"><span data-stu-id="118e8-125">S</span></span>|<span data-ttu-id="118e8-126">Mensaje de correcto.</span><span class="sxs-lookup"><span data-stu-id="118e8-126">Success message.</span></span>|  
|<span data-ttu-id="118e8-127">E</span><span class="sxs-lookup"><span data-stu-id="118e8-127">E</span></span>|<span data-ttu-id="118e8-128">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="118e8-128">Error message</span></span>|  
|<span data-ttu-id="118e8-129">W</span><span class="sxs-lookup"><span data-stu-id="118e8-129">W</span></span>|<span data-ttu-id="118e8-130">Mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="118e8-130">Warning message.</span></span>|  
|<span data-ttu-id="118e8-131">I</span><span class="sxs-lookup"><span data-stu-id="118e8-131">I</span></span>|<span data-ttu-id="118e8-132">Mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="118e8-132">Informational message.</span></span>|  
|<span data-ttu-id="118e8-133">Un</span><span class="sxs-lookup"><span data-stu-id="118e8-133">A</span></span>|<span data-ttu-id="118e8-134">Se anuló la operación.</span><span class="sxs-lookup"><span data-stu-id="118e8-134">The operation was aborted.</span></span>|  
  
 <span data-ttu-id="118e8-135">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="118e8-135">**Message**</span></span>  
 <span data-ttu-id="118e8-136">Muestra el texto del mensaje asociado al evento registrado.</span><span class="sxs-lookup"><span data-stu-id="118e8-136">Displays the message text that is associated with the logged event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118e8-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="118e8-137">See Also</span></span>  
 <span data-ttu-id="118e8-138">[Editor de origen de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="118e8-138">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="118e8-139">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="118e8-139">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
