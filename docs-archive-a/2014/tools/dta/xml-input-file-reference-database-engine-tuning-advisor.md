---
title: Referencia del archivo de entrada XML (Asistente para la optimización de motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], XML input files
- input file reference [Database Engine Tuning Advisor]
- XML input files [Database Engine Tuning Advisor]
ms.assetid: 05e5e5f0-d6df-4336-b18e-e9bc2835a766
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3bbd38299e4921db33cbaf318883c2f0a9041d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750394"
---
# <a name="xml-input-file-reference-database-engine-tuning-advisor"></a><span data-ttu-id="28f70-102">Referencia del archivo de entrada XML (Asistente para la optimización de motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="28f70-102">XML Input File Reference (Database Engine Tuning Advisor)</span></span>
  [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="28f70-103">puede utilizar un archivo de entrada XML para optimizar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f70-103">Tuning Advisor can use an XML input file to tune a database.</span></span> <span data-ttu-id="28f70-104">Este archivo XML designa las bases de datos, las tablas, los archivos o las tablas de carga de trabajo y las opciones de optimización que se van a utilizar durante la sesión de optimización.</span><span class="sxs-lookup"><span data-stu-id="28f70-104">This XML file designates which databases, tables, workload files or tables, and tuning options to use for the tuning session.</span></span> <span data-ttu-id="28f70-105">También se puede utilizar este archivo para definir una configuración especificada por el usuario para realizar análisis de escenarios condicionales.</span><span class="sxs-lookup"><span data-stu-id="28f70-105">You can also use this file to specify a user-specified configuration to perform "what-if" analysis.</span></span>  
  
 <span data-ttu-id="28f70-106">Un archivo de entrada XML del Asistente para la optimización de [!INCLUDE[ssDE](../../includes/ssde-md.md)] contiene una jerarquía de elementos XML. Cada uno de estos contiene texto u otros elementos que especifican la configuración de la sesión de optimización.</span><span class="sxs-lookup"><span data-stu-id="28f70-106">A [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file contains a hierarchy of XML elements, each containing text or other elements that specify the tuning session settings.</span></span> <span data-ttu-id="28f70-107">El archivo de entrada XML del Asistente para la optimización de [!INCLUDE[ssDE](../../includes/ssde-md.md)] debe ajustarse a los estándares de formato XML correcto, de modo que todos los nombres de elemento distingan entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="28f70-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file must conform to the standards for well-formed XML, so all element names are case sensitive.</span></span> <span data-ttu-id="28f70-108">Los elementos se especifican siguiendo el formato Pascal: el primer carácter y la primera letra de cualquier palabra concatenada siguiente van en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="28f70-108">Elements are specified using Pascal case, which means that the first character is uppercase and the first letter of any subsequent concatenated word is uppercase.</span></span>  
  
 <span data-ttu-id="28f70-109">Todos los valores de los elementos deben ajustarse a las convenciones de nomenclatura XML.</span><span class="sxs-lookup"><span data-stu-id="28f70-109">All element values must conform to XML naming conventions.</span></span> <span data-ttu-id="28f70-110">Para obtener más información acerca de estas convenciones, vea el artículo sobre [contenido de texto XML](https://go.microsoft.com/fwlink/?LinkId=7614) en Microsoft MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="28f70-110">For more information about these conventions, see [XML Textual Content](https://go.microsoft.com/fwlink/?LinkId=7614) in the MSDN Library.</span></span>  
  
 <span data-ttu-id="28f70-111">Tenga en cuenta que esta referencia no es completa.</span><span class="sxs-lookup"><span data-stu-id="28f70-111">Note that this reference is not comprehensive.</span></span> <span data-ttu-id="28f70-112">Para obtener más información acerca de los elementos que se pueden utilizar para definir una entrada XML, vea el esquema XML del Asistente para la optimización de [!INCLUDE[ssDE](../../includes/ssde-md.md)] , DTASchema.xsd.</span><span class="sxs-lookup"><span data-stu-id="28f70-112">For information about all the elements you can use to define XML input, refer to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML schema, DTASchema.xsd.</span></span>  
  
## <a name="xml-declaration"></a><span data-ttu-id="28f70-113">Declaración XML</span><span class="sxs-lookup"><span data-stu-id="28f70-113">XML Declaration</span></span>  
  
-   [<span data-ttu-id="28f70-114">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-114">XML Data &#40;SQL Server&#41;</span></span>](../../relational-databases/xml/xml-data-sql-server.md)  
  
## <a name="dtaxml-root-element"></a><span data-ttu-id="28f70-115">Elemento raíz DTAXML</span><span class="sxs-lookup"><span data-stu-id="28f70-115">DTAXML Root Element</span></span>  
  
-   [<span data-ttu-id="28f70-116">Elemento DTAXML &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-116">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)  
  
## <a name="dtainput-elements"></a><span data-ttu-id="28f70-117">Elementos DTAInput</span><span class="sxs-lookup"><span data-stu-id="28f70-117">DTAInput Elements</span></span>  
  
-   [<span data-ttu-id="28f70-118">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)  
  
-   [<span data-ttu-id="28f70-119">Server &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-119">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)  
  
-   [<span data-ttu-id="28f70-120">Workload &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)  
  
-   [<span data-ttu-id="28f70-121">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-121">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)  
  
-   [<span data-ttu-id="28f70-122">Elemento Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-122">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)  
  
## <a name="server-elements"></a><span data-ttu-id="28f70-123">Elementos Server</span><span class="sxs-lookup"><span data-stu-id="28f70-123">Server Elements</span></span>  
  
-   [<span data-ttu-id="28f70-124">Name &#40;DTA, elemento de Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-124">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)  
  
-   [<span data-ttu-id="28f70-125">Elemento Database para servidor &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-125">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)  
  
## <a name="workload-elements"></a><span data-ttu-id="28f70-126">Elementos Workload</span><span class="sxs-lookup"><span data-stu-id="28f70-126">Workload Elements</span></span>  
  
-   [<span data-ttu-id="28f70-127">File &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-127">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)  
  
-   [<span data-ttu-id="28f70-128">Database &#40;DTA, elemento de Workload&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-128">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)  
  
-   [<span data-ttu-id="28f70-129">EventString &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-129">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)  
  
## <a name="tuning-options-elements"></a><span data-ttu-id="28f70-130">Elementos de opciones de optimización</span><span class="sxs-lookup"><span data-stu-id="28f70-130">Tuning Options Elements</span></span>  
  
-   [<span data-ttu-id="28f70-131">TuningTimeInMin &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-131">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)  
  
-   [<span data-ttu-id="28f70-132">StorageBoundInMB &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-132">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)  
  
-   [<span data-ttu-id="28f70-133">TestServer &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-133">TestServer Element &#40;DTA&#41;</span></span>](testserver-element-dta.md)  
  
-   [<span data-ttu-id="28f70-134">FeatureSet &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-134">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)  
  
-   [<span data-ttu-id="28f70-135">Partitioning &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-135">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)  
  
-   [<span data-ttu-id="28f70-136">DropOnlyMode &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-136">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)  
  
-   [<span data-ttu-id="28f70-137">KeepExisting &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-137">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)  
  
-   [<span data-ttu-id="28f70-138">OnlineIndexOperation &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-138">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)  
  
-   [<span data-ttu-id="28f70-139">DatabaseToConnect &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-139">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)  
  
## <a name="configuration-elements"></a><span data-ttu-id="28f70-140">Elementos Configuration</span><span class="sxs-lookup"><span data-stu-id="28f70-140">Configuration Elements</span></span>  
  
-   [<span data-ttu-id="28f70-141">Server &#40;DTA, elemento de Configuration&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-141">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="28f70-142">Database &#40;DTA, elemento de Configuration&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-142">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="28f70-143">Elemento Recommendation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-143">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)  
  
-   [<span data-ttu-id="28f70-144">Create &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-144">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)  
  
-   [<span data-ttu-id="28f70-145">Index &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-145">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)  
  
-   [<span data-ttu-id="28f70-146">Name &#40;DTA, elemento de Index&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-146">Name Element for Index &#40;DTA&#41;</span></span>](name-element-for-index-dta.md)  
  
-   [<span data-ttu-id="28f70-147">Column &#40;DTA, elemento de Index&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-147">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)  
  
-   [<span data-ttu-id="28f70-148">Elemento Name de Column &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-148">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)  
  
-   [<span data-ttu-id="28f70-149">Filegroup &#40;DTA. elemento de Index&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-149">Filegroup Element for Index &#40;DTA&#41;</span></span>](filegroup-element-for-index-dta.md)  
  
## <a name="database-elements"></a><span data-ttu-id="28f70-150">Elementos Database</span><span class="sxs-lookup"><span data-stu-id="28f70-150">Database Elements</span></span>  
  
-   [<span data-ttu-id="28f70-151">Name &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-151">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)  
  
-   [<span data-ttu-id="28f70-152">Schema &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-152">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)  
  
-   [<span data-ttu-id="28f70-153">Name &#40;DTA, elemento de Schema&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-153">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="28f70-154">Table &#40;DTA, elemento de Schema&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-154">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="28f70-155">Elemento Name de Table &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="28f70-155">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)  
  
## <a name="see-also"></a><span data-ttu-id="28f70-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28f70-156">See Also</span></span>  
 [<span data-ttu-id="28f70-157">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="28f70-157">Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
