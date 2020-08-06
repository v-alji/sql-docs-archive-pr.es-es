---
title: Cuadro de diálogo Propiedades del proyecto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.general.f1
- sql12.ssis.ssms.isprojectprop.permissions.f1
ms.assetid: d5cf52f5-1fe2-438a-98a3-fe117360acf8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 259ad48f2b1f33356243635bbaa5426a5199eccf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745942"
---
# <a name="project-properties-dialog-box"></a><span data-ttu-id="e9dc7-102">Propiedades del proyecto (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="e9dc7-102">Project Properties Dialog Box</span></span>
  <span data-ttu-id="e9dc7-103">Un proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] es una unidad de implementación.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project is a unit of deployment.</span></span> <span data-ttu-id="e9dc7-104">Cada proyecto puede contener paquetes, parámetros y referencias de entorno.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-104">Each project can contain packages, parameters, and environment references.</span></span> <span data-ttu-id="e9dc7-105">Un proyecto es un objeto protegible y puede definir permisos en las entidades de seguridad de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-105">A project is a securable object and can define permissions for database principals.</span></span> <span data-ttu-id="e9dc7-106">Cuando se vuelve a implementar un proyecto, la versión anterior del mismo puede almacenarse en el catálogo de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9dc7-106">When a project is re-deployed, the previous version of the project can be stored in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
 <span data-ttu-id="e9dc7-107">Los parámetros del proyecto y los parámetros del paquete se pueden utilizar para asignar valores a las propiedades de los paquetes en el momento de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-107">Project parameters and package parameters can be used to assign values to properties within packages at the time of execution.</span></span> <span data-ttu-id="e9dc7-108">Algunos parámetros requieren valores para que el paquete se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-108">Some parameters require values before the package can be executed.</span></span> <span data-ttu-id="e9dc7-109">Los valores de parámetros que hacen referencia a las variables de entorno requieren que el proyecto tenga la referencia de entorno correspondiente antes de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-109">Parameter values that reference environment variables require that the project has the corresponding environment reference prior to execution.</span></span>  
  
 <span data-ttu-id="e9dc7-110">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-110">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="e9dc7-111">Abrir el cuadro de diálogo de Propiedades del proyecto</span><span class="sxs-lookup"><span data-stu-id="e9dc7-111">Open the Project Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="e9dc7-112">Establecer las opciones de la página General</span><span class="sxs-lookup"><span data-stu-id="e9dc7-112">Set the options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="e9dc7-113">Establecer las opciones de la página Permisos</span><span class="sxs-lookup"><span data-stu-id="e9dc7-113">Set the options on the Permissions page</span></span>](#permissions)  
  
##  <a name="open-the-project-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="e9dc7-114">Abrir el cuadro de diálogo de Propiedades del proyecto</span><span class="sxs-lookup"><span data-stu-id="e9dc7-114">Open the Project Properties dialog box</span></span>  
  
1.  <span data-ttu-id="e9dc7-115">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9dc7-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="e9dc7-116">Se conectará a la instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos SSISDB.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-116">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="e9dc7-117">En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="e9dc7-117">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="e9dc7-118">Expanda el nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="e9dc7-118">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="e9dc7-119">Expanda la carpeta que contiene el proyecto para el que desea establecer las propiedades.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-119">Expand the folder that contains the project that you want to set properties for.</span></span>  
  
5.  <span data-ttu-id="e9dc7-120">Haga clic con el botón derecho en el proyecto y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-120">Right-click the project, and then click **Properties**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="e9dc7-121">Establecer las opciones de la página General</span><span class="sxs-lookup"><span data-stu-id="e9dc7-121">Set the options on the General page</span></span>  
 <span data-ttu-id="e9dc7-122">Use la página General para ver las propiedades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-122">Use the General page to view project properties.</span></span>  
  
 <span data-ttu-id="e9dc7-123">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-123">**Name**</span></span>  
 <span data-ttu-id="e9dc7-124">Muestra el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-124">Lists the project name.</span></span>  
  
 <span data-ttu-id="e9dc7-125">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-125">**Identifier**</span></span>  
 <span data-ttu-id="e9dc7-126">Muestra el identificador del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-126">Lists the project ID.</span></span>  
  
 <span data-ttu-id="e9dc7-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-127">**Description**</span></span>  
 <span data-ttu-id="e9dc7-128">Muestra la descripción opcional del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-128">Displays the optional description of the project.</span></span>  
  
 <span data-ttu-id="e9dc7-129">**Versión del proyecto**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-129">**Project Version**</span></span>  
 <span data-ttu-id="e9dc7-130">Muestra la versión del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-130">Lists the project version.</span></span>  
  
 <span data-ttu-id="e9dc7-131">**Fecha de implementación**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-131">**Deployment Date**</span></span>  
 <span data-ttu-id="e9dc7-132">Muestra la fecha y hora en que el proyecto se implementó por primera vez o se volvió a implementar.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-132">Lists the date and time the project was deployed or redeployed.</span></span>  
  
##  <a name="set-the-options-on-the-permissions-page"></a><a name="permissions"></a> <span data-ttu-id="e9dc7-133">Establecer las opciones de la página Permisos</span><span class="sxs-lookup"><span data-stu-id="e9dc7-133">Set the options on the Permissions page</span></span>  
 <span data-ttu-id="e9dc7-134">Use la página **Permisos** para ver y establecer permisos explícitos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-134">Use the **Permissions** page to view and set explicit permissions for the project.</span></span>  
  
 <span data-ttu-id="e9dc7-135">Examinar</span><span class="sxs-lookup"><span data-stu-id="e9dc7-135">Browse</span></span>  
 <span data-ttu-id="e9dc7-136">Haga clic en **Examinar** para seleccionar los usuarios y los roles para los que quiere establecer permisos con el cuadro de diálogo **Examinar todas las entidades** .</span><span class="sxs-lookup"><span data-stu-id="e9dc7-136">Click **Browse** to select users and roles that you want to set permissions for, by using the **Browse All Principals** dialog box.</span></span>  
  
 <span data-ttu-id="e9dc7-137">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-137">**Name**</span></span>  
 <span data-ttu-id="e9dc7-138">Muestra el nombre del usuario o del rol.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-138">Lists the name of the user or role.</span></span>  
  
 <span data-ttu-id="e9dc7-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-139">**Type**</span></span>  
 <span data-ttu-id="e9dc7-140">Muestra el tipo de usuario o de rol.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-140">Lists the type of user or role.</span></span>  
  
 <span data-ttu-id="e9dc7-141">**Permiso**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-141">**Permission**</span></span>  
 <span data-ttu-id="e9dc7-142">Muestra los permisos.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-142">Lists the permissions.</span></span>  
  
 <span data-ttu-id="e9dc7-143">**Otorgante de permisos**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-143">**Grantor**</span></span>  
 <span data-ttu-id="e9dc7-144">Muestra el usuario o el rol que concede el permiso.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-144">Lists the user or role that grants the permission.</span></span>  
  
 <span data-ttu-id="e9dc7-145">**Conceder**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-145">**Grant**</span></span>  
 <span data-ttu-id="e9dc7-146">Al seleccionar **Conceder** , se concede el permiso al usuario o al rol seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-146">When **Grant** is selected, the permission is granted for the selected user or role.</span></span>  
  
 <span data-ttu-id="e9dc7-147">**Deny**</span><span class="sxs-lookup"><span data-stu-id="e9dc7-147">**Deny**</span></span>  
 <span data-ttu-id="e9dc7-148">Al seleccionar **Denegar** , se deniega el permiso al usuario o al rol seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e9dc7-148">When **Deny** is selected, the permission is denied for the selected user or role.</span></span>  
  
  
