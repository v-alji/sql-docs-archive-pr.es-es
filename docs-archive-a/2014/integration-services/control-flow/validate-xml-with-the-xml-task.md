---
title: Validar XML con la tarea XML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- XML validation
- XML, validating
ms.assetid: 224fc025-c21f-4d43-aa9d-5ffac337f9b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 633a269f53c85353c956b33bff8fd3af518dad56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662170"
---
# <a name="validate-xml-with-the-xml-task"></a><span data-ttu-id="3ecf8-102">Validate XML with the XML Task</span><span class="sxs-lookup"><span data-stu-id="3ecf8-102">Validate XML with the XML Task</span></span>
  <span data-ttu-id="3ecf8-103">Valide documentos XML y obtenga una salida de error enriquecida habilitando la propiedad `ValidationDetails` de la tarea XML.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-103">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span>

 <span data-ttu-id="3ecf8-104">La siguiente captura de pantalla muestra el **Editor de la tarea XML** con la configuración necesaria para la validación de XML con la salida de error completa.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-104">The following screen shot shows the **XML Task Editor** with the settings required for XML validation with rich error output.</span></span>

 <span data-ttu-id="3ecf8-105">![Propiedades de la tarea XML en el Editor de la tarea XML](../media/xmltaskproperties.jpg "Propiedades de la tarea XML en el Editor de la tarea XML")</span><span class="sxs-lookup"><span data-stu-id="3ecf8-105">![XML task properties in the XML Task Editor](../media/xmltaskproperties.jpg "XML task properties in the XML Task Editor")</span></span>

 <span data-ttu-id="3ecf8-106">Antes de que la propiedad `ValidationDetails` estuviera disponible, la validación de XML efectuada mediante la tarea XML solo devolvía un resultado true o false, sin información sobre errores o sus ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-106">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="3ecf8-107">Ahora, cuando se establece `ValidationDetails` en true, el archivo de salida contiene información detallada sobre cada uno de los errores, incluido el número de línea y la posición.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-107">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="3ecf8-108">Puede usar esta información para comprender, buscar y corregir errores en documentos XML.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-108">You can use this information to understand, locate, and fix errors in XML documents.</span></span>

 <span data-ttu-id="3ecf8-109">La funcionalidad de validación de XML se escala fácilmente en el caso de documentos XML grandes y un gran número de errores.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-109">The XML validation functionality scales easily for large XML documents and large numbers of errors.</span></span> <span data-ttu-id="3ecf8-110">Puesto que el propio archivo de salida está en formato XML, puede consultar y analizar la salida.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-110">Since the output file itself is in XML format, you can query and analyze the output.</span></span> <span data-ttu-id="3ecf8-111">Por ejemplo, si la salida contiene un gran número de errores, puede agruparlos mediante una consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] , como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-111">For example, if the output contains a large number of errors, you can group the errors by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, as described in this topic.</span></span>

> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="3ecf8-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) ha introducido la `ValidationDetails` propiedad en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="3ecf8-113">La propiedad también está disponible en [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] y en SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-113">The property is also available in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>

## <a name="sample-output-for-xml-thats-valid"></a><span data-ttu-id="3ecf8-114">Ejemplo de salida de un archivo XML que no es válido</span><span class="sxs-lookup"><span data-stu-id="3ecf8-114">Sample output for XML that's valid</span></span>
 <span data-ttu-id="3ecf8-115">Este es un ejemplo de archivo de salida con los resultados de validación de un archivo XML válido.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-115">Here is a sample output file with validation results for a valid XML file.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>true</result>
        <errors>0</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:27:22.087</startTime>
        <endTime>2015-05-28T10:29:07.007</endTime>
        <xmlFile>d:\Temp\TestData.xml</xmlFile>
        <xsdFile>d:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages />
</root>
```

## <a name="sample-output-for-xml-thats-not-valid"></a><span data-ttu-id="3ecf8-116">Ejemplo de salida de un archivo XML que no es válido</span><span class="sxs-lookup"><span data-stu-id="3ecf8-116">Sample output for XML that's not valid</span></span>
 <span data-ttu-id="3ecf8-117">Este es un ejemplo de archivo de salida con los resultados de validación de un archivo XML que contiene un pequeño número de errores.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-117">Here is a sample output file with validation results for an XML file that contains a small number of errors.</span></span> <span data-ttu-id="3ecf8-118">El texto de los elementos \<error> se ha ajustado para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-118">The text of the \<error> elements has been wrapped for readability.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>false</result>
        <errors>2</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:45:09.538</startTime>
        <endTime>2015-05-28T10:45:09.558</endTime>
        <xmlFile>C:\Temp\TestData.xml</xmlFile>
        <xsdFile>C:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages>
        <error line="5" position="26">The 'ApplicantRole' element is invalid - The value 'wer3' is invalid
    according to its datatype 'ApplicantRoleType' - The Enumeration constraint failed.</error>
        <error line="16" position="28">The 'Phone' element is invalid - The value 'we3056666666' is invalid
     according to its datatype 'phone' - The Pattern constraint failed.</error>
    </messages>
</root>
```

## <a name="analyze-xml-validation-output-with-a-transact-sql-query"></a><span data-ttu-id="3ecf8-119">Analizar la salida de validación XML con una consulta de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3ecf8-119">Analyze XML validation output with a Transact-SQL query</span></span>
 <span data-ttu-id="3ecf8-120">Si la salida de validación XML contiene un gran número de errores, puede usar una consulta de [!INCLUDE[tsql](../../../includes/tsql-md.md)] para cargar la salida en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ecf8-120">If the output of XML validation contains a large number of errors, you can use a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query to load the output in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="3ecf8-121">Luego, puede analizar la lista de errores con todas las funcionalidades del lenguaje T-SQL, como WHERE, GROUP BY, ORDER BY, JOIN, etc.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-121">Then you can analyze the error list with all the capabilities of the T-SQL language including WHERE, GROUP BY, ORDER BY, JOIN, and so forth.</span></span>

```sql
DECLARE @xml XML;

SELECT @xml = XmlDoc   
FROM OPENROWSET (BULK N'C:\Temp\XMLValidation_2016-02-212T10-41-00.xml', SINGLE_BLOB) AS Tab(XmlDoc);

-- Query # 1, flat list of errors
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT * FROM rs;
-- WHERE error LIKE '%whatever_string%'

-- Query # 2, count of errors grouped by the error message
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT COALESCE(error,'Total # of errors:') AS [error], COUNT(*) AS [counter]
FROM rs
GROUP BY GROUPING SETS ((error), ())
ORDER BY 2 DESC, COALESCE(error, 'Z');

```

 <span data-ttu-id="3ecf8-122">Este es el resultado de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] de la segunda consulta de ejemplo que se muestra en el texto anterior.</span><span class="sxs-lookup"><span data-stu-id="3ecf8-122">Here is the result in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] of the second sample query shown in the preceding text.</span></span>

 <span data-ttu-id="3ecf8-123">![Consulta para agrupar errores de XML en Management Studio](../media/queryforxmlerrors.jpg "Consulta para agrupar errores de XML en Management Studio")</span><span class="sxs-lookup"><span data-stu-id="3ecf8-123">![Query to group XML errors in Management Studio](../media/queryforxmlerrors.jpg "Query to group XML errors in Management Studio")</span></span>

## <a name="see-also"></a><span data-ttu-id="3ecf8-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ecf8-124">See Also</span></span>
 <span data-ttu-id="3ecf8-125">Editor de la tarea XML de la [tarea xml](xml-task.md) [&#40;página general&#41;](../xml-task-editor-general-page.md)</span><span class="sxs-lookup"><span data-stu-id="3ecf8-125">[XML Task](xml-task.md) [XML Task Editor &#40;General Page&#41;](../xml-task-editor-general-page.md)</span></span>


