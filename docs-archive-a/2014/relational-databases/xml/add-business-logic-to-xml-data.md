---
title: Agregar lógica comercial a los datos XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- business logic [XML]
ms.assetid: 0877fb38-f1a2-43d8-86cf-4754be224dc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 5bf8e9edc36e9c420faa92f2db1a92c311194e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670870"
---
# <a name="add-business-logic-to-xml-data"></a><span data-ttu-id="a50d7-102">Agregar lógica comercial a los datos XML</span><span class="sxs-lookup"><span data-stu-id="a50d7-102">Add Business Logic to XML Data</span></span>
  <span data-ttu-id="a50d7-103">La lógica de negocios se puede agregar a los datos XML de varias formas:</span><span class="sxs-lookup"><span data-stu-id="a50d7-103">Your business logic can be added to XML data in several ways:</span></span>  
  
-   <span data-ttu-id="a50d7-104">Se pueden escribir restricciones de filas o columnas para forzar restricciones específicas de un dominio durante la inserción y modificación de datos XML.</span><span class="sxs-lookup"><span data-stu-id="a50d7-104">You can write row or column constraints to enforce domain-specific constraints during insertion and modification of XML data.</span></span>  
  
-   <span data-ttu-id="a50d7-105">Es posible escribir un desencadenador en la columna XML que se active al insertar o actualizar valores en la columna.</span><span class="sxs-lookup"><span data-stu-id="a50d7-105">You can write a trigger on the XML column that fires when you insert or update values in the column.</span></span> <span data-ttu-id="a50d7-106">El desencadenador puede contener reglas de validación específicas de un dominio o rellenar tablas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="a50d7-106">The trigger can contain domain-specific validation rules or populate property tables.</span></span>  
  
-   <span data-ttu-id="a50d7-107">El motor de base de datos incluye la capacidad de ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="a50d7-107">The Database Engine includes the ability execute managed code.</span></span> <span data-ttu-id="a50d7-108">Puede usar esta integración de Common Language Runtime (CLR) para escribir funciones en código administrado a las que pasar valores XML y usar capacidades de procesamiento XML proporcionadas por el espacio de nombres System.Xml.</span><span class="sxs-lookup"><span data-stu-id="a50d7-108">You can use this common language runtime (CLR) integration to write functions in managed code to which you pass XML values, and use XML processing capabilities provided by the System.Xml namespace.</span></span> <span data-ttu-id="a50d7-109">Un ejemplo es aplicar la transformación XSL a datos XML.</span><span class="sxs-lookup"><span data-stu-id="a50d7-109">An example is to apply XSL transformation to XML data.</span></span> <span data-ttu-id="a50d7-110">Otra posibilidad es deserializar el XML en una o más clases administradas y operar con ellas mediante código administrado.</span><span class="sxs-lookup"><span data-stu-id="a50d7-110">Alternatively, you can deserialize the XML into one or more managed classes and operate on them by using managed code.</span></span>  
  
-   <span data-ttu-id="a50d7-111">Se pueden escribir procedimientos almacenados de Transact-SQL y funciones que inicien el procesamiento en la columna XML de acuerdo con las necesidades de la empresa.</span><span class="sxs-lookup"><span data-stu-id="a50d7-111">You can write Transact-SQL stored procedures and functions that start the processing on the XML column for your business needs.</span></span>  
  
## <a name="example-applying-xsl-transformation"></a><span data-ttu-id="a50d7-112">Ejemplo: Aplicación de una transformación XSL</span><span class="sxs-lookup"><span data-stu-id="a50d7-112">Example: Applying XSL Transformation</span></span>  
 <span data-ttu-id="a50d7-113">Considere una función CLR **TransformXml ()** que acepta una `xml` instancia de tipo de datos y una transformación XSL almacenada en un archivo, aplica la transformación a los datos XML y, a continuación, devuelve el XML transformado en el resultado.</span><span class="sxs-lookup"><span data-stu-id="a50d7-113">Consider a CLR function **TransformXml()** that accepts an `xml` data type instance and an XSL transformation stored in a file, applies the transformation to the XML data, and then returns the transformed XML in the result.</span></span> <span data-ttu-id="a50d7-114">A continuación, se muestra una función esquemática escrita en C#:</span><span class="sxs-lookup"><span data-stu-id="a50d7-114">Following is a skeleton function that is written in C#:</span></span>  
  
```  
public static SqlXml TransformXml (SqlXml XmlData, string xslPath) {  
   // Load XSL transformation  
   XslCompiledTransform xform = new XslCompiledTransform();  
   XPathDocument xslDoc = new XPathDocument (xslPath);  
   xform.Load(xslDoc);  
  
   // Load XML data   
   XPathDocument xDoc = new XPathDocument (XmlData.CreateReader());  
  
   // Return the transformed value  
   MemoryStream xsltResult = new MemoryStream();  
   xform.Transform(xDoc, null, xsltResult);  
   SqlXml retSqlXml = new SqlXml(xsltResult);  
   return (retSqlXml);  
}   
```  
  
 <span data-ttu-id="a50d7-115">Después de registrar el ensamblado y crear una función [!INCLUDE[tsql](../../includes/tsql-md.md)] definida por el usuario, **SqlXslTransform()** correspondiente a **TransformXml()** , se puede invocar la función desde Transact-SQL como se indica en la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="a50d7-115">After the assembly is registered and a user-defined [!INCLUDE[tsql](../../includes/tsql-md.md)] function is created, **SqlXslTransform()** corresponding to **TransformXml()**, the function can be invoked from Transact-SQL as shown in the following query:</span></span>  
  
```  
SELECT SqlXslTransform (xCol, 'C:\MyFile\xsltransform.xsl')  
FROM    T  
WHERE  xCol.exist('/book/title/text()[contains(.,"custom")]') =1;  
```  
  
 <span data-ttu-id="a50d7-116">El resultado de la consulta contiene un conjunto de filas del XML transformado.</span><span class="sxs-lookup"><span data-stu-id="a50d7-116">The query result contains a rowset of the transformed XML.</span></span>  
  
 <span data-ttu-id="a50d7-117">La integración de CLR en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] amplía las posibilidades de descomponer datos XML en tablas o promoción de propiedades, y de consulta de datos XML usando clases administradas en el espacio de nombres System.Xml.</span><span class="sxs-lookup"><span data-stu-id="a50d7-117">The CLR integration into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expands the possibilities for decomposing XML data into tables or property promotion, and querying XML data by using managed classes in the System.Xml namespace.</span></span> <span data-ttu-id="a50d7-118">Para obtener más información, vea [Datos XML &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a50d7-118">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
  
