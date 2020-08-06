---
title: Agregar miembros a una colección (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], adding members
ms.assetid: 1a7155e6-2d4a-4ed1-a72c-edb37fa1a46b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce2038f3bc90a2f17506b0aadaaf9707fa911896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677189"
---
# <a name="add-members-to-a-collection-master-data-services"></a><span data-ttu-id="c5ef0-102">Agregar miembros a una colección (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c5ef0-102">Add Members to a Collection (Master Data Services)</span></span>
  <span data-ttu-id="c5ef0-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], puede agregar miembros hoja y consolidados a una colección.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can add leaf and consolidated members to a collection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c5ef0-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c5ef0-104">Prerequisites</span></span>  
 <span data-ttu-id="c5ef0-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="c5ef0-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c5ef0-106">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="c5ef0-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="c5ef0-107">Como mínimo, debe tener el permiso **Actualizar** para el objeto de modelo de la colección a la que vaya a agregar miembros.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-107">You must have a minimum of **Update** permission to the collection model object that you are adding members to.</span></span>  
  
-   <span data-ttu-id="c5ef0-108">Una colección debe existir.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-108">A collection must exist.</span></span> <span data-ttu-id="c5ef0-109">Para obtener más información, consulte [Crear una colección &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c5ef0-109">For more information, see [Create a Collection &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span></span>  
  
### <a name="to-add-members-to-a-collection"></a><span data-ttu-id="c5ef0-110">Para agregar miembros a una colección</span><span class="sxs-lookup"><span data-stu-id="c5ef0-110">To add members to a collection</span></span>  
  
1.  <span data-ttu-id="c5ef0-111">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-111">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="c5ef0-112">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-112">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="c5ef0-113">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-113">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="c5ef0-114">En la barra de menús, seleccione **Colecciones** y haga clic en *entity_name*.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-114">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="c5ef0-115">En la cuadrícula, haga clic en la fila de la colección a la que desea agregar miembros.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-115">In the grid, click the row for the collection you want to add members to.</span></span>  
  
6.  <span data-ttu-id="c5ef0-116">Haga clic en la pestaña **Miembros de colección** .</span><span class="sxs-lookup"><span data-stu-id="c5ef0-116">Click the **Collection Members** tab.</span></span>  
  
7.  <span data-ttu-id="c5ef0-117">Haga clic en **Editar miembros**.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-117">Click **Edit Members**.</span></span>  
  
8.  <span data-ttu-id="c5ef0-118">Para filtrar la lista de miembros disponibles, realice una selección en la lista a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-118">To filter the list of available members, select from the list on the left.</span></span>  
  
9. <span data-ttu-id="c5ef0-119">Haga clic en la fila con el miembro que desea agregar y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-119">Click the row with the member you want to add and click **Add**.</span></span>  
  
10. <span data-ttu-id="c5ef0-120">Si lo desea, reorganice los miembros de la colección haciendo clic en **Subir** o **Bajar**.</span><span class="sxs-lookup"><span data-stu-id="c5ef0-120">Optionally, rearrange collection members by clicking **Up** or **Down**.</span></span>  
  
11. <span data-ttu-id="c5ef0-121">Además, puede establecer los valores de ponderación haciendo clic en el valor de la columna **Ponderación** .</span><span class="sxs-lookup"><span data-stu-id="c5ef0-121">Optionally, set weight values by clicking the value in the **Weight** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5ef0-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5ef0-122">See Also</span></span>  
 [<span data-ttu-id="c5ef0-123">Colecciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c5ef0-123">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
