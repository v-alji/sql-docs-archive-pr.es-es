---
title: Realizar una copia de seguridad en un conjunto de medios reflejado (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 5fc43a5d-dfd6-4c53-a4ef-3c8da23ccc81
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 255a3c190139c029f5211dcab9780b6d07d975a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673731"
---
# <a name="back-up-to-a-mirrored-media-set-transact-sql"></a><span data-ttu-id="4d8f8-102">Realizar una copia de seguridad en un conjunto de medios reflejado (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4d8f8-102">Back Up to a Mirrored Media Set (Transact-SQL)</span></span>
  <span data-ttu-id="4d8f8-103">En este tema se describe cómo utilizar la [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucción [backup](/sql/t-sql/statements/backup-transact-sql) de para especificar un conjunto de medios reflejado cuando se realiza una copia de seguridad de una base de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] datos.</span><span class="sxs-lookup"><span data-stu-id="4d8f8-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to specify a mirrored media set when backing up a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="4d8f8-104">En la instrucción BACKUP, especifique el primer reflejo en la cláusula TO.</span><span class="sxs-lookup"><span data-stu-id="4d8f8-104">In your BACKUP statement, specify the first mirror in the TO clause.</span></span> <span data-ttu-id="4d8f8-105">A continuación, especifique cada reflejo en su propia cláusula MIRROR TO.</span><span class="sxs-lookup"><span data-stu-id="4d8f8-105">Then, specify each mirror in its own MIRROR TO clause.</span></span> <span data-ttu-id="4d8f8-106">Las cláusulas TO y MIRROR TO deben especificar el mismo número y tipo de dispositivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4d8f8-106">The TO and MIRROR TO clauses must specify the same number and type of backup devices.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d8f8-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d8f8-107">Example</span></span>  
 <span data-ttu-id="4d8f8-108">En el siguiente ejemplo se crea el conjunto de medios reflejado de la ilustración anterior y se realiza una copia de seguridad de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] en ambos reflejos.</span><span class="sxs-lookup"><span data-stu-id="4d8f8-108">The following example creates the mirrored media set illustrated in the previous illustration and backs up the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to both mirrors.</span></span>  
  
```  
BACKUP DATABASE AdventureWorks2012  
TO TAPE = '\\.\tape0', TAPE = '\\.\tape1'  
MIRROR TO TAPE = '\\.\tape2', TAPE = '\\.\tape3'  
WITH  
    FORMAT,  
    MEDIANAME = 'AdventureWorks2012Set1';  
GO  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="4d8f8-109">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4d8f8-109">Related Tasks</span></span>  
 <span data-ttu-id="4d8f8-110">**Para restaurar a partir de una copia de seguridad reflejada**</span><span class="sxs-lookup"><span data-stu-id="4d8f8-110">**To restore from a mirrored backup**</span></span>  
  
-   [<span data-ttu-id="4d8f8-111">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d8f8-111">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="4d8f8-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d8f8-112">See Also</span></span>  
 <span data-ttu-id="4d8f8-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4d8f8-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="4d8f8-114">Conjuntos de medios de copia de seguridad reflejados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4d8f8-114">Mirrored Backup Media Sets &#40;SQL Server&#41;</span></span>](mirrored-backup-media-sets-sql-server.md)  
  
  
