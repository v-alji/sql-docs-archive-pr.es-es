---
title: Crear InfoSource para datos maestros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b52a9a89-8380-4a02-8a83-dcfb46ae860e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bb90bc5cf27f37dc89df236b765db98088a5804a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744240"
---
# <a name="create-infosource-for-master-data"></a><span data-ttu-id="bf72c-102">Crear InfoSource para datos maestros</span><span class="sxs-lookup"><span data-stu-id="bf72c-102">Create InfoSource for Master Data</span></span>
  <span data-ttu-id="bf72c-103">Use el cuadro de diálogo **Crear InfoSource para los datos maestros** para crear un InfoSource nuevo para los datos maestros en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="bf72c-103">Use the **Create InfoSource for Master Data** dialog box to create a new InfoSource for master data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="bf72c-104">Puede abrir el cuadro de diálogo **Crear InfoSource para los datos maestros** desde la página **Administrador de conexiones** del **Editor de destino de SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="bf72c-104">You can open the **Create InfoSource for Master Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="bf72c-105">Para más información acerca del destino de SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="bf72c-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bf72c-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="bf72c-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="bf72c-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="bf72c-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="bf72c-108">**Para abrir el cuadro de diálogo Crear InfoSource para los datos maestros**</span><span class="sxs-lookup"><span data-stu-id="bf72c-108">**To open the Create InfoSource for Master Data dialog box**</span></span>  
  
1.  <span data-ttu-id="bf72c-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="bf72c-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="bf72c-110">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="bf72c-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="bf72c-111">En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="bf72c-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="bf72c-112">En la página **Administrador de conexiones** , en el cuadro del grupo **Crear objetos de SAP BW** , seleccione **InfoSource**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="bf72c-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="bf72c-113">En el cuadro de diálogo **Crear InfoSource** , seleccione **Datos maestros**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bf72c-113">In the **Create InfoSource** dialog box, select **Master data**, and then click **OK**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bf72c-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="bf72c-114">Options</span></span>  
 <span data-ttu-id="bf72c-115">**Nombre de InfoObject**</span><span class="sxs-lookup"><span data-stu-id="bf72c-115">**InfoObject name**</span></span>  
 <span data-ttu-id="bf72c-116">Permite escribir el nombre del InfoObject en el que se va a basar el nuevo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="bf72c-116">Enter the name of the InfoObject on which the new InfoSource should be based.</span></span>  
  
 <span data-ttu-id="bf72c-117">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="bf72c-117">**Look up**</span></span>  
 <span data-ttu-id="bf72c-118">Permite buscar el InfoObject.</span><span class="sxs-lookup"><span data-stu-id="bf72c-118">Look up the InfoObject.</span></span> <span data-ttu-id="bf72c-119">Esta opción abre el cuadro de diálogo **Buscar InfoObject** , donde podrá seleccionar el InfoObject.</span><span class="sxs-lookup"><span data-stu-id="bf72c-119">This option opens the **Look Up InfoObject** dialog box in which you can select the InfoObject.</span></span> <span data-ttu-id="bf72c-120">Para obtener más información sobre este cuadro de diálogo, vea [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="bf72c-120">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="bf72c-121">Después de seleccionar un InfoObject, el componente rellena el cuadro de texto **Nombre de InfoObject** con el nombre del InfoObject seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bf72c-121">After you select an InfoObject, the component populates the **InfoObject name** text box with the name of the selected InfoObject.</span></span>  
  
 <span data-ttu-id="bf72c-122">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="bf72c-122">**New**</span></span>  
 <span data-ttu-id="bf72c-123">Permite crear un nuevo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="bf72c-123">Create a new InfoObject.</span></span> <span data-ttu-id="bf72c-124">Esta opción abre el cuadro de diálogo **Crear nuevo InfoObject**, donde podrá crear el InfoObject nuevo.</span><span class="sxs-lookup"><span data-stu-id="bf72c-124">This option opens the **Create New InfoObject** dialog box in which you can create the new InfoObject.</span></span> <span data-ttu-id="bf72c-125">Para obtener más información sobre este cuadro de diálogo, vea [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="bf72c-125">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="bf72c-126">Después de crear un InfoObject, el componente rellena el cuadro de texto **Nombre de InfoObject** con el nombre del InfoObject nuevo.</span><span class="sxs-lookup"><span data-stu-id="bf72c-126">After you create an InfoObject, the component populates the **InfoObject name** text box with the name of the new InfoObject.</span></span>  
  
 <span data-ttu-id="bf72c-127">**Descripción breve**</span><span class="sxs-lookup"><span data-stu-id="bf72c-127">**Short description**</span></span>  
 <span data-ttu-id="bf72c-128">Permite escribir una descripción breve para el nuevo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="bf72c-128">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="bf72c-129">**Descripción larga**</span><span class="sxs-lookup"><span data-stu-id="bf72c-129">**Long description**</span></span>  
 <span data-ttu-id="bf72c-130">Permite escribir una descripción larga para el nuevo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="bf72c-130">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="bf72c-131">**Sistema de origen**</span><span class="sxs-lookup"><span data-stu-id="bf72c-131">**Source system**</span></span>  
 <span data-ttu-id="bf72c-132">Permite seleccionar el sistema de origen que se va a asociar al InfoSource.</span><span class="sxs-lookup"><span data-stu-id="bf72c-132">Select the source system to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="bf72c-133">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="bf72c-133">**Application**</span></span>  
 <span data-ttu-id="bf72c-134">Permite escribir el nombre de la aplicación que se va a asociar al nuevo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="bf72c-134">Enter the name of the application to be associated with the new InfoSource.</span></span>  
  
 <span data-ttu-id="bf72c-135">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="bf72c-135">**Attributes**</span></span>  
 <span data-ttu-id="bf72c-136">Permite indicar que los datos maestros están compuestos de atributos.</span><span class="sxs-lookup"><span data-stu-id="bf72c-136">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="bf72c-137">**Textos**</span><span class="sxs-lookup"><span data-stu-id="bf72c-137">**Texts**</span></span>  
 <span data-ttu-id="bf72c-138">Permite indicar que los datos maestros están compuestos de atributos.</span><span class="sxs-lookup"><span data-stu-id="bf72c-138">Indicates that the master data consists of attributes.</span></span>  
  
 <span data-ttu-id="bf72c-139">**Guardar y activar**</span><span class="sxs-lookup"><span data-stu-id="bf72c-139">**Save & Activate**</span></span>  
 <span data-ttu-id="bf72c-140">Permite guardar y activar el nuevo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="bf72c-140">Save and activate the new InfoSource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf72c-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf72c-141">See Also</span></span>  
 <span data-ttu-id="bf72c-142">[Crear InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="bf72c-142">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="bf72c-143">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="bf72c-143">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
