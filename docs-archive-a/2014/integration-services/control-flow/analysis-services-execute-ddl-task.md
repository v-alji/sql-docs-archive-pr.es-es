---
title: Tarea Ejecutar DDL de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.f1
helpviewer_keywords:
- Analysis Services Execute DDL task
- DDL
ms.assetid: 7f25c8c6-b601-41f2-9553-be0a2ee0751a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a75bae174c816cdabd07ce688e068cbadb016b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673207"
---
# <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="dd4fa-102">Tarea Ejecutar DDL de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="dd4fa-102">Analysis Services Execute DDL Task</span></span>
  <span data-ttu-id="dd4fa-103">La tarea Ejecutar DDL de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ejecuta instrucciones del lenguaje de definición de datos (DDL) que pueden crear, quitar o modificar modelos de minería de datos y objetos multidimensionales, como cubos y dimensiones.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task runs data definition language (DDL) statements that can create, drop, or alter mining models and multidimensional objects such as cubes and dimensions.</span></span> <span data-ttu-id="dd4fa-104">Por ejemplo, una instrucción DDL puede crear una partición en el cubo de **Adventure Works** o eliminar una dimensión de [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], la base de datos de ejemplo de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluida en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd4fa-104">For example, a DDL statement can create a partition in the **Adventure Works** cube, or delete a dimension in [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="dd4fa-105">La tarea Ejecutar DDL de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utiliza un administrador de conexiones de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para conectar con una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd4fa-105">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="dd4fa-106">Para más información, consulte [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dd4fa-106">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="dd4fa-107">incluye diversas tareas que realizan operaciones de Business Intelligence, como procesamiento de objetos de análisis y la ejecución de consultas de predicción de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-107">includes a number of tasks that perform business intelligence operations, such as processing analytic objects and running data mining prediction queries.</span></span>  
  
 <span data-ttu-id="dd4fa-108">Para obtener más información sobre tareas de Business Intelligence relacionadas, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd4fa-108">For more information about related business intelligence tasks, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="dd4fa-109">Tarea de procesamiento de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="dd4fa-109">Analysis Services Processing Task</span></span>](analysis-services-processing-task.md)  
  
-   [<span data-ttu-id="dd4fa-110">Tarea Consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="dd4fa-110">Data Mining Query Task</span></span>](data-mining-query-task.md)  
  
## <a name="ddl-statements"></a><span data-ttu-id="dd4fa-111">Instrucciones DDL</span><span class="sxs-lookup"><span data-stu-id="dd4fa-111">DDL Statements</span></span>  
 <span data-ttu-id="dd4fa-112">Las instrucciones de DDL se representan como instrucciones del Lenguaje de scripting de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] (ASSL) y se generan como comandos de XML for Analysis (XMLA).</span><span class="sxs-lookup"><span data-stu-id="dd4fa-112">The DDL statements are represented as statements in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL), and framed in an XML for Analysis (XMLA) command.</span></span>  
  
-   <span data-ttu-id="dd4fa-113">ASSL se usa para definir y describir una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , así como las bases de datos y los objetos de base de datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-113">ASSL is used to define and describe an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and the databases and database objects it contains.</span></span> <span data-ttu-id="dd4fa-114">Para obtener más información, vea [Analysis Services scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span><span class="sxs-lookup"><span data-stu-id="dd4fa-114">For more information, see [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span></span>  
  
-   <span data-ttu-id="dd4fa-115">XMLA es un lenguaje de comandos que se usa para enviar comandos de acción, como Create, Alter o Process, a una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd4fa-115">XMLA is a command language that is used to send action commands, such as Create, Alter, or Process, to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="dd4fa-116">Para más información, vea [Referencia XML for Analysis &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="dd4fa-116">For more information, see [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="dd4fa-117">Si se almacena el código de DDL en un archivo independiente, la tarea Ejecutar DDL de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utiliza un administrador de conexiones de archivos para especificar la ruta del archivo.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-117">If the DDL code is stored in a separate file, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses a File connection manager to specify the path of the file.</span></span> <span data-ttu-id="dd4fa-118">Para obtener más información, consulte [File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="dd4fa-118">For more information, see [File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="dd4fa-119">Como las instrucciones de DDL pueden contener contraseñas y otros datos confidenciales, un paquete que contenga una o varias tareas Ejecutar DDL de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] debe usar el nivel de protección de paquetes `EncryptAllWithUserKey` o `EncryptAllWithPassword`.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-119">Because DDL statements can contain passwords and other sensitive information, a package that contains one or more [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL tasks should use the package protection level `EncryptAllWithUserKey` or `EncryptAllWithPassword`.</span></span> <span data-ttu-id="dd4fa-120">Para obtener más información, vea [Paquetes de Integration Services &#40;SSIS&#41;](../integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="dd4fa-120">For more information, see [Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md).</span></span>  
  
### <a name="ddl-examples"></a><span data-ttu-id="dd4fa-121">Ejemplos de DDL</span><span class="sxs-lookup"><span data-stu-id="dd4fa-121">DDL Examples</span></span>  
 <span data-ttu-id="dd4fa-122">Las tres instrucciones DDL siguientes se generaron mediante objetos de scripting de [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluida en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd4fa-122">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="dd4fa-123">La siguiente instrucción DDL elimina la dimensión **Promotion** .</span><span class="sxs-lookup"><span data-stu-id="dd4fa-123">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="dd4fa-124">La siguiente instrucción DDL procesa el cubo de [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd4fa-124">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="dd4fa-125">La siguiente instrucción DDL crea el modelo de minería **Forecasting** .</span><span class="sxs-lookup"><span data-stu-id="dd4fa-125">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
 <span data-ttu-id="dd4fa-126">Las tres instrucciones DDL siguientes se generaron mediante objetos de scripting de [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluida en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd4fa-126">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="dd4fa-127">La siguiente instrucción DDL elimina la dimensión **Promotion** .</span><span class="sxs-lookup"><span data-stu-id="dd4fa-127">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="dd4fa-128">La siguiente instrucción DDL procesa el cubo de [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd4fa-128">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="dd4fa-129">La siguiente instrucción DDL crea el modelo de minería **Forecasting** .</span><span class="sxs-lookup"><span data-stu-id="dd4fa-129">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
## <a name="configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="dd4fa-130">Configuración de la tarea Ejecutar DDL de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="dd4fa-130">Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="dd4fa-131">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="dd4fa-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="dd4fa-132">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd4fa-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="dd4fa-133">Editor de la tarea Ejecutar DDL de Analysis Services &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="dd4fa-133">Analysis Services Execute DDL Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="dd4fa-134">Editor de la tarea Ejecutar DDL de Analysis Services &#40;página DDL&#41;</span><span class="sxs-lookup"><span data-stu-id="dd4fa-134">Analysis Services Execute DDL Task Editor &#40;DDL Page&#41;</span></span>](../analysis-services-execute-ddl-task-editor-ddl-page.md)  
  
-   [<span data-ttu-id="dd4fa-135">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="dd4fa-135">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="dd4fa-136">Para obtener más información sobre cómo configurar estas propiedades en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="dd4fa-136">For more information about setting these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="dd4fa-137">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="dd4fa-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="dd4fa-138">Configuración mediante programación de la tarea Ejecutar DDL de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="dd4fa-138">Programmatic Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="dd4fa-139">Para obtener más información sobre cómo establecer estas propiedades mediante programación, haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd4fa-139">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.DataTransformationServices.Tasks.DTSProcessingTask.ASExecuteDDLTask>  
  
  
