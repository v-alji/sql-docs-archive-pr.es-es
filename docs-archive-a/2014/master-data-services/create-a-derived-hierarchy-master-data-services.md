---
title: Crear una jerarquía derivada (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, creating
- creating derived hierarchies [Master Data Services]
ms.assetid: fec653c4-11cc-46a2-8dd8-b605341ebb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 20469ad30222e43a3104503cc32187c2e6512743
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746314"
---
# <a name="create-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="fd67a-102">Crear una jerarquía derivada (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="fd67a-102">Create a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="fd67a-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree una jerarquía derivada cuando desee una jerarquía basada en nivel que garantice que los miembros existen en el nivel correcto.</span><span class="sxs-lookup"><span data-stu-id="fd67a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a derived hierarchy when you want a level-based hierarchy that ensures that members exist at the correct level.</span></span> <span data-ttu-id="fd67a-104">Las jerarquías derivadas se basan en las relaciones de atributo basados en dominios que existen en un modelo.</span><span class="sxs-lookup"><span data-stu-id="fd67a-104">Derived hierarchies are based on the domain-based attribute relationships that exist in a model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd67a-105">Si un valor de atributo basado en dominios no existe para un miembro, este no se incluye en la jerarquía derivada.</span><span class="sxs-lookup"><span data-stu-id="fd67a-105">If a domain-based attribute value doesn't exist for a member, the member is not included in the derived hierarchy.</span></span> <span data-ttu-id="fd67a-106">Consulte [Requerir valores de atributo &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md) para requerir un valor de atributo basado en dominio para todos los miembros.</span><span class="sxs-lookup"><span data-stu-id="fd67a-106">See [Require Attribute Values &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md) to require a domain-based attribute value for all members.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fd67a-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fd67a-107">Prerequisites</span></span>  
 <span data-ttu-id="fd67a-108">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="fd67a-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="fd67a-109">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="fd67a-109">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="fd67a-110">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="fd67a-110">You must be a model administrator.</span></span> <span data-ttu-id="fd67a-111">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="fd67a-111">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-derived-hierarchy"></a><span data-ttu-id="fd67a-112">Crear una jerarquía derivada</span><span class="sxs-lookup"><span data-stu-id="fd67a-112">To create a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="fd67a-113">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="fd67a-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="fd67a-114">En la página **vista de modelo** , en la barra de menús, seleccione **administrar** y haga clic en **jerarquías derivadas**.</span><span class="sxs-lookup"><span data-stu-id="fd67a-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="fd67a-115">En la página **Mantenimiento de jerarquías derivadas** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="fd67a-115">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="fd67a-116">Haga clic en **Agregar jerarquía derivada**.</span><span class="sxs-lookup"><span data-stu-id="fd67a-116">Click **Add derived hierarchy**.</span></span>  
  
5.  <span data-ttu-id="fd67a-117">En la página **Agregar jerarquía derivada** , en el cuadro **Nombre de jerarquía derivada** , escriba un nombre para la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="fd67a-117">On the **Add Derived Hierarchy** page, in the **Derived hierarchy name** box, type a name for the hierarchy.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="fd67a-118">Use un nombre que describa los niveles de la jerarquía, por ejemplo **Producto de subcategoría a categoría**.</span><span class="sxs-lookup"><span data-stu-id="fd67a-118">Use a name that describes the levels in the hierarchy, for example **Product to Subcategory to Category**.</span></span>  
  
6.  <span data-ttu-id="fd67a-119">Haga clic en **Guardar jerarquía derivada**.</span><span class="sxs-lookup"><span data-stu-id="fd67a-119">Click **Save derived hierarchy**.</span></span>  
  
7.  <span data-ttu-id="fd67a-120">En la página **Editar jerarquía derivada** , en el panel **entidades y jerarquías disponibles** , haga clic en una entidad o jerarquía y arrástrela hasta el panel **niveles actuales** .</span><span class="sxs-lookup"><span data-stu-id="fd67a-120">On the **Edit Derived Hierarchy** page, in the **Available Entities and Hierarchies** pane, click an entity or hierarchy and drag it to the **Current Levels** pane.</span></span>  
  
8.  <span data-ttu-id="fd67a-121">Siga arrastrando entidades o jerarquías hasta que la jerarquía esté completa.</span><span class="sxs-lookup"><span data-stu-id="fd67a-121">Continue dragging entities or hierarchies until your hierarchy is complete.</span></span>  
  
9. <span data-ttu-id="fd67a-122">Haga clic en **Atrás**.</span><span class="sxs-lookup"><span data-stu-id="fd67a-122">Click **Back**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd67a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd67a-123">See Also</span></span>  
 <span data-ttu-id="fd67a-124">[Jerarquías derivadas &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fd67a-124">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="fd67a-125">[Jerarquías derivadas con límites explícitos &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="fd67a-125">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="fd67a-126">Atributos basados en dominios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="fd67a-126">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)  
  
  
