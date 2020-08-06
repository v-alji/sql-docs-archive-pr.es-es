---
title: Crear InfoCube para los datos de transacción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 673cea01-a260-4fce-a1a0-f73839289805
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a20fe051cfdd3e6afe285279996fcf696a83c21b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744244"
---
# <a name="create-infocube-for-transaction-data"></a><span data-ttu-id="0f0d5-102">Crear InfoCube para los datos de transacción</span><span class="sxs-lookup"><span data-stu-id="0f0d5-102">Create InfoCube for Transaction Data</span></span>
  <span data-ttu-id="0f0d5-103">Use el cuadro de diálogo **Crear InfoCube para los datos de transacción** para crear un InfoCube nuevo para los datos de transacciones en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-103">Use the **Create InfoCube for Transaction Data** dialog box to create a new InfoCube for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="0f0d5-104">Puede abrir el cuadro de diálogo **Crear InfoCube para los datos de transacción** desde la página **Administrador de conexiones** del **Editor de destino de SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-104">You can open the **Create InfoCube for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="0f0d5-105">Para más información acerca del destino de SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="0f0d5-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0f0d5-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="0f0d5-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="0f0d5-108">**Para abrir el cuadro de diálogo Crear InfoCube para los datos de transacción**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-108">**To open the Create InfoCube for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="0f0d5-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="0f0d5-110">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="0f0d5-111">En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="0f0d5-112">En la página **Administrador de conexiones** , en el cuadro del grupo **Crear objetos de SAP BW** , seleccione **InfoCube**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoCube**, and then click **Create**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="0f0d5-113">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="0f0d5-113">General Options</span></span>  
 <span data-ttu-id="0f0d5-114">**Nombre de InfoCube**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-114">**InfoCube name**</span></span>  
 <span data-ttu-id="0f0d5-115">Permite escribir un nombre para el nuevo InfoCube.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-115">Enter a name for the new InfoCube.</span></span>  
  
 <span data-ttu-id="0f0d5-116">**Descripción larga**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-116">**Long description**</span></span>  
 <span data-ttu-id="0f0d5-117">Permite escribir una descripción para el nuevo InfoCube.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-117">Enter a description for the new InfoCube.</span></span>  
  
 <span data-ttu-id="0f0d5-118">**Guardar y activar**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-118">**Save & Activate**</span></span>  
 <span data-ttu-id="0f0d5-119">Permite guardar y activar el nuevo InfoCube.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-119">Save and activate the new InfoCube.</span></span>  
  
## <a name="infocube-transfer-structure-options"></a><span data-ttu-id="0f0d5-120">Opciones de la estructura de transferencia de InfoCube</span><span class="sxs-lookup"><span data-stu-id="0f0d5-120">InfoCube Transfer Structure Options</span></span>  
 <span data-ttu-id="0f0d5-121">La sección sobre la estructura de transferencia de InfoCube permite asociar columnas del flujo de datos a InfoObjects.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-121">The InfoCube transfer structure section lets you associate data flow columns to InfoObjects.</span></span>  
  
 <span data-ttu-id="0f0d5-122">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-122">**PipelineElement**</span></span>  
 <span data-ttu-id="0f0d5-123">Permite mostrar la columna en la salida del flujo de datos que está conectada al destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-123">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="0f0d5-124">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-124">**PipelineDataType**</span></span>  
 <span data-ttu-id="0f0d5-125">Permite mostrar el tipo de datos de la columna del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-125">Displays the data type of the data flow column.</span></span>  
  
 <span data-ttu-id="0f0d5-126">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-126">**InfoObject**</span></span>  
 <span data-ttu-id="0f0d5-127">Permite mostrar el nombre del InfoObject que está asociado a la columna del flujo datos.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-127">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="0f0d5-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-128">**Type**</span></span>  
 <span data-ttu-id="0f0d5-129">Permite mostrar el tipo del InfoObject que está asociado a la columna del flujo datos.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-129">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="0f0d5-130">En la siguiente tabla se muestran los posibles valores para el tipo.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-130">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="0f0d5-131">Value</span><span class="sxs-lookup"><span data-stu-id="0f0d5-131">Value</span></span>|<span data-ttu-id="0f0d5-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f0d5-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f0d5-133">CHA</span><span class="sxs-lookup"><span data-stu-id="0f0d5-133">CHA</span></span>|<span data-ttu-id="0f0d5-134">Características</span><span class="sxs-lookup"><span data-stu-id="0f0d5-134">Characteristics</span></span>|  
|<span data-ttu-id="0f0d5-135">UNI</span><span class="sxs-lookup"><span data-stu-id="0f0d5-135">UNI</span></span>|<span data-ttu-id="0f0d5-136">Unidades</span><span class="sxs-lookup"><span data-stu-id="0f0d5-136">Units</span></span>|  
|<span data-ttu-id="0f0d5-137">KYF</span><span class="sxs-lookup"><span data-stu-id="0f0d5-137">KYF</span></span>|<span data-ttu-id="0f0d5-138">Cifras clave</span><span class="sxs-lookup"><span data-stu-id="0f0d5-138">Key figures</span></span>|  
|<span data-ttu-id="0f0d5-139">TIM</span><span class="sxs-lookup"><span data-stu-id="0f0d5-139">TIM</span></span>|<span data-ttu-id="0f0d5-140">Características de tiempo</span><span class="sxs-lookup"><span data-stu-id="0f0d5-140">Time characteristics</span></span>|  
  
 <span data-ttu-id="0f0d5-141">**IObject - Buscar**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-141">**Iobject - Search**</span></span>  
 <span data-ttu-id="0f0d5-142">Permite asociar un InfoObject existente a la columna de flujo de datos de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-142">Associate an existing InfoObject to the data flow column for the current row.</span></span> <span data-ttu-id="0f0d5-143">Para efectuar este tipo de asociación, haga clic en **Buscar** y, a continuación use el cuadro de diálogo **Buscar InfoObject** para seleccionar el InfoObject existente.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-143">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="0f0d5-144">Para obtener más información sobre este cuadro de diálogo, vea [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="0f0d5-144">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="0f0d5-145">Después de seleccionar un InfoObject existente, el componente rellena las columnas **InfoObject** y **Tipo** con los valores seleccionados.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-145">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="0f0d5-146">**IObject - Nuevo**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-146">**Iobject - New**</span></span>  
 <span data-ttu-id="0f0d5-147">Permite crear un InfoObject nuevo y asociarlo a la columna de flujo de datos de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-147">Create a new InfoObject and associate this new InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="0f0d5-148">Para crear el InfoObject nuevo, haga clic en **Nuevo**y, a continuación, use el cuadro de diálogo **Crear nuevo InfoObject** para crear el InfoObject.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-148">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="0f0d5-149">Para obtener más información sobre este cuadro de diálogo, vea [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="0f0d5-149">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="0f0d5-150">Después haber creado un InfoObject nuevo, el componente rellena las columnas **InfoObject** y **Tipo** con los valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-150">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="0f0d5-151">**IObject - Quitar**</span><span class="sxs-lookup"><span data-stu-id="0f0d5-151">**Iobject - Remove**</span></span>  
 <span data-ttu-id="0f0d5-152">Permite quitar la asociación entre el InfoObject y la columna de flujo de datos de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-152">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="0f0d5-153">Para quitar esta asociación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="0f0d5-153">To remove this association, click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f0d5-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f0d5-154">See Also</span></span>  
 [<span data-ttu-id="0f0d5-155">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="0f0d5-155">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
