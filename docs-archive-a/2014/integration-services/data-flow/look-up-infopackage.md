---
title: Buscar Infopackage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7c0cb7a4-cd07-44cc-85cb-eb1ad91f85fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e45477e8faeed07faa114850e10a3bc4bbcf170
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745920"
---
# <a name="look-up-infopackage"></a><span data-ttu-id="8af21-102">Buscar InfoPackage</span><span class="sxs-lookup"><span data-stu-id="8af21-102">Look Up InfoPackage</span></span>
  <span data-ttu-id="8af21-103">Use el cuadro de diálogo **Buscar InfoPackage** para buscar un InfoPackage que se haya definido en el sistema de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8af21-103">Use the **Look Up InfoPackage** dialog box to look up an InfoPackage that is defined in the SAP Netweaver BW system.</span></span> <span data-ttu-id="8af21-104">Cuando aparezca la lista de InfoPackages, seleccione el InfoPackage que desee y el destino rellenará las opciones asociadas a los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="8af21-104">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
 <span data-ttu-id="8af21-105">El destino de SAP BW de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW usa el cuadro de diálogo **Buscar cadena de procesos** .</span><span class="sxs-lookup"><span data-stu-id="8af21-105">The SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW uses the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="8af21-106">Para más información acerca del destino de SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="8af21-106">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8af21-107">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8af21-107">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="8af21-108">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="8af21-108">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="8af21-109">**Para abrir el cuadro de diálogo Buscar InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="8af21-109">**To open the Look Up InfoPackage dialog box**</span></span>  
  
1.  <span data-ttu-id="8af21-110">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8af21-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="8af21-111">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="8af21-111">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="8af21-112">En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="8af21-112">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="8af21-113">En la página **Administrador de conexiones** , en el cuadro del grupo **InfoPackage/InfoSource** , haga clic en **Buscar** para mostrar el cuadro de diálogo **Buscar InfoPackage** .</span><span class="sxs-lookup"><span data-stu-id="8af21-113">On the **Connection Manager** page, in the **InfoPackage/InfoSource** group box, click **Look up** to display the **Look Up InfoPackage** dialog box.</span></span>  
  
## <a name="lookup-options"></a><span data-ttu-id="8af21-114">Opciones de búsqueda</span><span class="sxs-lookup"><span data-stu-id="8af21-114">Lookup Options</span></span>  
 <span data-ttu-id="8af21-115">En los campos de búsqueda, puede filtrar los resultados mediante el carácter comodín de asterisco (\*) o mediante una cadena parcial en combinación con el carácter comodín de asterisco.</span><span class="sxs-lookup"><span data-stu-id="8af21-115">In the lookup fields, you can filter results by using the asterisk wildcard character (\*), or by using a partial string in combination with the asterisk wildcard character.</span></span> <span data-ttu-id="8af21-116">Sin embargo, si deja un campo de búsqueda vacío, la operación de búsqueda solamente se corresponderá con cadenas vacías en ese campo.</span><span class="sxs-lookup"><span data-stu-id="8af21-116">However, if you leave a lookup field empty, the lookup operation will only match empty strings in that field.</span></span>  
  
 <span data-ttu-id="8af21-117">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="8af21-117">**InfoPackage**</span></span>  
 <span data-ttu-id="8af21-118">Escriba el nombre del InfoPackage que desea buscar o un nombre parcial con el carácter comodín de asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="8af21-118">Enter the name of the InfoPackage that you want to look up, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="8af21-119">O bien, use el carácter comodín de asterisco por sí solo para incluir todos los InfoPackages.</span><span class="sxs-lookup"><span data-stu-id="8af21-119">Or, use the asterisk wildcard character alone to include all InfoPackages.</span></span>  
  
 <span data-ttu-id="8af21-120">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="8af21-120">**InfoSource**</span></span>  
 <span data-ttu-id="8af21-121">Escriba el nombre del InfoSource que desea buscar o un nombre parcial con el carácter comodín de asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="8af21-121">Enter the name of the InfoSource, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="8af21-122">O bien, use el carácter comodín de asterisco por sí solo para incluir todos los InfoPackages independientemente del InfoSource.</span><span class="sxs-lookup"><span data-stu-id="8af21-122">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of InfoSource.</span></span>  
  
 <span data-ttu-id="8af21-123">**Sistema de origen**</span><span class="sxs-lookup"><span data-stu-id="8af21-123">**Source system**</span></span>  
 <span data-ttu-id="8af21-124">Escriba el nombre del sistema de origen o un nombre parcial con el carácter comodín de asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="8af21-124">Enter the name of the source system, or a partial name with the asterisk wildcard character (\*).</span></span> <span data-ttu-id="8af21-125">O bien, use el carácter comodín de asterisco por sí solo para incluir todos los InfoPackages independientemente de los sistemas de origen.</span><span class="sxs-lookup"><span data-stu-id="8af21-125">Or, use the asterisk wildcard character alone to include all InfoPackages regardless of source systems.</span></span>  
  
 <span data-ttu-id="8af21-126">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="8af21-126">**Look up**</span></span>  
 <span data-ttu-id="8af21-127">Permite buscar InfoPackages coincidentes que se hayan definido en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8af21-127">Look up matching InfoPackages that are defined in the SAP Netweaver BW system.</span></span>  
  
## <a name="lookup-results"></a><span data-ttu-id="8af21-128">Buscar resultados</span><span class="sxs-lookup"><span data-stu-id="8af21-128">Lookup Results</span></span>  
 <span data-ttu-id="8af21-129">Después de hacer clic en el botón Buscar, aparece una lista de InfoPackages del sistema SAP Netweaver BW en una tabla con los siguientes encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="8af21-129">After you click the Look up button, a list of the InfoPackages in the SAP Netweaver BW system appears in a table with the following column headings.</span></span>  
  
 <span data-ttu-id="8af21-130">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="8af21-130">**InfoPackage**</span></span>  
 <span data-ttu-id="8af21-131">Permite mostrar el nombre del InfoPackage que se haya definido en el sistema de SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="8af21-131">Displays the name of the InfoPackage that is defined in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="8af21-132">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8af21-132">**Type**</span></span>  
 <span data-ttu-id="8af21-133">Permite mostrar el tipo de InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="8af21-133">Displays the type of the InfoPackage.</span></span> <span data-ttu-id="8af21-134">En la siguiente tabla se muestran los posibles valores para el tipo.</span><span class="sxs-lookup"><span data-stu-id="8af21-134">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="8af21-135">Value</span><span class="sxs-lookup"><span data-stu-id="8af21-135">Value</span></span>|<span data-ttu-id="8af21-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="8af21-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8af21-137">de transacciones</span><span class="sxs-lookup"><span data-stu-id="8af21-137">Trans.</span></span>|<span data-ttu-id="8af21-138">Datos de transacción.</span><span class="sxs-lookup"><span data-stu-id="8af21-138">Transaction data.</span></span>|  
|<span data-ttu-id="8af21-139">Atr.</span><span class="sxs-lookup"><span data-stu-id="8af21-139">Attr.</span></span>|<span data-ttu-id="8af21-140">Datos de atributo.</span><span class="sxs-lookup"><span data-stu-id="8af21-140">Attribute data.</span></span>|  
|<span data-ttu-id="8af21-141">Textos</span><span class="sxs-lookup"><span data-stu-id="8af21-141">Texts</span></span>|<span data-ttu-id="8af21-142">Textos.</span><span class="sxs-lookup"><span data-stu-id="8af21-142">Texts.</span></span>|  
  
 <span data-ttu-id="8af21-143">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8af21-143">**Description**</span></span>  
 <span data-ttu-id="8af21-144">Permite mostrar la descripción del InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="8af21-144">Displays the description of the InfoPackage.</span></span>  
  
 <span data-ttu-id="8af21-145">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="8af21-145">**InfoSource**</span></span>  
 <span data-ttu-id="8af21-146">Permite mostrar el nombre del InfoSource, en su caso, que está asociado al InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="8af21-146">Displays the name of the InfoSource, if any, that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="8af21-147">**Source System**</span><span class="sxs-lookup"><span data-stu-id="8af21-147">**Source System**</span></span>  
 <span data-ttu-id="8af21-148">Permite mostrar el nombre del sistema de origen.</span><span class="sxs-lookup"><span data-stu-id="8af21-148">Displays the name of the source system.</span></span>  
  
 <span data-ttu-id="8af21-149">Cuando aparezca la lista de InfoPackages, seleccione el InfoPackage que desee y el destino rellenará las opciones asociadas a los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="8af21-149">When the list of InfoPackages appears, select the InfoPackage that you want, and the destination will populate the associated options with the required values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af21-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8af21-150">See Also</span></span>  
 <span data-ttu-id="8af21-151">[Editor de destino de SAP BW &#40;página Administrador de conexiones&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="8af21-151">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="8af21-152">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="8af21-152">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
