---
title: Administrar desprotecciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- source controls [SQL Server Management Studio], checkouts
- checkouts [SQL Server Management Studio]
- checking out files
ms.assetid: ddd4adba-d432-4005-9cb2-bb9ee3163d8e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfa25cdc27e707d4be705e66b215130c9d70ce1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677812"
---
# <a name="manage-checkouts"></a><span data-ttu-id="1e3ed-102">Administrar desprotecciones</span><span class="sxs-lookup"><span data-stu-id="1e3ed-102">Manage Checkouts</span></span>
  <span data-ttu-id="1e3ed-103">Una vez que un archivo se ha agregado al control de código fuente, es necesario desprotegerlo antes de poder modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-103">After a file has been added to source control, you must check out the file before you can modify it.</span></span> <span data-ttu-id="1e3ed-104">Cuando se desprotege un archivo del control de código fuente, el proveedor de control de código fuente crea una copia de la última versión en el disco local y quita el atributo de solo lectura del archivo.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-104">When you check a file out of source control, the source control provider creates a copy of the latest version on your local disk and removes the read-only attribute of the file.</span></span> <span data-ttu-id="1e3ed-105">En algunas circunstancias, quizás sea necesario modificar un archivo sin desprotegerlo.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-105">In some circumstances you might need to edit a file without checking out the file.</span></span> <span data-ttu-id="1e3ed-106">Para obtener más información sobre la edición de un archivo sin desprotegerlo, consulte [editar archivos protegidos](../../2014/database-engine/edit-checked-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="1e3ed-106">For more information about editing a file without checking the file out, see [Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md).</span></span>  
  
 <span data-ttu-id="1e3ed-107">Puede usar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para desproteger archivos de forma manual o automática.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-107">You can use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out files manually or automatically.</span></span> <span data-ttu-id="1e3ed-108">Para desproteger los archivos manualmente, abra la solución que contiene los archivos en el [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] entorno y, a continuación, haga clic en el comando **Desproteger** .</span><span class="sxs-lookup"><span data-stu-id="1e3ed-108">You check out files manually by opening the solution that contains the files in the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment, and then clicking the **Check Out** command.</span></span> <span data-ttu-id="1e3ed-109">Puede desproteger archivos de forma automática si se configura el entorno de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para que lo haga.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-109">You can check out files automatically if you configure the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to do so.</span></span>  
  
 <span data-ttu-id="1e3ed-110">Según las opciones que el administrador establezca en el proveedor de control de código fuente, también podrá desproteger archivos en modo exclusivo o compartido.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-110">Depending on the options that your administrator sets on your source control provider, you can also check out files in exclusive or shared mode.</span></span> <span data-ttu-id="1e3ed-111">Si desprotege un archivo en modo exclusivo, solo usted puede modificarlo y ningún otro usuario podrá desprotegerlo hasta que usted lo vuelva a proteger.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-111">When you check out a file exclusively, only you can modify it, and no other user can check out the file until you check it in.</span></span> <span data-ttu-id="1e3ed-112">Si desprotege un archivo en modo compartido, cualquier usuario podrá desprotegerlo.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-112">When you check out a file in shared mode, any number of users can check out the same file.</span></span> <span data-ttu-id="1e3ed-113">A medida que cada usuario protege el archivo, el proveedor de control de código fuente intenta combinarlo con la última versión del servidor.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-113">As each user checks in the file, the source control provider attempts to merge the file with the latest server version of the file.</span></span> <span data-ttu-id="1e3ed-114">Si surgen contradicciones entre la versión que se está protegiendo y la última, el proveedor de control de código fuente pide al usuario que solucione el conflicto.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-114">If conflicts arise between the version that is being checked in and the latest version, the source control provider prompts the user to resolve the conflicts.</span></span>  
  
 <span data-ttu-id="1e3ed-115">En la tabla siguiente se describen los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-115">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="1e3ed-116">Tema</span><span class="sxs-lookup"><span data-stu-id="1e3ed-116">Topic</span></span>|<span data-ttu-id="1e3ed-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e3ed-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1e3ed-118">Desproteger archivos</span><span class="sxs-lookup"><span data-stu-id="1e3ed-118">Check Out Files</span></span>](../../2014/database-engine/check-out-files.md)|<span data-ttu-id="1e3ed-119">Proporciona instrucciones sobre cómo desproteger un archivo para modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-119">Provides instructions on how to check out a file so you can modify it.</span></span>|  
|[<span data-ttu-id="1e3ed-120">Deshacer desprotecciones</span><span class="sxs-lookup"><span data-stu-id="1e3ed-120">Undo Checkouts</span></span>](../../2014/database-engine/undo-checkouts.md)|<span data-ttu-id="1e3ed-121">Explica cómo cancelar una desprotección existente.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-121">Explains how to cancel an existing checkout.</span></span>|  
|[<span data-ttu-id="1e3ed-122">Desproteger archivos automáticamente durante la modificación</span><span class="sxs-lookup"><span data-stu-id="1e3ed-122">Automatically Check Out Files Upon Edit</span></span>](../../2014/database-engine/automatically-check-out-files-upon-edit.md)|<span data-ttu-id="1e3ed-123">Explica cómo configurar el control de código fuente para desproteger un archivo al comenzar a modificarlo.</span><span class="sxs-lookup"><span data-stu-id="1e3ed-123">Explains how to configure source control to check out a file when you start to edit it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e3ed-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e3ed-124">See Also</span></span>  
 <span data-ttu-id="1e3ed-125">[Administrar protecciones](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="1e3ed-125">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="1e3ed-126">Modificar archivos protegidos</span><span class="sxs-lookup"><span data-stu-id="1e3ed-126">Edit Checked-In Files</span></span>](../../2014/database-engine/edit-checked-in-files.md)  
  
  
