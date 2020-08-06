---
title: Implementar IDENTITY en una tabla con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c0a704a3-3a31-4c2c-b967-addacda62ef8
author: rothja
ms.author: jroth
ms.openlocfilehash: 955f9f1a905a9d0c71304320f60abe300e430e4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671555"
---
# <a name="implementing-identity-in-a-memory-optimized-table"></a><span data-ttu-id="d6477-102">Implementar IDENTITY en una tabla con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="d6477-102">Implementing IDENTITY in a Memory-Optimized Table</span></span>
  <span data-ttu-id="d6477-103">IDENTITY(1, 1) se admite en una tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="d6477-103">IDENTITY(1, 1) is supported on a memory-optimized table.</span></span> <span data-ttu-id="d6477-104">Sin embargo, las columnas de identidad con la definición de IDENTITY(x, y) donde x != 1 o y != 1 no se admiten en las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="d6477-104">However, identity columns with definition of IDENTITY(x, y) where x != 1 or y != 1 are not supported on memory-optimized tables.</span></span> <span data-ttu-id="d6477-105">La solución para los valores de IDENTITY utiliza el objeto SEQUENCE ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span><span class="sxs-lookup"><span data-stu-id="d6477-105">The workaround for IDENTITY values uses the SEQUENCE object ([Sequence Numbers](../sequence-numbers/sequence-numbers.md)).</span></span>  
  
 <span data-ttu-id="d6477-106">Quite primero la propiedad IDENTITY de la tabla que está convirtiendo a OLTP en memoria.</span><span class="sxs-lookup"><span data-stu-id="d6477-106">First remove the IDENTITY property from the table you are converting to In-Memory OLTP.</span></span> <span data-ttu-id="d6477-107">A continuación, defina un nuevo objeto SEQUENCE para la columna en la tabla.</span><span class="sxs-lookup"><span data-stu-id="d6477-107">Then, define a new SEQUENCE object for the column in the table.</span></span> <span data-ttu-id="d6477-108">Los objetos SEQUENCE como las columnas de identidad se basan en la capacidad de crear valores DEFAULT para las columnas que utilizan la sintaxis NEXT VALUE FOR para obtener un nuevo valor de identidad.</span><span class="sxs-lookup"><span data-stu-id="d6477-108">SEQUENCE objects as identity columns rely on the ability to create DEFAULT values for columns that use the NEXT VALUE FOR syntax to get a new identity value.</span></span> <span data-ttu-id="d6477-109">Puesto que los valores DEFAULT no se admiten en OLTP en memoria, es necesario pasar el valor SEQUENCE recién generado a la instrucción INSERT o a un procedimiento almacenado compilado de forma nativa que lleve a cabo la inserción.</span><span class="sxs-lookup"><span data-stu-id="d6477-109">Since DEFAULTs are not supported in In-Memory OLTP, you need to pass the newly-generated SEQUENCE value either to the INSERT statement or to a natively compiled stored procedure that does the insert.</span></span> <span data-ttu-id="d6477-110">El ejemplo siguiente demuestra este patrón.</span><span class="sxs-lookup"><span data-stu-id="d6477-110">The following example demonstrates this pattern.</span></span>  
  
```sql  
-- Create a new In-Memory OLTP table to simulate IDENTITY insert  
-- Here the column C1 was the identity column in the original table  
--  
create table T1  
(  
  
[c1] integer not null primary key T1_c1 nonclustered,  
[c2] varchar(32) not null,  
[c3] datetime not null  
  
) with (memory_optimized = on)  
go  
  
-- This is a sequence provider that will give us values for column [c1]  
--  
create sequence usq_SequenceForT1 as integer start with 2 increment by 1  
go  
  
--   insert a sample row using the sequence  
--   note that a new value needs to be retrieved form   
--   the sequence object for every insert  
--  
declare @c1 integer = next value for [dbo].[usq_SequenceForT1]  
insert into T1 values (@c1, 'test', getdate())  
```  
  
 <span data-ttu-id="d6477-111">Después de realizar la inserción varias veces, verá valores que aumentan con una progresión continua en la columna [c1].</span><span class="sxs-lookup"><span data-stu-id="d6477-111">After performing the insert several times, you see valid monotonically increasing values in column [c1].</span></span> <span data-ttu-id="d6477-112">Este conjunto de resultados se genera utilizando un recorrido de tabla y un índice hash sin `ORDER BY`, por lo que las filas no están ordenadas.</span><span class="sxs-lookup"><span data-stu-id="d6477-112">This result set is generated using table scan and hash index without `ORDER BY` so the rows are not ordered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6477-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6477-113">See Also</span></span>  
 [<span data-ttu-id="d6477-114">Migrar a OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="d6477-114">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
