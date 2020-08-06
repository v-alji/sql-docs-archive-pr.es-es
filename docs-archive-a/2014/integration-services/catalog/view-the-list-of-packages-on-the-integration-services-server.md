---
title: Ver la lista de paquetes en el servidor de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 67a992d1-7524-4f4b-b3d8-ebd9e5ea82a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47b30f9ea0b2abae73f9260b873b7c8436c423eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743615"
---
# <a name="view-the-list-of-packages-on-the-integration-services-server"></a><span data-ttu-id="77fc0-102">Ver la lista de paquetes en el servidor de Integration Services</span><span class="sxs-lookup"><span data-stu-id="77fc0-102">View the List of Packages on the Integration Services Server</span></span>
  <span data-ttu-id="77fc0-103">Puede ver la lista de paquetes que están almacenados en el servidor [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] de una de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="77fc0-103">You can view the list of packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server in one of two ways.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="77fc0-104">access</span><span class="sxs-lookup"><span data-stu-id="77fc0-104">access</span></span>  
 <span data-ttu-id="77fc0-105">Para ver la lista de paquetes que están almacenados en el servidor, consulte la vista [catalog.packages &#40;base de datos de SSISDB&#41;](/sql/integration-services/system-views/catalog-packages-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="77fc0-105">To view the list of packages that are stored on the server, query the view, [catalog.packages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-packages-ssisdb-database).</span></span>  
  
 <span data-ttu-id="77fc0-106">En [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77fc0-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>  
 <span data-ttu-id="77fc0-107">Para ver los paquetes almacenados en el servidor con el Explorador de objetos en [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], siga el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="77fc0-107">To view packages stored on the server by using Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], follow the procedure below.</span></span>  
  
### <a name="to-view-packages-using-ssmanstudiofull"></a><span data-ttu-id="77fc0-108">Para ver los paquetes con [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77fc0-108">To view packages using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>  
  
1.  <span data-ttu-id="77fc0-109">En [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], conéctese al servidor de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77fc0-109">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="77fc0-110">Es decir, conéctese a la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda la base de datos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="77fc0-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="77fc0-111">En el Explorador de objetos, expanda el árbol para que se muestre el nodo **Catálogos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="77fc0-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="77fc0-112">Expanda el nodo **Catálogos de Integration Services** para mostrar el nodo de **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="77fc0-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="77fc0-113">Expanda el nodo **SSISDB** para mostrar una lista de una o varias carpetas.</span><span class="sxs-lookup"><span data-stu-id="77fc0-113">Expand the **SSISDB** node to display a list of one or more folders.</span></span> <span data-ttu-id="77fc0-114">Cada carpeta contiene uno o más proyectos en la carpeta **Proyectos** y cada proyecto contiene uno varios paquetes en la carpeta **Paquetes** .</span><span class="sxs-lookup"><span data-stu-id="77fc0-114">Each folder contains one or more projects in the **Projects** folder, and each project contains one more packages in the **Packages** folder.</span></span>  
  
  
