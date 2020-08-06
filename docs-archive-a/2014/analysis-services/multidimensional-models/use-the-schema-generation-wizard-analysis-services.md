---
title: Usar el Asistente para generar esquemas (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Schema Generation Wizard, steps
- relational schema [Analysis Services], Schema Generation Wizard
ms.assetid: 8c710745-d41d-4c31-b6a2-2956229df75a
author: minewiskan
ms.author: owend
ms.openlocfilehash: fa65c2c6f377a375d0fc6aa8298cdec749805b6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674388"
---
# <a name="use-the-schema-generation-wizard-analysis-services"></a><span data-ttu-id="79ee6-102">Usar el Asistente para generar esquemas (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="79ee6-102">Use the Schema Generation Wizard (Analysis Services)</span></span>
  <span data-ttu-id="79ee6-103">El Asistente para generar esquemas requiere una cantidad limitada de información durante la fase de generación.</span><span class="sxs-lookup"><span data-stu-id="79ee6-103">The Schema Generation Wizard requires a limited amount of information during the generation phase.</span></span> <span data-ttu-id="79ee6-104">La mayoría de la información que el Asistente para generar esquemas requiere para generar esquemas relacionales se extrae de los cubos y las dimensiones de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se han creado previamente en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="79ee6-104">Most of the information that the Schema Generation Wizard requires for generating relational schemas is extracted from the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cubes and dimensions that you already created in the project.</span></span> <span data-ttu-id="79ee6-105">Además, puede personalizar el modo en que se genera el esquema de la base de datos del área de asunto y cómo se asignan nombres a los objetos del esquema.</span><span class="sxs-lookup"><span data-stu-id="79ee6-105">Additionally, you can customize how the subject area database schema is generated and how objects in the schema are named.</span></span>  
  
## <a name="start-the-wizard"></a><span data-ttu-id="79ee6-106">Iniciar el asistente</span><span class="sxs-lookup"><span data-stu-id="79ee6-106">Start the Wizard</span></span>  
 <span data-ttu-id="79ee6-107">Puede abrir el Asistente para generar esquemas desde [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] de varias formas:</span><span class="sxs-lookup"><span data-stu-id="79ee6-107">You can open the Schema Generation Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in several different ways:</span></span>  
  
-   <span data-ttu-id="79ee6-108">Haga clic con el botón derecho en el objeto de proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y, después, haga clic en **Generar esquema relacional** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="79ee6-108">Right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project object and then click **Generate Relational Schema** from the context menu.</span></span>  
  
-   <span data-ttu-id="79ee6-109">Haga clic en el objeto de proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y, a continuación, en **Generar esquema relacional** en el menú **Base de datos** .</span><span class="sxs-lookup"><span data-stu-id="79ee6-109">Click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project object, and then click **Generate Relational Schema** from the **Database** menu.</span></span>  
  
-   <span data-ttu-id="79ee6-110">Inicie el asistente desde el Asistente para dimensiones haciendo clic en la casilla **Generar el esquema ahora** en la última página del asistente.</span><span class="sxs-lookup"><span data-stu-id="79ee6-110">Start the wizard from within the Dimension Wizard by clicking the **Generate Schema Now** check box on the last page of the wizard.</span></span>  
  
## <a name="step-1-specify-targets"></a><span data-ttu-id="79ee6-111">Paso 1: especificar los destinos</span><span class="sxs-lookup"><span data-stu-id="79ee6-111">Step 1: Specify Targets</span></span>  
 <span data-ttu-id="79ee6-112">Debe especificar la vista del origen de datos (DSV) en que desea que el Asistente para generar esquemas genere el esquema para la base de datos del área de asunto.</span><span class="sxs-lookup"><span data-stu-id="79ee6-112">You must specify the data source view (DSV) in which you want the Schema Generation Wizard to generate the schema for the subject area database.</span></span> <span data-ttu-id="79ee6-113">Aunque puede seleccionar una DSV existente, lo habitual es crear una nueva basada en un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="79ee6-113">Although you can select an existing DSV, typically you create a new one based on a data source.</span></span> <span data-ttu-id="79ee6-114">El origen de datos se puede crear en función de una conexión nueva o una existente, o bien basándose en otro objeto.</span><span class="sxs-lookup"><span data-stu-id="79ee6-114">You can create the data source based on an existing or a new connection, or based on another object.</span></span> <span data-ttu-id="79ee6-115">El Asistente para generar esquemas crea el esquema para la base de datos del área de asunto en la base de datos a la que se hace referencia en el origen de datos, así como en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="79ee6-115">The Schema Generation Wizard generates the schema for the subject area database in the database referenced by the data source, as well as the data source view.</span></span> <span data-ttu-id="79ee6-116">El Asistente para generar esquemas no crea la propia base de datos del área de asunto; lo que hace es crear el esquema relacional para que los cubos y las dimensiones sean compatibles con la base de datos existente que se especifique.</span><span class="sxs-lookup"><span data-stu-id="79ee6-116">The Schema Generation Wizard does not create the subject area database itself; instead, the wizard creates the relational schema to support the cubes and dimensions in an existing database that you specify.</span></span>  
  
 <span data-ttu-id="79ee6-117">Cuando el Asistente para generar esquemas crea los objetos subyacentes, enlaza las dimensiones y los cubos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] a las tablas y las columnas generadas mediante enlaces con estilo de vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="79ee6-117">When the Schema Generation Wizard generates the underlying objects, it binds the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimensions and cubes to the generated tables and columns by using data source view-style bindings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79ee6-118">Para cancelar el enlace entre las dimensiones y los cubos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de los objetos generados previamente, elimine la vista del origen de datos a la que están enlazados los cubos y las dimensiones de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y, a continuación, defina una nueva vista del origen de datos para los cubos y las dimensiones mediante el Asistente para generar esquemas.</span><span class="sxs-lookup"><span data-stu-id="79ee6-118">To unbind [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimensions and cubes from previously generated objects, delete the data source view to which the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cubes and dimensions are bound, and then define a new data source view for the cubes and dimensions by using the Schema Generation Wizard.</span></span>  
  
## <a name="step-3-specify-schema-options-for-the-subject-area-database"></a><span data-ttu-id="79ee6-119">Paso 3: especificar opciones de esquema para la base de datos del área de asunto</span><span class="sxs-lookup"><span data-stu-id="79ee6-119">Step 3: Specify Schema Options for the Subject Area Database</span></span>  
 <span data-ttu-id="79ee6-120">El Asistente para generar esquemas proporciona una serie de opciones para definir el esquema que se genera para la base de datos del área de asunto.</span><span class="sxs-lookup"><span data-stu-id="79ee6-120">The Schema Generation Wizard provides a number of options for defining the schema that is generated for the subject area database.</span></span> <span data-ttu-id="79ee6-121">Estas opciones se pueden especificar en la página **Opciones de esquema de la base de datos del área de asunto** del asistente.</span><span class="sxs-lookup"><span data-stu-id="79ee6-121">You can specify these options on the **Subject Area Database Schema Options** page of the wizard.</span></span>  
  
### <a name="specifying-the-schema-owner"></a><span data-ttu-id="79ee6-122">Especificar el propietario del esquema</span><span class="sxs-lookup"><span data-stu-id="79ee6-122">Specifying the Schema Owner</span></span>  
 <span data-ttu-id="79ee6-123">Para especificar el propietario del esquema, establezca el valor de **Esquema de propiedad** en una cadena válida.</span><span class="sxs-lookup"><span data-stu-id="79ee6-123">You can specify the owner of the schema by setting the value of **Owning schema** to a valid string.</span></span> <span data-ttu-id="79ee6-124">El propietario predeterminado del esquema es el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , pero puede especificar el propietario que desee.</span><span class="sxs-lookup"><span data-stu-id="79ee6-124">The default owner of the schema is the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, but you can specify any desired schema owner.</span></span>  
  
### <a name="specifying-primary-keys-indexes-and-constraints"></a><span data-ttu-id="79ee6-125">Especificar claves principales, índices y restricciones</span><span class="sxs-lookup"><span data-stu-id="79ee6-125">Specifying Primary Keys, Indexes, and Constraints</span></span>  
 <span data-ttu-id="79ee6-126">El Asistente para generar esquemas crea de forma predeterminada una restricción de clave principal en cada tabla de dimensiones de la base de datos del área de asunto.</span><span class="sxs-lookup"><span data-stu-id="79ee6-126">The Schema Generation Wizard by default creates a primary key constraint in each dimension table in the subject area database.</span></span> <span data-ttu-id="79ee6-127">La clave principal corresponde al atributo que se designa como atributo clave en la dimensión de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] correspondiente.</span><span class="sxs-lookup"><span data-stu-id="79ee6-127">The primary key corresponds to the attribute that is designated as the key attribute in the corresponding [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dimension.</span></span> <span data-ttu-id="79ee6-128">Esta restricción mejora el rendimiento del procesamiento en la mayoría de entornos, con un costo mínimo.</span><span class="sxs-lookup"><span data-stu-id="79ee6-128">This constraint improves processing performance in most environments, with minimal cost.</span></span> <span data-ttu-id="79ee6-129">Las claves principales lógicas siempre se crean en la vista del origen de datos, incluso aunque se elija no crear la clave principal en la base de datos del área de asunto.</span><span class="sxs-lookup"><span data-stu-id="79ee6-129">Logical primary keys are always created in the data source view, even if you choose not to create the primary key in the subject area database.</span></span> <span data-ttu-id="79ee6-130">Para definir restricciones de clave principal en tablas de dimensiones, seleccione **Crear claves principales en tablas de dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="79ee6-130">To define primary key constraints on dimension tables, select **Create primary keys on dimension tables**.</span></span>  
  
 <span data-ttu-id="79ee6-131">De forma predeterminada, el asistente también crea índices en las columnas de clave externa de cada tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="79ee6-131">The wizard by default also creates indexes on the foreign key columns in each fact table.</span></span> <span data-ttu-id="79ee6-132">Estos índices mejoran el rendimiento del procesamiento en la mayoría de entornos.</span><span class="sxs-lookup"><span data-stu-id="79ee6-132">These indexes improve processing performance in most environments.</span></span> <span data-ttu-id="79ee6-133">El rendimiento mejora habitualmente porque las consultas de procesamiento que genera [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para recuperar nuevos datos de la base de datos del área de asunto suelen incluir un número importante de instrucciones de combinación entre la tabla de hechos y las tablas de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="79ee6-133">Performance is typically improved because the processing queries that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] generates to retrieve new data from the subject area database typically include a significant number of join statements between the fact table and the dimension tables.</span></span> <span data-ttu-id="79ee6-134">Para definir índices en las columnas de clave externa de cada tabla de hechos, seleccione **Crear índices**.</span><span class="sxs-lookup"><span data-stu-id="79ee6-134">To define indexes on the foreign key columns in each fact table, select **Create indexes**.</span></span>  
  
 <span data-ttu-id="79ee6-135">Por último, de forma predeterminada el asistente impone la integridad referencial entre la tabla de hechos y cada una de las tablas de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="79ee6-135">Finally, the wizard by default enforces referential integrity between the fact table and each of the dimension tables.</span></span> <span data-ttu-id="79ee6-136">Aunque decida no imponer la integridad referencial, el Asistente para generar esquemas creará estas relaciones en la base de datos y la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="79ee6-136">If you choose not to enforce referential integrity, the Schema Generation Wizard still creates these relationships in the database and the data source view.</span></span> <span data-ttu-id="79ee6-137">Para imponer la integridad referencial, seleccione **Exigir integridad referencial**.</span><span class="sxs-lookup"><span data-stu-id="79ee6-137">To enforce referential integrity, select **Enforce referential integrity**.</span></span>  
  
### <a name="preserving-data-for-incremental-generation"></a><span data-ttu-id="79ee6-138">Conservar datos para la generación incremental</span><span class="sxs-lookup"><span data-stu-id="79ee6-138">Preserving Data for Incremental Generation</span></span>  
 <span data-ttu-id="79ee6-139">De forma predeterminada, el Asistente para generar esquemas trata de conservar los datos cuando se vuelve a generar el esquema de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="79ee6-139">The Schema Generation Wizard by default attempts to preserve data when the database schema is regenerated.</span></span> <span data-ttu-id="79ee6-140">Si el Asistente para generar esquemas tiene que eliminar alguna fila debido a un cambio en el esquema, se muestra una advertencia antes de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="79ee6-140">If the Schema Generation Wizard has to delete any rows because of a schema change, you receive a warning before the rows are deleted.</span></span> <span data-ttu-id="79ee6-141">Por ejemplo, es posible que haya que eliminar filas para resolver problemas de integridad referencial por haber quitado una dimensión o porque haya cambiado un tipo de datos al modificar un atributo de dimensión.</span><span class="sxs-lookup"><span data-stu-id="79ee6-141">For example, rows may have to be deleted to solve referential integrity issues because you dropped a dimension or because a data type changed when you changed a dimension attribute.</span></span> <span data-ttu-id="79ee6-142">Para conservar los datos cuando se vuelve a generar el esquema de la base de datos, seleccione **Mantener los datos al volver a generar**.</span><span class="sxs-lookup"><span data-stu-id="79ee6-142">To preserve data when the database schema is regenerated, select **Preserve data on regeneration**.</span></span>  
  
## <a name="step-4-specify-naming-conventions"></a><span data-ttu-id="79ee6-143">Paso 4: especificar convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="79ee6-143">Step 4: Specify Naming Conventions</span></span>  
 <span data-ttu-id="79ee6-144">En la página **Especificar convenciones de nomenclatura** del Asistente para generar esquemas, puede definir las convenciones de nomenclatura que usará el asistente a la hora de crear ciertos objetos de la base de datos del área de asunto.</span><span class="sxs-lookup"><span data-stu-id="79ee6-144">You can define the naming conventions that the Schema Generation Wizard uses when generating certain objects in the subject area database on the **Specify Naming Conventions** page of the wizard.</span></span> <span data-ttu-id="79ee6-145">Para obtener más información sobre las opciones disponibles en la página **Especificar convenciones de nomenclatura**, vea [Especificar convenciones de nomenclatura &#40;Asistente para generar esquemas&#41; &#40;Analysis Services - Datos multidimensionales&#41;](../specify-naming-conventions-schema-generation-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="79ee6-145">For more information about the options available on the **Specify Naming Conventions** page, see [Specify Naming Conventions &#40;Schema Generation Wizard&#41; &#40;Analysis Services - Multidimensional Data&#41;](../specify-naming-conventions-schema-generation-analysis-services-multidimensional-data.md).</span></span>  
  
  