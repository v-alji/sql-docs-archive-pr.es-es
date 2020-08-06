---
title: Cambiar el nombre de una regla de negocios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], changing name
ms.assetid: cffcae43-a208-443f-9f43-a0ec9e05f79c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0e99047ffe27332aaed4514394ca2357942a1297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677758"
---
# <a name="change-a-business-rule-name-master-data-services"></a><span data-ttu-id="b28b6-102">Cambiar el nombre de una regla de negocios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b28b6-102">Change a Business Rule Name (Master Data Services)</span></span>
  <span data-ttu-id="b28b6-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cambie el nombre de una regla de negocios cuando el nombre asignado no satisfaga sus necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="b28b6-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], change a business rule name when the name assigned does not meet your business needs.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b28b6-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b28b6-104">Prerequisites</span></span>  
 <span data-ttu-id="b28b6-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b28b6-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b28b6-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="b28b6-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="b28b6-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="b28b6-107">You must be a model administrator.</span></span> <span data-ttu-id="b28b6-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b28b6-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="b28b6-109">Una regla de negocios debe existir.</span><span class="sxs-lookup"><span data-stu-id="b28b6-109">A business rule must exist.</span></span> <span data-ttu-id="b28b6-110">Para obtener más información, consulte [Crear y publicar una regla de negocios &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b28b6-110">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-change-the-name-of-a-business-rule"></a><span data-ttu-id="b28b6-111">Cambiar el nombre de una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="b28b6-111">To change the name of a business rule</span></span>  
  
1.  <span data-ttu-id="b28b6-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="b28b6-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="b28b6-113">En la barra de menús, seleccione **Administrar** y haga clic en **Reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="b28b6-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="b28b6-114">En la página **Mantenimiento de reglas de negocios** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="b28b6-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="b28b6-115">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="b28b6-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="b28b6-116">En la lista **tipo de miembro** , seleccione un tipo de miembro.</span><span class="sxs-lookup"><span data-stu-id="b28b6-116">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="b28b6-117">En la lista **Atributo** , seleccione un atributo o deje el valor predeterminado de **Todos**.</span><span class="sxs-lookup"><span data-stu-id="b28b6-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="b28b6-118">En la cuadrícula, en la fila de la regla de negocios, haga doble clic en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="b28b6-118">In the grid, in the row for the business rule, double-click the **Name** field.</span></span>  
  
8.  <span data-ttu-id="b28b6-119">Escriba un nombre para la regla de negocios.</span><span class="sxs-lookup"><span data-stu-id="b28b6-119">Type a name for the business rule.</span></span>  
  
9. <span data-ttu-id="b28b6-120">Presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b28b6-120">Press ENTER.</span></span>  
  
10. <span data-ttu-id="b28b6-121">Haga clic en **Publicar reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="b28b6-121">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="b28b6-122">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b28b6-122">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="b28b6-123">El estado de la regla cambia a **Activo**.</span><span class="sxs-lookup"><span data-stu-id="b28b6-123">The rule's status changes to **Active**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28b6-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b28b6-124">See Also</span></span>  
 [<span data-ttu-id="b28b6-125">Reglas de negocios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b28b6-125">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
