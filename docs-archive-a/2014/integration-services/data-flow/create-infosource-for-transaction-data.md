---
title: Crear InfoSource para datos de transacción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab5f23e2-cd4e-4507-83d9-ac5ef721c171
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e3a60bb93da17e79087982473e92c35fa0856d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744236"
---
# <a name="create-infosource-for-transaction-data"></a><span data-ttu-id="220b1-102">Crear Infosource para datos de transacción</span><span class="sxs-lookup"><span data-stu-id="220b1-102">Create InfoSource for Transaction Data</span></span>
  <span data-ttu-id="220b1-103">Use el cuadro de diálogo **Crear InfoSource para los datos de transacción** para crear un InfoSource nuevo para los datos de transacción en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="220b1-103">Use the **Create InfoSource for Transaction Data** dialog box to create a new InfoSource for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="220b1-104">Puede abrir el cuadro de diálogo **Crear InfoSource para los datos de transacción** desde la página **Administrador de conexiones** del **Editor de destino de SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="220b1-104">You can open the **Create InfoSource for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="220b1-105">Para más información acerca del destino de SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="220b1-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="220b1-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="220b1-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="220b1-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="220b1-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="220b1-108">**Para abrir el cuadro de diálogo Crear InfoSource para los datos de transacción**</span><span class="sxs-lookup"><span data-stu-id="220b1-108">**To open the Create InfoSource for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="220b1-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="220b1-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="220b1-110">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="220b1-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="220b1-111">En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="220b1-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="220b1-112">En la página **Administrador de conexiones** , en el cuadro del grupo **Crear objetos de SAP BW** , seleccione **InfoSource**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="220b1-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="220b1-113">En el cuadro de diálogo **Crear InfoSource** , seleccione **Datos transaccionales**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="220b1-113">In the **Create InfoSource** dialog box, select **Transaction data**, and then click **OK**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="220b1-114">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="220b1-114">General Options</span></span>  
 <span data-ttu-id="220b1-115">**Nombre de InfoSource**</span><span class="sxs-lookup"><span data-stu-id="220b1-115">**InfoSource name**</span></span>  
 <span data-ttu-id="220b1-116">Permite escribir un nombre para el nuevo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="220b1-116">Enter a name for the new InfoSource.</span></span>  
  
 <span data-ttu-id="220b1-117">**Descripción breve**</span><span class="sxs-lookup"><span data-stu-id="220b1-117">**Short description**</span></span>  
 <span data-ttu-id="220b1-118">Permite escribir una descripción breve para el nuevo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="220b1-118">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="220b1-119">**Descripción larga**</span><span class="sxs-lookup"><span data-stu-id="220b1-119">**Long description**</span></span>  
 <span data-ttu-id="220b1-120">Permite escribir una descripción larga para el nuevo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="220b1-120">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="220b1-121">**Sistema de origen**</span><span class="sxs-lookup"><span data-stu-id="220b1-121">**Source system**</span></span>  
 <span data-ttu-id="220b1-122">Permite seleccionar el sistema de origen asociado al InfoSource.</span><span class="sxs-lookup"><span data-stu-id="220b1-122">Select the source system associated with the InfoSource.</span></span>  
  
 <span data-ttu-id="220b1-123">**Guardar y activar**</span><span class="sxs-lookup"><span data-stu-id="220b1-123">**Save & Activate**</span></span>  
 <span data-ttu-id="220b1-124">Permite guardar y activar el nuevo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="220b1-124">Save and activate the new InfoSource.</span></span>  
  
## <a name="infosource-transfer-structure-options"></a><span data-ttu-id="220b1-125">Opciones de la estructura de transferencia de InfoSource</span><span class="sxs-lookup"><span data-stu-id="220b1-125">InfoSource Transfer Structure Options</span></span>  
 <span data-ttu-id="220b1-126">La estructura de transferencia de InfoSource permite asociar columnas del flujo de datos a InfoSources.</span><span class="sxs-lookup"><span data-stu-id="220b1-126">The InfoSource transfer structure lets you associate data flow columns to InfoSources.</span></span>  
  
 <span data-ttu-id="220b1-127">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="220b1-127">**PipelineElement**</span></span>  
 <span data-ttu-id="220b1-128">Permite mostrar la columna en la salida del flujo de datos que está conectada al destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="220b1-128">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="220b1-129">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="220b1-129">**PipelineDataType**</span></span>  
 <span data-ttu-id="220b1-130">Muestra el tipo de datos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] de la columna del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="220b1-130">Displays the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type of the data flow column.</span></span>  
  
 <span data-ttu-id="220b1-131">**IObject - Buscar**</span><span class="sxs-lookup"><span data-stu-id="220b1-131">**Iobject - Search**</span></span>  
 <span data-ttu-id="220b1-132">Permite asociar un InfoObject existente a la columna de flujo de datos de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="220b1-132">Associate an existing InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="220b1-133">Para efectuar este tipo de asociación, haga clic en **Buscar** y, a continuación use el cuadro de diálogo **Buscar InfoObject** para seleccionar el InfoObject existente.</span><span class="sxs-lookup"><span data-stu-id="220b1-133">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="220b1-134">Para obtener más información sobre este cuadro de diálogo, vea [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="220b1-134">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="220b1-135">Después de seleccionar un InfoObject existente, el componente rellena las columnas **InfoObject** y **Tipo** con los valores seleccionados.</span><span class="sxs-lookup"><span data-stu-id="220b1-135">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="220b1-136">**IObject - Nuevo**</span><span class="sxs-lookup"><span data-stu-id="220b1-136">**Iobject - New**</span></span>  
 <span data-ttu-id="220b1-137">Permite crear un InfoObject nuevo y asociarlo a la columna de flujo de datos de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="220b1-137">Create a new InfoObject and associate this new InfoObect to the data flow column in the current row.</span></span> <span data-ttu-id="220b1-138">Para crear el InfoObject nuevo, haga clic en **Nuevo**y, a continuación, use el cuadro de diálogo **Crear nuevo InfoObject** para crear el InfoObject.</span><span class="sxs-lookup"><span data-stu-id="220b1-138">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="220b1-139">Para obtener más información sobre este cuadro de diálogo, vea [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="220b1-139">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="220b1-140">Después haber creado un InfoObject nuevo, el componente rellena las columnas **InfoObject** y **Tipo** con los valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="220b1-140">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="220b1-141">**IObject - Quitar**</span><span class="sxs-lookup"><span data-stu-id="220b1-141">**Iobject - Remove**</span></span>  
 <span data-ttu-id="220b1-142">Permite quitar la asociación entre el InfoObject y la columna de flujo de datos de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="220b1-142">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="220b1-143">Para quitar esta asociación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="220b1-143">To remove this association, click **Remove**.</span></span>  
  
 <span data-ttu-id="220b1-144">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="220b1-144">**InfoObject**</span></span>  
 <span data-ttu-id="220b1-145">Permite mostrar el nombre del InfoObject que está asociado a la columna del flujo datos.</span><span class="sxs-lookup"><span data-stu-id="220b1-145">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="220b1-146">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="220b1-146">**Type**</span></span>  
 <span data-ttu-id="220b1-147">Permite mostrar el tipo del InfoObject que está asociado a la columna del flujo datos.</span><span class="sxs-lookup"><span data-stu-id="220b1-147">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="220b1-148">En la siguiente tabla se muestran los posibles valores para el tipo.</span><span class="sxs-lookup"><span data-stu-id="220b1-148">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="220b1-149">Value</span><span class="sxs-lookup"><span data-stu-id="220b1-149">Value</span></span>|<span data-ttu-id="220b1-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="220b1-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="220b1-151">CHA</span><span class="sxs-lookup"><span data-stu-id="220b1-151">CHA</span></span>|<span data-ttu-id="220b1-152">Características</span><span class="sxs-lookup"><span data-stu-id="220b1-152">Characteristics</span></span>|  
|<span data-ttu-id="220b1-153">UNI</span><span class="sxs-lookup"><span data-stu-id="220b1-153">UNI</span></span>|<span data-ttu-id="220b1-154">Unidades</span><span class="sxs-lookup"><span data-stu-id="220b1-154">Units</span></span>|  
|<span data-ttu-id="220b1-155">KYF</span><span class="sxs-lookup"><span data-stu-id="220b1-155">KYF</span></span>|<span data-ttu-id="220b1-156">Cifras clave</span><span class="sxs-lookup"><span data-stu-id="220b1-156">Key figures</span></span>|  
|<span data-ttu-id="220b1-157">TIM</span><span class="sxs-lookup"><span data-stu-id="220b1-157">TIM</span></span>|<span data-ttu-id="220b1-158">Características de tiempo</span><span class="sxs-lookup"><span data-stu-id="220b1-158">Time characteristics</span></span>|  
  
 <span data-ttu-id="220b1-159">**Campo de unidad**</span><span class="sxs-lookup"><span data-stu-id="220b1-159">**Unit Field**</span></span>  
 <span data-ttu-id="220b1-160">Permite especificar las unidades que va a usar el InfoObject.</span><span class="sxs-lookup"><span data-stu-id="220b1-160">Specify the units that the InfoObject will use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="220b1-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="220b1-161">See Also</span></span>  
 <span data-ttu-id="220b1-162">[Crear InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="220b1-162">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="220b1-163">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="220b1-163">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
