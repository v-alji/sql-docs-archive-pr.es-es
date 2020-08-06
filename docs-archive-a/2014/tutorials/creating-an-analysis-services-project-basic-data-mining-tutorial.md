---
title: Crear un proyecto de Analysis Services (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 784c0401-0358-4117-9c85-4e8220ce71d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 83eb808bc7d18ebe715d309d9f911c010ee172d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663239"
---
# <a name="creating-an-analysis-services-project-basic-data-mining-tutorial"></a><span data-ttu-id="45f0d-102">Crear un proyecto de Analysis Services (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="45f0d-102">Creating an Analysis Services Project (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="45f0d-103">Cada [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] proyecto define los objetos en una sola [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="45f0d-103">Each [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project defines the objects in a single [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="45f0d-104">Una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] puede contener muchos tipos diferentes de objetos</span><span class="sxs-lookup"><span data-stu-id="45f0d-104">An [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database can contains many different types of objects</span></span>  
  
-   <span data-ttu-id="45f0d-105">Modelos multidimensionales (cubos)</span><span class="sxs-lookup"><span data-stu-id="45f0d-105">Multidimensional models (cubes)</span></span>  
  
-   <span data-ttu-id="45f0d-106">Estructuras de minería de datos y modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="45f0d-106">Mining structures and mining models</span></span>  
  
-   <span data-ttu-id="45f0d-107">Objetos auxiliares como orígenes de datos, vistas del origen de datos y ensamblados personalizados</span><span class="sxs-lookup"><span data-stu-id="45f0d-107">Supporting objects such as data sources, data source views, and custom assemblies</span></span>  
  
 <span data-ttu-id="45f0d-108">Tenga en cuenta que **no** se necesita un cubo para realizar tareas de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="45f0d-108">Note that you **do not** require a cube to do data mining.</span></span> <span data-ttu-id="45f0d-109">Si necesita realizar minería de datos en un cubo existente, debe agregar los modelos de minería de datos al mismo proyecto que utilizó para generar el cubo.</span><span class="sxs-lookup"><span data-stu-id="45f0d-109">If you need to perform data mining on an existing cube, you should add the data mining models to the same project you used to build the cube.</span></span> <span data-ttu-id="45f0d-110">Sin embargo, para la mayoría de los fines se pueden generar los modelos en orígenes de datos relacionales, como un almacenamiento de datos, y obtener mejor rendimiento si no se emplea un cubo.</span><span class="sxs-lookup"><span data-stu-id="45f0d-110">However, for most purposes you can build your models on relational data sources, such as a data warehouse, and get better performance if a cube is not involved.</span></span>  
  
 <span data-ttu-id="45f0d-111">En este tutorial utilizará un almacenamiento de datos relacional, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="45f0d-111">In this tutorial you will use a relational data warehouse, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], as the data source.</span></span> <span data-ttu-id="45f0d-112">Implementará todos los objetos de minería de datos en una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] denominada `BasicDataMining`, que se usa solamente para minería de datos.</span><span class="sxs-lookup"><span data-stu-id="45f0d-112">You will deploy all your data mining objects to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database named `BasicDataMining`, used just for data mining.</span></span>  
  
 <span data-ttu-id="45f0d-113">De forma predeterminada, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usa la instancia **localhost** para los proyectos nuevos.</span><span class="sxs-lookup"><span data-stu-id="45f0d-113">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses the **localhost** instance for new projects.</span></span> <span data-ttu-id="45f0d-114">Si está utilizando una instancia con nombre o un servidor diferente, debe crear y abrir el proyecto primero y, a continuación, cambiar el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="45f0d-114">If you are using a named instance or a different server, you must first create and open the project and then change the instance name.</span></span>  
  
 <span data-ttu-id="45f0d-115">Para obtener más información acerca de los proyectos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , vea [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span><span class="sxs-lookup"><span data-stu-id="45f0d-115">For more information about [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projects, see [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span></span>  
  
### <a name="to-create-an-analysis-services-project"></a><span data-ttu-id="45f0d-116">Para crear un proyecto de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="45f0d-116">To create an Analysis Services project</span></span>  
  
1.  <span data-ttu-id="45f0d-117">Abra [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45f0d-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="45f0d-118">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="45f0d-118">On the **File** menu, point to **New**, and then select **Project**.</span></span>  
  
3.  <span data-ttu-id="45f0d-119">Compruebe que la opción **Proyectos de Business Intelligence** esté seleccionada en el panel **Tipos de proyecto** .</span><span class="sxs-lookup"><span data-stu-id="45f0d-119">Verify that **Business Intelligence Projects** is selected in the **Project types** pane.</span></span>  
  
4.  <span data-ttu-id="45f0d-120">En el panel **Plantillas** , seleccione **Proyecto multidimensional y de minería de datos de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="45f0d-120">In the **Templates** pane, select **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
5.  <span data-ttu-id="45f0d-121">En el cuadro **nombre** , asigne al nuevo proyecto el nombre `BasicDataMining` .</span><span class="sxs-lookup"><span data-stu-id="45f0d-121">In the **Name** box, name the new project `BasicDataMining`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-change-the-instance-where-data-mining-objects-are-stored"></a><span data-ttu-id="45f0d-122">Para cambiar la instancia donde se almacenan los objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="45f0d-122">To change the instance where data mining objects are stored</span></span>  
  
1.  <span data-ttu-id="45f0d-123">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en el menú **Proyecto** , seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="45f0d-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Project** menu, select **Properties**.</span></span>  
  
2.  <span data-ttu-id="45f0d-124">En el lado izquierdo del panel **Páginas de propiedades** , en **Propiedades de configuración**, haga clic en **Implementación**.</span><span class="sxs-lookup"><span data-stu-id="45f0d-124">On the left side of the **Property Pages** pane, under **Configuration Properties**, click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="45f0d-125">En el lado derecho del panel **Páginas de propiedades** , en **Destino**, compruebe que el nombre de **Servidor** es **localhost**.</span><span class="sxs-lookup"><span data-stu-id="45f0d-125">On the right side of the **Property Pages** pane, under **Target**, verify that the **Server** name is **localhost**.</span></span> <span data-ttu-id="45f0d-126">Si usa una instancia diferente, escriba el nombre de la instancia.</span><span class="sxs-lookup"><span data-stu-id="45f0d-126">If you are using a different instance, type the name of the instance.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="45f0d-127">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="45f0d-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="45f0d-128">Crear un origen de datos &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="45f0d-128">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="45f0d-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45f0d-129">See Also</span></span>  
 <span data-ttu-id="45f0d-130">[Compilar proyectos de Analysis Services &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="45f0d-130">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="45f0d-131">Crear un proyecto de Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="45f0d-131">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/create-an-analysis-services-project-ssdt)  
  
  
