---
title: Crear InfoPackage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9cd4a848-409f-4681-a390-1c49a2aadbd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95f6ddce4e97c0c21d9f77c432231d414770dbce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744242"
---
# <a name="create-infopackage"></a><span data-ttu-id="ac212-102">Crear InfoPackage</span><span class="sxs-lookup"><span data-stu-id="ac212-102">Create InfoPackage</span></span>
  <span data-ttu-id="ac212-103">Use el cuadro de diálogo **Crear nuevo InfoPackage** para crear un nuevo InfoPackage en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ac212-103">Use the **Create InfoPackage** dialog box to create a new InfoPackage in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="ac212-104">Puede abrir el cuadro de diálogo **Crear InfoPackage** desde la página **Administrador de conexiones** del **Editor de destino de SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="ac212-104">You can open the **Create InfoPackage** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="ac212-105">Para más información acerca del destino de SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ac212-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ac212-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="ac212-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="ac212-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="ac212-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="ac212-108">**Para abrir el cuadro de diálogo Crear InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="ac212-108">**To open the Create InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="ac212-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ac212-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="ac212-110">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="ac212-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="ac212-111">En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="ac212-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="ac212-112">En la página **Administrador de conexiones** , en el cuadro del grupo **Crear objetos de SAP BW** , seleccione **InfoPackage**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="ac212-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoPackage**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac212-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="ac212-113">Options</span></span>  
 <span data-ttu-id="ac212-114">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="ac212-114">**InfoSource**</span></span>  
 <span data-ttu-id="ac212-115">Permite escribir el nombre del InfoSource en el que se va a basar el nuevo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="ac212-115">Enter the name of the InfoSource on which the new InfoPackage should be based.</span></span>  
  
 <span data-ttu-id="ac212-116">**Descripción breve**</span><span class="sxs-lookup"><span data-stu-id="ac212-116">**Short description**</span></span>  
 <span data-ttu-id="ac212-117">Permite escribir una descripción para el nuevo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="ac212-117">Enter a description for the new InfoPackage.</span></span>  
  
 <span data-ttu-id="ac212-118">**Sistema de origen**</span><span class="sxs-lookup"><span data-stu-id="ac212-118">**Source system**</span></span>  
 <span data-ttu-id="ac212-119">Permite seleccionar el sistema origen con el que se va asociar el nuevo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="ac212-119">Select the source system with which the new InfoPackage should be associated.</span></span>  
  
 <span data-ttu-id="ac212-120">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="ac212-120">**Attributes**</span></span>  
 <span data-ttu-id="ac212-121">Permite indicar que el InfoPackage cargará los datos del atributo.</span><span class="sxs-lookup"><span data-stu-id="ac212-121">Indicates that the InfoPackage will load attribute data.</span></span>  
  
 <span data-ttu-id="ac212-122">**Textos**</span><span class="sxs-lookup"><span data-stu-id="ac212-122">**Texts**</span></span>  
 <span data-ttu-id="ac212-123">Permite indicar que el InfoPackage cargará los datos de texto.</span><span class="sxs-lookup"><span data-stu-id="ac212-123">Indicates that the InfoPackage will load text data.</span></span>  
  
 <span data-ttu-id="ac212-124">**Transacción**</span><span class="sxs-lookup"><span data-stu-id="ac212-124">**Transaction**</span></span>  
 <span data-ttu-id="ac212-125">Permite indicar que el InfoPackage cargará los datos de transacciones.</span><span class="sxs-lookup"><span data-stu-id="ac212-125">Indicates that the InfoPackage will load transaction data.</span></span>  
  
 <span data-ttu-id="ac212-126">**Guardar y activar**</span><span class="sxs-lookup"><span data-stu-id="ac212-126">**Save & Activate**</span></span>  
 <span data-ttu-id="ac212-127">Permite guardar y activar el nuevo InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="ac212-127">Save and activate the new InfoPackage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac212-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac212-128">See Also</span></span>  
 [<span data-ttu-id="ac212-129">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="ac212-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
