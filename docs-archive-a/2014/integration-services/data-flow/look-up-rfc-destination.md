---
title: Buscar destino RFC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db9404d8-4c42-45e5-a100-c7a84b056109
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 397298fce16509e667aa4baccaee62c6ff0f5cca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750049"
---
# <a name="look-up-rfc-destination"></a><span data-ttu-id="0ae76-102">Buscar destino RFC</span><span class="sxs-lookup"><span data-stu-id="0ae76-102">Look Up RFC Destination</span></span>
  <span data-ttu-id="0ae76-103">Use el cuadro de diálogo **Buscar destino RFC** para buscar un destino RFC que se haya definido en el sistema de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0ae76-103">Use the **Look Up RFC Destination** dialog box to look up an RFC destination that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="0ae76-104">Cuando aparezca la lista de destinos RFC disponibles, seleccione el destino que desee y el componente rellenará las opciones asociadas a los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="0ae76-104">When the list of available RFC destinations appears, select the destination that you want, and the component will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="0ae76-105">El origen y el destino de SAP BW utilizan el cuadro de diálogo **Buscar destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="0ae76-105">Both the SAP BW source and the SAP BW destination use the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="0ae76-106">Para más información sobre estos componentes de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Origen de SAP BW](sap-bw-source.md) y [Destino de SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="0ae76-106">For more information about these components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md) and [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0ae76-107">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0ae76-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="0ae76-108">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="0ae76-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="0ae76-109">**Para abrir el cuadro de diálogo Buscar destino RFC**</span><span class="sxs-lookup"><span data-stu-id="0ae76-109">**To open the Look Up RFC Destination dialog box**</span></span>  
  
1.  <span data-ttu-id="0ae76-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el origen o destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0ae76-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source or destination.</span></span>  
  
2.  <span data-ttu-id="0ae76-111">En la pestaña **Flujo de datos** , haga doble clic en el origen o destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0ae76-111">On the **Data Flow** tab, double-click the SAP BW source or destination.</span></span>  
  
3.  <span data-ttu-id="0ae76-112">En **Editor de origen SAP BW** o **Editor de destino de SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="0ae76-112">In the **SAP BW Source Editor** or the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="0ae76-113">En la página **Administrador de conexiones** , en el cuadro del grupo **Destino RFC** , haga clic en **Buscar** para mostrar el cuadro de diálogo **Buscar destino RFC** .</span><span class="sxs-lookup"><span data-stu-id="0ae76-113">On the **Connection Manager** page, in the **RFC Destination** group box, click **Look up** to display the **Look Up RFC Destination** dialog box.</span></span>  
  
     <span data-ttu-id="0ae76-114">En el **Editor de origen de SAP BW**, el cuadro del grupo **Destino RFC** solo aparece si el valor de **Modo de ejecución** es **P - Desencadenar cadena de procesos** o **W - Esperar notificación**.</span><span class="sxs-lookup"><span data-stu-id="0ae76-114">In the **SAP BW Source Editor**, the **RFC Destination** group box appears only if the value for **Execution mode** is **P - Trigger process chain** or **W - Wait for notify**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ae76-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="0ae76-115">Options</span></span>  
 <span data-ttu-id="0ae76-116">**Destino**</span><span class="sxs-lookup"><span data-stu-id="0ae76-116">**Destination**</span></span>  
 <span data-ttu-id="0ae76-117">Permite ver el nombre del destino RFC que se haya definido en el sistema de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0ae76-117">View the name of the RFC destination that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="0ae76-118">**Host de puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="0ae76-118">**Gateway Host**</span></span>  
 <span data-ttu-id="0ae76-119">Permite ver el nombre del servidor o la dirección IP del host de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="0ae76-119">View the server name or IP address of the gateway host.</span></span> <span data-ttu-id="0ae76-120">Normalmente, el nombre o la dirección IP es el mismo que el del servidor de aplicaciones SAP.</span><span class="sxs-lookup"><span data-stu-id="0ae76-120">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="0ae76-121">**Servicio de puerta de enlace**</span><span class="sxs-lookup"><span data-stu-id="0ae76-121">**Gateway Service**</span></span>  
 <span data-ttu-id="0ae76-122">Vea el nombre del servicio de puerta de enlace, con el formato `sapgwNN`, donde `NN` es el número del sistema.</span><span class="sxs-lookup"><span data-stu-id="0ae76-122">View the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="0ae76-123">**Id. de programa**</span><span class="sxs-lookup"><span data-stu-id="0ae76-123">**Program ID**</span></span>  
 <span data-ttu-id="0ae76-124">Permite ver el identificador de programa asociado al destino RFC.</span><span class="sxs-lookup"><span data-stu-id="0ae76-124">View the Program ID that is associated with the RFC destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae76-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ae76-125">See Also</span></span>  
 <span data-ttu-id="0ae76-126">[Editor de origen de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="0ae76-126">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="0ae76-127">[Editor de destino de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="0ae76-127">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="0ae76-128">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="0ae76-128">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
