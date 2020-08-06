---
title: Crear jerarquías definidas por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined hierarchies [Analysis Services]
ms.assetid: 16715b85-0630-4a8e-99b0-c0d213cade26
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e870a2b20125132342db1845689b7c2481d623
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746003"
---
# <a name="create-user-defined-hierarchies"></a><span data-ttu-id="888d1-102">Crear jerarquías definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="888d1-102">Create User-Defined Hierarchies</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="888d1-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]permite crear jerarquías definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="888d1-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lets you create user-defined hierarchies.</span></span> <span data-ttu-id="888d1-104">Una jerarquía es una colección de niveles basados en atributos.</span><span class="sxs-lookup"><span data-stu-id="888d1-104">A hierarchy is a collection of levels based on attributes.</span></span> <span data-ttu-id="888d1-105">Por ejemplo, una jerarquía de tiempo puede contener los niveles año, trimestre, mes, semana y día.</span><span class="sxs-lookup"><span data-stu-id="888d1-105">For example, a time hierarchy might contain the Year, Quarter, Month, Week, and Day levels.</span></span> <span data-ttu-id="888d1-106">En algunas jerarquías, cada atributo de miembro implica únicamente al atributo de miembro que tiene por encima.</span><span class="sxs-lookup"><span data-stu-id="888d1-106">In some hierarchies, each member attribute uniquely implies the member attribute above it.</span></span> <span data-ttu-id="888d1-107">Esto se conoce a veces como una jerarquía natural.</span><span class="sxs-lookup"><span data-stu-id="888d1-107">This is sometimes referred to as a natural hierarchy.</span></span> <span data-ttu-id="888d1-108">Los usuarios finales pueden utilizar una jerarquía para examinar los datos del cubo.</span><span class="sxs-lookup"><span data-stu-id="888d1-108">A hierarchy can be used by end users to browse cube data.</span></span> <span data-ttu-id="888d1-109">Defina las jerarquías utilizando el panel Jerarquías del Diseñador de dimensiones de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="888d1-109">Define hierarchies by using the Hierarchies pane of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="888d1-110">Al crear una jerarquía definida por el usuario, esta se podría volver *desigual*.</span><span class="sxs-lookup"><span data-stu-id="888d1-110">When you create a user-defined hierarchy, the hierarchy might become *ragged*.</span></span> <span data-ttu-id="888d1-111">En una jerarquía desigual, el miembro primario lógico de al menos un miembro no se encuentra en el nivel que está inmediatamente por encima del miembro.</span><span class="sxs-lookup"><span data-stu-id="888d1-111">A ragged hierarchy is where the logical parent member of at least one member is not in the level immediately above the member.</span></span> <span data-ttu-id="888d1-112">Si tiene una jerarquía desigual, hay valores que controlan si los miembros que faltan están visibles y cómo mostrarlos.</span><span class="sxs-lookup"><span data-stu-id="888d1-112">If you have a ragged hierarchy, there are settings that control whether the missing members are visible and how to display the missing members.</span></span> <span data-ttu-id="888d1-113">Para más información, vea [Jerarquías desiguales](user-defined-hierarchies-ragged-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="888d1-113">For more information, see [Ragged Hierarchies](user-defined-hierarchies-ragged-hierarchies.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="888d1-114">Para más información sobre los problemas de rendimiento relacionados con el diseño y la configuración de las jerarquías definidas por el usuario, vea la [Guía de rendimiento de SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="888d1-114">For more information about performance issues related to the design and configuration of user-defined hierarchies, see the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="888d1-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="888d1-115">See Also</span></span>  
 <span data-ttu-id="888d1-116">[Propiedades de jerarquía de usuario](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span><span class="sxs-lookup"><span data-stu-id="888d1-116">[User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span></span>  
 <span data-ttu-id="888d1-117">[Propiedades de nivel &#91;Paved sobre&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span><span class="sxs-lookup"><span data-stu-id="888d1-117">[Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span></span>  
 [<span data-ttu-id="888d1-118">Jerarquía de elementos primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="888d1-118">Parent-Child Hierarchy</span></span>](parent-child-dimension.md)  
  
  
