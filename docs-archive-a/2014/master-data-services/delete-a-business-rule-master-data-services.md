---
title: Eliminar una regla de negocios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting business rules [Master Data Services]
- business rules [Master Data Services], deleting
ms.assetid: b97aa4f9-569f-451d-ad62-65b81f980299
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8e6db486f71634cf025c57eabbedeeb9efdbc437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744165"
---
# <a name="delete-a-business-rule-master-data-services"></a><span data-ttu-id="961f4-102">Eliminar una regla de negocios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="961f4-102">Delete a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="961f4-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], elimine una regla de negocios cuando ya no se necesite.</span><span class="sxs-lookup"><span data-stu-id="961f4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a business rule when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="961f4-104">Puede evitar que los datos se validen con una regla de negocios excluyéndola, en lugar de eliminándola.</span><span class="sxs-lookup"><span data-stu-id="961f4-104">You can prevent data from being validated against a business rule by excluding it, rather than deleting it.</span></span> <span data-ttu-id="961f4-105">Para obtener más información, consulte [Excluir una regla de negocios &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="961f4-105">For more information, see [Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="961f4-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="961f4-106">Prerequisites</span></span>  
 <span data-ttu-id="961f4-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="961f4-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="961f4-108">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="961f4-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="961f4-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="961f4-109">You must be a model administrator.</span></span> <span data-ttu-id="961f4-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="961f4-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-business-rule"></a><span data-ttu-id="961f4-111">Eliminar una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="961f4-111">To delete a business rule</span></span>  
  
1.  <span data-ttu-id="961f4-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="961f4-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="961f4-113">En la barra de menús, seleccione **Administrar** y haga clic en **Reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="961f4-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="961f4-114">En la página **Mantenimiento de reglas de negocios** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="961f4-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="961f4-115">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="961f4-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="961f4-116">En la lista **Tipo de miembro** , seleccione un tipo de miembro al que aplicar la regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="961f4-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="961f4-117">En la lista **Atributo** , seleccione un atributo o deje el valor predeterminado de **Todos**.</span><span class="sxs-lookup"><span data-stu-id="961f4-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="961f4-118">En la cuadrícula, haga clic en la fila de la regla de negocios que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="961f4-118">In the grid, click the row for the business rule you want to delete.</span></span>  
  
8.  <span data-ttu-id="961f4-119">Haga clic en **eliminar regla de negocios seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="961f4-119">Click **Delete selected business rule**.</span></span>  
  
9. <span data-ttu-id="961f4-120">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="961f4-120">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="961f4-121">El valor de la columna **Estado** es **eliminación pendiente**.</span><span class="sxs-lookup"><span data-stu-id="961f4-121">The value in the **Status** column is **Deletion pending**.</span></span>  
  
10. <span data-ttu-id="961f4-122">Haga clic en **Publicar reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="961f4-122">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="961f4-123">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="961f4-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961f4-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="961f4-124">See Also</span></span>  
 <span data-ttu-id="961f4-125">[Excluir una regla de negocios &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="961f4-125">[Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="961f4-126">[Crear y publicar una regla de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="961f4-126">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="961f4-127">Reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="961f4-127">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
