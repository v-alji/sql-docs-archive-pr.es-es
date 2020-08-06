---
title: Importar un proyecto de minería de datos mediante el Asistente para importación de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 62bc9fc5-c6ff-4517-b598-d92df76743a2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5b39062cc5bc5401a1746f35e98ea643db2d16c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671265"
---
# <a name="import-a-data-mining-project-using-the-analysis-services-import-wizard"></a><span data-ttu-id="cc866-102">Cantidad un proyecto de minería de datos mediante el Asistente para la importación de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="cc866-102">Import a Data Mining Project using the Analysis Services Import Wizard</span></span>
  <span data-ttu-id="cc866-103">En este tema se describe cómo crear un nuevo proyecto de minería de datos mediante la importación de los metadatos de un proyecto de minería de datos existente en otro servidor, usando para ello la plantilla de proyecto **Importar del servidor (multidimensional y minería de datos)**, en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc866-103">This topic describes how to create a new data mining project by importing the metadata from an existing data mining project on another server, using the template, **Import from Server (Multidimensional and Data Mining) Project**, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="import-data-sources-mining-structures-and-mining-models-from-an-existing-data-mining-project"></a><span data-ttu-id="cc866-104">Importar los orígenes de datos, estructuras de minería de datos y modelos de minería de datos de un proyecto de minería de datos existente</span><span class="sxs-lookup"><span data-stu-id="cc866-104">Import data sources, mining structures, and mining models from an existing data mining project</span></span>  
 <span data-ttu-id="cc866-105">Al usar la plantilla **importar del proyecto de servidor (multidimensional y minería de datos)**, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] crea un nuevo proyecto de minería de datos y, a continuación, copia los metadatos del proyecto de minería de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="cc866-105">When you use the template, **Import from Server (Multidimensional and Data Mining) Project**, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates a new data mining project, and then copies the metadata from the specified data mining project.</span></span> <span data-ttu-id="cc866-106">El nuevo proyecto contiene los mismos orígenes de datos, vistas del origen de datos, estructuras de minería de datos y modelos de minería de datos que la base de datos de los que los importó.</span><span class="sxs-lookup"><span data-stu-id="cc866-106">The new project contains the same data sources, data source views, mining structures, and mining models as the ssASnoversion database that you imported from.</span></span> <span data-ttu-id="cc866-107">Sin embargo, el proyecto no se puede utilizar hasta que se haya actualizado ciertas propiedades y haya procesado los objetos según se indica:</span><span class="sxs-lookup"><span data-stu-id="cc866-107">However, the project cannot be used until you have updated certain properties and processed the objects as described:</span></span>  
  
-   <span data-ttu-id="cc866-108">Los propios datos no se copian del servidor de origen al nuevo proyecto de minería de datos; solo se importan las definiciones de los orígenes de datos y las vistas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cc866-108">The data itself is not copied from the source server to the new data mining project-only the definitions of the data sources and data source views are imported.</span></span> <span data-ttu-id="cc866-109">Por consiguiente, cuando el proceso de importación haya finalizado y los objetos se hayan creado, debe rellenar los objetos con datos entrenando los modelos dependientes y las estructuras de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="cc866-109">Therefore, after the import process has completed, and the objects have been created, you must populate the objects with data by training the mining structures and dependent models.</span></span> <span data-ttu-id="cc866-110">Puede utilizar el comando **Procesar todo** del Diseñador de minería de datos para entrenar los modelos y las estructuras.</span><span class="sxs-lookup"><span data-stu-id="cc866-110">You can use the command **Process All** in Data Mining Designer to train the models and structures.</span></span>  
  
-   <span data-ttu-id="cc866-111">Si importa un proyecto creado en una versión anterior de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], el origen de datos puede utilizar proveedores que no estén instalados en el servidor en el que vaya a importar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="cc866-111">If you are importing a project that was created in a previous version of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the data source might use providers that are not installed on the server to which you are importing the project.</span></span> <span data-ttu-id="cc866-112">Si surgen errores al procesar las estructuras de minería de datos importadas, haga clic con el botón derecho en cada origen de datos y seleccione **Abrir diseñador** para modificar la cadena de conexión y revisar las propiedades del proveedor.</span><span class="sxs-lookup"><span data-stu-id="cc866-112">If you encounter errors when processing the imported mining structures, right-click each data source and select **Open Designer** to edit the connection string and review the provider properties.</span></span>  
  
     <span data-ttu-id="cc866-113">En este momento, puede que también deba comprobar que la cuenta que utiliza para procesar los objetos de minería de datos o los modelos de minería de datos de consulta tengan los permisos necesarios en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="cc866-113">At this time, you might also need to verify that the account you are using to process the data mining objects or query data mining models has the necessary permissions on the data source.</span></span>  
  
-   <span data-ttu-id="cc866-114">De forma predeterminada, cuando se importa un proyecto, la base de datos del área de trabajo se establece en el host local, o cualquier instancia predeterminada se configura como **Servidor de destino predeterminado** en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc866-114">By default, when you import a project, the workspace database is set to localhost, or whatever default instance is configured as the **Default Target Server** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="cc866-115">Para establecer esta propiedad, en el menú **Opciones** , seleccione **Diseñadores de Business Intelligence**, seleccione **Analysis Services**y, a continuación, seleccione **General**.</span><span class="sxs-lookup"><span data-stu-id="cc866-115">To set this property, from the **Options** menu, select **Business Intelligence Designers**, select **Analysis Services**, and then select **General**.</span></span>  
  
     <span data-ttu-id="cc866-116">Tenga en cuenta que, en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], hay otra opción distinta que puede establecer para configurar el servidor de implementación predeterminado para los proyectos de modelos tabulares de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc866-116">Note that, in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], there is another, separate option that you can set to configure the default deployment server for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tabular model projects.</span></span> <span data-ttu-id="cc866-117">El valor, **Servidor de implementación predeterminado**, determina la base de datos predeterminada del área de trabajo de los proyectos de modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="cc866-117">The setting, **Default Deployment Server**, determines the default workspace database for tabular model projects.</span></span> <span data-ttu-id="cc866-118">No puede utilizar las instancias que admitan modelos tabulares para proyectos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="cc866-118">You cannot use instances that support tabular models for data mining projects</span></span>  
  
     <span data-ttu-id="cc866-119">Si no puede cambiar la base de datos predeterminada de implementación para utilizar una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se ejecuta en modo MDX o de minería de datos, siempre puede especificar la base de datos de implementación mediante el cuadro de diálogo **Propiedades del proyecto** .</span><span class="sxs-lookup"><span data-stu-id="cc866-119">If you cannot change the default deployment database to use an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] running in multidimensional or data mining mode, you can always specify the deployment database by using the **Project Properties** dialog box.</span></span>  
  
#### <a name="to-create-a-new-data-mining-project-by-importing-an-existing-data-mining-project"></a><span data-ttu-id="cc866-120">Para crear un nuevo proyecto de minería de datos importando un proyecto de minería de datos existente</span><span class="sxs-lookup"><span data-stu-id="cc866-120">To create a new data mining project by importing an existing data mining project</span></span>  
  
1.  <span data-ttu-id="cc866-121">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], en el menú **Archivo** , haga clic en **Nuevo**y, a continuación, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="cc866-121">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="cc866-122">En el cuadro de diálogo **Nuevo proyecto** , en **Plantillas instaladas**, haga clic en **Business Intelligence**, haga clic en **Analysis Services**y, después, haga clic en **Importar del servidor (multidimensional y minería de datos)**.</span><span class="sxs-lookup"><span data-stu-id="cc866-122">In the **New Project** dialog box, under **Installed Templates**, click **Business Intelligence**, click **Analysis Services**, and then click **Import from Server (Multidimensional/Data Mining)**.</span></span>  
  
3.  <span data-ttu-id="cc866-123">En **Nombre**, escriba un nombre para el proyecto, después especifique una ubicación y un nombre de solución, y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cc866-123">For **Name**, type a name for the project, then specify a location and solution name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="cc866-124">Se inicia el **Asistente para importar bases de datos de Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="cc866-124">The **Import Analysis Services Database wizard** starts.</span></span> <span data-ttu-id="cc866-125">Haga clic en ACEPTAR en la página de bienvenida para continuar.</span><span class="sxs-lookup"><span data-stu-id="cc866-125">Click OK on the Welcome page to proceed.</span></span>  
  
4.  <span data-ttu-id="cc866-126">En la página **Seleccionar base de datos de origen**, en **Servidor**, especifique la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contenga la solución que desea importar.</span><span class="sxs-lookup"><span data-stu-id="cc866-126">On the page, **Select Source Database**, for **Server**, specify the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that contains the solution you want to import.</span></span>  
  
     <span data-ttu-id="cc866-127">En **Base de datos**, elija la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contenga los objetos de minería de datos que desea importar.</span><span class="sxs-lookup"><span data-stu-id="cc866-127">For **Database**, choose the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains the data mining objects you want to import.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="cc866-128">No puede especificar los objetos que desea importar; al elegir una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , se importan todos los objetos multidimensionales y de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="cc866-128">You cannot specify the objects you want to import; when you choose an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, all multidimensional and data mining objects are imported.</span></span>  
  
     <span data-ttu-id="cc866-129">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="cc866-129">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="cc866-130">La página **Finalización del asistente**muestra el progreso de la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="cc866-130">The page, **Completing the Wizard**, displays the progress of the import operation.</span></span> <span data-ttu-id="cc866-131">No puede cancelar la operación ni cambiar los objetos que se están importando.</span><span class="sxs-lookup"><span data-stu-id="cc866-131">You cannot cancel the operation or change the objects that are being imported.</span></span> <span data-ttu-id="cc866-132">Haga clic **Finalizar** cuando haya terminado.</span><span class="sxs-lookup"><span data-stu-id="cc866-132">Click **Finish** when done.</span></span>  
  
     <span data-ttu-id="cc866-133">El nuevo proyecto se abre de modo automático mediante [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc866-133">The new project is automatically opened using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc866-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc866-134">See Also</span></span>  
 [<span data-ttu-id="cc866-135">Propiedades del proyecto &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="cc866-135">Project Properties &#40;SSAS Tabular&#41;</span></span>](../tabular-models/properties-ssas-tabular.md)  
  
  