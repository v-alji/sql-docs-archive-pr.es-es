---
title: Cuadro de diálogo Examinar todas las entidades de seguridad | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.browseprincipals.f1
ms.assetid: f11d2c5e-ee05-45f3-8dc2-0feb99b2f76f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c204411a4daace27745e46269cbcfa0ed33f323f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663651"
---
# <a name="browse-all-principals-dialog-box"></a><span data-ttu-id="fbb00-102">Examinar todas las entidades (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="fbb00-102">Browse All Principals Dialog Box</span></span>
  <span data-ttu-id="fbb00-103">Use el cuadro de diálogo **Examinar todas las entidades** para seleccionar la entidad de seguridad de base de datos a la que desea cambiar los permisos en el proyecto seleccionado o en todos los proyectos incluidos en una carpeta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fbb00-103">Use the **Browse All Principals** dialog box to select a database principal to change the principal's permissions on the selected project or on all projects contained in a selected folder.</span></span>  
  
 <span data-ttu-id="fbb00-104">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="fbb00-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="fbb00-105">Abrir el cuadro de diálogo Examinar todas las entidades</span><span class="sxs-lookup"><span data-stu-id="fbb00-105">Open the Browse All Principals dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="fbb00-106">Configurar las opciones</span><span class="sxs-lookup"><span data-stu-id="fbb00-106">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-browse-all-principals-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="fbb00-107">Abrir el cuadro de diálogo Examinar todas las entidades</span><span class="sxs-lookup"><span data-stu-id="fbb00-107">Open the Browse All Principals dialog box</span></span>  
  
1.  <span data-ttu-id="fbb00-108">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbb00-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="fbb00-109">Se conectará a la instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda el catálogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="fbb00-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB catalog.</span></span>  
  
2.  <span data-ttu-id="fbb00-110">En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="fbb00-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="fbb00-111">Expanda el nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="fbb00-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="fbb00-112">Para cambiar los permisos de la entidad de seguridad en todos los proyectos incluidos en una carpeta seleccionada, haga clic con el botón derecho en la carpeta y después haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fbb00-112">To change the principal's permissions on all projects contained in a selected folder, right-click the folder and then click **Properties**.</span></span>  
  
     <span data-ttu-id="fbb00-113">Para cambiar los permisos de la entidad de seguridad en un proyecto seleccionado, expanda la carpeta que contiene el proyecto, haga clic con el botón derecho en él y después haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fbb00-113">To change the principal's permissions on a selected project, expand the folder that contains the project, right-click the project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="fbb00-114">Seleccione la página **Permisos** y haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="fbb00-114">Select the **Permissions** page, and then click **Browse**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="fbb00-115">Configurar las opciones</span><span class="sxs-lookup"><span data-stu-id="fbb00-115">Configure the Options</span></span>  
 <span data-ttu-id="fbb00-116">En esta página se muestran las entidades de seguridad de la vista de catálogo, sys.database_principals, de la base de datos de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="fbb00-116">This page displays the principals from the catalog view, sys.database_principals, of the SSISDB database.</span></span>  
  
 <span data-ttu-id="fbb00-117">Si selecciona las entidades de seguridad, se agregarán a la lista **Inicios de sesión o roles** de la página **Permisos** del cuadro de diálogo principal cuando haga clic en **Aceptar** y cierre el cuadro de diálogo **Examinar todas las entidades** .</span><span class="sxs-lookup"><span data-stu-id="fbb00-117">Selecting principals adds them to the **Logins or roles** list on the **Permissions** page of the parent dialog box when you click **OK** and close the **Browse All Principals** dialog box.</span></span> <span data-ttu-id="fbb00-118">Después de agregar entidades de seguridad a la lista de **Inicios de sesión o roles** , puede cambiar sus permisos en el proyecto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="fbb00-118">After adding principals to the **Logins or roles** list, you can change their permissions on the selected project.</span></span>  
  
 <span data-ttu-id="fbb00-119">**Columna de selección**</span><span class="sxs-lookup"><span data-stu-id="fbb00-119">**Selection column**</span></span>  
 <span data-ttu-id="fbb00-120">Seleccione esta opción para agregar la entidad de seguridad a la lista **Inicios de sesión o roles** de la página **Permisos** del cuadro de diálogo principal.</span><span class="sxs-lookup"><span data-stu-id="fbb00-120">Select to add the principal to the **Logins or roles** list on the **Permissions** page of the parent dialog box.</span></span>  
  
 <span data-ttu-id="fbb00-121">**Columna de icono**</span><span class="sxs-lookup"><span data-stu-id="fbb00-121">**Icon column**</span></span>  
 <span data-ttu-id="fbb00-122">Icono que corresponde al **Tipo** de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fbb00-122">An icon that corresponds to the **Type** of the principal.</span></span>  
  
 <span data-ttu-id="fbb00-123">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fbb00-123">**Name**</span></span>  
 <span data-ttu-id="fbb00-124">Nombre de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fbb00-124">The name of the principal.</span></span>  
  
 <span data-ttu-id="fbb00-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fbb00-125">**Type**</span></span>  
 <span data-ttu-id="fbb00-126">Tipo de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fbb00-126">The type of the principal.</span></span> <span data-ttu-id="fbb00-127">Los tipos comunes son:</span><span class="sxs-lookup"><span data-stu-id="fbb00-127">The common types are:</span></span>  
  
-   <span data-ttu-id="fbb00-128">Usuario de SQL</span><span class="sxs-lookup"><span data-stu-id="fbb00-128">SQL User</span></span>  
  
-   <span data-ttu-id="fbb00-129">Usuario de Windows</span><span class="sxs-lookup"><span data-stu-id="fbb00-129">Windows User</span></span>  
  
-   <span data-ttu-id="fbb00-130">Rol de base de datos</span><span class="sxs-lookup"><span data-stu-id="fbb00-130">Database Role</span></span>  
  
  
