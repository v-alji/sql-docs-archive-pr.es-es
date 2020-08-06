---
title: Conectar una aplicación de servicio PowerPivot a una aplicación Web de SharePoint en administración central | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5da8e29-7ffd-44e7-bf61-344fa5bea8ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5fc6dcde4cc2d18c3650adbab0ec71ef5c6265cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675581"
---
# <a name="connect-a-powerpivot-service-application-to-a-sharepoint-web-application-in-central-administration"></a><span data-ttu-id="9202e-102">Conectar una aplicación de servicio PowerPivot a una aplicación Web de SharePoint en administración central</span><span class="sxs-lookup"><span data-stu-id="9202e-102">Connect a PowerPivot Service Application to a SharePoint Web Application in Central Administration</span></span>
  <span data-ttu-id="9202e-103">Una aplicación de servicio PowerPivot puede ser utilizada por cualquier número de aplicaciones web de SharePoint de la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="9202e-103">A PowerPivot service application can be used by any number of SharePoint Web applications in the farm.</span></span> <span data-ttu-id="9202e-104">Para hacer que una aplicación de servicio PowerPivot esté disponible, agréguela a una lista de asociaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="9202e-104">To make a PowerPivot service application available, you add it to a service association list.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9202e-105">Debe haber una aplicación de servicio PowerPivot en el grupo predeterminado para asegurarse de que el Panel de administración de PowerPivot funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="9202e-105">You must have one PowerPivot service application in the default group to ensure that PowerPivot Management Dashboard works properly.</span></span> <span data-ttu-id="9202e-106">No agregue más de una aplicación de servicio PowerPivot al grupo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9202e-106">Do not add more than one PowerPivot service application to the default group.</span></span> <span data-ttu-id="9202e-107">Agregar varias entradas del mismo tipo de aplicación de servicio no se admite y podría producir errores.</span><span class="sxs-lookup"><span data-stu-id="9202e-107">Adding multiple entries of the same service application type is not a supported configuration and might cause errors.</span></span> <span data-ttu-id="9202e-108">Si va a crear aplicaciones de servicio adicionales, agréguelas a listas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9202e-108">If you are creating additional service applications, add them to custom lists.</span></span>  
  
 <span data-ttu-id="9202e-109">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="9202e-109">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="9202e-110">Agregar la aplicación de servicios PowerPivot al grupo predeterminado</span><span class="sxs-lookup"><span data-stu-id="9202e-110">Add PowerPivot Services Application to the Default Group</span></span>](#default)  
  
 [<span data-ttu-id="9202e-111">Agregar la aplicación de servicios PowerPivot a una lista de asociaciones de servicio personalizada</span><span class="sxs-lookup"><span data-stu-id="9202e-111">Add PowerPivot Services Application a Custom Service Association List</span></span>](#custom)  
  
##  <a name="add-powerpivot-services-application-to-the-default-group"></a><a name="default"></a><span data-ttu-id="9202e-112">Agregar la aplicación de servicios PowerPivot al grupo predeterminado</span><span class="sxs-lookup"><span data-stu-id="9202e-112">Add PowerPivot Services Application to the Default Group</span></span>  
 <span data-ttu-id="9202e-113">Una lista de asociaciones de servicio es una lista de servicios compartidos que proporcionan recursos a otras aplicaciones web de SharePoint en la granja.</span><span class="sxs-lookup"><span data-stu-id="9202e-113">A service association list is a list of shared services that provide resources to other SharePoint Web applications in the farm.</span></span> <span data-ttu-id="9202e-114">Hay un grupo predeterminado de asociaciones del servicio para la granja.</span><span class="sxs-lookup"><span data-stu-id="9202e-114">There is one default group of service associations for the farm.</span></span>  
  
 <span data-ttu-id="9202e-115">Para estar en la lista, una aplicación de servicio PowerPivot puede agregarse al crear la aplicación o después siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9202e-115">To be on the list, a PowerPivot service application can either be added when you create the application or afterwards by using the following steps.</span></span>  
  
1.  <span data-ttu-id="9202e-116">En Administración central, en **Administración de aplicaciones**, haga clic en **Configurar las asociaciones de aplicación de servicio**.</span><span class="sxs-lookup"><span data-stu-id="9202e-116">In Central Administration, in **Application Management**, click **Configure service application associations**.</span></span>  
  
2.  <span data-ttu-id="9202e-117">En Grupo de proxy de aplicación, haga clic en **predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="9202e-117">In Application Proxy Group, click **default**.</span></span>  
  
3.  <span data-ttu-id="9202e-118">Active la casilla situada al lado de la aplicación de servicio PowerPivot (lo que se indica por el nombre de tipo `PowerPivot Service Application Proxy`).</span><span class="sxs-lookup"><span data-stu-id="9202e-118">Select the checkbox next to the PowerPivot service application (indicated by type name `PowerPivot Service Application Proxy`).</span></span> <span data-ttu-id="9202e-119">Si tiene más de una aplicación de servicio PowerPivot, simplemente elija una.</span><span class="sxs-lookup"><span data-stu-id="9202e-119">If you have more than one PowerPivot service application, choose just one.</span></span>  
  
4.  <span data-ttu-id="9202e-120">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9202e-120">Click **OK**.</span></span>  
  
##  <a name="add-powerpivot-services-application-a-custom-service-association-list"></a><a name="custom"></a><span data-ttu-id="9202e-121">Agregar la aplicación de servicios PowerPivot a una lista de asociaciones de servicio personalizadas</span><span class="sxs-lookup"><span data-stu-id="9202e-121">Add PowerPivot Services Application a Custom Service Association List</span></span>  
 <span data-ttu-id="9202e-122">El grupo personalizado puede reemplazar a una lista predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9202e-122">The default group can be replaced by a custom list.</span></span> <span data-ttu-id="9202e-123">Una lista personalizada se crea específicamente para una sola aplicación web de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9202e-123">A custom list is created specifically for a single SharePoint Web application.</span></span> <span data-ttu-id="9202e-124">Invalida el grupo predeterminado y lo reemplaza solo con las asociaciones de servicio que un administrador o servicio de la granja especifique.</span><span class="sxs-lookup"><span data-stu-id="9202e-124">It overrides the default group and replaces it with only those service associations that a farm or service administrator specifies.</span></span> <span data-ttu-id="9202e-125">Si creó varias aplicaciones de servicio PowerPivot, debe utilizar una lista personalizada para especificar cuál utilizar.</span><span class="sxs-lookup"><span data-stu-id="9202e-125">If you created multiple PowerPivot service applications, you must use a custom list to specify which one to use.</span></span> <span data-ttu-id="9202e-126">Otras aplicaciones web no pueden reutilizar una lista personalizada.</span><span class="sxs-lookup"><span data-stu-id="9202e-126">A custom list cannot be reused by other Web applications.</span></span> <span data-ttu-id="9202e-127">Solo se aplica a la aplicación web para la que se creó.</span><span class="sxs-lookup"><span data-stu-id="9202e-127">It applies only to the Web application for which it was created.</span></span>  
  
1.  <span data-ttu-id="9202e-128">En Administración central, en **Administración de aplicaciones**, haga clic en **Administrar aplicaciones web**.</span><span class="sxs-lookup"><span data-stu-id="9202e-128">In Central Administration, in **Application Management**, click **Manage web applications**.</span></span>  
  
2.  <span data-ttu-id="9202e-129">Seleccione la aplicación (por ejemplo, SharePoint -80).</span><span class="sxs-lookup"><span data-stu-id="9202e-129">Select the application (for example, SharePoint -80).</span></span>  
  
3.  <span data-ttu-id="9202e-130">En Aplicaciones web, en Administrar, haga clic en **Conexiones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="9202e-130">In Web Applications, in Manage, click **Service Connections**.</span></span>  
  
4.  <span data-ttu-id="9202e-131">En **Editar el siguiente grupo de conexiones**, seleccione **[personalizado]**.</span><span class="sxs-lookup"><span data-stu-id="9202e-131">In **Edit the following group of connections**, select **[custom]**.</span></span>  
  
5.  <span data-ttu-id="9202e-132">Active la casilla situada al lado de cada conexión de aplicación de servicio que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="9202e-132">Select the checkbox next to each service application connection you want to use.</span></span> <span data-ttu-id="9202e-133">Si tiene varias aplicaciones de servicio PowerPivot (que se indican con el tipo establecido en `PowerPivot Service Application Proxy`), asegúrese de elegir solo una.</span><span class="sxs-lookup"><span data-stu-id="9202e-133">If you have multiple PowerPivot service applications (indicated by Type set to `PowerPivot Service Application Proxy`), be sure to choose only one.</span></span>  
  
6.  <span data-ttu-id="9202e-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9202e-134">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9202e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9202e-135">See Also</span></span>  
 <span data-ttu-id="9202e-136">[Crear y configurar una aplicación de servicio PowerPivot en administración central](create-and-configure-power-pivot-service-application-in-ca.md) </span><span class="sxs-lookup"><span data-stu-id="9202e-136">[Create and Configure a PowerPivot Service Application in Central Administration](create-and-configure-power-pivot-service-application-in-ca.md) </span></span>  
 [<span data-ttu-id="9202e-137">PowerPivot para SharePoint de &#40;de configuración inicial&#41;</span><span class="sxs-lookup"><span data-stu-id="9202e-137">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
  
