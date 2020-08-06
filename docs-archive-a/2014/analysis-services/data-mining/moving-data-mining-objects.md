---
title: Mover objetos de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], models
- data mining editor [Analysis Services]
- mining models [Analysis Services], managing
- Data Mining Designer
- mining models [Analysis Services], modifying
ms.assetid: bc108407-2603-4387-b930-b5bb9df78069
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b10be3a79487376b173eab87059404b7f7a618e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744441"
---
# <a name="moving-data-mining-objects"></a><span data-ttu-id="1d4f0-102">Mover objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1d4f0-102">Moving Data Mining Objects</span></span>
  <span data-ttu-id="1d4f0-103">Los escenarios más frecuentes para mover objetos de minería de datos son implementar un modelo de un entorno de prueba o de análisis en un entorno de producción, o compartir modelos con otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-103">The most common scenarios for moving data mining objects are to deploy a model from a testing or analysis environment to a production environment, or to share models with other users.</span></span>  
  
 <span data-ttu-id="1d4f0-104">En este tema se describe cómo usar las herramientas y los lenguajes de scripting que proporciona [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], para mover objetos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-104">This topic describes how you can use the tools and scripting languages provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], for moving data mining objects.</span></span>  
  
## <a name="moving-data-mining-objects-between-databases-or-servers"></a><span data-ttu-id="1d4f0-105">Mover objetos de minería de datos entre bases de datos o servidores</span><span class="sxs-lookup"><span data-stu-id="1d4f0-105">Moving Data Mining Objects between Databases or Servers</span></span>  
 <span data-ttu-id="1d4f0-106">Puede mover objetos de minería de datos entre bases de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o entre instancias de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="1d4f0-106">You can move data mining objects between [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases or between instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="1d4f0-107">Volviendo a implementar la solución en una base de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-107">Re-deploying the solution to a different database.</span></span>  
  
-   <span data-ttu-id="1d4f0-108">Generando scripting de objetos individuales.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-108">Scripting individual objects.</span></span>  
  
-   <span data-ttu-id="1d4f0-109">Haciendo una copia de seguridad y restaurando una copia de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-109">Backing up and then restoring a copy of the database.</span></span>  
  
-   <span data-ttu-id="1d4f0-110">Exportando e importando estructuras y modelos.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-110">Exporting and importing structures and models.</span></span>  
  
 <span data-ttu-id="1d4f0-111">En la siguiente sección se describen estas opciones con más detalle.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-111">The following section explains these options in more detail.</span></span>  
  
### <a name="deploying"></a><span data-ttu-id="1d4f0-112">Implementando</span><span class="sxs-lookup"><span data-stu-id="1d4f0-112">Deploying</span></span>  
 <span data-ttu-id="1d4f0-113">La implementación de la solución en otro servidor o base de datos requiere que tenga el archivo de solución creado con [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d4f0-113">Deploying the solution to a different server or database requires that you have the solution file that was created by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1d4f0-114">Para más información sobre cómo implementar soluciones de Analysis Services, vea [Implementar proyectos de Analysis Services &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="1d4f0-114">For more information about deploying Analysis Services solutions, see [Deploy Analysis Services Projects &#40;SSDT&#41;](../multidimensional-models/deploy-analysis-services-projects-ssdt.md).</span></span>  
  
### <a name="scripting"></a><span data-ttu-id="1d4f0-115">Scripting</span><span class="sxs-lookup"><span data-stu-id="1d4f0-115">Scripting</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="1d4f0-116">proporciona varios lenguajes que puede utilizar para crear scripts de objetos.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-116">provides several languages that you can use to script objects.</span></span>  
  
-   <span data-ttu-id="1d4f0-117">**XMLA**: puede incluir objetos con XMLA si hace clic con el botón derecho en objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d4f0-117">**XMLA**: You can script objects using XMLA by right-clicking objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1d4f0-118">Para ejecutar el script, ábralo en una ventana de **Consulta XMLA** en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-118">To execute the script, open it in an **XMLA Query** window on the target server.</span></span>  
  
-   <span data-ttu-id="1d4f0-119">**DMX**: puede crear scripts mediante plantillas o uno de los generadores de consultas que se proporcionan en [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] y [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d4f0-119">**DMX**: You can create scripts by using templates or one of the query builders provided in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1d4f0-120">Tenga en cuenta, no obstante, que existen diferencias en las tareas que puede realizar con cada lenguaje de scripting:</span><span class="sxs-lookup"><span data-stu-id="1d4f0-120">Note, however, that there are differences in the tasks that you can perform with each scripting language:</span></span>  
  
-   <span data-ttu-id="1d4f0-121">Las propiedades, como la descripción y los enlaces de datos del objeto, solo se pueden crear o cambiar mediante lenguajes DDL de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y no utilizando DMX.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-121">Properties such as the object description and data bindings can only by created or changed by using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] DDL languages, not by using DMX.</span></span>  
  
-   <span data-ttu-id="1d4f0-122">Solo DMX admite la importación y exportación de objetos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-122">Only DMX supports the import and export of mining objects.</span></span>  
  
-   <span data-ttu-id="1d4f0-123">Solo DMX admite la generación de PMML o la importación de definiciones de modelo PMML.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-123">Only DMX supports generating PMML or importing model definitions from PMML.</span></span>  
  
-   <span data-ttu-id="1d4f0-124">Solo DMX admite el aprendizaje de un modelo con datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-124">Only DMX supports training a model with application data.</span></span> <span data-ttu-id="1d4f0-125">Además, la instrucción DMX INSERT INTO admite el aprendizaje de un modelo sin proporcionar valores para una columna de clave.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-125">Moreover, the DMX INSERT INTO statement supports training a model without providing values for a key column.</span></span>  
  
 <span data-ttu-id="1d4f0-126">Para obtener más información, vea [Desarrollar aplicaciones con Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="1d4f0-126">For more information, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
### <a name="backup-and-restore"></a><span data-ttu-id="1d4f0-127">Copias de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="1d4f0-127">Backup and Restore</span></span>  
 <span data-ttu-id="1d4f0-128">La copia de seguridad y restauración de una base de datos de Analysis Services completa es el mejor método si la solución de minería de datos se basa en objetos OLAP.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-128">Backup and restore of an entire Analysis Services database is the method of choice if your data mining solution relies on OLAP objects.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="1d4f0-129">proporciona una funcionalidad de copia de seguridad y restauración que realiza copias de seguridad de bases de datos con más rapidez y facilidad.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-129">provides backup and restore functionality that makes database backups faster and easier.</span></span>  
  
 <span data-ttu-id="1d4f0-130">Para más información sobre las copias de seguridad, vea [Realizar una copia de seguridad y restaurar las bases de datos de Analysis Services](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1d4f0-130">For more information about backup, see [Backup and Restore of Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span></span>  
  
### <a name="exporting-and-importing"></a><span data-ttu-id="1d4f0-131">Exportación e importación</span><span class="sxs-lookup"><span data-stu-id="1d4f0-131">Exporting and Importing</span></span>  
 <span data-ttu-id="1d4f0-132">Exportar y volver a importar después modelos y estructuras de minería de datos utilizando instrucciones DMX es la forma más fácil de mover o hacer copias de seguridad de objetos de minería de datos relacionales individuales.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-132">Exporting and then re-importing mining models and structures by using DMX statements is the easiest way to move or back up individual relational data mining objects.</span></span> <span data-ttu-id="1d4f0-133">Para obtener más información sobre la sintaxis DMX para estas operaciones, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d4f0-133">For more information about the DMX syntax for these operations, see the following topics:</span></span>  
  
-   [<span data-ttu-id="1d4f0-134">EXPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1d4f0-134">EXPORT &#40;DMX&#41;</span></span>](/sql/dmx/export-dmx)  
  
-   [<span data-ttu-id="1d4f0-135">IMPORT &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="1d4f0-135">IMPORT &#40;DMX&#41;</span></span>](/sql/dmx/import-dmx)  
  
 <span data-ttu-id="1d4f0-136">Si especifica la opción INCLUDE DEPENDENCIES, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] también exportará la definición de las vistas del origen de datos necesarias y, al importar el modelo o la estructura, volverá a crear la vista del origen de datos en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-136">If you specify the INCLUDE DEPENDENCIES option, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will also export the definition of any required data source views, and when you import the model or structure, it will re-create the data source view on the target server.</span></span> <span data-ttu-id="1d4f0-137">Cuando termine de importar el modelo, asegúrese de establecer los permisos de minería de datos necesarios en el objeto.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-137">After you have finished importing the model, make sure to set the necessary mining permissions on the object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d4f0-138">No se pueden exportar e importar modelos OLAP utilizando DMX.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-138">You cannot export and import OLAP models by using DMX.</span></span> <span data-ttu-id="1d4f0-139">Si el modelo de minería de datos se basa en un cubo OLAP, debe utilizar la funcionalidad proporcionada por [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para hacer una copia de seguridad y restaurar una base de datos completa, o vuelva a implementar el cubo y sus modelos.</span><span class="sxs-lookup"><span data-stu-id="1d4f0-139">If your mining model is based on an OLAP cube, you must use the functionality provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for backing up and restoring an entire database, or redeploy the cube and its models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d4f0-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d4f0-140">See Also</span></span>  
 [<span data-ttu-id="1d4f0-141">Administración de las soluciones y los objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1d4f0-141">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
  
