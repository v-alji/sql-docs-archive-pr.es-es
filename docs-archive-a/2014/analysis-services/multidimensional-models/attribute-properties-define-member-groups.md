---
title: Definir grupos de miembros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- member groups [Analysis Services]
- grouping members
- DiscretizationMethod property
ms.assetid: 006cc915-c499-4781-b9a7-01ad31bebf6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 95f9516c7a0077e97af348afa863fe15c8d4528b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750334"
---
# <a name="define-member-groups"></a><span data-ttu-id="0c16f-102">Definir grupos de miembros</span><span class="sxs-lookup"><span data-stu-id="0c16f-102">Define Member Groups</span></span>
  <span data-ttu-id="0c16f-103">Si un atributo contiene muchos miembros, puede elegir agruparlos en cubos, reduciendo así el número de miembros que los usuarios ven cuando exploran los datos en una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="0c16f-103">If an attribute has a large number of members, you can choose to group those members into buckets, reducing the number of members that users see when they browse the data in a hierarchy.</span></span> <span data-ttu-id="0c16f-104">También puede determinar el número de cubos en los que se agrupan los miembros y establecer un esquema de nomenclatura para los cubos.</span><span class="sxs-lookup"><span data-stu-id="0c16f-104">You can also determine the number of buckets in which the members are groups and set a naming scheme for the buckets.</span></span> <span data-ttu-id="0c16f-105">Para más información, vea [Agrupar miembros de atributos &#40;Discretización&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="0c16f-105">For more information, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
 <span data-ttu-id="0c16f-106">Los miembros se agrupan estableciendo la propiedad **DiscretizationMethod** , a la que puede obtener acceso mediante la ventana **Propiedades** de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c16f-106">You group members by setting the **DiscretizationMethod** property, which is accessed through the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="0c16f-107">Al crear grupos de miembros, los cambios no están a disposición de los usuarios hasta que se procesa la dimensión.</span><span class="sxs-lookup"><span data-stu-id="0c16f-107">When you create member groups, your changes are not available to users until you process the dimension.</span></span> <span data-ttu-id="0c16f-108">Para obtener más información, vea [procesamiento de objetos de modelo multidimensional](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="0c16f-108">For more information, see [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-create-member-groups"></a><span data-ttu-id="0c16f-109">Para crear grupos de miembros</span><span class="sxs-lookup"><span data-stu-id="0c16f-109">To create member groups</span></span>  
  
1.  <span data-ttu-id="0c16f-110">Abra la dimensión con la que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="0c16f-110">Open the dimension that you want to work with.</span></span> <span data-ttu-id="0c16f-111">De forma predeterminada, se abrirá la pestaña **Estructura de dimensión** .</span><span class="sxs-lookup"><span data-stu-id="0c16f-111">The **Dimension Structure** tab opens by default.</span></span>  
  
2.  <span data-ttu-id="0c16f-112">En **Atributos**, haga clic con el botón derecho en el atributo cuyos miembros quiere agrupar y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0c16f-112">In **Attributes**, right-click the attribute whose members you want to group, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0c16f-113">En la lista desplegable junto a **DiscretizationMethod**, seleccione un método para agrupar los miembros.</span><span class="sxs-lookup"><span data-stu-id="0c16f-113">From the drop-down list next to **DiscretizationMethod**, select a method by which to group the members.</span></span> <span data-ttu-id="0c16f-114">Para más información sobre la configuración de **DiscretizationMethod**, vea [Agrupar miembros de atributos &#40;Discretización&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="0c16f-114">For more information about **DiscretizationMethod** settings, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
  
