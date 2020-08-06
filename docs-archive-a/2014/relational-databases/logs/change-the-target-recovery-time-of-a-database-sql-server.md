---
title: Cambio del tiempo de recuperación de destino de una base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/13/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: e466419a-d8a4-48f7-8d97-13a903ad6b15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c4331d2ade2819d172189a0de9daddecf3d9f6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671541"
---
# <a name="change-the-target-recovery-time-of-a-database-sql-server"></a><span data-ttu-id="cea9d-102">Cambiar el tiempo de recuperación de destino de una base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cea9d-102">Change the Target Recovery Time of a Database (SQL Server)</span></span>
  <span data-ttu-id="cea9d-103">En este tema se describe cómo establecer el cambio el tiempo de recuperación de destino de una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cea9d-103">This topic describes how to set the change the target recovery time of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cea9d-104">De forma predeterminada, el tiempo de recuperación de destino es 0 y la base de datos utiliza *puntos de comprobación automáticos* (que se controlan mediante la opción de servidor **intervalo de recuperación** ).</span><span class="sxs-lookup"><span data-stu-id="cea9d-104">By default, the target recovery time is 0, and the database uses *automatic checkpoints* (which are controlled by the **recovery interval** server option).</span></span> <span data-ttu-id="cea9d-105">Establecer el tiempo de recuperación de destino en un valor mayor que 0 hace que la base de datos utilice *puntos de comprobación indirectos* y establece un límite superior en el tiempo de recuperación de esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="cea9d-105">Setting the target recovery time to greater than 0 causes the database to use the *indirect-checkpoints* and establishes an upper-bound on recovery time for this database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cea9d-106">El límite superior especificado para una base de datos determinada por el valor de tiempo de recuperación de destino se puede superar si una transacción de larga duración provoca tiempos de UNDO excesivos.</span><span class="sxs-lookup"><span data-stu-id="cea9d-106">The upper-bound that is specified for a given database by its target recovery time setting could be exceeded if a long-running transaction causes excessive UNDO times.</span></span>  
  
-   <span data-ttu-id="cea9d-107">**Antes de empezar:**  [Limitaciones y restricciones](#Restrictions), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="cea9d-107">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="cea9d-108">**Para cambiar el tiempo de recuperación de destino con:**  [SQL Server Management Studio](#SSMSProcedure) o [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="cea9d-108">**To change the target recovery time, using:**  [SQL Server Management Studio](#SSMSProcedure) or [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cea9d-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="cea9d-109">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>  
  
> [!CAUTION]  
>  <span data-ttu-id="cea9d-110">Una carga de trabajo transaccional en línea en una base de datos que esté configurada para puntos de comprobación indirectos podría experimentar un deterioro del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cea9d-110">An online transactional workload on a database that is configured for indirect checkpoints could experience performance degradation.</span></span> <span data-ttu-id="cea9d-111">Los puntos de comprobación indirectos garantizan que el número de páginas desfasadas se encuentra por debajo de un umbral determinado para que la recuperación de la base de datos finalice en el tiempo de recuperación de destino.</span><span class="sxs-lookup"><span data-stu-id="cea9d-111">Indirect checkpoints make sure that the number of dirty pages are below a certain threshold so that the database recovery completes within the target recovery time.</span></span> <span data-ttu-id="cea9d-112">La opción de configuración de intervalo de recuperación usa el número de transacciones para determinar el tiempo de recuperación a diferencia de los puntos de comprobación indirectos, que usan el número de páginas desfasadas.</span><span class="sxs-lookup"><span data-stu-id="cea9d-112">The recovery interval configuration option uses the number of transactions to determine the recovery time as opposed to indirect checkpoints which makes use of number of dirty pages.</span></span> <span data-ttu-id="cea9d-113">Cuando se habilitan los puntos de comprobación indirectos en una base de datos que recibe un gran número de operaciones de DML, el escritor en segundo plano puede iniciar agresivamente el vaciado de búferes desfasados en el disco para asegurarse de que el tiempo necesario para realizar la recuperación se encuentra dentro del tiempo de recuperación de destino establecido de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cea9d-113">When indirect checkpoints are enabled on a database receiving a large number of DML operations, the background writer can start aggressively flushing dirty buffers to disk to ensure that the time required to perform recovery is within the target recovery time set of the database.</span></span> <span data-ttu-id="cea9d-114">Esto puede provocar actividad de E/S adicional en determinados sistemas que pueden contribuir a un cuello de botella de rendimiento si el subsistema del disco está funcionando por encima del umbral de E/S o cerca de él.</span><span class="sxs-lookup"><span data-stu-id="cea9d-114">This can cause additional I/O activity on certain systems which can contribute to a performance bottleneck if the disk subsystem is operating above or nearing the I/O threshold.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cea9d-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cea9d-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cea9d-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="cea9d-116">Permissions</span></span>  
 <span data-ttu-id="cea9d-117">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cea9d-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cea9d-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cea9d-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="cea9d-119">**Para cambiar el tiempo de recuperación de destino**</span><span class="sxs-lookup"><span data-stu-id="cea9d-119">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="cea9d-120">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y expándala.</span><span class="sxs-lookup"><span data-stu-id="cea9d-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and expand that instance.</span></span>  
  
2.  <span data-ttu-id="cea9d-121">Haga clic con el botón derecho en la base de datos que quiera cambiar y haga clic en el comando **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="cea9d-121">Right-click the database you want to change, and click the **Properties** command.</span></span>  
  
3.  <span data-ttu-id="cea9d-122">En el cuadro de diálogo **Propiedades de la base de datos** , haga clic en la página **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="cea9d-122">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="cea9d-123">En el panel **Recuperación** , en el campo de **Tiempo de recuperación de destino (segundos)** , especifique el número de segundos que quiera como límite superior para el tiempo de recuperación de esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="cea9d-123">In the **Recovery** panel, in the **Target Recovery Time (Seconds)** field, specify the number of seconds that you want as the upper-bound on the recovery time for this database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cea9d-124">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cea9d-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="cea9d-125">**Para cambiar el tiempo de recuperación de destino**</span><span class="sxs-lookup"><span data-stu-id="cea9d-125">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="cea9d-126">Conéctese a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] donde reside la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cea9d-126">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the database resides.</span></span>  
  
2.  <span data-ttu-id="cea9d-127">Use la siguiente instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="cea9d-127">Use the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)statement, as follows:</span></span>  
  
     <span data-ttu-id="cea9d-128">TARGET_RECOVERY_TIME **=** _target_recovery_time_ { SECONDS | MINUTES }</span><span class="sxs-lookup"><span data-stu-id="cea9d-128">TARGET_RECOVERY_TIME **=**_target_recovery_time_ { SECONDS | MINUTES }</span></span>  
  
     <span data-ttu-id="cea9d-129">*target_recovery_time*</span><span class="sxs-lookup"><span data-stu-id="cea9d-129">*target_recovery_time*</span></span>  
     <span data-ttu-id="cea9d-130">Cuando el valor es mayor que 0 (valor predeterminado), especifica el límite superior para el tiempo de recuperación de la base de datos especificada en caso de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cea9d-130">When greater than 0 (the default), specifies the upper-bound on the recovery time for the specified database in the event of a crash.</span></span>  
  
     <span data-ttu-id="cea9d-131">SECONDS</span><span class="sxs-lookup"><span data-stu-id="cea9d-131">SECONDS</span></span>  
     <span data-ttu-id="cea9d-132">Indica que *target_recovery_time* se expresa como el número de segundos.</span><span class="sxs-lookup"><span data-stu-id="cea9d-132">Indicates that *target_recovery_time* is expressed as the number of seconds.</span></span>  
  
     <span data-ttu-id="cea9d-133">MINUTES</span><span class="sxs-lookup"><span data-stu-id="cea9d-133">MINUTES</span></span>  
     <span data-ttu-id="cea9d-134">Indica que *target_recovery_time* se expresa como el número de minutos.</span><span class="sxs-lookup"><span data-stu-id="cea9d-134">Indicates that *target_recovery_time* is expressed as the number of minutes.</span></span>  
  
     <span data-ttu-id="cea9d-135">El ejemplo siguiente se establece el tiempo de recuperación de destino de la base de datos de [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] en `60` segundos.</span><span class="sxs-lookup"><span data-stu-id="cea9d-135">The following example sets the target recovery time of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to `60` seconds.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET TARGET_RECOVERY_TIME = 60 SECONDS;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cea9d-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cea9d-136">See Also</span></span>  
 <span data-ttu-id="cea9d-137">[Puntos de comprobación de base de datos &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cea9d-137">[Database Checkpoints &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span></span>  
 [<span data-ttu-id="cea9d-138">Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cea9d-138">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
