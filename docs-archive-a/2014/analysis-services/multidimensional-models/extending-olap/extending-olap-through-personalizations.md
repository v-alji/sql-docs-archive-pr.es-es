---
title: Extender OLAP mediante personalizaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, extensibility
ms.assetid: 348e49fc-4390-43c1-9b6c-61b386ff4373
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93669980e989b1cb11673f45c111de3609bbe920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750293"
---
# <a name="extending-olap-through-personalizations"></a><span data-ttu-id="611c3-102">Extender OLAP mediante personalizaciones</span><span class="sxs-lookup"><span data-stu-id="611c3-102">Extending OLAP through personalizations</span></span>
  <span data-ttu-id="611c3-103">Microsoft [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] proporciona numerosas funciones intrínsecas para su uso con los lenguajes MDX (Expresiones multidimensionales) y DMX (Extensiones de minería de datos).</span><span class="sxs-lookup"><span data-stu-id="611c3-103">Microsoft  [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] supplies many intrinsic functions for use with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span> <span data-ttu-id="611c3-104">Estas funciones están diseñadas para realizar multitud de tareas, desde cálculos estadísticos estándar hasta recorridos por los miembros de una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="611c3-104">These functions are designed to accomplish everything from standard statistical calculations to traversing members in a hierarchy.</span></span> <span data-ttu-id="611c3-105">No obstante, al igual que sucede con cualquier otro producto de gran complejidad y solidez, existe siempre la necesidad de ampliar su funcionalidad en el futuro.</span><span class="sxs-lookup"><span data-stu-id="611c3-105">However, as with any other complex and robust product, there is always the need to extend the functionality of such a product further.</span></span>  
  
 <span data-ttu-id="611c3-106">Por lo tanto, Analysis Services proporciona la posibilidad de agregar ensamblados y extensiones personalizadas a una instancia del servicio para completar las necesidades empresariales cuando la funcionalidad estándar deja de ser suficiente.</span><span class="sxs-lookup"><span data-stu-id="611c3-106">Therefore, Analysis Services provides you with the ability to add assemblies and personalized extensions to an instance of the service, in order to complete your business needs whenever the standard functionality is not enough.</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="611c3-107">Ensamblados</span><span class="sxs-lookup"><span data-stu-id="611c3-107">Assemblies</span></span>  
 <span data-ttu-id="611c3-108">Los ensamblados permiten ampliar la funcionalidad empresarial de MDX y DMX.</span><span class="sxs-lookup"><span data-stu-id="611c3-108">Assemblies enable you to extend the business functionality of MDX and DMX.</span></span> <span data-ttu-id="611c3-109">Se puede crear la funcionalidad que se desee en una biblioteca, como por ejemplo una biblioteca de vínculos dinámicos (DLL), y agregar la biblioteca como un ensamblado a una instancia o una base de datos de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="611c3-109">You build the functionality that you want into a library, such as a dynamic link library (DLL), then add the library as an assembly to an instance of Analysis Services or to an Analysis Services database.</span></span> <span data-ttu-id="611c3-110">Los métodos públicos de la biblioteca se ofrecerán como funciones definidas por el usuario a procedimientos, cálculos, acciones, aplicaciones cliente y expresiones de MDX y DMX.</span><span class="sxs-lookup"><span data-stu-id="611c3-110">The public methods in the library are then exposed as user-defined functions to MDX and DMX expressions, procedures, calculations, actions, and client applications.</span></span>  
  
## <a name="personalized-extensions"></a><span data-ttu-id="611c3-111">Extensiones personalizadas</span><span class="sxs-lookup"><span data-stu-id="611c3-111">Personalized Extensions</span></span>  
 <span data-ttu-id="611c3-112">Las extensiones de personalización de SQL Server Analysis Services constituyen el fundamento de la idea de implementar una arquitectura de complemento.</span><span class="sxs-lookup"><span data-stu-id="611c3-112">SQL Server Analysis Services personalization extensions are the foundation of the idea of implementing a plug-in architecture.</span></span> <span data-ttu-id="611c3-113">Analysis Services las extensiones de personalización son una modificación simple y elegante de la arquitectura de ensamblado administrado existente y se exponen en Analysis Services el modelo de objetos de [Microsoft. AnalysisServices. AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) , sintaxis de expresiones multidimensionales (MDX) y conjuntos de filas de esquema.</span><span class="sxs-lookup"><span data-stu-id="611c3-113">Analysis Services personalization extensions are a simple and elegant modification to the existing managed assembly architecture and are exposed throughout the Analysis Services [Microsoft.AnalysisServices.AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) object model, Multidimensional Expressions (MDX) syntax, and schema rowsets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="611c3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="611c3-114">See Also</span></span>  
 <span data-ttu-id="611c3-115">[Administración de ensamblados de modelos multidimensionales](../multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="611c3-115">[Multidimensional Model Assemblies Management](../multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="611c3-116">Extensiones de personalización de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="611c3-116">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
  
