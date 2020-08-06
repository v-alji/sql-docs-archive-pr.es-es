---
title: Administrar protecciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- checkins [SQL Server Management Studio]
- checking in files
- source controls [SQL Server Management Studio], checkins
ms.assetid: 293e60f3-15e3-4258-b73a-8baabe15c760
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a868aafff6d9bd389671544b5f1898e82707d933
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677817"
---
# <a name="manage-checkins"></a><span data-ttu-id="33c7a-102">Administrar protecciones</span><span class="sxs-lookup"><span data-stu-id="33c7a-102">Manage Checkins</span></span>
  <span data-ttu-id="33c7a-103">Para realizar cambios en un archivo controlado por código fuente que está a disposición de otros usuarios, es necesario protegerlo.</span><span class="sxs-lookup"><span data-stu-id="33c7a-103">To make changes to a source-controlled file available to other users, you must check in the file.</span></span> <span data-ttu-id="33c7a-104">Al proteger un archivo, la versión creada se copia en el proveedor de control de código fuente, se convierte en la última versión del archivo y se suele poner a disposición de otros usuarios que disponen de los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="33c7a-104">When you check in a file, the version you have created is copied to the source control provider, becomes the latest version of the file, and is generally available to users who have the appropriate permissions.</span></span>  
  
 <span data-ttu-id="33c7a-105">Use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para proteger archivos.</span><span class="sxs-lookup"><span data-stu-id="33c7a-105">Use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check in files.</span></span> <span data-ttu-id="33c7a-106">Cuando necesite actualizar el almacén de control de código fuente periódicamente, pero también necesite conservar el control sobre un conjunto de archivos, puede especificar que los archivos protegidos permanezcan desprotegidos para usted.</span><span class="sxs-lookup"><span data-stu-id="33c7a-106">When you need to update the source control store periodically, but also need to maintain control over a set of files, you can specify that files you check in remain checked out to you.</span></span>  
  
 <span data-ttu-id="33c7a-107">En la tabla siguiente se describen los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="33c7a-107">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="33c7a-108">Tema</span><span class="sxs-lookup"><span data-stu-id="33c7a-108">Topic</span></span>|<span data-ttu-id="33c7a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="33c7a-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="33c7a-110">Proteger archivos</span><span class="sxs-lookup"><span data-stu-id="33c7a-110">Check In Files</span></span>](../../2014/database-engine/check-in-files.md)|<span data-ttu-id="33c7a-111">Proporciona instrucciones para proteger un archivo modificado.</span><span class="sxs-lookup"><span data-stu-id="33c7a-111">Provides instructions on how to check in a file you have modified.</span></span>|  
|[<span data-ttu-id="33c7a-112">Ver una lista de archivos modificados</span><span class="sxs-lookup"><span data-stu-id="33c7a-112">View a List of Modified Files</span></span>](../../2014/database-engine/view-a-list-of-modified-files.md)|<span data-ttu-id="33c7a-113">Explica cómo mostrar una lista de archivos modificados que se puedan proteger a la vez al terminar de trabajar.</span><span class="sxs-lookup"><span data-stu-id="33c7a-113">Explains how to display a list of modified files that you can check in together when you are finished working.</span></span>|  
|[<span data-ttu-id="33c7a-114">Modificar archivos protegidos</span><span class="sxs-lookup"><span data-stu-id="33c7a-114">Edit Checked-In Files</span></span>](../../2014/database-engine/edit-checked-in-files.md)|<span data-ttu-id="33c7a-115">Explica cómo configurar el entorno de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para que se puedan modificar los archivos que no estén desprotegidos.</span><span class="sxs-lookup"><span data-stu-id="33c7a-115">Explains how to configure the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment so that you can modify files that are not checked out.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33c7a-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33c7a-116">See Also</span></span>  
 [<span data-ttu-id="33c7a-117">Administrar desprotecciones</span><span class="sxs-lookup"><span data-stu-id="33c7a-117">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  