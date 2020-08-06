---
title: Restaurar una base de datos al punto de error en el modelo de recuperación completa (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- point of failure [SQL Server]
- restoring databases [SQL Server], point of failure
- database restores [SQL Server], point of failure
ms.assetid: 04106e18-bbf7-4a5e-a2e1-3d65319814d5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95b73660ebb44f4daffe6eaefd873699cfbbd8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672119"
---
# <a name="restore-a-database-to-the-point-of-failure-under-the-full-recovery-model-transact-sql"></a><span data-ttu-id="4eec3-102">Restaurar una base de datos según el punto de error en el modelo de recuperación completa (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4eec3-102">Restore a Database to the Point of Failure Under the Full Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="4eec3-103">En este tema se explica cómo realizar una restauración hasta el momento del error.</span><span class="sxs-lookup"><span data-stu-id="4eec3-103">This topic explains how to restore to the point of failure.</span></span> <span data-ttu-id="4eec3-104">Este tema solo es relevante para las bases de datos que utilizan los modelos de recuperación completa u optimizado para cargas masivas de registros.</span><span class="sxs-lookup"><span data-stu-id="4eec3-104">The topic is relevant only for databases that are using the full or bulk-logged recovery models.</span></span>  
  
### <a name="to-restore-to-the-point-of-failure"></a><span data-ttu-id="4eec3-105">Para restaurar hasta el momento del error</span><span class="sxs-lookup"><span data-stu-id="4eec3-105">To restore to the point of failure</span></span>  
  
1.  <span data-ttu-id="4eec3-106">Realice una copia de seguridad del final del registro mediante la ejecución de la siguiente instrucción [BACKUP](/sql/t-sql/statements/backup-transact-sql) básica:</span><span class="sxs-lookup"><span data-stu-id="4eec3-106">Back up the tail of the log by running the following basic [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement:</span></span>  
  
    ```  
    BACKUP LOG <database_name> TO <backup_device>   
       WITH NORECOVERY, NO_TRUNCATE;  
    ```  
  
2.  <span data-ttu-id="4eec3-107">Restaure una copia de seguridad completa de la base de datos mediante la ejecución de la siguiente instrucción [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) básica:</span><span class="sxs-lookup"><span data-stu-id="4eec3-107">Restore a full database backup by running the following basic [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql) statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
3.  <span data-ttu-id="4eec3-108">Opcionalmente, restaure una copia de seguridad diferencial de la base de datos mediante la ejecución de la siguiente instrucción RESTORE DATABASE básica:</span><span class="sxs-lookup"><span data-stu-id="4eec3-108">Optionally, restore a differential database backup by running the following basic RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
4.  <span data-ttu-id="4eec3-109">Aplique los registros de transacciones, incluida la copia del final del registro que ha creado en el paso 1, mediante la especificación de WITH NORECOVERY en la instrucción RESTORE LOG:</span><span class="sxs-lookup"><span data-stu-id="4eec3-109">Apply each transaction log, including the tail-log backup you created in step 1, by specifying WITH NORECOVERY in the RESTORE LOG statement:</span></span>  
  
    ```  
    RESTORE LOG <database_name> FROM <backup_device>   
       WITH NORECOVERY;  
    ```  
  
5.  <span data-ttu-id="4eec3-110">Recupere la base de datos mediante la ejecución de la siguiente instrucción RESTORE DATABASE:</span><span class="sxs-lookup"><span data-stu-id="4eec3-110">Recover the database by running the following RESTORE DATABASE statement:</span></span>  
  
    ```  
    RESTORE DATABASE <database_name>   
       WITH RECOVERY;  
    ```  
  
## <a name="example"></a><span data-ttu-id="4eec3-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4eec3-111">Example</span></span>  
 <span data-ttu-id="4eec3-112">Antes de que pueda ejecutar el ejemplo, debe completar los preparativos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4eec3-112">Before you can run the example, you must complete the following preparations:</span></span>  
  
1.  <span data-ttu-id="4eec3-113">La base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] utiliza el modelo de recuperación simple de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4eec3-113">The default recovery model of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database is the simple recovery model.</span></span> <span data-ttu-id="4eec3-114">Puesto que este modelo de recuperación no admite la restauración hasta el punto del error, configure [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] para que utilice el modelo de recuperación completa mediante la ejecución de la siguiente instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="4eec3-114">Because this recovery model does not support restoring to the point of a failure, set [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] to use the full recovery model by running the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement:</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks2012 SET RECOVERY FULL;  
    ```  
  
2.  <span data-ttu-id="4eec3-115">Cree una copia de seguridad completa de la base de datos mediante la siguiente instrucción BACKUP:</span><span class="sxs-lookup"><span data-stu-id="4eec3-115">Create a full database back of the database by using the following BACKUP statement:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Data.bck';  
    ```  
  
3.  <span data-ttu-id="4eec3-116">Cree una copia de seguridad de registros rutinaria:</span><span class="sxs-lookup"><span data-stu-id="4eec3-116">Create a routine log backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks2012 TO DISK = 'C:\AdventureWorks2012_Log.bck';  
    ```  
  
 <span data-ttu-id="4eec3-117">En el ejemplo siguiente se restauran las copias de seguridad que se han creado con anterioridad, tras crear una copia del final del registro de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eec3-117">The following example restores the backups that are created previously, after creating a tail-log backup of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="4eec3-118">(En este paso se asume que se puede tener acceso al disco de registros).</span><span class="sxs-lookup"><span data-stu-id="4eec3-118">(This step assumes that the log disk can be accessed.)</span></span>  
  
 <span data-ttu-id="4eec3-119">Primero, en el ejemplo se crea una copia del final del registro de la base de datos que captura el registro activo y deja la base de datos en el estado de restauración.</span><span class="sxs-lookup"><span data-stu-id="4eec3-119">First, the example creates a tail-log backup of the database that captures the active log and leaves the database in the Restoring state.</span></span> <span data-ttu-id="4eec3-120">A continuación, en el ejemplo se restaura la copia de seguridad de la base de datos, se aplica la copia del final del registro rutinaria que se ha creado con anterioridad y se aplica la copia de seguridad de registros después del error.</span><span class="sxs-lookup"><span data-stu-id="4eec3-120">Then, the example restores the database backup, applies the routine log backup created previously, and applies the tail-log backup.</span></span> <span data-ttu-id="4eec3-121">Finalmente, en el ejemplo se recupera la base de datos en un paso diferente.</span><span class="sxs-lookup"><span data-stu-id="4eec3-121">Finally, the example recovers the database in a separate step.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4eec3-122">El comportamiento predeterminado es recuperar una base de datos como parte de la instrucción que restaura la copia de seguridad final.</span><span class="sxs-lookup"><span data-stu-id="4eec3-122">The default behavior is to recover a database as part of the statement that restores the final backup.</span></span>  
  
```  
/* Example of restoring a to the point of failure */  
-- Step 1: Create a tail-log backup by using WITH NORECOVERY.  
BACKUP LOG AdventureWorks2012  
   TO DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 2: Restore the full database backup.  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Data.bck'  
   WITH NORECOVERY;  
GO  
-- Step 3: Restore the first transaction log backup.  
RESTORE LOG AdventureWorks2012  
   FROM DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 4: Restore the tail-log backup.  
RESTORE LOG AdventureWorks2012  
   FROM  DISK = 'C:\AdventureWorks2012_Log.bck'  
   WITH NORECOVERY;  
GO  
-- Step 5: Recover the database.  
RESTORE DATABASE AdventureWorks2012  
   WITH RECOVERY;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4eec3-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4eec3-123">See Also</span></span>  
 <span data-ttu-id="4eec3-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4eec3-124">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="4eec3-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4eec3-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
