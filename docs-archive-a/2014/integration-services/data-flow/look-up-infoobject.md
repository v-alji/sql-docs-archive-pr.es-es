---
title: Buscar InfoObject | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7f4c132-a5ec-49d8-a964-45775432731f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1616b4fcb368afc9e3f1157a3fc2511d4a7e8cce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745921"
---
# <a name="look-up-infoobject"></a><span data-ttu-id="dec28-102">Buscar InfoObject</span><span class="sxs-lookup"><span data-stu-id="dec28-102">Look Up InfoObject</span></span>
  <span data-ttu-id="dec28-103">Use el cuadro de diálogo **Buscar InfoObject** para buscar un InfoObject que se haya definido en el sistema de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="dec28-103">Use the **Look Up InfoObject** dialog box to look up an InfoObject that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="dec28-104">Cuando aparezca la lista de InfoObjects disponibles, seleccione el InfoObject que desee y el destino de SAP BW rellenará las opciones asociadas a los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="dec28-104">When the list of available InfoObjects appears, select the InfoObject that you want, and the SAP BW destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="dec28-105">El destino de SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW usa el cuadro de diálogo **Buscar InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="dec28-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up InfoObject** dialog box.</span></span> <span data-ttu-id="dec28-106">Para más información acerca del destino de SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="dec28-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dec28-107">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="dec28-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="dec28-108">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="dec28-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="dec28-109">**Para abrir el cuadro de diálogo Buscar InfoObject**</span><span class="sxs-lookup"><span data-stu-id="dec28-109">**To open the Look Up InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="dec28-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="dec28-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="dec28-111">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="dec28-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="dec28-112">En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="dec28-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="dec28-113">En la página **Administrador de conexiones** , en el cuadro del grupo **Crear objetos de SAP BW** , seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dec28-113">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select one of the following options:</span></span>  
  
    1.  <span data-ttu-id="dec28-114">Seleccione **InfoCube**.</span><span class="sxs-lookup"><span data-stu-id="dec28-114">Select **InfoCube**.</span></span> <span data-ttu-id="dec28-115">A continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="dec28-115">Then, click **Create**.</span></span> <span data-ttu-id="dec28-116">En el cuadro de diálogo **Crear InfoCube para datos de transacción** , haga clic en **Buscar** en la columna **IObject** para una de las filas de la lista.</span><span class="sxs-lookup"><span data-stu-id="dec28-116">In the **Create InfoCube for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="dec28-117">Cada fila representa una columna en el flujo de datos del paquete.</span><span class="sxs-lookup"><span data-stu-id="dec28-117">Each row represents a column in the data flow of the package.</span></span>  
  
    2.  <span data-ttu-id="dec28-118">Seleccione **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="dec28-118">Select **InfoSource**.</span></span> <span data-ttu-id="dec28-119">A continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="dec28-119">Then click **Create**.</span></span> <span data-ttu-id="dec28-120">En el cuadro de diálogo **Crear InfoSource** , seleccione **Datos de transacción**.</span><span class="sxs-lookup"><span data-stu-id="dec28-120">In the **Create InfoSource** dialog box, select **Transaction data**.</span></span> <span data-ttu-id="dec28-121">En el cuadro de diálogo **Crear InfoSource para datos de transacción** , haga clic en **Buscar** en la columna **IObject** para una de las filas de la lista.</span><span class="sxs-lookup"><span data-stu-id="dec28-121">In the **Create InfoSource for Transaction Data** dialog box, click **Search** in the **IObject** column for one of the rows in the list.</span></span> <span data-ttu-id="dec28-122">Cada fila representa una columna en el flujo de datos del paquete.</span><span class="sxs-lookup"><span data-stu-id="dec28-122">Each row represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="dec28-123">Seleccione **InfoSource**.</span><span class="sxs-lookup"><span data-stu-id="dec28-123">Select **InfoSource**.</span></span> <span data-ttu-id="dec28-124">A continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="dec28-124">Then click **Create**.</span></span> <span data-ttu-id="dec28-125">En el cuadro de diálogo **Crear InfoSource** , seleccione **Datos maestros**.</span><span class="sxs-lookup"><span data-stu-id="dec28-125">In the **Create InfoSource** dialog box, select **Master data**.</span></span> <span data-ttu-id="dec28-126">En el cuadro de diálogo **Crear InfoSource para datos maestros** , haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="dec28-126">In the **Create InfoSource for Master Data** dialog box, click **Look up**.</span></span>  
  
 <span data-ttu-id="dec28-127">También puede abrir el cuadro de diálogo **Buscar InfoObject** si hace clic en **Agregar** en la sección **Atributos** del cuadro de diálogo **Crear nuevo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="dec28-127">You can also open the **Look Up InfoObject** dialog box by clicking **Add** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="dec28-128">Opciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="dec28-128">Lookup Options</span></span>  
 <span data-ttu-id="dec28-129">En los cuadros de texto de los campos de búsqueda, puede filtrar los resultados mediante el carácter comodín de asterisco (\*) o mediante una cadena parcial en combinación con el carácter comodín de asterisco.</span><span class="sxs-lookup"><span data-stu-id="dec28-129">In the lookup field text boxes, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="dec28-130">Sin embargo, si deja de un campo de búsqueda vacío, el proceso de búsqueda solamente se corresponderá con cadenas vacías en ese campo.</span><span class="sxs-lookup"><span data-stu-id="dec28-130">However, if you leave a lookup field empty, the lookup process will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="dec28-131">**Características**</span><span class="sxs-lookup"><span data-stu-id="dec28-131">**Characteristics**</span></span>  
 <span data-ttu-id="dec28-132">Permite buscar InfoObjects que representan características.</span><span class="sxs-lookup"><span data-stu-id="dec28-132">Look up InfoObjects that represent characteristics.</span></span>  
  
 <span data-ttu-id="dec28-133">**Unidades**</span><span class="sxs-lookup"><span data-stu-id="dec28-133">**Units**</span></span>  
 <span data-ttu-id="dec28-134">Permite buscar InfoObjects que representan unidades.</span><span class="sxs-lookup"><span data-stu-id="dec28-134">Look up InfoObjects that represent units.</span></span>  
  
 <span data-ttu-id="dec28-135">**Cifras clave**</span><span class="sxs-lookup"><span data-stu-id="dec28-135">**Key figures**</span></span>  
 <span data-ttu-id="dec28-136">Permite buscar InfoObjects que representan cifras clave.</span><span class="sxs-lookup"><span data-stu-id="dec28-136">Look up InfoObjects that represent key figures.</span></span>  
  
 <span data-ttu-id="dec28-137">**Características de tiempo**</span><span class="sxs-lookup"><span data-stu-id="dec28-137">**Time characteristics**</span></span>  
 <span data-ttu-id="dec28-138">Permite buscar InfoObjects que representan características de tiempo.</span><span class="sxs-lookup"><span data-stu-id="dec28-138">Look up InfoObjects that represent time characteristics.</span></span>  
  
 <span data-ttu-id="dec28-139">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dec28-139">**Name**</span></span>  
 <span data-ttu-id="dec28-140">Permite escribir el nombre del InfoObject que desea buscar o un nombre parcial con el carácter comodín de asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="dec28-140">Enter the name of the InfoObject that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="dec28-141">O bien, use el carácter comodín de asterisco por sí solo para incluir todos los InfoObjects.</span><span class="sxs-lookup"><span data-stu-id="dec28-141">Or, use the asterisk wildcard character alone to include all InfoObjects.</span></span>  
  
 <span data-ttu-id="dec28-142">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dec28-142">**Description**</span></span>  
 <span data-ttu-id="dec28-143">Escriba la descripción o una descripción parcial con el carácter comodín de asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="dec28-143">Enter the description, or a partial description with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="dec28-144">O bien, use el carácter comodín de asterisco por sí solo para incluir todos los InfoObjects independientemente de la descripción.</span><span class="sxs-lookup"><span data-stu-id="dec28-144">Or, use the asterisk wildcard character alone to include all InfoObjects regardless of description.</span></span>  
  
 <span data-ttu-id="dec28-145">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="dec28-145">**Look up**</span></span>  
 <span data-ttu-id="dec28-146">Busque InfoObjects coincidentes que se hayan definido en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="dec28-146">Look up matching InfoObjects that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="dec28-147">Buscar resultados</span><span class="sxs-lookup"><span data-stu-id="dec28-147">Lookup Results</span></span>  
 <span data-ttu-id="dec28-148">Después de hacer clic en el botón Buscar, aparece una lista de InfoObjects del sistema SAP Netweaver BW en una tabla con los siguientes encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="dec28-148">After you click the Look up button, a list of the InfoObjects in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="dec28-149">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="dec28-149">**InfoObject**</span></span>  
 <span data-ttu-id="dec28-150">Permite mostrar el nombre del InfoObject que se haya definido en el sistema de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="dec28-150">Displays the name of the InfoObject that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="dec28-151">**Texto (corto)**</span><span class="sxs-lookup"><span data-stu-id="dec28-151">**Text (short)**</span></span>  
 <span data-ttu-id="dec28-152">Permite mostrar el texto breve que está asociado al InfoObject.</span><span class="sxs-lookup"><span data-stu-id="dec28-152">Displays the short text that is associated with the InfoObject.</span></span>  
  
 <span data-ttu-id="dec28-153">Cuando aparezca la lista de InfoObjects disponibles, seleccione el InfoObject que desee y el destino rellenará las opciones asociadas a los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="dec28-153">When the list of available InfoObjects appears, select the InfoObject that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec28-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dec28-154">See Also</span></span>  
 <span data-ttu-id="dec28-155">[Crear InfoCube para datos de transacción](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="dec28-155">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="dec28-156">[Crear InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="dec28-156">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="dec28-157">[Crear InfoSource para datos de transacción](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="dec28-157">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="dec28-158">[Crear InfoSource para datos maestros](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="dec28-158">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 <span data-ttu-id="dec28-159">[Crear nuevo InfoObject](create-new-infoobject.md) </span><span class="sxs-lookup"><span data-stu-id="dec28-159">[Create New InfoObject](create-new-infoobject.md) </span></span>  
 <span data-ttu-id="dec28-160">[Editor de destino de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="dec28-160">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="dec28-161">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="dec28-161">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
