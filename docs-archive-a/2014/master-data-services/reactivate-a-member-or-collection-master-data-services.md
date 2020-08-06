---
title: Reactivar un miembro o una colección (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], reactivating
- consolidated members [Master Data Services], reactivating
- reactivating members [Master Data Services]
- members [Master Data Services], reactivating
- reactivating collections [Master Data Services]
- leaf members [Master Data Services], reactivating
ms.assetid: bb4884c0-3658-4763-92d1-636804278b1c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c449a5a277128bbca6ae24e848bcf12cb0881968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675488"
---
# <a name="reactivate-a-member-or-collection-master-data-services"></a><span data-ttu-id="0ed4d-102">Reactivar un miembro o una colección (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0ed4d-102">Reactivate a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="0ed4d-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], puede reactivar un miembro que:</span><span class="sxs-lookup"><span data-stu-id="0ed4d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can reactivate a member that was either:</span></span>  
  
-   <span data-ttu-id="0ed4d-104">Se desactivó usando el proceso de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-104">Deactivated by the staging process.</span></span>  
  
-   <span data-ttu-id="0ed4d-105">Se eliminó en MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ed4d-105">Deleted in the MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)].</span></span>  
  
-   <span data-ttu-id="0ed4d-106">Se eliminó en la aplicación web de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ed4d-106">Deleted in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
 <span data-ttu-id="0ed4d-107">Al reactivar un miembro, se restauran sus atributos y su pertenencia a jerarquías y colecciones.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-107">When you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span>  
  
 <span data-ttu-id="0ed4d-108">También puede reactivar colecciones.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-108">You can also reactivate collections.</span></span> <span data-ttu-id="0ed4d-109">Cuando lo hace, se restauran los atributos y los miembros que pertenecen a la colección.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-109">When you do, the collection's attributes and the members that belong to the collection are restored.</span></span>  
  
 <span data-ttu-id="0ed4d-110">Cuando se reactiva un miembro o colección, se restauran todas las transacciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-110">When either a collection or member is reactivated, all previous transactions are restored.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0ed4d-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0ed4d-111">Prerequisites</span></span>  
 <span data-ttu-id="0ed4d-112">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="0ed4d-112">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0ed4d-113">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], debe disponer de permiso para el área funcional **Administración de versiones** .</span><span class="sxs-lookup"><span data-stu-id="0ed4d-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you must have permission to the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="0ed4d-114">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-114">You must be a model administrator.</span></span> <span data-ttu-id="0ed4d-115">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0ed4d-115">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reactivate-a-member-or-collection"></a><span data-ttu-id="0ed4d-116">Para reactivar un miembro o colección</span><span class="sxs-lookup"><span data-stu-id="0ed4d-116">To reactivate a member or collection</span></span>  
  
1.  <span data-ttu-id="0ed4d-117">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , haga clic en **Administración de versiones**.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-117">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="0ed4d-118">En la barra de menús, haga clic en **Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-118">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="0ed4d-119">En la página **Transacciones** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-119">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="0ed4d-120">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-120">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="0ed4d-121">En el panel **Transacciones** , haga clic en la fila correspondiente al miembro o colección que desea reactivar.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-121">In the **Transactions** pane, click the row for the member or collection you want to reactivate.</span></span> <span data-ttu-id="0ed4d-122">Esta fila debe mostrar **Activo** en la columna **Valor anterior** y **Desactivado** en la columna **Nuevo valor** .</span><span class="sxs-lookup"><span data-stu-id="0ed4d-122">This row should have **Active** displayed in the **Prior Value** column and **De-Activated** in the **New Value** column.</span></span>  
  
6.  <span data-ttu-id="0ed4d-123">Haga clic en **Invertir transacción**.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-123">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="0ed4d-124">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0ed4d-124">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="0ed4d-125">Se agregará una nueva transacción que muestra **Activo** en la columna **Nuevo valor** .</span><span class="sxs-lookup"><span data-stu-id="0ed4d-125">A new transaction is added, showing **Active** in the **New Value** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed4d-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ed4d-126">See Also</span></span>  
 <span data-ttu-id="0ed4d-127">[Desactive o elimine miembros mediante el proceso de almacenamiento provisional &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0ed4d-127">[Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="0ed4d-128">[Eliminar un miembro o una colección &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0ed4d-128">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="0ed4d-129">[Miembros &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0ed4d-129">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="0ed4d-130">Colecciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0ed4d-130">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
