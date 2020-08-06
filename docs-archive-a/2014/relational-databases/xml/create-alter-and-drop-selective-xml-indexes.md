---
title: Creación, modificación y eliminación de índices XML selectivos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: c398f396-f630-4a2d-a264-f243c5346de1
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4123a46cc13359c936e6f9cfc0db3dcfdaa175
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745082"
---
# <a name="create-alter-and-drop-selective-xml-indexes"></a><span data-ttu-id="bd6b7-102">Crear, modificar y quitar índices XML selectivos</span><span class="sxs-lookup"><span data-stu-id="bd6b7-102">Create, Alter, and Drop Selective XML Indexes</span></span>
  <span data-ttu-id="bd6b7-103">Describe cómo crear un nuevo índice XML selectivo, o cómo modificar o quitar un índice XML selectivo existente.</span><span class="sxs-lookup"><span data-stu-id="bd6b7-103">Describes how to create a new selective XML index, or alter or drop an existing selective XML index.</span></span>  
  
 <span data-ttu-id="bd6b7-104">Para obtener más información sobre los índices XML selectivos, vea [Índices XML selectivos &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="bd6b7-104">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="creating-a-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="bd6b7-105">Crear un índice XML selectivo</span><span class="sxs-lookup"><span data-stu-id="bd6b7-105">Creating a Selective XML Index</span></span>  
  
### <a name="how-to-create-a-selective-xml-index"></a><span data-ttu-id="bd6b7-106">Procedimientos: Crear un índice XML selectivo</span><span class="sxs-lookup"><span data-stu-id="bd6b7-106">How to: Create a Selective XML Index</span></span>  
 <span data-ttu-id="bd6b7-107">**Crear un nuevo índice XML selectivo con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="bd6b7-107">**Create a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="bd6b7-108">Crear un índice XML selectivo llamado a la instrucción CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="bd6b7-108">Create a selective XML index by calling the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="bd6b7-109">Para obtener más información, vea [CREAR ÍNDICE XML SELECTIVO &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bd6b7-109">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
 <span data-ttu-id="bd6b7-110">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bd6b7-110">**Example**</span></span>  
  
 <span data-ttu-id="bd6b7-111">En el ejemplo siguiente se muestra la sintaxis para crear un índice XML selectivo.</span><span class="sxs-lookup"><span data-stu-id="bd6b7-111">The following example shows the syntax for creating a selective XML index.</span></span> <span data-ttu-id="bd6b7-112">También se muestran varias variaciones de la sintaxis para describir las rutas de acceso que se van a indizar, con sugerencias opcionales de optimización.</span><span class="sxs-lookup"><span data-stu-id="bd6b7-112">It also shows several variations of the syntax for describing the paths to be indexed, with optional optimization hints.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX sxi_index  
ON Tbl(xmlcol)  
  
FOR(  
    pathab   = '/a/b' as XQUERY 'node()'  
    pathabc  = '/a/b/c' as XQUERY 'xs:double',   
    pathdtext = '/a/b/d/text()' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
    pathabe = '/a/b/e' as SQL NVARCHAR(100)  
)  
```  
  
  
  
##  <a name="altering-a-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="bd6b7-113">Modificar un índice XML selectivo</span><span class="sxs-lookup"><span data-stu-id="bd6b7-113">Altering a Selective XML Index</span></span>  
  
### <a name="how-to-alter-a-selective-xml-index"></a><span data-ttu-id="bd6b7-114">Procedimientos: Modificar un índice XML selectivo</span><span class="sxs-lookup"><span data-stu-id="bd6b7-114">How to: Alter a Selective XML Index</span></span>  
 <span data-ttu-id="bd6b7-115">**Modificar un índice XML selectivo con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="bd6b7-115">**Alter a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="bd6b7-116">Modificar un índice XML selectivo existente llamado a la instrucción ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="bd6b7-116">Alter an existing selective XML index by calling the ALTER INDEX statement.</span></span> <span data-ttu-id="bd6b7-117">Para obtener más información, vea [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="bd6b7-117">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="bd6b7-118">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bd6b7-118">**Example**</span></span>  
  
 <span data-ttu-id="bd6b7-119">En el ejemplo siguiente se muestra una instrucción ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="bd6b7-119">The following example shows an ALTER INDEX statement.</span></span> <span data-ttu-id="bd6b7-120">Esta instrucción agrega la ruta de acceso `'/a/b/m'` a la parte XQuery del índice y elimina la ruta de acceso `'/a/b/e'` de la parte SQL del índice creado en el ejemplo del tema [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bd6b7-120">This statement adds the path `'/a/b/m'` to the XQuery part of the index and deletes the path `'/a/b/e'` from the SQL part of the index created in the example in the topic [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span> <span data-ttu-id="bd6b7-121">La ruta de acceso que se va a eliminar se identifica por el nombre que se especificó cuando se creó.</span><span class="sxs-lookup"><span data-stu-id="bd6b7-121">The path to delete is identified by the name that was given to it when it was created.</span></span>  
  
```sql  
ALTER INDEX sxi_index  
ON Tbl  
FOR   
(  
    ADD pathm = '/a/b/m' as XQUERY 'node()' ,  
    REMOVE pathabe  
)  
```  
  
  
  
##  <a name="dropping-a-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="bd6b7-122">Quitar un índice XML selectivo</span><span class="sxs-lookup"><span data-stu-id="bd6b7-122">Dropping a Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-selective-xml-index"></a><span data-ttu-id="bd6b7-123">Procedimientos: Quitar un índice XML selectivo</span><span class="sxs-lookup"><span data-stu-id="bd6b7-123">How to: Drop a Selective XML Index</span></span>  
 <span data-ttu-id="bd6b7-124">**Quitar un índice XML selectivo con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="bd6b7-124">**Drop a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="bd6b7-125">Quitar un índice XML selectivo llamando a la instrucción DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="bd6b7-125">Drop a selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="bd6b7-126">Para obtener más información, vea [DROP INDEX &#40;índices XML selectivos&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span><span class="sxs-lookup"><span data-stu-id="bd6b7-126">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span></span>  
  
 <span data-ttu-id="bd6b7-127">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="bd6b7-127">**Example**</span></span>  
  
 <span data-ttu-id="bd6b7-128">En el ejemplo siguiente se muestra una instrucción DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="bd6b7-128">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX sxi_index ON tbl  
```  
  
 
  
  
