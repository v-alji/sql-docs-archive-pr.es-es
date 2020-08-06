---
title: Compilar proyectos de Analysis Services (SSDT) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Analysis Services], building
- Business Intelligence Development Studio, project building [Analysis Services]
ms.assetid: caac03cb-b2b4-4652-8913-3dd39c4b0127
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0e447da20df3d7894df1a9afcf4888a4d9799e37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748383"
---
# <a name="build-analysis-services-projects-ssdt"></a><span data-ttu-id="a0522-102">Generar proyectos de Analysis Services (SSDT)</span><span class="sxs-lookup"><span data-stu-id="a0522-102">Build Analysis Services Projects (SSDT)</span></span>
  <span data-ttu-id="a0522-103">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], los proyectos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se generan de forma muy similar a como se generan los proyectos de programación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a0522-103">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you build an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project much like you build any programming project in Visual Studio.</span></span> <span data-ttu-id="a0522-104">Al generar el proyecto, se crea un conjunto de archivos XML en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="a0522-104">When you build the project, a set of XML files are created in the output directory.</span></span> <span data-ttu-id="a0522-105">Estos archivos XML usan el Lenguaje de scripting de Analysis Services (ASSL), que es el dialecto XML que usan las aplicaciones cliente, incluidos [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , para comunicarse con una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a fin de crear o modificar objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0522-105">These XML files use Analysis Services Scripting Language (ASSL), which is the XML dialect the client applications including [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] use to communicate with an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to create or modify [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects.</span></span> <span data-ttu-id="a0522-106">Los archivos XML se usan para implementar definiciones de objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en una instancia especificada de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0522-106">These XML files are used to deploy [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object definitions in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
## <a name="building-a-project"></a><span data-ttu-id="a0522-107">Generar un proyecto</span><span class="sxs-lookup"><span data-stu-id="a0522-107">Building a Project</span></span>  
 <span data-ttu-id="a0522-108">Al generar un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generará un conjunto completo de archivos XML en la carpeta de salida con todos los comandos ASSL necesarios para generar todos los objetos de base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a0522-108">When you build an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] will build a complete set of XML files in the output folder containing all of the necessary ASSL commands needed to build all of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database objects in the project.</span></span> <span data-ttu-id="a0522-109">Si el proyecto ya se había generado y se había especificado la implementación incremental para la configuración activa, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generará también un archivo XML con los comandos ASSL para realizar una actualización incremental en los objetos implementados.</span><span class="sxs-lookup"><span data-stu-id="a0522-109">If the project was previously built and incremental deployment specified for the active configuration, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] will also build an XML file containing the ASSL commands to perform an incremental update to the deployed objects.</span></span> <span data-ttu-id="a0522-110">Este archivo XML se escribe en la carpeta ..\obj\\<configuración activa\> del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a0522-110">This XML file is written to the ..\obj\\<active configuration\> folder for the project.</span></span> <span data-ttu-id="a0522-111">Las generaciones incrementales pueden ahorrar tiempo al implementar y procesar proyectos o bases de datos de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="a0522-111">Incremental builds can save time when deploying and processing a very large project or database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0522-112">Puede usar el comando Volver a generar todo para omitir la opción de implementación incremental.</span><span class="sxs-lookup"><span data-stu-id="a0522-112">You can use the Rebuild All command to ignore the incremental deployment setting.</span></span>  
  
 <span data-ttu-id="a0522-113">La generación de un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] valida las definiciones de objetos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a0522-113">Building an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project validates the object definitions in the project.</span></span> <span data-ttu-id="a0522-114">La validación incluye los ensamblados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="a0522-114">The validation includes any referenced assemblies.</span></span> <span data-ttu-id="a0522-115">Los errores de generación se muestran en la ventana Lista de tareas, junto con el texto de error de Objetos de administración de análisis (AMO).</span><span class="sxs-lookup"><span data-stu-id="a0522-115">Build errors appear in the Task List window, along with the Analysis Management Objects (AMO) error text.</span></span> <span data-ttu-id="a0522-116">Puede hacer clic en un error para abrir el diseñador necesario para solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="a0522-116">You can click an error to open the designer that is required to fix the error.</span></span>  
  
 <span data-ttu-id="a0522-117">La validación correcta no garantiza que los objetos se puedan crear en el servidor de destino durante la implementación ni se puedan procesar correctamente tras la implementación.</span><span class="sxs-lookup"><span data-stu-id="a0522-117">Successful validation does not guarantee that objects can be created on the destination server during deployment or processed successfully after deployment.</span></span> <span data-ttu-id="a0522-118">Los siguientes problemas pueden evitar la implementación o el procesamiento correctos tras la implementación:</span><span class="sxs-lookup"><span data-stu-id="a0522-118">The following issues can prevent successful deployment or processing after deployment:</span></span>  
  
-   <span data-ttu-id="a0522-119">No se realizan comprobaciones de seguridad en el servidor, por lo que los bloqueos pueden evitar la implementación.</span><span class="sxs-lookup"><span data-stu-id="a0522-119">Security checks for the server are not performed, so locks can prevent deployment.</span></span>  
  
-   <span data-ttu-id="a0522-120">Las ubicaciones físicas no se validan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a0522-120">Physical locations are not validated on the server.</span></span>  
  
-   <span data-ttu-id="a0522-121">Los detalles de las vistas del origen de datos no se comprueban en el origen de datos real del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="a0522-121">Details of data source views are not checked against the actual data source on the destination server.</span></span>  
  
 <span data-ttu-id="a0522-122">Si la validación es correcta, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] genera los archivos XML.</span><span class="sxs-lookup"><span data-stu-id="a0522-122">If validation is successful, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generates the XML files.</span></span> <span data-ttu-id="a0522-123">Después de la generación, la carpeta de salida contiene los archivos descritos en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="a0522-123">After the build, the output folder will contain the files described in the following table.</span></span>  
  
|<span data-ttu-id="a0522-124">Archivos (en la carpeta BIN)</span><span class="sxs-lookup"><span data-stu-id="a0522-124">Files (in bin folder)</span></span>|<span data-ttu-id="a0522-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0522-125">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="a0522-126">*nombre de proyecto*.asdatabase</span><span class="sxs-lookup"><span data-stu-id="a0522-126">*Projectname*.asdatabase</span></span>|<span data-ttu-id="a0522-127">Contiene los elementos ASSL que definen los metadatos de los objetos del proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en un archivo de script de implementación.</span><span class="sxs-lookup"><span data-stu-id="a0522-127">Contains the ASSL elements that define metadata for the objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project in a deployment script file.</span></span> <span data-ttu-id="a0522-128">El motor de implementación utiliza este archivo para implementar los objetos en una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0522-128">This file is used by the deployment engine to deploy the objects to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="a0522-129">*nombre de proyecto*.configsettings</span><span class="sxs-lookup"><span data-stu-id="a0522-129">*Projectname*.configsettings</span></span>|<span data-ttu-id="a0522-130">Contiene las opciones de configuración usadas en la implementación que se pueden modificar directamente o en el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (por ejemplo, la cadena de conexión de los orígenes de datos).</span><span class="sxs-lookup"><span data-stu-id="a0522-130">Contains configuration settings using during deployment that you can modify directly or in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard (for example, the connection string for the data sources).</span></span>|  
|<span data-ttu-id="a0522-131">*nombre de proyecto*.deploymenttargets</span><span class="sxs-lookup"><span data-stu-id="a0522-131">*Projectname*.deploymenttargets</span></span>|<span data-ttu-id="a0522-132">Contiene la configuración de destino utilizada en la implementación que puede modificar directamente o en el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (por ejemplo, los nombres del servidor y la base de datos).</span><span class="sxs-lookup"><span data-stu-id="a0522-132">Contains the destination settings used during deployment that you can modify directly or in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard (for example, the server and database names)</span></span>|  
|<span data-ttu-id="a0522-133">*nombre de proyecto*.deploymentoptions</span><span class="sxs-lookup"><span data-stu-id="a0522-133">*Projectname*.deploymentoptions</span></span>|<span data-ttu-id="a0522-134">Contiene diversas opciones de configuración usadas en la implementación que se pueden modificar directamente o en el Asistente para la implementación de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (por ejemplo, ubicaciones de almacenamiento)</span><span class="sxs-lookup"><span data-stu-id="a0522-134">Contain various option settings used during deployment that you can modify directly or in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard (for example, storage locations)</span></span>|  
|<span data-ttu-id="a0522-135">*AssemblyName* / *DllName.* dll</span><span class="sxs-lookup"><span data-stu-id="a0522-135">*Assemblyname*/*dllname.* dll</span></span>|<span data-ttu-id="a0522-136">Hay carpetas independientes para cada ensamblado al que se hace referencia; cada carpeta contiene el archivo DLL del ensamblado, los ensamblados a los que se hace referencia y los archivos .pdb asociados para la información de depuración del resultado.</span><span class="sxs-lookup"><span data-stu-id="a0522-136">Separate folders for each referenced assembly; each folder contains the DLL for the assembly, any referenced assembly, and any associated .pdb files for output debug information.</span></span>|  
  
|<span data-ttu-id="a0522-137">Archivos (en la carpeta OBJ)</span><span class="sxs-lookup"><span data-stu-id="a0522-137">Files (in obj folder)</span></span>|<span data-ttu-id="a0522-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0522-138">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="a0522-139">\<Configuration Name>\LastBuilt.xml</span><span class="sxs-lookup"><span data-stu-id="a0522-139">\<Configuration Name>\LastBuilt.xml</span></span>|<span data-ttu-id="a0522-140">Contiene la marca de tiempo y el código hash que identifica la última vez que se generó el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0522-140">Contains the time stamp and hash code that identifies the last time the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project was built.</span></span>|  
  
 <span data-ttu-id="a0522-141">Estos archivos XML no contienen \<Create> etiquetas y \<Alter> , que se crean durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="a0522-141">These XML files do not contain \<Create> and \<Alter> tags, which are constructed during deployment.</span></span>  
  
 <span data-ttu-id="a0522-142">Los ensamblados a los que se hace referencia (excepto los ensamblados estándar del sistema y de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ) también se copian en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="a0522-142">Referenced assemblies (excluding standard system and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] assemblies) are also copied to the output directory.</span></span> <span data-ttu-id="a0522-143">Si hay referencias a otros proyectos de una solución, dichos proyectos se generan primero, con la configuración de proyecto adecuada y las dependencias de generación establecidas por las referencias a proyectos; a continuación, los proyectos a los que se hace referencia se copian en la carpeta de salida del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a0522-143">When references are to other projects in a solution, those projects are built first, using the appropriate project configuration and build dependencies established by the project references, and then are copied to the project output folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0522-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0522-144">See Also</span></span>  
 <span data-ttu-id="a0522-145">[Referencia de ASSL&#41; &#40;de lenguaje de scripting Analysis Services](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span><span class="sxs-lookup"><span data-stu-id="a0522-145">[Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span></span>  
 [<span data-ttu-id="a0522-146">Implementar proyectos de Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="a0522-146">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](deploy-analysis-services-projects-ssdt.md)  
  
  