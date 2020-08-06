---
title: Bloquear una versión (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], locking
- locking versions [Master Data Services]
ms.assetid: 7bb62a84-12d8-4b29-9b6e-6aa25410618e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 68ef979b14d9bd228c7ca89a260b31b2fc6efccd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748816"
---
# <a name="lock-a-version-master-data-services"></a><span data-ttu-id="8a4d4-102">Bloquear una versión (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8a4d4-102">Lock a Version (Master Data Services)</span></span>
  <span data-ttu-id="8a4d4-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], bloquee una versión de un modelo para impedir cambios en los miembros del modelo y en sus atributos.</span><span class="sxs-lookup"><span data-stu-id="8a4d4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], lock a version of a model to prevent changes to the model's members and their attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a4d4-104">Cuando se bloquea una versión, los administradores del modelo pueden continuar agregando, modificando y quitando los miembros.</span><span class="sxs-lookup"><span data-stu-id="8a4d4-104">When a version is locked, model administrators can continue to add, edit, and remove members.</span></span> <span data-ttu-id="8a4d4-105">Otros usuarios con permiso en el modelo solo pueden ver los miembros.</span><span class="sxs-lookup"><span data-stu-id="8a4d4-105">Other users with permission to the model can view members only.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8a4d4-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8a4d4-106">Prerequisites</span></span>  
 <span data-ttu-id="8a4d4-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="8a4d4-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8a4d4-108">Debe disponer del permiso para tener acceso al área funcional de **Administración de versiones** .</span><span class="sxs-lookup"><span data-stu-id="8a4d4-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="8a4d4-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="8a4d4-109">You must be a model administrator.</span></span> <span data-ttu-id="8a4d4-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8a4d4-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="8a4d4-111">El estado de la versión debe ser **Abierta**.</span><span class="sxs-lookup"><span data-stu-id="8a4d4-111">The version's status must be **Open**.</span></span>  
  
### <a name="to-lock-a-version"></a><span data-ttu-id="8a4d4-112">Para bloquear una versión</span><span class="sxs-lookup"><span data-stu-id="8a4d4-112">To lock a version</span></span>  
  
1.  <span data-ttu-id="8a4d4-113">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración de versiones**.</span><span class="sxs-lookup"><span data-stu-id="8a4d4-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="8a4d4-114">En la página **Administrar versiones** , seleccione la fila de la versión que desea bloquear.</span><span class="sxs-lookup"><span data-stu-id="8a4d4-114">On the **Manage Versions** page, select the row for the version that you want to lock.</span></span>  
  
3.  <span data-ttu-id="8a4d4-115">Haga clic en **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="8a4d4-115">Click **Lock**.</span></span>  
  
4.  <span data-ttu-id="8a4d4-116">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8a4d4-116">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8a4d4-117">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8a4d4-117">Next Steps</span></span>  
  
-   [<span data-ttu-id="8a4d4-118">Validar una versión con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8a4d4-118">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="8a4d4-119">Confirmar una versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8a4d4-119">Commit a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/commit-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a4d4-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a4d4-120">See Also</span></span>  
 <span data-ttu-id="8a4d4-121">[Versiones &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8a4d4-121">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="8a4d4-122">Desbloquear una versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8a4d4-122">Unlock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/unlock-a-version-master-data-services.md)  
  
  
