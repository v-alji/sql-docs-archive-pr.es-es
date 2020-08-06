---
title: MSSQLSERVER_3159 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3159 (Database Engine error)
ms.assetid: c93c1003-0e3a-40aa-9873-44a0f5b8b57e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b469842b2aab15980c72ea01e46270c55ef29e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673020"
---
# <a name="mssqlserver_3159"></a><span data-ttu-id="75b44-102">MSSQLSERVER_3159</span><span class="sxs-lookup"><span data-stu-id="75b44-102">MSSQLSERVER_3159</span></span>
    
## <a name="details"></a><span data-ttu-id="75b44-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="75b44-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75b44-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="75b44-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="75b44-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="75b44-105">Event ID</span></span>|<span data-ttu-id="75b44-106">3159</span><span class="sxs-lookup"><span data-stu-id="75b44-106">3159</span></span>|  
|<span data-ttu-id="75b44-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="75b44-107">Event Source</span></span>|<span data-ttu-id="75b44-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="75b44-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="75b44-109">Componente</span><span class="sxs-lookup"><span data-stu-id="75b44-109">Component</span></span>|<span data-ttu-id="75b44-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="75b44-110">SQLEngine</span></span>|  
|<span data-ttu-id="75b44-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="75b44-111">Symbolic Name</span></span>|<span data-ttu-id="75b44-112">LDDB_LOGNOTBACKEDUP</span><span class="sxs-lookup"><span data-stu-id="75b44-112">LDDB_LOGNOTBACKEDUP</span></span>|  
|<span data-ttu-id="75b44-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="75b44-113">Message Text</span></span>|<span data-ttu-id="75b44-114">No se hizo copia del final del registro de la base de datos "%ls".</span><span class="sxs-lookup"><span data-stu-id="75b44-114">The tail of the log for the database "%ls" has not been backed up.</span></span> <span data-ttu-id="75b44-115">Use BACKUP LOG WITH NORECOVERY para realizar una copia de seguridad del registro si contiene trabajo que no desea perder.</span><span class="sxs-lookup"><span data-stu-id="75b44-115">Use BACKUP LOG WITH NORECOVERY to back up the log if it contains work that you do not want to lose.</span></span> <span data-ttu-id="75b44-116">Utilice la cláusula WITH REPLACE o WITH STOPAT de la instrucción RESTORE para sobrescribir el contenido del registro.</span><span class="sxs-lookup"><span data-stu-id="75b44-116">Use the WITH REPLACE or WITH STOPAT clause of the RESTORE statement to just overwrite the contents of the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="75b44-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="75b44-117">Explanation</span></span>  
 <span data-ttu-id="75b44-118">En la mayoría de los casos, en los modelos de recuperación optimizado para cargas masivas de registros [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requiere que se realice una copia deL final del registro después del error para capturar las entradas del registro de las que todavía no se ha realizado una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="75b44-118">In most cases, under the full or bulk-logged recovery models, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires that you back up the tail of the log to capture the log records that have not yet been backed up.</span></span> <span data-ttu-id="75b44-119">Una copia del final del registro que se realizan después del error, justo antes de una operación de restauración, se denominan copias del final del registro después del error.</span><span class="sxs-lookup"><span data-stu-id="75b44-119">A log backup taken of the tail of the log just before a restore operation is called a tail-log backup.</span></span>  
  
 <span data-ttu-id="75b44-120">Cuando se recupera una base de datos al momento en que se produjo el error, la copia del final del registro después del error es la última copia de seguridad de interés del plan de recuperación.</span><span class="sxs-lookup"><span data-stu-id="75b44-120">When you are recovering a database to the point of a failure, the tail-log backup is the last backup of interest in the recovery plan.</span></span> <span data-ttu-id="75b44-121">Si no puede realizar una copia del final del registro después del error, puede recuperar una base de datos solo al final de la última copia de seguridad que se creó antes del error.</span><span class="sxs-lookup"><span data-stu-id="75b44-121">If you cannot back up the tail of the log, you can recover a database only to the end of the last backup that was created before the failure.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="75b44-122">, por lo general, requiere que se realice una copia del final del registro después del error antes de comenzar a restaurar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="75b44-122">usually requires that you take a tail-log backup before you start to restore a database.</span></span> <span data-ttu-id="75b44-123">La copia del final del registro después del error evita la pérdida de trabajo y mantiene intacta la cadena de registros.</span><span class="sxs-lookup"><span data-stu-id="75b44-123">The tail-log backup prevents work loss and keeps the log chain intact.</span></span> <span data-ttu-id="75b44-124">Sin embargo, no todos los escenarios de restauración requieren una copia del final del registro después del error.</span><span class="sxs-lookup"><span data-stu-id="75b44-124">However, not all restore scenarios require a tail-log backup.</span></span> <span data-ttu-id="75b44-125">No es necesario tener una copia del final del registro si el punto de recuperación está incluido en una copia de seguridad de registros anterior, o si está moviendo o reemplazando (sobrescribiendo) la base de datos y no necesita restaurarla a un momento después de la copia de seguridad más reciente.</span><span class="sxs-lookup"><span data-stu-id="75b44-125">You do not have to have a tail-log backup if the recovery point is included in an earlier log backup, or if you are moving or replacing (overwriting) the database and do not need to restore it to a point of time after the most recent backup.</span></span> <span data-ttu-id="75b44-126">También, si los archivos de registro están dañados y no se puede crear una copia del final del registro, debe restaurar la base de datos sin utilizar una copia de seguridad de registros después del error.</span><span class="sxs-lookup"><span data-stu-id="75b44-126">Also, if the log files are damaged and a tail-log backup cannot be created, you must restore the database without using a tail-log backup.</span></span> <span data-ttu-id="75b44-127">Las transacciones confirmadas después de la última copia de seguridad de registros se perderán.</span><span class="sxs-lookup"><span data-stu-id="75b44-127">Any transactions committed after the latest log backup are lost.</span></span> <span data-ttu-id="75b44-128">Para obtener más información, vea "Restaurar sin utilizar una copia del final del registro después del error" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="75b44-128">For more information, see "Restoring Without Using a Tail-Log Backup," later in this topic.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="75b44-129">REPLACE no debe usarse a menudo y solo después de haberlo pensado detenidamente.</span><span class="sxs-lookup"><span data-stu-id="75b44-129">REPLACE should be used rarely, and only after careful consideration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="75b44-130">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="75b44-130">User Action</span></span>  
 <span data-ttu-id="75b44-131">Haga una copia del final del registro después del error y vuelva a intentar la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="75b44-131">Take a tail-log backup, and retry the restore operation.</span></span>  
  
 <span data-ttu-id="75b44-132">Si no puede hacer una copia del final del registro después del error, utilice WITH STOPAT o WITH REPLACE en las instrucciones RESTORE.</span><span class="sxs-lookup"><span data-stu-id="75b44-132">If you cannot back up the tail of the log, use WITH STOPAT or WITH REPLACE in your RESTORE statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b44-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75b44-133">See Also</span></span>  
 <span data-ttu-id="75b44-134">[Restaurar una base de datos de SQL Server a un momento dado &#40;modelo de recuperación completa&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="75b44-134">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="75b44-135">[Realice una copia de seguridad del registro de transacciones cuando la base de datos esté dañada &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="75b44-135">[Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span></span>  
 <span data-ttu-id="75b44-136">[Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="75b44-136">[Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="75b44-137">Copias del final del registro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="75b44-137">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/tail-log-backups-sql-server.md)  
  
  
