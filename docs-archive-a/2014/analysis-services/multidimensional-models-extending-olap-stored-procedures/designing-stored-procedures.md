---
title: Diseñar procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services], designing
- dependent assemblies [Analysis Services]
- assemblies [Analysis Services]
ms.assetid: af4e7bd5-041b-4a40-9942-0ef6a3af46c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 42b33873d6bdf28f7f702bcf186d681f57d6024d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746038"
---
# <a name="designing-stored-procedures"></a><span data-ttu-id="277af-102">Diseñar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="277af-102">Designing Stored Procedures</span></span>
  <span data-ttu-id="277af-103">El modelo de objeto administrativo Objetos de administración de análisis (AMO) y el modelo de objeto orientado al cliente Objetos de datos [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® (Multidimensional) (ADO MD) se incluyen en los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="277af-103">Both the administrative object model Analysis Management Objects (AMO) and the client oriented object model [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® Data Objects (Multidimensional) (ADO MD) are available in stored procedures.</span></span>  
  
 <span data-ttu-id="277af-104">Los procedimientos almacenados deben estar en el ámbito (el servidor o la base de datos) para ser visibles en el nivel de Expresiones multidimensionales (MDX) para ser llamados.</span><span class="sxs-lookup"><span data-stu-id="277af-104">Stored procedures must be in scope (either the server or the database) to be visible at the Multidimensional Expressions (MDX) level to be called.</span></span> <span data-ttu-id="277af-105">Sin embargo, cuando se invoca un procedimiento almacenado, su ámbito no se limita a acciones bajo su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="277af-105">However, once a stored procedure is invoked, its scope is not limited to actions under its parent.</span></span> <span data-ttu-id="277af-106">Un procedimiento almacenado puede realizar cambios o modificaciones en cualquier lugar del servidor, sujeto únicamente a las limitaciones de seguridad del proceso de usuario que lo invoca o a las limitaciones de la transacción en la que opera.</span><span class="sxs-lookup"><span data-stu-id="277af-106">A stored procedure may make changes or modifications anywhere on the server, subject only to the security limitations of the user process that invokes it or to the limitations of the transaction in which it is operating.</span></span>  
  
 <span data-ttu-id="277af-107">Los procedimientos del ámbito del servidor están disponibles en todos los contextos del servidor.</span><span class="sxs-lookup"><span data-stu-id="277af-107">Server scope procedures are available in all contexts on the server.</span></span> <span data-ttu-id="277af-108">Los procedimientos almacenados del ámbito de la base de datos solamente están visibles en el contexto de la base de datos en la que se definen.</span><span class="sxs-lookup"><span data-stu-id="277af-108">Database scope stored procedures are visible only in the database context of the database in which they are defined.</span></span>  
  
 <span data-ttu-id="277af-109">Al igual que con cualquier función MDX, para que pueda continuar una sesión MDX se debe resolver el procedimiento almacenado; los procedimientos almacenados bloquean las sesiones MDX mientras se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="277af-109">As with any MDX function, stored procedure must be resolved before an MDX session can continue; stored procedures lock MDX sessions while executing.</span></span> <span data-ttu-id="277af-110">A menos que exista una razón específica para detener una sesión MDX pendiente de interacción del usuario, se desaconsejan las interacciones del usuario (como los cuadros de diálogo).</span><span class="sxs-lookup"><span data-stu-id="277af-110">Unless a specific reason exists to halt an MDX session pending user interaction, then user interactions (such as dialog boxes) are discouraged.</span></span>  
  
## <a name="dependent-assemblies"></a><span data-ttu-id="277af-111">Ensamblados dependientes</span><span class="sxs-lookup"><span data-stu-id="277af-111">Dependent Assemblies</span></span>  
 <span data-ttu-id="277af-112">Todos los ensamblados dependientes se deben cargar en una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para que los encuentre Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="277af-112">All dependent assemblies must be loaded into an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to be found by the common language runtime (CLR).</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="277af-113">almacena los ensamblados dependientes en la misma carpeta que el ensamblado principal, de manera que CLR resuelve automáticamente todas las referencias de función a las funciones en esos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="277af-113">stores the dependent assemblies in the same folder as the main assembly, so the CLR automatically resolves all function references to functions in those assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="277af-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="277af-114">See Also</span></span>  
 <span data-ttu-id="277af-115">[Administración de ensamblados de modelos multidimensionales](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="277af-115">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="277af-116">Definir procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="277af-116">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
