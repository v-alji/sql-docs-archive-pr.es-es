---
title: Creación, modificación y eliminación de índices XML selectivos secundarios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 45128105-833b-40a9-9cc9-1ae03ac0b52b
author: rothja
ms.author: jroth
ms.openlocfilehash: e6f7296896b6421db5329565403cdcbaf10b26a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745083"
---
# <a name="create-alter-and-drop-secondary-selective-xml-indexes"></a><span data-ttu-id="8af50-102">Crear, modificar y quitar índices XML selectivos secundarios</span><span class="sxs-lookup"><span data-stu-id="8af50-102">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>
  <span data-ttu-id="8af50-103">Describe cómo crear un nuevo índice XML selectivo secundario, o cómo modificar o quitar un índice XML selectivo secundario existente.</span><span class="sxs-lookup"><span data-stu-id="8af50-103">Describes how to create a new secondary selective XML index, or alter or drop an existing secondary selective XML index.</span></span>  
  
##  <a name="creating-a-secondary-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="8af50-104">Crear un índice XML selectivo secundario</span><span class="sxs-lookup"><span data-stu-id="8af50-104">Creating a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-create-a-secondary-selective-xml-index"></a><span data-ttu-id="8af50-105">Procedimientos: Crear un índice XML selectivo secundario</span><span class="sxs-lookup"><span data-stu-id="8af50-105">How to: Create a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="8af50-106">**Crear un índice XML selectivo secundario con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="8af50-106">**Create a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="8af50-107">Crear un índice XML selectivo secundario llamando a la instrucción CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="8af50-107">Create a secondary selective XML index by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="8af50-108">Para obtener más información, vea [crear índice XML &#40;índices XML selectivos&#41;] (~/t-SQL/statements/Create-XML-index-Selective-XML-Indexes.</span><span class="sxs-lookup"><span data-stu-id="8af50-108">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="8af50-109">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="8af50-109">**Example**</span></span>  
  
 <span data-ttu-id="8af50-110">En el ejemplo siguiente se crea un índice XML selectivo secundario en la ruta de acceso `'pathabc'`.</span><span class="sxs-lookup"><span data-stu-id="8af50-110">The following example creates a secondary selective XML index on the path `'pathabc'`.</span></span> <span data-ttu-id="8af50-111">La ruta de acceso del índice se identifica mediante el nombre que se ha especificado cuando se creó con la instrucción CREATE SELECTIVE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="8af50-111">The path to index is identified by the name that was given to it when it was created with the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="8af50-112">Para obtener más información, vea [CREAR ÍNDICE XML SELECTIVO &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8af50-112">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
```sql  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="altering-a-secondary-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="8af50-113">Alterar un índice XML selectivo secundario</span><span class="sxs-lookup"><span data-stu-id="8af50-113">Altering a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="8af50-114">La instrucción ALTER no se admite para los índices XML selectivos secundarios.</span><span class="sxs-lookup"><span data-stu-id="8af50-114">The ALTER statement is not supported for secondary selective XML indexes.</span></span> <span data-ttu-id="8af50-115">Para cambiar un índice XML secundario selectivo, quite el índice existente y vuelva a crearlo.</span><span class="sxs-lookup"><span data-stu-id="8af50-115">To change a secondary selective XML index, drop the existing index and recreate it.</span></span>  
  
### <a name="how-to-alter-a-secondary-selective-xml-index"></a><span data-ttu-id="8af50-116">Procedimientos: Alterar un índice XML selectivo secundario</span><span class="sxs-lookup"><span data-stu-id="8af50-116">How to: Alter a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="8af50-117">**Modificar un índice XML selectivo secundario con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="8af50-117">**Alter a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 1.  <span data-ttu-id="8af50-118">Quite el índice XML selectivo secundario existente llamando a la instrucción DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="8af50-118">Drop the existing secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="8af50-119">Para obtener más información, vea [DROP INDEX &#40;índices XML selectivos&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="8af50-119">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
2.  <span data-ttu-id="8af50-120">Vuelva a crear el índice con las opciones deseadas llamando a la instrucción CREATE XML INDEX.</span><span class="sxs-lookup"><span data-stu-id="8af50-120">Recreate the index with the desired options by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="8af50-121">Para obtener más información, vea [crear índice XML &#40;índices XML selectivos&#41;] (~/t-SQL/statements/Create-XML-index-Selective-XML-Indexes.</span><span class="sxs-lookup"><span data-stu-id="8af50-121">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="8af50-122">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="8af50-122">**Example**</span></span>  
  
 <span data-ttu-id="8af50-123">En el ejemplo siguiente se cambia un índice XML selectivo secundario quitándolo y volviéndolo a crear.</span><span class="sxs-lookup"><span data-stu-id="8af50-123">The following example changes a secondary selective XML index by dropping it and recreating it.</span></span>  
  
```sql  
DROP INDEX filt_sxi_index_c  
  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="dropping-a-secondary-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="8af50-124">Quitar un índice XML selectivo secundario</span><span class="sxs-lookup"><span data-stu-id="8af50-124">Dropping a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-secondary-selective-xml-index"></a><span data-ttu-id="8af50-125">Procedimientos: Quitar un índice XML selectivo secundario</span><span class="sxs-lookup"><span data-stu-id="8af50-125">How to: Drop a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="8af50-126">**Quitar un índice XML selectivo secundario con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="8af50-126">**Drop a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="8af50-127">Quitar un índice XML selectivo secundario llamando a la instrucción DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="8af50-127">Drop a secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="8af50-128">Para obtener más información, vea [DROP INDEX &#40;índices XML selectivos&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="8af50-128">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="8af50-129">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="8af50-129">**Example**</span></span>  
  
 <span data-ttu-id="8af50-130">En el ejemplo siguiente se muestra una instrucción DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="8af50-130">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX ssxi_index  
ON tbl  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="8af50-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8af50-131">See Also</span></span>  
 [<span data-ttu-id="8af50-132">Índices XML selectivos &#40;SXI&#41;</span><span class="sxs-lookup"><span data-stu-id="8af50-132">Selective XML Indexes &#40;SXI&#41;</span></span>](selective-xml-indexes-sxi.md)  
  
  
