---
title: Implementar la funcionalidad de combinación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: d4bcdc36-3302-4abc-9b35-64ec2b920986
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c2e2d3f0796396c0f3f451215f1fd685979a842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671554"
---
# <a name="implementing-merge-functionality"></a><span data-ttu-id="ef932-102">Implementar la funcionalidad MERGE</span><span class="sxs-lookup"><span data-stu-id="ef932-102">Implementing MERGE Functionality</span></span>
  <span data-ttu-id="ef932-103">Una base de datos puede necesitar realizar una inserción o una actualización, dependiendo de si una fila determinada ya existe en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef932-103">A database may need to perform either an insert of an update, depending on whether a particular row already exists in the database.</span></span>  
  
 <span data-ttu-id="ef932-104">Es posible usar el siguiente método en [!INCLUDE[tsql](../../includes/tsql-md.md)] sin hacer uso de la instrucción `MERGE`:</span><span class="sxs-lookup"><span data-stu-id="ef932-104">Without using the `MERGE` statement, the following is one approach you can use in [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```sql  
UPDATE mytable SET col=@somevalue WHERE myPK = @parm  
IF @@ROWCOUNT = 0  
    INSERT mytable (columns) VALUES (@parm, @other values)  
```  
  
 <span data-ttu-id="ef932-105">Otro método para implementar una combinación en [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ef932-105">Another [!INCLUDE[tsql](../../includes/tsql-md.md)] method to implement a merge:</span></span>  
  
```sql  
IF EXISTS (SELECT 1 FROM mytable WHERE myPK = @parm)  
    UPDATE....  
ELSE  
    INSERT  
```  
  
 <span data-ttu-id="ef932-106">Para un procedimiento almacenado compilado de forma nativa:</span><span class="sxs-lookup"><span data-stu-id="ef932-106">For a natively compiled stored procedure</span></span>  
  
```sql  
DECLARE @i  int  = 0  -- or whatever your PK data type is  
UPDATE mytable SET @i=myPK, othercolums = other values WHERE myPK = @parm  
IF @i = 0  
   INSERT....  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef932-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef932-107">See Also</span></span>  
 <span data-ttu-id="ef932-108">[Problemas de migración para los procedimientos almacenados compilados de forma nativa](migration-issues-for-natively-compiled-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ef932-108">[Migration Issues for Natively Compiled Stored Procedures](migration-issues-for-natively-compiled-stored-procedures.md) </span></span>  
 [<span data-ttu-id="ef932-109">Construcciones de Transact-SQL no admitidas en In-Memory OLTP.</span><span class="sxs-lookup"><span data-stu-id="ef932-109">Transact-SQL Constructs Not Supported by In-Memory OLTP</span></span>](transact-sql-constructs-not-supported-by-in-memory-oltp.md)  
  
  
