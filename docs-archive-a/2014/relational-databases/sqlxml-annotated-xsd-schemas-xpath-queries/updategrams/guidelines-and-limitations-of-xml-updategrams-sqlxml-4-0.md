---
title: Instrucciones y limitaciones de diagramas XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updategrams [SQLXML], about updategrams
ms.assetid: b5231859-14e2-4276-bc17-db2817b6f235
author: rothja
ms.author: jroth
ms.openlocfilehash: 6e01e366edc2889691862de639f69220ac4bb439
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746186"
---
# <a name="guidelines-and-limitations-of-xml-updategrams-sqlxml-40"></a><span data-ttu-id="f0e7a-102">Instrucciones y limitaciones de los diagramas de actualización XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f0e7a-102">Guidelines and Limitations of XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="f0e7a-103">Recuerde lo siguiente al utilizar los diagramas de actualización XML:</span><span class="sxs-lookup"><span data-stu-id="f0e7a-103">Remember the following when using XML updategrams:</span></span>  
  
-   <span data-ttu-id="f0e7a-104">Si usa un diagrama para una operación de inserción con un solo par de **\<before>** **\<after>** bloques y, **\<before>** se puede omitir el bloque.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-104">If you are using an updategram for an insert operation with only a single pair of **\<before>** and **\<after>** blocks, the **\<before>** block can be omitted.</span></span> <span data-ttu-id="f0e7a-105">Por el contrario, en el caso de una operación de eliminación, el **\<after>** bloque se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-105">Conversely, in case of a delete operation, the **\<after>** block can be omitted.</span></span>  
  
-   <span data-ttu-id="f0e7a-106">Si usa un diagrama con varios **\<before>** **\<after>** bloques y en la **\<sync>** etiqueta, **\<before>** **\<after>** se deben especificar bloques y bloques para formar **\<before>** y **\<after>** pares.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-106">If you are using an updategram with multiple **\<before>** and **\<after>** blocks in the **\<sync>** tag, both **\<before>** blocks and **\<after>** blocks must be specified to form **\<before>** and **\<after>** pairs.</span></span>  
  
-   <span data-ttu-id="f0e7a-107">Las actualizaciones de un diagrama de actualización se aplican a la vista XML proporcionada por el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-107">The updates in an updategram are applied to the XML view that is provided by the XML schema.</span></span> <span data-ttu-id="f0e7a-108">Por consiguiente, para que la asignación predeterminada sea correcta debe especificar el nombre de archivo del esquema del diagrama de actualización o, si no se proporciona el nombre de archivo, los nombres de atributo y elemento deben coincidir con los nombres de columna y tabla de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-108">Therefore, for the default mapping to succeed either you must specify the schema file name in the updategram or, if the file name is not provided, the element and attribute names must match the table and column names in the database.</span></span>  
  
-   <span data-ttu-id="f0e7a-109">SQLXML 4.0 requiere que todos los valores de columna de un diagrama de actualización estén asignados explícitamente en el esquema (XDR o XSD) proporcionado para componer la vista XML de sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-109">SQLXML 4.0 requires that all column values in an updategram must be explicitly mapped in the schema (either XDR or XSD) provided to compose the XML view for its child elements.</span></span> <span data-ttu-id="f0e7a-110">Este comportamiento difiere de las versiones anteriores de SQLXML, que permitían un valor de una columna no asignado en el esquema si estaba implícito como parte de la clave externa de una anotación `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-110">This behavior differs from earlier versions of SQLXML, which allowed a value for a column not mapped in the schema if it was implied as part of the foreign Key in a `sql:relationship` annotation.</span></span> <span data-ttu-id="f0e7a-111">(Observe que este cambio no afecta a la propagación de los valores de clave principal a los elementos secundarios, que todavía se produce para SQLXML 4.0 si no se especifica ningún valor explícitamente para el elemento secundario).</span><span class="sxs-lookup"><span data-stu-id="f0e7a-111">(Note that this change does not affect propagation of primary key values to child elements, which still occurs for SQLXML 4.0 if no value is explicitly specified for the child element.</span></span>  
  
-   <span data-ttu-id="f0e7a-112">Si usa un diagrama para modificar los datos de una columna binaria (como el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `image` tipo de datos), debe proporcionar un esquema de asignación en el que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se debe especificar el tipo de datos (por ejemplo, `sql:datatype="image"` ) y el tipo de datos XML (por ejemplo, `dt:type="binhex"` o `dt:type="binbase64` ).</span><span class="sxs-lookup"><span data-stu-id="f0e7a-112">If you are using an updategram to modify data in a binary column (such as the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `image` data type), you must provide a mapping schema in which the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type (for example, `sql:datatype="image"`) and the XML data type (for example, `dt:type="binhex"` or `dt:type="binbase64`) must be specified.</span></span> <span data-ttu-id="f0e7a-113">Los datos de la columna binaria se deben especificar en el diagrama de actualización; el diagrama de actualización omite la anotación `sql:url-encode` especificada en el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-113">The data for the binary column must be specified in the updategram; the `sql:url-encode` annotation that is specified in the mapping schema is ignored by the updategram.</span></span>  
  
-   <span data-ttu-id="f0e7a-114">Cuando escribe un esquema XSD, si el valor que especifica para la anotación `sql:relation` o `sql:field` incluye un carácter especial, como un carácter de espacio en blanco (por ejemplo, en el nombre de tabla "Detalles de pedido"), este valor se debe incluir entre corchetes (por ejemplo, "[Detalles de pedido]").</span><span class="sxs-lookup"><span data-stu-id="f0e7a-114">When you are writing an XSD schema, if the value you specify for the `sql:relation` or `sql:field` annotation includes a special character, such as a space character (for example, in the "Order Details" table name), this value must be enclosed in brackets (for example, "[Order Details]").</span></span>  
  
-   <span data-ttu-id="f0e7a-115">Al utilizar los diagramas de actualización, no se admiten las relaciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-115">When using updategrams, chain relationships are not supported.</span></span> <span data-ttu-id="f0e7a-116">Por ejemplo, si las tablas A y C están relacionadas mediante una relación de cadena que utiliza la tabla B, se producirá el error siguiente al intentar ejecutar el diagrama de actualización:</span><span class="sxs-lookup"><span data-stu-id="f0e7a-116">For example, if tables A and C are related through a chain relationship that uses table B, the following error will occur when attempting to run and execute the updategram:</span></span>  
  
    ```  
    There is an inconsistency in the schema provided.  
    ```  
  
     <span data-ttu-id="f0e7a-117">Aun cuando el esquema y el diagrama de actualización sean correctos y tengan un formato válido, se producirá este error si está presente una relación de cadena.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-117">Even if both schema and updategram are otherwise correct and validly formed, this error will occur if a chain relationship is present.</span></span>  
  
-   <span data-ttu-id="f0e7a-118">Los diagramas de actualización no permiten el paso de datos del tipo `image` como parámetros durante las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-118">Updategrams do not permit the passing of `image` type data as parameters during updates.</span></span>  
  
-   <span data-ttu-id="f0e7a-119">Los tipos de objetos binarios grandes (BLOB) como `text/ntext` y las imágenes no se deben usar en el **\<before>** bloque de cuando se trabaja con diagramas, porque se incluirán para su uso en el control de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-119">Binary large object (BLOB) types like `text/ntext` and images should not be used in the **\<before>** block in when working with updategrams, because this will include them for use in concurrency control.</span></span> <span data-ttu-id="f0e7a-120">Esto puede producir problemas con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] debido a las limitaciones en la comparación para los tipos BLOB.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-120">This can cause problems with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="f0e7a-121">Por ejemplo, la palabra clave LIKE se usa en la cláusula WHERE para comparar entre las columnas del tipo de datos `text`; sin embargo, se producirá un error en las comparaciones en el caso de los tipos BLOB donde el tamaño de los datos supere los 8 K.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-121">For example, the LIKE keyword is used in the WHERE clause for comparing between columns of the `text` data type; however, comparisons will fail in the case of BLOB types where the size of the data is greater than 8K.</span></span>  
  
-   <span data-ttu-id="f0e7a-122">Los caracteres especiales en los datos `ntext` pueden producir problemas con SQLXML 4.0 debido a las limitaciones en la comparación para los tipos BLOB.</span><span class="sxs-lookup"><span data-stu-id="f0e7a-122">Special characters in `ntext` data can cause problems with SQLXML 4.0 because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="f0e7a-123">Por ejemplo, el uso de "[Serializable]" en el **\<before>** bloque de un diagramas cuando se usa en la comprobación de simultaneidad de una columna de tipo producirá `ntext` un error con la siguiente descripción del error SQLOLEDB:</span><span class="sxs-lookup"><span data-stu-id="f0e7a-123">For example, the use of "[Serializable]" in the **\<before>** block of an updategrams when used in concurrency checking of a column of `ntext` type will fail with the following SQLOLEDB error description:</span></span>  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f0e7a-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0e7a-124">See Also</span></span>  
 [<span data-ttu-id="f0e7a-125">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f0e7a-125">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  