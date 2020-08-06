---
title: Vista previa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 551494c4-9e27-4592-9200-c6bf19e80c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a795338122c1e7a37a23fdb6af6153f74b927e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670462"
---
# <a name="preview"></a><span data-ttu-id="09a66-102">Versión preliminar</span><span class="sxs-lookup"><span data-stu-id="09a66-102">Preview</span></span>
  <span data-ttu-id="09a66-103">Use el cuadro de diálogo **Vista previa** para obtener una vista previa de los datos que va a extraer el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="09a66-103">Use the **Preview** dialog box to preview the data that the SAP BW source will extract.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="09a66-104">La opción de **Vista previa** , que está disponible en la página de **Administrador de conexiones** del **Editor de origen de SAP BW**, extrae los datos.</span><span class="sxs-lookup"><span data-stu-id="09a66-104">The **Preview** option, that is available on the **Connection Manager** page of the **SAP BW Source Editor**, actually extracts data.</span></span> <span data-ttu-id="09a66-105">Si ha configurado SAP Netweaver BW para extraer solamente los datos que han cambiado desde la extracción anterior, si selecciona **Vista previa** , excluirá datos de la vista previa de la extracción siguiente.</span><span class="sxs-lookup"><span data-stu-id="09a66-105">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="09a66-106">Para obtener más información sobre el componente de origen de SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vea [Origen de SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="09a66-106">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="09a66-107">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="09a66-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="09a66-108">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="09a66-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="09a66-109">La extracción de datos de SAP Netweaver BW requiere una licencia SAP adicional.</span><span class="sxs-lookup"><span data-stu-id="09a66-109">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="09a66-110">Póngase en contacto con SAP para comprobar estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="09a66-110">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="09a66-111">**Para abrir el cuadro de diálogo Vista Previa**</span><span class="sxs-lookup"><span data-stu-id="09a66-111">**To open the Preview dialog box**</span></span>  
  
1.  <span data-ttu-id="09a66-112">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="09a66-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="09a66-113">En la pestaña **Flujo de datos** , haga doble clic en el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="09a66-113">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="09a66-114">En **Editor de origen de SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="09a66-114">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="09a66-115">Configure el origen de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="09a66-115">Configure the SAP BW source.</span></span>  
  
5.  <span data-ttu-id="09a66-116">Después de configurar el origen de SAP BW, en la página **Administrador de conexiones** , haga clic en **Vista previa** para obtener una vista previa de los datos en el cuadro de diálogo **Vista previa** .</span><span class="sxs-lookup"><span data-stu-id="09a66-116">After you configure the SAP BW source, on the **Connection Manager** page, click **Preview** to preview the data in the **Preview** dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="09a66-117">Al hacer clic en **Vista previa** , también se abre el cuadro de diálogo **Registro de solicitudes** .</span><span class="sxs-lookup"><span data-stu-id="09a66-117">Clicking **Preview** also opens the **Request Log** dialog box.</span></span> <span data-ttu-id="09a66-118">Para obtener más información sobre este cuadro de diálogo, vea [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="09a66-118">For more information about this dialog box, see [Request Log](request-log.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="09a66-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="09a66-119">Options</span></span>  
 <span data-ttu-id="09a66-120">El cuadro de diálogo **Vista previa** muestra las filas que se solicitan desde el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="09a66-120">The **Preview** dialog box displays the rows that are requested from the SAP Netweaver BW system.</span></span> <span data-ttu-id="09a66-121">Las columnas que se muestran son columnas definidas en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="09a66-121">The columns that are displayed are the columns that are defined in the source data.</span></span>  
  
 <span data-ttu-id="09a66-122">No hay otras opciones en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="09a66-122">There are no other options in this dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a66-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09a66-123">See Also</span></span>  
 <span data-ttu-id="09a66-124">[Editor de origen de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="09a66-124">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="09a66-125">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="09a66-125">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
