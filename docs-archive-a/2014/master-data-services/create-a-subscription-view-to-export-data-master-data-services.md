---
title: Crear una vista de suscripciones (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- subscription views [Master Data Services], creating
- creating subscription views [Master Data Services]
ms.assetid: a5e28961-af16-414a-9845-d2e06aac5214
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e5e2b901e56d75e97a444fd2858ef95872f3b766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674886"
---
# <a name="create-a-subscription-view-master-data-services"></a><span data-ttu-id="b8b61-102">Crear una vista de suscripciones (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b8b61-102">Create a Subscription View (Master Data Services)</span></span>
  <span data-ttu-id="b8b61-103">Cree una vista de suscripciones cuando desee crear una vista de los datos en la [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] base de datos para su uso en sistemas de suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8b61-103">Create a subscription view when you want to create a view of your data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database for use by subscribing systems.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b8b61-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b8b61-104">Prerequisites</span></span>  
 <span data-ttu-id="b8b61-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b8b61-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b8b61-106">Debe disponer del permiso para tener acceso al área funcional de **Administración de integraciones** .</span><span class="sxs-lookup"><span data-stu-id="b8b61-106">You must have permission to access the **Integration Management** functional area.</span></span>  
  
-   <span data-ttu-id="b8b61-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="b8b61-107">You must be a model administrator.</span></span> <span data-ttu-id="b8b61-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b8b61-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-subscription-view"></a><span data-ttu-id="b8b61-109">Crear una vista de suscripción</span><span class="sxs-lookup"><span data-stu-id="b8b61-109">To create a subscription view</span></span>  
  
1.  <span data-ttu-id="b8b61-110">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración de integraciones**.</span><span class="sxs-lookup"><span data-stu-id="b8b61-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Integration Management**.</span></span>  
  
2.  <span data-ttu-id="b8b61-111">En la barra de menús, haga clic en **Crear vistas**.</span><span class="sxs-lookup"><span data-stu-id="b8b61-111">From the menu bar, click **Create Views**.</span></span>  
  
3.  <span data-ttu-id="b8b61-112">En la página **vistas de suscripciones** , haga clic en **Agregar vista de suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="b8b61-112">On the **Subscription Views** page, click **Add subscription view**.</span></span>  
  
4.  <span data-ttu-id="b8b61-113">En el panel **crear vista de suscripciones** , en el cuadro **nombre de vista de suscripciones** , escriba un nombre para la vista.</span><span class="sxs-lookup"><span data-stu-id="b8b61-113">In the **Create Subscription View** pane, in the **Subscription view name** box, type a name for the view.</span></span>  
  
5.  <span data-ttu-id="b8b61-114">En la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="b8b61-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="b8b61-115">Seleccione la opción **versión** o **marca de versión** y, a continuación, seleccione en la lista correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b8b61-115">Select either the **Version** or **Version Flag** option, and then select from the corresponding list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="b8b61-116">Cree una vista de suscripción basada en una marca de versión.</span><span class="sxs-lookup"><span data-stu-id="b8b61-116">Create a subscription view based on a version flag.</span></span> <span data-ttu-id="b8b61-117">Al bloquear una versión, puede reasignar la marca a una versión abierta sin actualizar la vista de suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8b61-117">When you lock a version, you can reassign the flag to an open version without updating the subscription view.</span></span>  
  
7.  <span data-ttu-id="b8b61-118">Seleccione la opción **entidad** o **jerarquía derivada** y, a continuación, seleccione en la lista correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b8b61-118">Select either the **Entity** or **Derived hierarchy** option, and then select from the corresponding list.</span></span>  
  
8.  <span data-ttu-id="b8b61-119">En la lista **Formato** , seleccione un formato de vista de suscripción.</span><span class="sxs-lookup"><span data-stu-id="b8b61-119">From the **Format** list, select a subscription view format.</span></span>  
  
9. <span data-ttu-id="b8b61-120">Si elige **Niveles explícitos** o **Niveles derivados** en la lista **Formato** , escriba el número de niveles en la jerarquía que se incluirán en la vista.</span><span class="sxs-lookup"><span data-stu-id="b8b61-120">If you chose **Explicit levels** or **Derived levels** from the **Format** list, type the number of levels in the hierarchy to include in the view.</span></span>  
  
10. <span data-ttu-id="b8b61-121">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="b8b61-121">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b61-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8b61-122">See Also</span></span>  
 <span data-ttu-id="b8b61-123">[Exportar datos &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b8b61-123">[Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span></span>  
 <span data-ttu-id="b8b61-124">[Eliminar una vista de suscripciones &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="b8b61-124">[Delete a Subscription View &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span></span>  
 [<span data-ttu-id="b8b61-125">Crear una marca de versión &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b8b61-125">Create a Version Flag &#40;Master Data Services&#41;</span></span>](create-a-version-flag-master-data-services.md)  
  
  
