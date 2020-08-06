---
title: Definir procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services]
- OLAP [Analysis Services], stored procedures
- external routines [Analysis Services]
- stored procedures [Analysis Services], about stored procedures
ms.assetid: f9c57d91-f60f-4f0e-8f7f-d87f4ba97b7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc1f028f822d2289ee79702feb2494487040977c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746037"
---
# <a name="defining-stored-procedures"></a><span data-ttu-id="8e319-102">Definir procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="8e319-102">Defining Stored Procedures</span></span>
  <span data-ttu-id="8e319-103">Puede utilizar procedimientos almacenados para llamar a rutinas externas desde [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e319-103">You can use stored procedures to call external routines from [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="8e319-104">Puede escribir una rutina externa llamada por un procedimiento almacenado en cualquier lenguaje de la biblioteca CLR (Common Language Runtime) como, por ejemplo C, C++, C#, Visual Basic o Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="8e319-104">You can write an external routines called by a stored procedure in any common language runtime (CLR) language, such as C, C++, C#, Visual Basic, or Visual Basic .NET.</span></span> <span data-ttu-id="8e319-105">Un procedimiento almacenado se puede crear una vez y ser llamado desde muchos contextos como, por ejemplo, otros procedimientos almacenados, medidas calculadas o aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="8e319-105">A stored procedure can be created once and called from many contexts, such as other stored procedures, calculated measures, or client applications.</span></span> <span data-ttu-id="8e319-106">Los procedimientos almacenados simplifican el desarrollo y la implementación de las bases de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] al permitir que se desarrolle una sola vez el código común y se almacene en una sola ubicación.</span><span class="sxs-lookup"><span data-stu-id="8e319-106">Stored procedures simplify [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="8e319-107">Los procedimientos almacenados se pueden utilizar para agregar funcionalidades de negocio a las aplicaciones que no sean suministradas por la funcionalidad nativa de MDX.</span><span class="sxs-lookup"><span data-stu-id="8e319-107">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="8e319-108">En esta sección se proporciona la información necesaria para comprender, diseñar e implementar procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="8e319-108">This section provides the information necessary to understand, design, and implement stored procedures.</span></span>  
  
|<span data-ttu-id="8e319-109">Tema</span><span class="sxs-lookup"><span data-stu-id="8e319-109">Topic</span></span>|<span data-ttu-id="8e319-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e319-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8e319-111">Diseñar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="8e319-111">Designing Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/designing-stored-procedures.md)|<span data-ttu-id="8e319-112">Describe cómo diseñar ensamblados que se utilizarán con [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e319-112">Describes how to design assemblies for use with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="8e319-113">Creación de procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="8e319-113">Creating Stored Procedures</span></span>](creating-stored-procedures.md)|<span data-ttu-id="8e319-114">Describe cómo crear ensamblados para [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e319-114">Describes how to create assemblies for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="8e319-115">Llamar a procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="8e319-115">Calling Stored Procedures</span></span>](calling-stored-procedures.md)|<span data-ttu-id="8e319-116">Proporciona información acerca de cómo utilizar ensamblados en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e319-116">Provides information on how to use assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="8e319-117">Acceder al contexto de la consulta en los procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="8e319-117">Accessing Query Context in Stored Procedures</span></span>](accessing-query-context-in-stored-procedures.md)|<span data-ttu-id="8e319-118">Describe cómo tener acceso a la información de ámbito y contexto con ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8e319-118">Describes how to access scope and context information with assemblies.</span></span>|  
|[<span data-ttu-id="8e319-119">Configurar la seguridad para procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="8e319-119">Setting Security for Stored Procedures</span></span>](setting-security-for-stored-procedures.md)|<span data-ttu-id="8e319-120">Describe cómo configurar la seguridad para ensamblados en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e319-120">Describes how to configure security for assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="8e319-121">Depurar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="8e319-121">Debugging Stored Procedures</span></span>](debugging-stored-procedures.md)|<span data-ttu-id="8e319-122">Describe cómo depurar ensamblados en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e319-122">Describes how to debug assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e319-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e319-123">See Also</span></span>  
 [<span data-ttu-id="8e319-124">Administración de ensamblados de modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="8e319-124">Multidimensional Model Assemblies Management</span></span>](../multidimensional-models/multidimensional-model-assemblies-management.md)  
  
  
