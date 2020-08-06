---
title: Asignar una marca a una versión (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], assigning flags
- versions [Master Data Services], assigning flags
ms.assetid: 6629ec7e-32e7-4a1e-8b31-eb43c5923766
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2de0d0d8d8ea96814e13b9123fe4fcd4782d6bef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677186"
---
# <a name="assign-a-flag-to-a-version-master-data-services"></a><span data-ttu-id="22272-102">Asignar una marca a una versión (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="22272-102">Assign a Flag to a Version (Master Data Services)</span></span>
  <span data-ttu-id="22272-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], asigne una marca a una versión para indicar la versión que los usuarios o los sistemas que se suscriben deberían utilizar.</span><span class="sxs-lookup"><span data-stu-id="22272-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign a flag to a version to indicate the version that users or subscribing systems should use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22272-104">Solo se pueden asignar marcas de versión a una versión al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="22272-104">Version flags can be assigned to only one version at a time.</span></span> <span data-ttu-id="22272-105">Si asigna una marca que ya está asignada a otra versión, se mueve a la versión que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="22272-105">If you assign a flag that is already assigned to another version, the flag is moved to the version you selected.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="22272-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="22272-106">Prerequisites</span></span>  
 <span data-ttu-id="22272-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="22272-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="22272-108">Debe disponer del permiso para tener acceso al área funcional de **Administración de versiones** .</span><span class="sxs-lookup"><span data-stu-id="22272-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="22272-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="22272-109">You must be a model administrator.</span></span> <span data-ttu-id="22272-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="22272-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="22272-111">Debe haber creado una marca de versión para asignarla.</span><span class="sxs-lookup"><span data-stu-id="22272-111">You must have created a version flag to assign.</span></span> <span data-ttu-id="22272-112">Para obtener más información, vea [Crear una marca de versión &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="22272-112">For more information, see [Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span></span>  
  
### <a name="to-assign-a-flag-to-a-version"></a><span data-ttu-id="22272-113">Asignar una marca a una versión</span><span class="sxs-lookup"><span data-stu-id="22272-113">To assign a flag to a version</span></span>  
  
1.  <span data-ttu-id="22272-114">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración de versiones**.</span><span class="sxs-lookup"><span data-stu-id="22272-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="22272-115">En la página **Administrar versiones** , en la fila de la versión a la que quiere asignar una marca, haga doble clic en la celda de la columna **Marca** .</span><span class="sxs-lookup"><span data-stu-id="22272-115">On the **Manage Versions** page, in the row for the version to which you want to assign a flag, double-click the cell in the **Flag** column.</span></span>  
  
3.  <span data-ttu-id="22272-116">En la lista, seleccione la marca que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="22272-116">From the list, select the flag you want to assign.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="22272-117">Si la marca que desea no está disponible, puede que solo esté disponible para versiones **Confirmado** .</span><span class="sxs-lookup"><span data-stu-id="22272-117">If the flag you want is not available, the flag might be available for **Committed** versions only.</span></span> <span data-ttu-id="22272-118">Para confirmar, ir a la página **Administrar marcas de versión** y ver el campo **Solo versiones confirmadas** para la marca.</span><span class="sxs-lookup"><span data-stu-id="22272-118">To confirm, go to the **Manage Version Flags** page and view the **Committed Versions Only** field for the flag.</span></span>  
  
4.  <span data-ttu-id="22272-119">Presione ENTRAR para guardar el cambio.</span><span class="sxs-lookup"><span data-stu-id="22272-119">Press ENTER to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22272-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22272-120">See Also</span></span>  
 <span data-ttu-id="22272-121">[Cree una marca de versión &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="22272-121">[Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span></span>  
 [<span data-ttu-id="22272-122">Versiones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="22272-122">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  
