---
title: Cuadro de diálogo Configurar | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.SSIS.SSMS.ISPROJECTPROP.PARAMETERS.F1
- SQL12.SSIS.SSMS.ISPROJECTPROP.REFERENCES.F1
- sql12.dts.designer.configure.f1
ms.assetid: 10183c8d-b1be-420f-972a-96ea97d4f4d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857baf3421f2744144e10b0df0b770538f533192
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674284"
---
# <a name="configure-dialog-box"></a><span data-ttu-id="03e2d-102">Cuadro de diálogo Configurar</span><span class="sxs-lookup"><span data-stu-id="03e2d-102">Configure Dialog Box</span></span>
  <span data-ttu-id="03e2d-103">Utilice el cuadro de diálogo **Configurar** para configurar parámetros, administradores de conexión y referencias a los entornos, para los paquetes y los proyectos.</span><span class="sxs-lookup"><span data-stu-id="03e2d-103">Use the **Configure** dialog box to configure parameters, connection managers, and references to environments, for packages and projects.</span></span>  
  
 <span data-ttu-id="03e2d-104">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="03e2d-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="03e2d-105">Abrir el cuadro de diálogo Configurar.</span><span class="sxs-lookup"><span data-stu-id="03e2d-105">Open the Configure Dialog Box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="03e2d-106">Establecer las opciones de la página Parámetros</span><span class="sxs-lookup"><span data-stu-id="03e2d-106">Set the options on the Parameters page</span></span>](#parameter)  
  
-   [<span data-ttu-id="03e2d-107">Establecer las opciones de la página Referencias</span><span class="sxs-lookup"><span data-stu-id="03e2d-107">Set the options on the References page</span></span>](#references)  
  
##  <a name="open-the-configure-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="03e2d-108">Abrir el cuadro de diálogo Configurar.</span><span class="sxs-lookup"><span data-stu-id="03e2d-108">Open the Configure Dialog Box</span></span>  
  
1.  <span data-ttu-id="03e2d-109">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03e2d-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="03e2d-110">Se conectará a la instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos SSISDB.</span><span class="sxs-lookup"><span data-stu-id="03e2d-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="03e2d-111">En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="03e2d-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="03e2d-112">Expanda el nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="03e2d-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="03e2d-113">Expanda la carpeta que contiene el paquete o proyecto que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="03e2d-113">Expand the folder that contains the package or project that you want to configure.</span></span>  
  
5.  <span data-ttu-id="03e2d-114">Haga clic con el botón derecho en el paquete o proyecto y, después, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="03e2d-114">Right-click the package or project, and then click **Configure**.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-page"></a><a name="parameter"></a> <span data-ttu-id="03e2d-115">Establecer las opciones de la página Parámetros</span><span class="sxs-lookup"><span data-stu-id="03e2d-115">Set the options on the Parameters page</span></span>  
 <span data-ttu-id="03e2d-116">Use la página **Parámetros** para ver los nombres de los parámetros y valores, así como para modificar los valores.</span><span class="sxs-lookup"><span data-stu-id="03e2d-116">Use the **Parameters** page to view parameter names and values, and to modify the values.</span></span>  
  
 <span data-ttu-id="03e2d-117">Seleccione el ámbito de los parámetros que aparecen en las pestañas **Parámetros** y **Administradores de conexiones** , en la lista desplegable **Ámbito** .</span><span class="sxs-lookup"><span data-stu-id="03e2d-117">Select the scope of the parameters displayed in the **Parameters** and **Connection Managers** tabs, in the **Scope** drop-down list.</span></span>  
  
 <span data-ttu-id="03e2d-118">La siguiente es una lista de las opciones de la pestaña **Parámetros** .</span><span class="sxs-lookup"><span data-stu-id="03e2d-118">The following is a list of the options in the **Parameters** tab.</span></span>  
  
 <span data-ttu-id="03e2d-119">**Contenedor**</span><span class="sxs-lookup"><span data-stu-id="03e2d-119">**Container**</span></span>  
 <span data-ttu-id="03e2d-120">Muestra el objeto que contiene el parámetro.</span><span class="sxs-lookup"><span data-stu-id="03e2d-120">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="03e2d-121">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="03e2d-121">**Name**</span></span>  
 <span data-ttu-id="03e2d-122">Muestra el nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="03e2d-122">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="03e2d-123">**Valor**</span><span class="sxs-lookup"><span data-stu-id="03e2d-123">**Value**</span></span>  
 <span data-ttu-id="03e2d-124">Muestra el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="03e2d-124">Lists the parameter value.</span></span> <span data-ttu-id="03e2d-125">Haga clic en los puntos suspensivos para cambiar el valor del cuadro de diálogo **Establecer valor de parámetro** .</span><span class="sxs-lookup"><span data-stu-id="03e2d-125">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span>  
  
 <span data-ttu-id="03e2d-126">La siguiente es una lista de las opciones de la pestaña de **Administradores de conexiones** . Use esta pestaña para cambiar los valores de las propiedades del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="03e2d-126">The following is a list of the options in the **Connection Managers** tab. You use this tab to change values for connection manager properties.</span></span> <span data-ttu-id="03e2d-127">En el servidor SSIS se generan automáticamente parámetros para las propiedades.</span><span class="sxs-lookup"><span data-stu-id="03e2d-127">Parameters are automatically generated on the SSIS server for the properties.</span></span>  
  
 <span data-ttu-id="03e2d-128">**Contenedor**</span><span class="sxs-lookup"><span data-stu-id="03e2d-128">**Container**</span></span>  
 <span data-ttu-id="03e2d-129">Muestra el objeto que contiene el administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="03e2d-129">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="03e2d-130">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="03e2d-130">**Name**</span></span>  
 <span data-ttu-id="03e2d-131">Muestra el nombre del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="03e2d-131">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="03e2d-132">**Nombre de propiedad**</span><span class="sxs-lookup"><span data-stu-id="03e2d-132">**Property name**</span></span>  
 <span data-ttu-id="03e2d-133">Muestra el nombre de la propiedad del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="03e2d-133">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="03e2d-134">**Valor**</span><span class="sxs-lookup"><span data-stu-id="03e2d-134">**Value**</span></span>  
 <span data-ttu-id="03e2d-135">Muestra el valor asignado a la propiedad del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="03e2d-135">Lists the value assigned to the connection manager property.</span></span> <span data-ttu-id="03e2d-136">Haga clic en los puntos suspensivos para cambiar el valor del cuadro de diálogo **Establecer valor de parámetro** .</span><span class="sxs-lookup"><span data-stu-id="03e2d-136">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span> <span data-ttu-id="03e2d-137">Puede especificar un valor literal, asignar una variable de entorno que contiene el valor que desea usar o emplear el valor predeterminado del paquete.</span><span class="sxs-lookup"><span data-stu-id="03e2d-137">You can enter a literal value, map an environment variable that contains the value you want to use, or use the default value from the package.</span></span>  
  
##  <a name="set-the-options-on-the-references-page"></a><a name="references"></a> <span data-ttu-id="03e2d-138">Establecer las opciones de la página Referencias</span><span class="sxs-lookup"><span data-stu-id="03e2d-138">Set the options on the References page</span></span>  
 <span data-ttu-id="03e2d-139">Use la página **Referencias** para agregar y quitar las referencias a los entornos y a las propiedades del entorno de acceso.</span><span class="sxs-lookup"><span data-stu-id="03e2d-139">Use the **References** page to add and remove references to environments, and to access environment properties.</span></span>  
  
 <span data-ttu-id="03e2d-140">Un entorno especifica los valores en tiempo de ejecución para los paquetes contenidos en los proyectos que ha implementado en el servidor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03e2d-140">An environment specifies runtime values for packages contained in the projects you've deployed to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="03e2d-141">**Entorno**</span><span class="sxs-lookup"><span data-stu-id="03e2d-141">**Environment**</span></span>  
 <span data-ttu-id="03e2d-142">Muestra el entorno.</span><span class="sxs-lookup"><span data-stu-id="03e2d-142">Lists the environment.</span></span>  
  
 <span data-ttu-id="03e2d-143">**Carpeta del entorno**</span><span class="sxs-lookup"><span data-stu-id="03e2d-143">**Environment Folder**</span></span>  
 <span data-ttu-id="03e2d-144">Muestra la carpeta que contiene el entorno.</span><span class="sxs-lookup"><span data-stu-id="03e2d-144">Lists the folder that contains the environment.</span></span>  
  
 <span data-ttu-id="03e2d-145">**Abrir**</span><span class="sxs-lookup"><span data-stu-id="03e2d-145">**Open**</span></span>  
 <span data-ttu-id="03e2d-146">Haga clic para abrir el cuadro de diálogo de **Propiedades del entorno** .</span><span class="sxs-lookup"><span data-stu-id="03e2d-146">Click to open the **Environment Properties** dialog box.</span></span>  
  
 <span data-ttu-id="03e2d-147">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="03e2d-147">**Add**</span></span>  
 <span data-ttu-id="03e2d-148">Haga clic para agregar una referencia a un entorno.</span><span class="sxs-lookup"><span data-stu-id="03e2d-148">Click to add a reference to an environment.</span></span> <span data-ttu-id="03e2d-149">En el cuadro de diálogo **Examinar entornos** , haga clic en un entorno y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="03e2d-149">In the **Browse Environments** dialog box click an environment and then click **OK**.</span></span>  
  
 <span data-ttu-id="03e2d-150">Puede seleccionar un entorno contenido en cualquier carpeta del proyecto bajo el nodo de **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="03e2d-150">You can select an environment contained in any project folder under the **SSISDB** node.</span></span>  
  
 <span data-ttu-id="03e2d-151">**Remove**</span><span class="sxs-lookup"><span data-stu-id="03e2d-151">**Remove**</span></span>  
 <span data-ttu-id="03e2d-152">Haga clic en un entorno que se muestra en el área de **Referencias** y, después, haga clic **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="03e2d-152">Click an environment listed in the **References** area, and then click **Remove**.</span></span>  
  
  
