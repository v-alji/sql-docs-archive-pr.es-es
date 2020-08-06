---
title: Crear InfoSource | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7db233b-5464-43de-9d26-6dd24c7ac1b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9620d3170310322c79679e8298ffe465067ae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744234"
---
# <a name="create-infosource"></a><span data-ttu-id="d497f-102">Crear InfoSource</span><span class="sxs-lookup"><span data-stu-id="d497f-102">Create InfoSource</span></span>
  <span data-ttu-id="d497f-103">Use el cuadro de diálogo **Crear InfoSource** para crear un InfoSource nuevo.</span><span class="sxs-lookup"><span data-stu-id="d497f-103">Use the **Create InfoSource** dialog box to create a new InfoSource.</span></span> <span data-ttu-id="d497f-104">Para crear un InfoSource nuevo, puede usar el cuadro de diálogo **Crear InfoSource para los datos de transacción** o **Crear InfoSource para datos maestros** .</span><span class="sxs-lookup"><span data-stu-id="d497f-104">To create the new InfoSource, you use either the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span>  
  
 <span data-ttu-id="d497f-105">Puede abrir el cuadro de diálogo **Crear InfoSource** desde la página **Administrador de conexiones** del **Editor de destino de SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="d497f-105">You can open the **Create InfoSource** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="d497f-106">Para más información acerca del destino de SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d497f-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d497f-107">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="d497f-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d497f-108">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="d497f-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="d497f-109">**Para abrir el cuadro de diálogo Crear InfoSource**</span><span class="sxs-lookup"><span data-stu-id="d497f-109">**To open the Create InfoSource dialog box**</span></span>  
  
1.  <span data-ttu-id="d497f-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d497f-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="d497f-111">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="d497f-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="d497f-112">En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="d497f-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="d497f-113">En la página **Administrador de conexiones** , en el cuadro del grupo **Crear objetos de SAP BW** , seleccione **InfoSource**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="d497f-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d497f-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="d497f-114">Options</span></span>  
 <span data-ttu-id="d497f-115">**Datos de transacción**</span><span class="sxs-lookup"><span data-stu-id="d497f-115">**Transaction data**</span></span>  
 <span data-ttu-id="d497f-116">Permite crear un InfoSource nuevo para los datos de transacción.</span><span class="sxs-lookup"><span data-stu-id="d497f-116">Create a new InfoSource for transaction data.</span></span>  
  
 <span data-ttu-id="d497f-117">Si selecciona esta opción, se abrirá el cuadro de diálogo **Crear InfoSource para datos de transacción** .</span><span class="sxs-lookup"><span data-stu-id="d497f-117">If you select this option, the **Create InfoSource for Transaction Data** dialog box opens.</span></span> <span data-ttu-id="d497f-118">Use el cuadro de diálogo **Crear InfoSource para datos de transacción** para crear el InfoSource nuevo.</span><span class="sxs-lookup"><span data-stu-id="d497f-118">You use the **Create InfoSource for Transaction Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="d497f-119">Para obtener más información sobre este cuadro de diálogo, vea [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="d497f-119">For more information about this dialog box, see [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md).</span></span>  
  
 <span data-ttu-id="d497f-120">**Datos maestros**</span><span class="sxs-lookup"><span data-stu-id="d497f-120">**Master data**</span></span>  
 <span data-ttu-id="d497f-121">Permite crear un InfoSource nuevo para los datos maestros.</span><span class="sxs-lookup"><span data-stu-id="d497f-121">Create a new InfoSource for master data.</span></span>  
  
 <span data-ttu-id="d497f-122">Si selecciona esta opción, se abrirá el cuadro de diálogo **Crear InfoSource para datos maestros** .</span><span class="sxs-lookup"><span data-stu-id="d497f-122">If you select this option, the **Create InfoSource for Master Data** dialog box opens.</span></span> <span data-ttu-id="d497f-123">Use el cuadro de diálogo **Crear InfoSource para datos maestros** para crear el InfoSource nuevo.</span><span class="sxs-lookup"><span data-stu-id="d497f-123">You use the **Create InfoSource for Master Data** dialog box to create the new InfoSource.</span></span> <span data-ttu-id="d497f-124">Para obtener más información sobre este cuadro de diálogo, vea [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="d497f-124">For more information about this dialog box, see [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d497f-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d497f-125">See Also</span></span>  
 [<span data-ttu-id="d497f-126">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d497f-126">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
