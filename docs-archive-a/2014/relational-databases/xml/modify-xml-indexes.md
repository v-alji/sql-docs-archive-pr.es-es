---
title: Modificación de índices XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML indexes [SQL Server], modifying
- modifying indexes
ms.assetid: 24d50fe1-c6ec-49e6-91a3-9791851ba53d
author: rothja
ms.author: jroth
ms.openlocfilehash: c5c67470fc9aaaeefe49e5ccb1a8602e082c4054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744535"
---
# <a name="modify-xml-indexes"></a><span data-ttu-id="e542b-102">Modificar índices XML</span><span class="sxs-lookup"><span data-stu-id="e542b-102">Modify XML Indexes</span></span>
  <span data-ttu-id="e542b-103">La instrucción DDL [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) de [!INCLUDE[tsql](../../includes/tsql-md.md)] se puede usar para modificar índices XML y no XML existentes.</span><span class="sxs-lookup"><span data-stu-id="e542b-103">The [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement can be used to modify existing XML and non-XML indexes.</span></span> <span data-ttu-id="e542b-104">No obstante, no todas las opciones ALTER INDEX están disponibles para índices XML.</span><span class="sxs-lookup"><span data-stu-id="e542b-104">However, not all the ALTER INDEX options are available to XML indexes.</span></span> <span data-ttu-id="e542b-105">Las siguientes opciones no son válidas al modificar índices XML:</span><span class="sxs-lookup"><span data-stu-id="e542b-105">The following options are not valid when modifying XML indexes:</span></span>  
  
-   <span data-ttu-id="e542b-106">La opción de reconstrucción y configuración IGNORE_DUP_KEY no es válida para índices XML.</span><span class="sxs-lookup"><span data-stu-id="e542b-106">The rebuild and set option IGNORE_DUP_KEY is not valid for XML indexes.</span></span> <span data-ttu-id="e542b-107">La opción de reconstrucción ONLINE debe establecerse en OFF para los índices XML secundarios.</span><span class="sxs-lookup"><span data-stu-id="e542b-107">The rebuild option ONLINE must be set to OFF for secondary XML indexes.</span></span> <span data-ttu-id="e542b-108">La opción DROP_EXISTING no se admite en la instrucción ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="e542b-108">The option DROP_EXISTING is not permitted in the ALTER INDEX statement.</span></span>  
  
-   <span data-ttu-id="e542b-109">Las modificaciones de la restricción de clave principal en la tabla de usuario no se propagan automáticamente a los índices XML.</span><span class="sxs-lookup"><span data-stu-id="e542b-109">The modifications of the primary key constraint in the user table are not automatically propagated to XML indexes.</span></span> <span data-ttu-id="e542b-110">El usuario debe quitar los índices XML primero y volver a crearlos después.</span><span class="sxs-lookup"><span data-stu-id="e542b-110">The user must drop the XML indexes first and then re-create them.</span></span>  
  
-   <span data-ttu-id="e542b-111">Cuando se especifica ALTER INDEX ALL, se aplica tanto a los índices XML como a los que no lo son.</span><span class="sxs-lookup"><span data-stu-id="e542b-111">If ALTER INDEX ALL is specified, it applies to both non-XML and XML indexes.</span></span> <span data-ttu-id="e542b-112">Se pueden especificar opciones de indización que no sean válidas para ambos tipos de índices.</span><span class="sxs-lookup"><span data-stu-id="e542b-112">Indexing options may be specified that are not valid for both types of indexes.</span></span> <span data-ttu-id="e542b-113">En este caso, la instrucción producirá un error.</span><span class="sxs-lookup"><span data-stu-id="e542b-113">In this case, the whole statement fails.</span></span>  
  
## <a name="example-modifying-an-xml-index"></a><span data-ttu-id="e542b-114">Ejemplo: Modificación de un índice XML</span><span class="sxs-lookup"><span data-stu-id="e542b-114">Example: Modifying an XML Index</span></span>  
 <span data-ttu-id="e542b-115">En el ejemplo siguiente se muestra cómo crear un índice XML y, a continuación, modificarlo estableciendo la opción `ALLOW_ROW_LOCKS` en `OFF`.</span><span class="sxs-lookup"><span data-stu-id="e542b-115">In the following example, an XML index is created and then modified by setting the option `ALLOW_ROW_LOCKS` to `OFF`.</span></span> <span data-ttu-id="e542b-116">Cuando `ALLOW_ROW_LOCKS` se ha establecido en `OFF`, las filas no se bloquean y el acceso a los índices especificados se obtiene usando los bloqueos de página y de tabla.</span><span class="sxs-lookup"><span data-stu-id="e542b-116">When `ALLOW_ROW_LOCKS` is `OFF`, rows are not locked and access to the specified indexes is obtained by using page-and table-level locks.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create primary XML index.   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
  
-- Modify and set an index option.  
ALTER INDEX PIdx_T_XmlCol on T   
SET (ALLOW_ROW_LOCKS = OFF)  
```  
  
## <a name="example-disabling-and-enabling-an-xml-index"></a><span data-ttu-id="e542b-117">Ejemplo: Deshabilitación y habilitación de un índice XML</span><span class="sxs-lookup"><span data-stu-id="e542b-117">Example: Disabling and Enabling an XML Index</span></span>  
 <span data-ttu-id="e542b-118">Un índice XML está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e542b-118">By default, an XML index is enabled.</span></span> <span data-ttu-id="e542b-119">Si un índice XML se deshabilita, las consultas que se realicen en la columna XML no usarán el índice XML.</span><span class="sxs-lookup"><span data-stu-id="e542b-119">If an XML index is disabled, the queries running against the XML column do not use the XML index.</span></span> <span data-ttu-id="e542b-120">Para habilitar un índice XML, use `ALTER INDEX` con la opción `REBUILD` .</span><span class="sxs-lookup"><span data-stu-id="e542b-120">To enable an XML index, use `ALTER INDEX` with the `REBUILD` option.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol ON T(XmlCol)  
GO  
ALTER INDEX PIdx_T_XmlCol on T DISABLE  
Go  
-- Verify index is disabled.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
-- Rebuild the index.  
ALTER INDEX PIdx_T_XmlCol on T REBUILD  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="e542b-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e542b-121">See Also</span></span>  
 [<span data-ttu-id="e542b-122">Índices XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e542b-122">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
