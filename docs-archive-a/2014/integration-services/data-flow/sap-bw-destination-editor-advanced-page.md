---
title: Editor de destino de SAP BW (página Opciones avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 862957db-bbc6-4dda-bc0e-591457f1baa7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c5ca943b804ad39cc391cb1cf7f06e056ddbe56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673811"
---
# <a name="sap-bw-destination-editor-advanced-page"></a><span data-ttu-id="c9499-102">Editor de destino de SAP BW (página Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="c9499-102">SAP BW Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="c9499-103">Use la página **Opciones avanzadas** del **Editor de destino de SAP BW** para establecer los valores de configuración avanzada como el tamaño del paquete y la información de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c9499-103">Use the **Advanced** page of the **SAP BW Destination Editor** to set advanced settings such as package size and time-out information.</span></span>  
  
 <span data-ttu-id="c9499-104">Para obtener más información sobre el destino SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Destino de SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c9499-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c9499-105">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="c9499-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="c9499-106">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="c9499-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="c9499-107">**Para abrir la página Opciones avanzadas**</span><span class="sxs-lookup"><span data-stu-id="c9499-107">**To open the Advanced page**</span></span>  
  
1.  <span data-ttu-id="c9499-108">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c9499-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="c9499-109">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="c9499-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="c9499-110">En **Editor de destino de SAP BW**, haga clic en **Opciones avanzadas** para abrir la página **Opciones avanzadas** del editor.</span><span class="sxs-lookup"><span data-stu-id="c9499-110">In the **SAP BW Destination Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9499-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="c9499-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9499-112">Si no conoce todos los valores necesarios para configurar el destino, puede que tenga que ponerse en contacto con el administrador de SAP.</span><span class="sxs-lookup"><span data-stu-id="c9499-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="c9499-113">**Tamaño de paquete**</span><span class="sxs-lookup"><span data-stu-id="c9499-113">**Package size**</span></span>  
 <span data-ttu-id="c9499-114">Permite especificar cuántas filas de datos se van a transferir a la vez.</span><span class="sxs-lookup"><span data-stu-id="c9499-114">Specify how many rows of data will be transferred at a time.</span></span> <span data-ttu-id="c9499-115">El valor óptimo para este parámetro depende del sistema SAP Netweaver BW y del procesamiento de datos adicional que pueda darse.</span><span class="sxs-lookup"><span data-stu-id="c9499-115">The optimal value for this parameter depends on the SAP Netweaver BW system and on additional processing of the data that might occur.</span></span> <span data-ttu-id="c9499-116">Normalmente, los valores entre 2 000 y 20 000 proporcionan el máximo rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c9499-116">Typically, values between 2000 and 20000 offer the best performance.</span></span>  
  
 <span data-ttu-id="c9499-117">**Cadena de proceso de desencadenador**</span><span class="sxs-lookup"><span data-stu-id="c9499-117">**Trigger process chain**</span></span>  
 <span data-ttu-id="c9499-118">(Opcional) Permite especificar el nombre de una cadena de procesos que se va a desencadenar una vez se haya completado la carga de datos.</span><span class="sxs-lookup"><span data-stu-id="c9499-118">(Optional) Specify the name of a process chain to be triggered after the loading of data is completed.</span></span>  
  
 <span data-ttu-id="c9499-119">**Tiempo de espera para InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="c9499-119">**Timeout for waiting InfoPackage**</span></span>  
 <span data-ttu-id="c9499-120">Permite especificar la cantidad máxima de segundos que va a esperar el destino para que finalice el InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="c9499-120">Specify the maximum number of seconds that the destination should wait for the InfoPackage to finish.</span></span>  
  
 <span data-ttu-id="c9499-121">**Esperar a que se complete la transferencia de datos**</span><span class="sxs-lookup"><span data-stu-id="c9499-121">**Wait for data transfer to finish**</span></span>  
 <span data-ttu-id="c9499-122">Permite especificar si el destino debe esperar hasta que el sistema SAP Netweaver BW haya terminado de cargar datos.</span><span class="sxs-lookup"><span data-stu-id="c9499-122">Specify whether the destination should wait until the SAP Netweaver BW system has finished loading the data.</span></span>  
  
 <span data-ttu-id="c9499-123">**No iniciar InfoPackage (Solo esperar)**</span><span class="sxs-lookup"><span data-stu-id="c9499-123">**No InfoPackage Start (Only Wait)**</span></span>  
 <span data-ttu-id="c9499-124">Permite especificar que el destino no va a activar un InfoPackage y que solo va a esperar a recibir la notificación de que el sistema SAP Netweaver BW ha comenzado a cargar datos.</span><span class="sxs-lookup"><span data-stu-id="c9499-124">Specify that the destination does not trigger an InfoPackage, but just waits for notification that the SAP Netweaver BW system has started loading the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9499-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9499-125">See Also</span></span>  
 <span data-ttu-id="c9499-126">[Editor de destino de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="c9499-126">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="c9499-127">[Editor de destino de SAP BW &#40;página Asignaciones&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="c9499-127">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="c9499-128">[Editor de destino de SAP BW &#40;página Salida de error&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c9499-128">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="c9499-129">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="c9499-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
