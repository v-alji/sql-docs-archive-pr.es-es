---
title: Hacer que un grupo de atributos sea visible para los usuarios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b2f6cc27-dbc9-4f3f-961e-e81e76375248
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 309ad0392cd717d4a8a11470621144ef9e604fd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662141"
---
# <a name="make-an-attribute-group-visible-to-users-master-data-services"></a><span data-ttu-id="93d7e-102">Hacer que un grupo de atributos sea visible para los usuarios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="93d7e-102">Make an Attribute Group Visible to Users (Master Data Services)</span></span>
  <span data-ttu-id="93d7e-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], haga que un grupo de atributos sea visible para los usuarios o los grupos cuando desee que los usuarios tengan pestañas en la cuadrícula del área funcional de **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="93d7e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], make an attribute group visible to users or groups when you want users to have tabs above the grid in the **Explorer** functional area.</span></span>  
  
 <span data-ttu-id="93d7e-104">Cuando se crea un grupo de atributos, se oculta automáticamente para todos los usuarios excepto para la persona que lo creó.</span><span class="sxs-lookup"><span data-stu-id="93d7e-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="93d7e-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="93d7e-105">Prerequisites</span></span>  
 <span data-ttu-id="93d7e-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="93d7e-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="93d7e-107">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="93d7e-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="93d7e-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="93d7e-108">You must be a model administrator.</span></span> <span data-ttu-id="93d7e-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="93d7e-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="93d7e-110">Por lo menos debe existir un grupo de atributos.</span><span class="sxs-lookup"><span data-stu-id="93d7e-110">At least one attribute group must exist.</span></span> <span data-ttu-id="93d7e-111">Para obtener más información, vea [Crear un grupo de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="93d7e-111">For more information, see [Create an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-attribute-group-master-data-services.md).</span></span>  
  
### <a name="to-make-an-attribute-group-visible-to-users"></a><span data-ttu-id="93d7e-112">Para hacer que un grupo de atributos sea visible para los usuarios</span><span class="sxs-lookup"><span data-stu-id="93d7e-112">To make an attribute group visible to users</span></span>  
  
1.  <span data-ttu-id="93d7e-113">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="93d7e-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="93d7e-114">En la página **vista de modelo** , en la barra de menús, seleccione **administrar** y haga clic en grupos de **atributos**.</span><span class="sxs-lookup"><span data-stu-id="93d7e-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="93d7e-115">En la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="93d7e-115">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="93d7e-116">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="93d7e-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="93d7e-117">Haga clic en el signo más para expandir **grupos hoja**, **grupos consolidados**o **grupos de recopilación**, según el tipo de grupo que desee hacer visible.</span><span class="sxs-lookup"><span data-stu-id="93d7e-117">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to make visible.</span></span>  
  
6.  <span data-ttu-id="93d7e-118">Haga clic en el signo más para expandir el grupo que desea hacer visible.</span><span class="sxs-lookup"><span data-stu-id="93d7e-118">Click the plus sign to expand the group you want to make visible.</span></span>  
  
7.  <span data-ttu-id="93d7e-119">Haga clic en **usuarios** o **grupos**, en función de si está haciendo que el grupo sea visible para un usuario o un grupo.</span><span class="sxs-lookup"><span data-stu-id="93d7e-119">Click either **Users** or **Groups**, depending on whether you are making the group visible to a user or a group.</span></span>  
  
8.  <span data-ttu-id="93d7e-120">Haga clic en **Editar elemento seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="93d7e-120">Click **Edit selected item**.</span></span>  
  
9. <span data-ttu-id="93d7e-121">Haga clic en usuarios o grupos en el cuadro **disponible** y haga clic en la flecha **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="93d7e-121">Click users or groups in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="93d7e-122">Para agregarlos todos, haga clic en la flecha **Agregar todo** .</span><span class="sxs-lookup"><span data-stu-id="93d7e-122">To add all, click the **Add All** arrow.</span></span>  
  
10. <span data-ttu-id="93d7e-123">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="93d7e-123">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d7e-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93d7e-124">See Also</span></span>  
 <span data-ttu-id="93d7e-125">[Grupos de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="93d7e-125">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="93d7e-126">Crear un grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="93d7e-126">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  
