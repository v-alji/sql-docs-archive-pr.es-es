---
title: Administrar paquetes y carpetas mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], managing
- custom enumerators [Integration Services]
ms.assetid: ec59b75d-ba09-44ac-9039-9d593bb462d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 695ff4ad020dbdfb2564b4964a55324db4248517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749373"
---
# <a name="managing-packages-and-folders-programmatically"></a><span data-ttu-id="6cf67-102">Administrar paquetes y carpetas mediante programación</span><span class="sxs-lookup"><span data-stu-id="6cf67-102">Managing Packages and Folders Programmatically</span></span>
  <span data-ttu-id="6cf67-103">Cuando trabaja con paquetes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] mediante programación, puede que desee determinar si existe un paquete o carpeta individual, o administrar las carpetas en las que se almacenan los paquetes.</span><span class="sxs-lookup"><span data-stu-id="6cf67-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to manage the folders in which packages are stored.</span></span> <span data-ttu-id="6cf67-104">La clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> del espacio de nombres <xref:Microsoft.SqlServer.Dts.Runtime> proporciona diferentes métodos para satisfacer estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="6cf67-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="6cf67-105">Determinar si existe un paquete o una carpeta</span><span class="sxs-lookup"><span data-stu-id="6cf67-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="6cf67-106">Para determinar mediante programación si existe un paquete guardado, llame a uno de los métodos siguientes antes de intentar cargar y ejecutar el paquete:</span><span class="sxs-lookup"><span data-stu-id="6cf67-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run the package:</span></span>  
  
|<span data-ttu-id="6cf67-107">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6cf67-107">Storage Location</span></span>|<span data-ttu-id="6cf67-108">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="6cf67-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6cf67-109">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="6cf67-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="6cf67-110">Para determinar mediante programación si existe una carpeta, llame a uno de los siguientes métodos antes de intentar enumerar los paquetes almacenados en la carpeta:</span><span class="sxs-lookup"><span data-stu-id="6cf67-110">To determine programmatically whether a folder exists, call one of the following methods before attempting to list the packages stored in the folder, :</span></span>  
  
|<span data-ttu-id="6cf67-111">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6cf67-111">Storage Location</span></span>|<span data-ttu-id="6cf67-112">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="6cf67-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6cf67-113">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="6cf67-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  

  
##  <a name="managing-packages-and-folders"></a><a name="managing"></a> <span data-ttu-id="6cf67-114">Administrar paquetes y carpetas</span><span class="sxs-lookup"><span data-stu-id="6cf67-114">Managing Packages and Folders</span></span>  
 <span data-ttu-id="6cf67-115">La clase <xref:Microsoft.SqlServer.Dts.Runtime.Application> del espacio de nombres <xref:Microsoft.SqlServer.Dts.Runtime> proporciona métodos adicionales para administrar paquetes y las carpetas en las que están almacenados.</span><span class="sxs-lookup"><span data-stu-id="6cf67-115">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides additional methods for managing packages and the folders in which they are stored.</span></span>  
  
###  <a name="removing-a-package"></a><a name="managing_rempkg"></a> <span data-ttu-id="6cf67-116">Quitar un paquete</span><span class="sxs-lookup"><span data-stu-id="6cf67-116">Removing a Package</span></span>  
 <span data-ttu-id="6cf67-117">Para quitar mediante programación un paquete guardado, llame a uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6cf67-117">To remove a saved package programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="6cf67-118">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6cf67-118">Storage Location</span></span>|<span data-ttu-id="6cf67-119">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="6cf67-119">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6cf67-120">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="6cf67-120">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromSqlServer%2A>|  
  

  
###  <a name="creating-a-folder"></a><a name="managing_create"></a> <span data-ttu-id="6cf67-121">Crear una carpeta</span><span class="sxs-lookup"><span data-stu-id="6cf67-121">Creating a Folder</span></span>  
 <span data-ttu-id="6cf67-122">Para crear mediante programación una carpeta de almacenamiento, llame a uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6cf67-122">To create a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="6cf67-123">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6cf67-123">Storage Location</span></span>|<span data-ttu-id="6cf67-124">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="6cf67-124">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6cf67-125">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="6cf67-125">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnSqlServer%2A>|  
  

  
###  <a name="removing-a-folder"></a><a name="managing_remfldr"></a> <span data-ttu-id="6cf67-126">Quitar una carpeta</span><span class="sxs-lookup"><span data-stu-id="6cf67-126">Removing a Folder</span></span>  
 <span data-ttu-id="6cf67-127">Para quitar mediante programación una carpeta de almacenamiento, llame a uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6cf67-127">To remove a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="6cf67-128">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6cf67-128">Storage Location</span></span>|<span data-ttu-id="6cf67-129">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="6cf67-129">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6cf67-130">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="6cf67-130">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromSqlServer%2A>|  
  
  
  
###  <a name="renaming-a-folder"></a><a name="managing_rename"></a> <span data-ttu-id="6cf67-131">Cambiar el nombre de una carpeta</span><span class="sxs-lookup"><span data-stu-id="6cf67-131">Renaming a Folder</span></span>  
 <span data-ttu-id="6cf67-132">Para cambiar el nombre de una carpeta de almacenamiento mediante programación, llame a uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6cf67-132">To rename a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="6cf67-133">Ubicación de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="6cf67-133">Storage Location</span></span>|<span data-ttu-id="6cf67-134">Método que se llama</span><span class="sxs-lookup"><span data-stu-id="6cf67-134">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="6cf67-135">Almacén de paquetes SSIS</span><span class="sxs-lookup"><span data-stu-id="6cf67-135">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnSqlServer%2A>|  
  

  
<span data-ttu-id="6cf67-136">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6cf67-136">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6cf67-137">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="6cf67-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6cf67-138">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="6cf67-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6cf67-139">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="6cf67-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf67-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6cf67-140">See Also</span></span>  
 <span data-ttu-id="6cf67-141">[Administración de paquetes &#40;servicio SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="6cf67-141">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="6cf67-142">Enumerar los paquetes disponibles mediante programación</span><span class="sxs-lookup"><span data-stu-id="6cf67-142">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
