---
title: Confirmar una versión (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- committing versions [Master Data Services]
- versions [Master Data Services], committing
ms.assetid: 6b967a39-b333-4b84-9e5f-4fb07e156826
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cec3244d4ddaa78d9168e3ede503fa16756633a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745887"
---
# <a name="commit-a-version-master-data-services"></a><span data-ttu-id="426cf-102">Confirmar una versión (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="426cf-102">Commit a Version (Master Data Services)</span></span>
  <span data-ttu-id="426cf-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], confirme una versión de un modelo para evitar cambios en los miembros del modelo y en sus atributos.</span><span class="sxs-lookup"><span data-stu-id="426cf-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], commit a version of a model to prevent changes to the model's members and their attributes.</span></span> <span data-ttu-id="426cf-104">Las versiones confirmadas no se pueden desbloquear.</span><span class="sxs-lookup"><span data-stu-id="426cf-104">Committed versions cannot be unlocked.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="426cf-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="426cf-105">Prerequisites</span></span>  
 <span data-ttu-id="426cf-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="426cf-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="426cf-107">Debe disponer del permiso para tener acceso al área funcional de **Administración de versiones** .</span><span class="sxs-lookup"><span data-stu-id="426cf-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="426cf-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="426cf-108">You must be a model administrator.</span></span> <span data-ttu-id="426cf-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="426cf-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="426cf-110">El estado de la versión debe ser **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="426cf-110">The version's status must be **Locked**.</span></span> <span data-ttu-id="426cf-111">Para obtener más información, vea [Bloquear una versión &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="426cf-111">For more information, see [Lock a Version &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="426cf-112">Todos los miembros deben haberse validado correctamente.</span><span class="sxs-lookup"><span data-stu-id="426cf-112">All members must have validated successfully.</span></span>  
  
### <a name="to-commit-a-version"></a><span data-ttu-id="426cf-113">Para confirmar una versión</span><span class="sxs-lookup"><span data-stu-id="426cf-113">To commit a version</span></span>  
  
1.  <span data-ttu-id="426cf-114">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración de versiones**.</span><span class="sxs-lookup"><span data-stu-id="426cf-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="426cf-115">En la página **Administrar versiones** , en la barra de menús, haga clic en **Validar versión**.</span><span class="sxs-lookup"><span data-stu-id="426cf-115">On the **Manage Versions** page, on the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="426cf-116">En la página **Validar versión** , seleccione el modelo y la versión que desea confirmar.</span><span class="sxs-lookup"><span data-stu-id="426cf-116">On the **Validate Version** page, select the model and version you want to commit.</span></span>  
  
4.  <span data-ttu-id="426cf-117">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="426cf-117">Click **Commit**.</span></span>  
  
5.  <span data-ttu-id="426cf-118">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="426cf-118">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="426cf-119">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="426cf-119">Next Steps</span></span>  
  
-   [<span data-ttu-id="426cf-120">Crear una marca de versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="426cf-120">Create a Version Flag &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-version-flag-master-data-services.md)  
  
-   [<span data-ttu-id="426cf-121">Asignar una marca a una versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="426cf-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
-   [<span data-ttu-id="426cf-122">Copiar una versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="426cf-122">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="426cf-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="426cf-123">See Also</span></span>  
 [<span data-ttu-id="426cf-124">Versiones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="426cf-124">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  
