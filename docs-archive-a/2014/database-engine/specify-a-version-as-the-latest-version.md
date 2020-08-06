---
title: Especifique una versión como la versión más reciente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], latest version
- latest file version specified
- file versions [SQL Server]
ms.assetid: 407dffb1-3ecf-461e-835d-124781f26ee7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: dafe4f757e33a5db63340c3d3cc7c9151871d438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663082"
---
# <a name="specify-a-version-as-the-latest-version"></a><span data-ttu-id="4fb12-102">Especificar una versión como última versión</span><span class="sxs-lookup"><span data-stu-id="4fb12-102">Specify a Version as the Latest Version</span></span>
  <span data-ttu-id="4fb12-103">Al proteger un archivo en el control de código fuente, la versión protegida se convierte en la última; los usuarios que desprotegen o recuperan la última versión reciben copias locales del elemento protegido más recientemente.</span><span class="sxs-lookup"><span data-stu-id="4fb12-103">When you check a file into source control, the version you check in becomes the latest version; users who check out or retrieve the latest version receive local copies of the item most recently checked in.</span></span>  
  
 <span data-ttu-id="4fb12-104">Sin embargo, en algunas situaciones, quizás desee designar una versión anterior de un elemento como la última.</span><span class="sxs-lookup"><span data-stu-id="4fb12-104">However, in some situations, you may want to designate an earlier version of an item as the latest version.</span></span> <span data-ttu-id="4fb12-105">Por ejemplo, desprotege un archivo, lo modifica y, a continuación, lo protege.</span><span class="sxs-lookup"><span data-stu-id="4fb12-105">For example, you check out a file, modify the file, and then check the file in.</span></span> <span data-ttu-id="4fb12-106">Posteriormente decide descartar las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="4fb12-106">You later decide to discard your modifications.</span></span> <span data-ttu-id="4fb12-107">Puesto que ha protegido el elemento, deshacer la desprotección original no es una opción.</span><span class="sxs-lookup"><span data-stu-id="4fb12-107">Because you have checked in the item, undoing your original checkout is not an option.</span></span> <span data-ttu-id="4fb12-108">En estos casos, puede designar la versión que desprotegió originalmente como última versión del elemento.</span><span class="sxs-lookup"><span data-stu-id="4fb12-108">In this situation, you can designate the version you originally checked out as the latest version of the item.</span></span>  
  
 <span data-ttu-id="4fb12-109">Para designar la última versión puede:</span><span class="sxs-lookup"><span data-stu-id="4fb12-109">You can designate the latest version by:</span></span>  
  
-   <span data-ttu-id="4fb12-110">**Anclar una versión**.</span><span class="sxs-lookup"><span data-stu-id="4fb12-110">**Pinning a version**.</span></span> <span data-ttu-id="4fb12-111">Al fijar una versión de un archivo, las versiones más recientes que la fijada no se eliminan.</span><span class="sxs-lookup"><span data-stu-id="4fb12-111">When you pin a file version, versions that are more recent than the pinned version are not deleted.</span></span> <span data-ttu-id="4fb12-112">Además, es posible liberar un archivo que se ha fijado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4fb12-112">In addition, you can unpin a file that you have previously pinned.</span></span> <span data-ttu-id="4fb12-113">Al hacer esto, la versión del archivo que se ha protegido más recientemente se convierte en la última.</span><span class="sxs-lookup"><span data-stu-id="4fb12-113">When you do this, the most recently checked in version of the file becomes the latest version.</span></span> <span data-ttu-id="4fb12-114">No obstante, no es posible desproteger un archivo fijado.</span><span class="sxs-lookup"><span data-stu-id="4fb12-114">However, you cannot check out a pinned file.</span></span>  
  
-   <span data-ttu-id="4fb12-115">**Revertir a una versión especificada**.</span><span class="sxs-lookup"><span data-stu-id="4fb12-115">**Rolling back to a specified version**.</span></span> <span data-ttu-id="4fb12-116">Al revertir a una versión, todas las versiones posteriores se eliminan del control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="4fb12-116">When you roll back to a version, all versions more recent than the one to which you have rolled back are deleted from source control.</span></span> <span data-ttu-id="4fb12-117">A continuación, se puede desproteger la última versión que queda.</span><span class="sxs-lookup"><span data-stu-id="4fb12-117">You can then check out the latest remaining version.</span></span>  
  
### <a name="to-pin-a-version"></a><span data-ttu-id="4fb12-118">Para fijar una versión</span><span class="sxs-lookup"><span data-stu-id="4fb12-118">To pin a version</span></span>  
  
1.  <span data-ttu-id="4fb12-119">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , abra la solución.</span><span class="sxs-lookup"><span data-stu-id="4fb12-119">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="4fb12-120">En el Explorador de soluciones, seleccione el archivo que desea especificar como última versión.</span><span class="sxs-lookup"><span data-stu-id="4fb12-120">In Solution Explorer, select the file that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="4fb12-121">En el menú **archivo** , seleccione **control de código fuente** y haga clic en **ViewHistory**.</span><span class="sxs-lookup"><span data-stu-id="4fb12-121">On the **File** menu, point to **Source Control** and click **ViewHistory**.</span></span>  
  
4.  <span data-ttu-id="4fb12-122">En el cuadro **de diálogo historial de** \<file> , seleccione la versión que desea especificar como última y haga clic en **anclar**.</span><span class="sxs-lookup"><span data-stu-id="4fb12-122">In the **History of** \<file> dialog box, select the version that you want to specify as the latest, and click **Pin**.</span></span>  
  
     <span data-ttu-id="4fb12-123">Aparece un símbolo junto a la versión seleccionada que indica que ésta es la versión actual del archivo.</span><span class="sxs-lookup"><span data-stu-id="4fb12-123">A pin symbol appears next to the version you have selected, indicating that it is the current file version.</span></span> <span data-ttu-id="4fb12-124">Si tiene cargada una versión distinta en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], se le pedirá que vuelva a cargar el archivo.</span><span class="sxs-lookup"><span data-stu-id="4fb12-124">If you have a different version loaded in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you are prompted to reload the file.</span></span>  
  
### <a name="to-roll-back-to-a-version"></a><span data-ttu-id="4fb12-125">Para revertir a una versión</span><span class="sxs-lookup"><span data-stu-id="4fb12-125">To roll back to a version</span></span>  
  
1.  <span data-ttu-id="4fb12-126">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , abra la solución.</span><span class="sxs-lookup"><span data-stu-id="4fb12-126">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="4fb12-127">En el Explorador de soluciones, seleccione el elemento que desea especificar como última versión.</span><span class="sxs-lookup"><span data-stu-id="4fb12-127">In Solution Explorer, select the item that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="4fb12-128">En el menú **archivo** , seleccione **control de código fuente** y haga clic en **historial**.</span><span class="sxs-lookup"><span data-stu-id="4fb12-128">On the **File** menu, point to **Source Control** and click **History**.</span></span>  
  
4.  <span data-ttu-id="4fb12-129">En el cuadro de diálogo **Opciones de historial** , haga clic en **Aceptar** para mostrar el cuadro **de diálogo historial del archivo** .</span><span class="sxs-lookup"><span data-stu-id="4fb12-129">In the **History Options** dialog box, click **OK** to display the **History of File** dialog box.</span></span>  
  
5.  <span data-ttu-id="4fb12-130">En el cuadro **historial de archivo** , seleccione la versión que desea especificar como última versión y haga clic en **revertir**.</span><span class="sxs-lookup"><span data-stu-id="4fb12-130">In the **History of File** box, select the version you want to specify as the latest version, and click **Rollback**.</span></span>  
  
     <span data-ttu-id="4fb12-131">Aparece un mensaje diciendo que todas las versiones siguientes a la seleccionada serán eliminadas.</span><span class="sxs-lookup"><span data-stu-id="4fb12-131">A message appears notifying you that all versions subsequent to the one you have selected will be deleted.</span></span>  
  
6.  <span data-ttu-id="4fb12-132">Haga clic en **sí** para revertir a la versión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4fb12-132">Click **Yes** to roll back to the selected version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb12-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4fb12-133">See Also</span></span>  
 <span data-ttu-id="4fb12-134">[Administrar protecciones](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="4fb12-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="4fb12-135">Proteger archivos</span><span class="sxs-lookup"><span data-stu-id="4fb12-135">Check In Files</span></span>](../../2014/database-engine/check-in-files.md)  
  
  
