---
title: Validar una versión con las reglas de negocios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- validating versions [Master Data Services]
- validating versions [Master Data Services], about validating versions
- versions [Master Data Services], validating
- business rules [Master Data Services], applying to all members
ms.assetid: 5aee7901-6d05-41d4-8bbb-c6f26791d1df
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 085fa071ca511c9d838c140547419bf87fb857bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672153"
---
# <a name="validate-a-version-against-business-rules-master-data-services"></a><span data-ttu-id="ec3a7-102">Validar una versión con las reglas de negocios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ec3a7-102">Validate a Version against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="ec3a7-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], valide una versión para aplicar las reglas de negocios a todos los miembros de la versión del modelo.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="ec3a7-104">En este procedimiento se explica cómo usar la aplicación web de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] para validar datos.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-104">This procedure explains how to use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application to validate data.</span></span> <span data-ttu-id="ec3a7-105">Si tiene permisos en la base de datos de MDS, puede usar un procedimiento almacenado en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-105">If you have permission in the MDS database, you can use a stored procedure instead.</span></span> <span data-ttu-id="ec3a7-106">Para obtener más información, consulte [Procedimiento almacenado de validación &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ec3a7-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec3a7-107">Todos los miembros deben superar la validación antes de que se pueda confirmar una versión.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-107">All members must pass validation before a version can be committed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ec3a7-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ec3a7-108">Prerequisites</span></span>  
 <span data-ttu-id="ec3a7-109">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="ec3a7-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ec3a7-110">Debe disponer del permiso para tener acceso al área funcional de **Administración de versiones** .</span><span class="sxs-lookup"><span data-stu-id="ec3a7-110">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="ec3a7-111">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-111">You must be a model administrator.</span></span> <span data-ttu-id="ec3a7-112">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ec3a7-112">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="ec3a7-113">El estado de la versión debe ser **Abrir** o **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-113">The version's status must be **Open** or **Locked**.</span></span>  
  
-   <span data-ttu-id="ec3a7-114">En la página **Validar versiones** , los miembros deben existir con un estado que no sea **Validación correcta**.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-114">On the **Validate Versions** page, members must exist with a status other than **Validation succeeded**.</span></span>  
  
### <a name="to-validate-a-version"></a><span data-ttu-id="ec3a7-115">Validar una versión</span><span class="sxs-lookup"><span data-stu-id="ec3a7-115">To validate a version</span></span>  
  
1.  <span data-ttu-id="ec3a7-116">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración de versiones**.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="ec3a7-117">En la página **Administrar versiones** , en la barra de menús, haga clic en **Validar versión**.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-117">On the **Manage Versions** page, from the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="ec3a7-118">En la página **Validar versiones** , seleccione el modelo y la versión que desea validar.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-118">On the **Validate Versions** page, select the model and version you want to validate.</span></span>  
  
4.  <span data-ttu-id="ec3a7-119">Haga clic en **Validar**.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-119">Click **Validate**.</span></span>  
  
5.  <span data-ttu-id="ec3a7-120">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-120">In the confirmation dialog box, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ec3a7-121">Cuando ya no se muestre el indicador de progreso, la validación de la versión habrá terminado.</span><span class="sxs-lookup"><span data-stu-id="ec3a7-121">When the progress indicator is no longer displayed, the version has finished validation.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ec3a7-122">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ec3a7-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="ec3a7-123">Bloquear una versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ec3a7-123">Lock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/lock-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec3a7-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec3a7-124">See Also</span></span>  
 <span data-ttu-id="ec3a7-125">[Estados de validación &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ec3a7-125">[Validation Statuses &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span></span>  
 <span data-ttu-id="ec3a7-126">[Master Data Services de &#40;de procedimiento almacenado de validación&#41;](validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ec3a7-126">[Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="ec3a7-127">[Versiones &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ec3a7-127">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 <span data-ttu-id="ec3a7-128">[Reglas de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ec3a7-128">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="ec3a7-129">Validar miembros específicos con las reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ec3a7-129">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
  
