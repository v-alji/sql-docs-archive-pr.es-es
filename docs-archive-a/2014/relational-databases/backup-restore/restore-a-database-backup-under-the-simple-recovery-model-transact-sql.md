---
title: Restaurar una copia de seguridad de base de datos en el modelo de recuperación simple (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- database restores [SQL Server], full backups
- backing up databases [SQL Server], full backups
- database backups [SQL Server], full backups
- restoring databases [SQL Server], full backups
ms.assetid: a928fa36-e285-476f-9a7b-6840a8bb7283
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e264dd380c3dff40dacc4eb576d34af5195dec01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745338"
---
# <a name="restore-a-database-backup-under-the-simple-recovery-model-transact-sql"></a><span data-ttu-id="14ab8-102">Restaurar una copia de seguridad de base de datos en el modelo de recuperación simple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="14ab8-102">Restore a Database Backup Under the Simple Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="14ab8-103">En este tema se explica cómo restaurar una copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14ab8-103">This topic explains how to restore a full database backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="14ab8-104">El administrador del sistema encargado de restaurar la copia de seguridad de la base de datos completa debe ser la única persona que esté utilizando la base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="14ab8-104">The system administrator restoring the full database backup must be the only person currently using the database to be restored.</span></span>  
  
## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="14ab8-105">Requisitos previos y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="14ab8-105">Prerequisites and Recommendations</span></span>  
  
-   <span data-ttu-id="14ab8-106">Para restaurar una base de datos cifrada, debe tener acceso al certificado o la clave asimétrica que se usó para cifrarla.</span><span class="sxs-lookup"><span data-stu-id="14ab8-106">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="14ab8-107">La base de datos no se puede restaurar sin el certificado o la clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="14ab8-107">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="14ab8-108">Como resultado, se debe conservar el certificado que se usa para cifrar la clave de cifrado de base de datos mientras se necesite la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="14ab8-108">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="14ab8-109">Para obtener más información, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="14ab8-109">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
-   <span data-ttu-id="14ab8-110">Por razones de seguridad, se recomienda no adjuntar ni restaurar bases de datos de orígenes desconocidos o que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="14ab8-110">For security purposes, we recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="14ab8-111">Es posible que dichas bases de datos contengan código malintencionado que podría ejecutar código [!INCLUDE[tsql](../../includes/tsql-md.md)] no deseado o provocar errores al modificar el esquema o la estructura de la base de datos física.</span><span class="sxs-lookup"><span data-stu-id="14ab8-111">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="14ab8-112">Para usar una base de datos desde un origen desconocido o que no sea de confianza, ejecute [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) en la base de datos de un servidor que no sea de producción y examine también el código, como procedimientos almacenados u otro código definido por el usuario, en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14ab8-112">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="database-compatibility-level-after-upgrade"></a><span data-ttu-id="14ab8-113">Nivel de compatibilidad de la base de datos después de la actualización</span><span class="sxs-lookup"><span data-stu-id="14ab8-113">Database Compatibility Level After Upgrade</span></span>  
 <span data-ttu-id="14ab8-114">Los niveles de compatibilidad de las bases de datos **tempdb**, **model**, **msdb** y **Resource** quedan establecidos en el nivel de compatibilidad de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] después de la actualización.</span><span class="sxs-lookup"><span data-stu-id="14ab8-114">The compatibility levels of the **tempdb**, **model**, **msdb** and **Resource** databases are set to the compatibility level of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after upgrade.</span></span> <span data-ttu-id="14ab8-115">La base de datos del sistema **master** conserva el nivel de compatibilidad que tenía antes de la actualización, a menos que dicho nivel sea inferior a 100.</span><span class="sxs-lookup"><span data-stu-id="14ab8-115">The **master** system database retains the compatibility level it had before upgrade, unless that level was less than 100.</span></span> <span data-ttu-id="14ab8-116">Si el nivel de compatibilidad de la base de datos **master** era inferior a 100 antes de la actualización, se establece en 100 después de la misma.</span><span class="sxs-lookup"><span data-stu-id="14ab8-116">If the compatibility level of **master** was less than 100 before upgrade, it is set to 100 after upgrade.</span></span>  
  
 <span data-ttu-id="14ab8-117">Si el nivel de compatibilidad de una base de datos de usuario era 100 o superior antes de la actualización, permanece igual después de la misma.</span><span class="sxs-lookup"><span data-stu-id="14ab8-117">If the compatibility level of a user database was 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="14ab8-118">Si el nivel de compatibilidad era 90 antes de la actualización, en la base de datos actualizada, el nivel de compatibilidad se establece en 100, que es el nivel de compatibilidad mínimo admitido en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14ab8-118">If the compatibility level was 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14ab8-119">Las nuevas bases de datos de usuario heredarán el nivel de compatibilidad de la base de datos **model** .</span><span class="sxs-lookup"><span data-stu-id="14ab8-119">New user databases will inherit the compatibility level of the **model** database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="14ab8-120">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="14ab8-120">Procedures</span></span>  
  
#### <a name="to-restore-a-full-database-backup"></a><span data-ttu-id="14ab8-121">Para restaurar una copia de seguridad completa de la base de datos</span><span class="sxs-lookup"><span data-stu-id="14ab8-121">To restore a full database backup</span></span>  
  
1.  <span data-ttu-id="14ab8-122">Ejecute la instrucción RESTORE DATABASE para restaurar la copia de seguridad completa de la base de datos; para ello, especifique:</span><span class="sxs-lookup"><span data-stu-id="14ab8-122">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="14ab8-123">El nombre de la base de datos que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="14ab8-123">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="14ab8-124">El dispositivo de copia de seguridad desde el que se restaurará la copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14ab8-124">The backup device from where the full database backup is restored.</span></span>  
  
    -   <span data-ttu-id="14ab8-125">La cláusula NORECOVERY si va a aplicar una copia de seguridad del registro de transacciones o una copia de seguridad diferencial de la base de datos después de restaurar la copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14ab8-125">The NORECOVERY clause if you have a transaction log or differential database backup to apply after restoring the full database backup.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="14ab8-126">Para restaurar una base de datos cifrada, debe tener acceso al certificado o la clave asimétrica que se usó para cifrarla.</span><span class="sxs-lookup"><span data-stu-id="14ab8-126">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="14ab8-127">La base de datos no se puede restaurar sin el certificado o la clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="14ab8-127">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="14ab8-128">Como resultado, se debe conservar el certificado que se usa para cifrar la clave de cifrado de base de datos mientras se necesite la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="14ab8-128">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="14ab8-129">Para obtener más información, consulte [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="14ab8-129">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
2.  <span data-ttu-id="14ab8-130">Opcionalmente, especifique:</span><span class="sxs-lookup"><span data-stu-id="14ab8-130">Optionally, specify:</span></span>  
  
    -   <span data-ttu-id="14ab8-131">La cláusula FILE para identificar el conjunto de copia de seguridad en el dispositivo de copia de seguridad con el que se realizará la restauración.</span><span class="sxs-lookup"><span data-stu-id="14ab8-131">The FILE clause to identify the backup set on the backup device to restore.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14ab8-132">Si restaura una base de datos de una versión anterior en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], la base de datos se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="14ab8-132">If you restore an earlier version database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the database is automatically upgraded.</span></span> <span data-ttu-id="14ab8-133">Normalmente, la base de datos está disponible inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="14ab8-133">Typically, the database becomes available immediately.</span></span> <span data-ttu-id="14ab8-134">Pero si la base de datos de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tiene índices de texto completo, el proceso de actualización los importa, los restablece o los vuelve a generar, en función del valor de la propiedad del servidor  **upgrade_option** .</span><span class="sxs-lookup"><span data-stu-id="14ab8-134">However, if a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the  **upgrade_option** server property.</span></span> <span data-ttu-id="14ab8-135">Si la opción de actualización se establece en importar (**upgrade_option** = 2) o en volver a generar (**upgrade_option** = 0), los índices de texto completo no estarán disponibles durante la actualización.</span><span class="sxs-lookup"><span data-stu-id="14ab8-135">If the upgrade option is set to import (**upgrade_option** = 2) or rebuild (**upgrade_option** = 0), the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="14ab8-136">Dependiendo de la cantidad de datos que se indicen, la importación puede requerir varias horas y volver a generar puede requerir hasta diez veces más.</span><span class="sxs-lookup"><span data-stu-id="14ab8-136">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="14ab8-137">Observe también que cuando la opción de actualización se establece en importar, se vuelven a generar los índices de texto completo asociados si no se dispone de un catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="14ab8-137">Note also that when the upgrade option is set to import, the associated full-text indexes are rebuilt if a full-text catalog is not available.</span></span> <span data-ttu-id="14ab8-138">Para cambiar el valor de la propiedad de servidor **upgrade_option** , use [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="14ab8-138">To change the setting of the **upgrade_option** server property, use [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14ab8-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14ab8-139">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="14ab8-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="14ab8-140">Description</span></span>  
 <span data-ttu-id="14ab8-141">En este ejemplo se restaura la copia de seguridad completa de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] desde una cinta.</span><span class="sxs-lookup"><span data-stu-id="14ab8-141">This example restores the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] full database backup from tape.</span></span>  
  
### <a name="example"></a><span data-ttu-id="14ab8-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14ab8-142">Example</span></span>  
  
```  
USE master;  
GO  
RESTORE DATABASE AdventureWorks2012  
   FROM TAPE = '\\.\Tape0';  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="14ab8-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14ab8-143">See Also</span></span>  
 <span data-ttu-id="14ab8-144">[Restauraciones de base de datos completas &#40;modelo de recuperación completa&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="14ab8-144">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="14ab8-145">[Restauraciones de base de datos completas &#40;modelo de recuperación simple&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="14ab8-145">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="14ab8-146">[Copias de seguridad completas de bases de datos &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="14ab8-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="14ab8-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14ab8-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="14ab8-148">[Historial de copias de seguridad e información de encabezados &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="14ab8-148">[Backup History and Header Information &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span></span>  
 [<span data-ttu-id="14ab8-149">Volver a generar bases de datos del sistema</span><span class="sxs-lookup"><span data-stu-id="14ab8-149">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
