---
title: Excluir una regla de negocios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], excluding
ms.assetid: bdbc9df0-23f7-40b9-8aba-4445c1482580
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 317964dcbc7b2cbe212c415b3aa4f9f1a0743301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745877"
---
# <a name="exclude-a-business-rule-master-data-services"></a><span data-ttu-id="907f1-102">Excluir una regla de negocios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="907f1-102">Exclude a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="907f1-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], excluya una regla de negocios cuando no desee eliminar la regla permanentemente, pero no desee validar los datos con ella.</span><span class="sxs-lookup"><span data-stu-id="907f1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclude a business rule when you do not want to delete the rule permanently, but you do not want to validate data against it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="907f1-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="907f1-104">Prerequisites</span></span>  
 <span data-ttu-id="907f1-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="907f1-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="907f1-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="907f1-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="907f1-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="907f1-107">You must be a model administrator.</span></span> <span data-ttu-id="907f1-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="907f1-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-exclude-a-business-rule"></a><span data-ttu-id="907f1-109">Para excluir una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="907f1-109">To exclude a business rule</span></span>  
  
1.  <span data-ttu-id="907f1-110">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="907f1-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="907f1-111">En la barra de menús, seleccione **Administrar** y haga clic en **Reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="907f1-111">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="907f1-112">En la página **Mantenimiento de reglas de negocios** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="907f1-112">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="907f1-113">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="907f1-113">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="907f1-114">En la lista **tipo de miembro** , seleccione un tipo de miembro.</span><span class="sxs-lookup"><span data-stu-id="907f1-114">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="907f1-115">En la lista **Atributo** , seleccione un atributo o deje el valor predeterminado de **Todos**.</span><span class="sxs-lookup"><span data-stu-id="907f1-115">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="907f1-116">En la cuadrícula, en la fila de la regla de negocios, active la casilla en la columna **excluir** .</span><span class="sxs-lookup"><span data-stu-id="907f1-116">In the grid, in the row for the business rule, select the check box in the **Exclude** column.</span></span> <span data-ttu-id="907f1-117">El valor de la columna **Estado** es **exclusión pendiente**.</span><span class="sxs-lookup"><span data-stu-id="907f1-117">The value in the **Status** column is **Exclusion pending**.</span></span>  
  
8.  <span data-ttu-id="907f1-118">Haga clic en **Publicar reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="907f1-118">Click **Publish business rules**.</span></span>  
  
9. <span data-ttu-id="907f1-119">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="907f1-119">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="907f1-120">Se **excluye**el valor de la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="907f1-120">The value in the **Status** column is **Excluded**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="907f1-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="907f1-121">See Also</span></span>  
 <span data-ttu-id="907f1-122">[Eliminar una regla de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="907f1-122">[Delete a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="907f1-123">[Crear y publicar una regla de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="907f1-123">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="907f1-124">Reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="907f1-124">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
