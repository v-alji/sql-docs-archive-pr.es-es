---
title: Especificar variables XPath en consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], XPath variables
- XPath variables [SQLXML]
ms.assetid: c11ab816-11b8-4131-8b77-c03fe500fa10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5045831f627722f7dbb9a9189be5c48d830f2add
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662741"
---
# <a name="specifying-xpath-variables-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="2e743-102">Especificar variables XPath en consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2e743-102">Specifying XPath Variables in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="2e743-103">Los ejemplos siguientes muestran cómo las variables XPath se pasan en consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="2e743-103">The following examples show how XPath variables are passed in XPath queries.</span></span> <span data-ttu-id="2e743-104">Las consultas XPath de estos ejemplos se especifican en el esquema de asignación que se incluye en SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="2e743-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="2e743-105">Para obtener información acerca de este esquema de ejemplo, vea [ejemplo de esquema XSD anotado para los ejemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2e743-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2e743-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2e743-106">Examples</span></span>  
  
### <a name="a-use-the-xpath-variables"></a><span data-ttu-id="2e743-107">A.</span><span class="sxs-lookup"><span data-stu-id="2e743-107">A.</span></span> <span data-ttu-id="2e743-108">Usar las variables XPath</span><span class="sxs-lookup"><span data-stu-id="2e743-108">Use the XPath variables</span></span>  
 <span data-ttu-id="2e743-109">Una plantilla de ejemplo consta de dos consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="2e743-109">A sample template consists of two XPath queries.</span></span> <span data-ttu-id="2e743-110">Cada uno de las consultas XPath toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="2e743-110">Each of the XPath queries takes one parameter.</span></span> <span data-ttu-id="2e743-111">La plantilla también especifica los valores predeterminados para estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="2e743-111">The template also specifies default values for these parameters.</span></span> <span data-ttu-id="2e743-112">Los valores predeterminados se usan si no se especifican valores de parámetro.</span><span class="sxs-lookup"><span data-stu-id="2e743-112">The default values are used if parameter values are not specified.</span></span> <span data-ttu-id="2e743-113">En se especifican dos parámetros con valores predeterminados **\<sql:header>** .</span><span class="sxs-lookup"><span data-stu-id="2e743-113">Two parameters with default values are specified in **\<sql:header>**.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='CustomerID'>1</sql:param>  
     <sql:param name='ContactID'>1</sql:param>   
  </sql:header>  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
    Customer[@CustomerID=$CustomerID]   
  </sql:xpath-query >  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
   Contact[@ContactID=$ContactID]   
  </sql:xpath-query>  
</ROOT>  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="2e743-114">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="2e743-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="2e743-115">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="2e743-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="2e743-116">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="2e743-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="2e743-117">Cree la plantilla siguiente (XPathVariables.xml) y guárdela en el directorio en el que:</span><span class="sxs-lookup"><span data-stu-id="2e743-117">Create the following template (XPathVariables.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:header>  
         <sql:param name='CustomerID'>1</sql:param>  
         <sql:param name='ContactID'>1</sql:param>   
      </sql:header>  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[@CustomerID=$CustomerID]   
      </sql:xpath-query >  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
       Contact[@ContactID=$ContactID]   
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="2e743-118">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="2e743-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="2e743-119">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2e743-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="2e743-120">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="2e743-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="2e743-121">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2e743-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e743-122">En este ejemplo, no se pasa ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="2e743-122">In this example, no parameters are passed.</span></span> <span data-ttu-id="2e743-123">Por tanto, se usan los valores de parámetros predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2e743-123">Therefore, the default parameter values are used.</span></span>  
  
  
