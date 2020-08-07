---
title: Editar archivos protegidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying checked-in files
- checking in files
ms.assetid: 560cd19f-ab22-4273-b00c-149993a630e6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e2dbe1aad203dfdc83e438d5b7f4ed19c15038c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746437"
---
# <a name="edit-checked-in-files"></a><span data-ttu-id="fdeb9-102">Modificar archivos protegidos</span><span class="sxs-lookup"><span data-stu-id="fdeb9-102">Edit Checked-In Files</span></span>
  <span data-ttu-id="fdeb9-103">Normalmente, es necesario desproteger los archivos controlados por código fuente antes de poder modificarlos.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-103">You typically must check out source-controlled files before you can edit them.</span></span> <span data-ttu-id="fdeb9-104">Sin embargo, puede configurar [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para que pueda modificar los archivos que no ha desprotegido. Al hacerlo, los cambios se conservan en la memoria hasta que se guardan los archivos.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-104">However, you can configure [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] so that you can modify files you have not checked out. When doing so, your changes are held in memory until you save the files.</span></span> <span data-ttu-id="fdeb9-105">En ese momento se le pedirá que desproteja el archivo del control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-105">You will then be prompted to check out the file from source control.</span></span>  
  
 <span data-ttu-id="fdeb9-106">Si trabaja en un equipo, no es recomendable que permita la modificación de archivos protegidos a menos que el proveedor de control de código fuente permita desproteger la versión local y la versión del servidor.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-106">If you work on a team, allowing checked-in files to be edited is not recommended unless your source control provider supports both local version and server version checkouts.</span></span> <span data-ttu-id="fdeb9-107">La mayoría de los proveedores no permite desproteger la versión local.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-107">Most providers do not support local version checkouts.</span></span> <span data-ttu-id="fdeb9-108">Si el proveedor no permite desproteger la versión local y se modifica un archivo protegido, será necesario combinar las versiones en memoria y en el servidor de forma manual antes de poder proteger el archivo.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-108">If your provider does not support local version checkouts and you edit a checked-in file, you have to merge the in-memory and server versions manually before the file can be checked in.</span></span> <span data-ttu-id="fdeb9-109">No se permiten las combinaciones automáticas y asistidas por el proveedor en esta situación.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-109">Automatic and provider-assisted merges are unsupported in this situation.</span></span>  
  
### <a name="to-edit-checked-in-files"></a><span data-ttu-id="fdeb9-110">Para modificar archivos protegidos</span><span class="sxs-lookup"><span data-stu-id="fdeb9-110">To edit checked-in files</span></span>  
  
1.  <span data-ttu-id="fdeb9-111">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-111">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="fdeb9-112">En el cuadro de diálogo **Opciones** , expanda la carpeta **Control de código fuente**y, a continuación, haga clic en **Entorno**.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-112">In the **Options** dialog box, expand the **Source Contro**l folder, and then click **Environment**.</span></span>  
  
3.  <span data-ttu-id="fdeb9-113">Haga clic en **Permitir que los elementos protegidos se puedan editar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fdeb9-113">Click **Allow checked-in items to be edited**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdeb9-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdeb9-114">See Also</span></span>  
 <span data-ttu-id="fdeb9-115">[Administrar protecciones](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="fdeb9-115">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="fdeb9-116">Administrar desprotecciones</span><span class="sxs-lookup"><span data-stu-id="fdeb9-116">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
