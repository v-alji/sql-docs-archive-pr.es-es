---
title: Consultas entre bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a0305f5b-91bd-4d18-a2fc-ec235b062fd3
author: rothja
ms.author: jroth
ms.openlocfilehash: 4afbb580a55273ec241005493fd37f99e98ec0e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670382"
---
# <a name="cross-database-queries"></a><span data-ttu-id="4a1b2-102">Consultas entre bases de datos</span><span class="sxs-lookup"><span data-stu-id="4a1b2-102">Cross-Database Queries</span></span>
  <span data-ttu-id="4a1b2-103">En [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], las tablas optimizadas para memoria no admiten las transacciones entre bases de datos.</span><span class="sxs-lookup"><span data-stu-id="4a1b2-103">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], memory-optimized tables do not support cross-database transactions.</span></span> <span data-ttu-id="4a1b2-104">No puede tener acceso a otra base de datos desde la misma transacción o desde la misma consulta que tiene acceso también a una tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="4a1b2-104">You cannot access another database from the same transaction or the same query that also accesses a memory-optimized table.</span></span> <span data-ttu-id="4a1b2-105">No puede copiar fácilmente los datos de una tabla de una base de datos en una tabla optimizada para memoria de otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a1b2-105">You cannot easily copy data from a table in one database, to a memory-optimized table in another database.</span></span>  
  
 <span data-ttu-id="4a1b2-106">Las variables de tabla no son transaccionales.</span><span class="sxs-lookup"><span data-stu-id="4a1b2-106">Table variables are not transactional.</span></span> <span data-ttu-id="4a1b2-107">Por tanto, se pueden utilizar las variables de tabla optimizada para memoria en consultas entre bases de datos y pueden así facilitar la migración de datos de una base de datos a tablas optimizadas para memoria de otra.</span><span class="sxs-lookup"><span data-stu-id="4a1b2-107">Therefore, memory-optimized table variables can be used in cross-database queries, and can thus facilitate moving data from one database into memory-optimized tables in another.</span></span> <span data-ttu-id="4a1b2-108">Puede utilizar dos transacciones.</span><span class="sxs-lookup"><span data-stu-id="4a1b2-108">You can use two transactions.</span></span> <span data-ttu-id="4a1b2-109">En la primera transacción, inserte los datos de la tabla remota en la variable.</span><span class="sxs-lookup"><span data-stu-id="4a1b2-109">In the first transaction, insert the data from the remote table into the variable.</span></span> <span data-ttu-id="4a1b2-110">En la segunda transacción, inserte los datos en la tabla optimizada para memoria local desde la variable.</span><span class="sxs-lookup"><span data-stu-id="4a1b2-110">In the second transaction, insert the data into the local memory-optimized table from the variable.</span></span>  
  
 <span data-ttu-id="4a1b2-111">Por ejemplo, para copiar la fila de la tabla T1 de la base de datos db1 en la tabla T2 de DB2, utilizando la variable @v1 de tipo DBO. TT1, puede usar algo parecido a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a1b2-111">For example, to copy the row from table t1 in database db1 to table t2 in db2, using variable @v1 of type dbo.tt1, you can use something like:</span></span>  
  
```sql  
USE db2   
GO   
DECLARE @v1 dbo.tt1   
INSERT @v1 SELECT * FROM db1.dbo.t1   
INSERT dbo.t2 SELECT * FROM @v1   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a1b2-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a1b2-112">See Also</span></span>  
 [<span data-ttu-id="4a1b2-113">Migrar a OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="4a1b2-113">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
