---
title: Creación de un proyecto de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 065fdc60-1791-4e27-9ed5-51d751b3f8c4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50640dd7821943dfc3914326f7e8cba32253d307
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662320"
---
# <a name="creating-an-analysis-services-project"></a><span data-ttu-id="f1488-102">Crear un proyecto de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f1488-102">Creating an Analysis Services Project</span></span>
  <span data-ttu-id="f1488-103">En la tarea siguiente, se usa [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para crear un nuevo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] proyecto denominado `Analysis Services Tutorial` , basado en la [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f1488-103">In the following task, you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project named `Analysis Services Tutorial`, based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Project template.</span></span> <span data-ttu-id="f1488-104">Un *proyecto* es una colección de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="f1488-104">A *project* is a collection of related objects.</span></span> <span data-ttu-id="f1488-105">Los proyectos existen en una solución, que incluye uno o más proyectos.</span><span class="sxs-lookup"><span data-stu-id="f1488-105">Projects exist within a solution, which includes one or more projects.</span></span> <span data-ttu-id="f1488-106">Para obtener más información, vea [Crear un proyecto de Analysis Services &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="f1488-106">For more information, see [Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span></span>  
  
### <a name="to-create-a-new-analysis-services-project"></a><span data-ttu-id="f1488-107">Para crear un nuevo proyecto de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f1488-107">To create a new Analysis Services project</span></span>  
  
1.  <span data-ttu-id="f1488-108">Haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server 2012**y, a continuación, haga clic en **Herramientas de datos de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f1488-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
     <span data-ttu-id="f1488-109">[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Se abre el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f1488-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment opens.</span></span>  
  
2.  <span data-ttu-id="f1488-110">En la página Inicio de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], haga clic en **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f1488-110">On the Start page of [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New Project**.</span></span>  
  
3.  <span data-ttu-id="f1488-111">En el cuadro de diálogo **Nuevo proyecto** , en el panel **Plantillas instaladas** , expanda **Business Intelligence**y seleccione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="f1488-111">In the **New Project** dialog box, in the **Installed Templates** pane, expand **Business Intelligence**, and then select **Analysis Services**.</span></span> <span data-ttu-id="f1488-112">Elija la plantilla **Proyecto multidimensional y de minería de datos de Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="f1488-112">Choose the **Analysis Services Multidimensional and Data Mining Project** template.</span></span>  
  
     <span data-ttu-id="f1488-113">Fíjese en el nombre predeterminado del proyecto, la ubicación y el nombre predeterminado de la solución que aparecen en la parte inferior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f1488-113">Notice the default project name, location, and the default solution name are generated in the bottom of the dialog box.</span></span> <span data-ttu-id="f1488-114">De forma predeterminada, se crea un directorio nuevo para la solución.</span><span class="sxs-lookup"><span data-stu-id="f1488-114">By default, a new directory is created for the solution.</span></span>  
  
4.  <span data-ttu-id="f1488-115">Cambie el nombre del proyecto a `Analysis Services Tutorial` , que también cambia el cuadro Nombre de la **solución** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f1488-115">Change the project Name to `Analysis Services Tutorial`, which also changes the **Solution name** box, and then click **OK**.</span></span>  
  
 <span data-ttu-id="f1488-116">Ha creado correctamente el `Analysis Services Tutorial` proyecto, basado en el Analysis Services plantilla de **proyecto multidimensional y de minería de datos** , dentro de una nueva solución que también se denomina `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="f1488-116">You have successfully created the `Analysis Services Tutorial` project, based on the **Analysis Services Multidimensional and Data Mining Project** template, within a new solution that is also named `Analysis Services Tutorial`.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f1488-117">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="f1488-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f1488-118">Definir un origen de datos</span><span class="sxs-lookup"><span data-stu-id="f1488-118">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="f1488-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1488-119">See Also</span></span>  
 <span data-ttu-id="f1488-120">[Crear modelos multidimensionales mediante SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="f1488-120">[Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span></span>  
 [<span data-ttu-id="f1488-121">Crear un proyecto de Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="f1488-121">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](multidimensional-models/create-an-analysis-services-project-ssdt.md)  
  
  
