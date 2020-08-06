---
title: Cuadro de diálogo Versiones del proyecto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.versions.f1
ms.assetid: a48a387c-2e70-45bc-be2e-26e57a9bb2c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 998dd194c2a056121fd6f7a404e75c7080b85aa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748223"
---
# <a name="project-versions-dialog-box"></a><span data-ttu-id="772de-102">Cuadro de diálogo Versiones del proyecto</span><span class="sxs-lookup"><span data-stu-id="772de-102">Project Versions Dialog Box</span></span>
  <span data-ttu-id="772de-103">Use el cuadro de diálogo **Versiones del proyecto** para ver las versiones de un proyecto y restaurar una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="772de-103">Use the **Project Versions** dialog box to view versions of a project and to restore a previous version.</span></span>  
  
 <span data-ttu-id="772de-104">También puede ver las versiones anteriores en la vista [catalog.object_versions &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) y usar el procedimiento almacenado [catalog.restore_project &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) para restaurar versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="772de-104">You can also view previous versions in the [catalog.object_versions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) view, and use the [catalog.restore_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) stored procedure to restore previous versions.</span></span>  
  
 <span data-ttu-id="772de-105">**¿Qué desea hacer?**</span><span class="sxs-lookup"><span data-stu-id="772de-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="772de-106">Abrir el cuadro de diálogo Versiones del proyecto</span><span class="sxs-lookup"><span data-stu-id="772de-106">Open the Project Versions dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="772de-107">Restaurar una versión del proyecto</span><span class="sxs-lookup"><span data-stu-id="772de-107">Restore a Project Version</span></span>](#restore)  
  
##  <a name="open-the-project-versions-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="772de-108">Abrir el cuadro de diálogo Versiones del proyecto</span><span class="sxs-lookup"><span data-stu-id="772de-108">Open the Project Versions dialog box</span></span>  
  
1.  <span data-ttu-id="772de-109">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="772de-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="772de-110">Es decir, conéctese a la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="772de-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="772de-111">En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="772de-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="772de-112">Expanda el nodo **Catálogos de Integration Services** para mostrar el nodo de **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="772de-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="772de-113">El nodo de **SSISDB** contiene una o varias carpetas y cada una de ellas contiene uno o más proyectos.</span><span class="sxs-lookup"><span data-stu-id="772de-113">The **SSISDB** node contains one or more folders that each contain one or more projects.</span></span> <span data-ttu-id="772de-114">Expanda la carpeta que contiene el proyecto que le interesa.</span><span class="sxs-lookup"><span data-stu-id="772de-114">Expand the folder that contains the project you are interested in.</span></span>  
  
5.  <span data-ttu-id="772de-115">Haga clic con el botón derecho en el proyecto y, después, haga clic en **Versiones**.</span><span class="sxs-lookup"><span data-stu-id="772de-115">Right-click the project, and then click **Versions**.</span></span>  
  
 <span data-ttu-id="772de-116">En el cuadro de diálogo **Versiones del proyecto** , la tabla **Versiones** muestra la lista de versiones del proyecto que se han implementado en el servidor, con la fecha y hora en que se implementaron, así como la fecha y hora en que se restauraron (en su caso), la descripción de la versión y un identificador de versión.</span><span class="sxs-lookup"><span data-stu-id="772de-116">In the **Project Versions** dialog box, the **Versions** table displays the list of versions of the project that have been deployed on the server, with the date and time the version was deployed, the date and time the version was restored (if it was restored), the version description, and a version identifier.</span></span> <span data-ttu-id="772de-117">Actualmente la versión activa se indica con una marca de verificación de la columna **Actual** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="772de-117">The currently active version is indicated with a check mark in the **Current** column of the table.</span></span>  
  
##  <a name="restore-a-project-version"></a><a name="restore"></a> <span data-ttu-id="772de-118">Restaurar una versión del proyecto</span><span class="sxs-lookup"><span data-stu-id="772de-118">Restore a Project Version</span></span>  
 <span data-ttu-id="772de-119">Para restaurar una versión anterior de un proyecto, seleccione la versión en la tabla **Versiones** y haga clic en **Restaurar a la versión seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="772de-119">To restore a previous version of a project, select the version in the **Versions** table, and then click **Restore to Selected Version**.</span></span> <span data-ttu-id="772de-120">El proyecto se restaura a la versión seleccionada y esa versión se indica con una marca de verificación en la columna **Actual** de la tabla **Versiones** .</span><span class="sxs-lookup"><span data-stu-id="772de-120">The project is restored to the selected version and that version is indicated with a check mark in the **Current** column of the **Versions** table.</span></span>  
  
  
