---
title: Aspectos básicos de los paquetes SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package requirements
ms.assetid: b0c86c35-e3d3-4724-9a96-4087e9d74bf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c58ddc13b5c149b84fa550f312782b02786d062
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747116"
---
# <a name="ssis-package-essentials"></a><span data-ttu-id="def41-102">Fundamentos de los paquetes de SSIS</span><span class="sxs-lookup"><span data-stu-id="def41-102">SSIS Package Essentials</span></span>
  <span data-ttu-id="def41-103">Un paquete es el objeto que implementa la funcionalidad de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para extraer, transformar y cargar datos.</span><span class="sxs-lookup"><span data-stu-id="def41-103">A package is the object that implements [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] functionality to extract, transform, and load data.</span></span> <span data-ttu-id="def41-104">Un paquete se crea utilizando el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] en [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="def41-104">You create a package by using the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="def41-105">También puede crear un paquete ejecutando el Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o el Asistente para proyectos de conexiones de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="def41-105">You can also create a package by running the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard or the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Connections Project Wizard.</span></span> <span data-ttu-id="def41-106">Para obtener más información, [cree paquetes en SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) en el diseñador SSIS y en el [Asistente para importar proyectos](../../2014/integration-services/import-project-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="def41-106">For more information, [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) in SSIS Designer and [Import Project Wizard](../../2014/integration-services/import-project-wizard.md).</span></span>  
  
 <span data-ttu-id="def41-107">Un paquete básico incluye los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="def41-107">A basic package includes the following elements:</span></span>  
  
 <span data-ttu-id="def41-108">**Elementos de flujo de control**</span><span class="sxs-lookup"><span data-stu-id="def41-108">**Control flow elements**</span></span>  
 <span data-ttu-id="def41-109">Estos elementos necesarios realizan varias funciones, proporcionan estructura y controlan el orden en el que se ejecutan los elementos.</span><span class="sxs-lookup"><span data-stu-id="def41-109">These required elements perform various functions, provide structure, and control the order in which elements run.</span></span> <span data-ttu-id="def41-110">Los principales elementos de flujo de control son las tareas, los contenedores y restricciones de precedencia.</span><span class="sxs-lookup"><span data-stu-id="def41-110">The main control flow elements are tasks, containers, and precedence constraints.</span></span> <span data-ttu-id="def41-111">Es necesario que haya por lo menos un elemento de flujo de control en un paquete.</span><span class="sxs-lookup"><span data-stu-id="def41-111">There must be at least one control flow element in a package.</span></span>  
  
 <span data-ttu-id="def41-112">Para más información, consulte [Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="def41-112">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="def41-113">**Elementos de flujo de datos**</span><span class="sxs-lookup"><span data-stu-id="def41-113">**Data flow elements**</span></span>  
 <span data-ttu-id="def41-114">Estos elementos opcionales extraen, modifican y cargan datos en los orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="def41-114">These optional elements extract data, modify data, and load data into data sources.</span></span> <span data-ttu-id="def41-115">Los principales elementos de un flujo de datos son orígenes, transformaciones y destinos.</span><span class="sxs-lookup"><span data-stu-id="def41-115">The main data flow elements are sources, transformations, and destinations.</span></span> <span data-ttu-id="def41-116">No es necesario que haya en este caso elementos de flujo de datos en el paquete.</span><span class="sxs-lookup"><span data-stu-id="def41-116">There does not have to be any data flow elements in package.</span></span>  
  
 <span data-ttu-id="def41-117">Para más información, consulte [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="def41-117">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="def41-118">Para obtener un ejemplo de cómo crear un paquete básico, vea [Lección 1: crear el proyecto y el paquete básico](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="def41-118">For an example of how to create a basic package, see [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="def41-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="def41-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="def41-120">Crear paquetes en herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="def41-120">Create Packages in SQL Server Data Tools</span></span>](create-packages-in-sql-server-data-tools.md)  
  
-   [<span data-ttu-id="def41-121">Agregar o eliminar tareas o contenedores en un flujo de control</span><span class="sxs-lookup"><span data-stu-id="def41-121">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
-   [<span data-ttu-id="def41-122">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="def41-122">Set the Properties of a Task or Container</span></span>](../../2014/integration-services/set-the-properties-of-a-task-or-container.md)  
  
-   [<span data-ttu-id="def41-123">Agregar o eliminar un componente en un flujo de datos</span><span class="sxs-lookup"><span data-stu-id="def41-123">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
## <a name="related-content"></a><span data-ttu-id="def41-124">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="def41-124">Related Content</span></span>  
  
1.  <span data-ttu-id="def41-125">Vídeo, [Crear un paquete básico (vídeo de SQL Server)](https://go.microsoft.com/fwlink/?LinkId=131023), en MSDN.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="def41-125">Video, [Creating a Basic Package (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131023), on MSDN.Microsoft.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def41-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="def41-126">See Also</span></span>  
 <span data-ttu-id="def41-127">[Integration Services &#40;paquetes&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="def41-127">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="def41-128">Restricciones de precedencia</span><span class="sxs-lookup"><span data-stu-id="def41-128">Precedence Constraints</span></span>](control-flow/precedence-constraints.md)  
  
  
