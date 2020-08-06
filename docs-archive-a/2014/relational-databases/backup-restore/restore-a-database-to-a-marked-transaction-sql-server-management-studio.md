---
title: Restaurar una base de datos en una transacción marcada (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.markedtransaction.f1
helpviewer_keywords:
- database restores [SQL Server], marked transactions
- restoring databases [SQL Server], marked transactions
- marked transactions [SQL Server], restoring
ms.assetid: 8f0ea144-1819-4832-905f-e5d0f49b066b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8de9ef5bed389f020f14e60ccd99f39698e7110f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675462"
---
# <a name="restore-a-database-to-a-marked-transaction-sql-server-management-studio"></a><span data-ttu-id="f7bb3-102">Restaurar una base de datos en una transacción marcada (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f7bb3-102">Restore a Database to a Marked Transaction (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f7bb3-103">Cuando una base de datos se encuentra en estado de restauración, puede usar el cuadro de diálogo **Restaurar registro de transacciones** para restaurar la base de datos a una transacción marcada en las copias de seguridad de registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-103">When a database is in the restoring state, you can use the **Restore Transaction Log** dialog box to restore the database to a marked transaction in the available log backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7bb3-104">Para obtener más información, vea [Usar transacciones marcadas para recuperar bases de datos relacionadas sistemáticamente &#40;modelo de recuperación completa&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) y [Recuperación de bases de datos relacionadas que contienen transacciones marcadas](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="f7bb3-104">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) and [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
### <a name="to-restore-a-marked-transaction"></a><span data-ttu-id="f7bb3-105">Para restaurar una transacción marcada</span><span class="sxs-lookup"><span data-stu-id="f7bb3-105">To restore a marked transaction</span></span>  
  
1.  <span data-ttu-id="f7bb3-106">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-106">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f7bb3-107">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-107">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="f7bb3-108">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, después, haga clic en **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-108">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="f7bb3-109">Haga clic en **Registro de transacciones**para abrir el cuadro de diálogo **Restaurar registro de transacciones** .</span><span class="sxs-lookup"><span data-stu-id="f7bb3-109">Click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
5.  <span data-ttu-id="f7bb3-110">En la página **General** , en la sección **Restaurar en** , seleccione **Transacción marcada**para abrir el cuadro de diálogo **Seleccionar transacción marcada** .</span><span class="sxs-lookup"><span data-stu-id="f7bb3-110">On the **General** page, in the **Restore To** section, select **Marked transaction**, which opens the **Select Marked Transaction** dialog box.</span></span> <span data-ttu-id="f7bb3-111">Este cuadro de diálogo muestra una cuadrícula en la que aparecen las transacciones marcadas disponibles en las copias de seguridad de los registros de transacciones seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-111">This dialog box displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
     <span data-ttu-id="f7bb3-112">De forma predeterminada, la restauración se realiza hasta la transacción marcada, sin incluirla.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-112">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="f7bb3-113">Para restaurar también la transacción marcada, seleccione **Incluir transacción marcada**.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-113">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
     <span data-ttu-id="f7bb3-114">En la tabla siguiente se muestran los encabezados de columna de la cuadrícula y se describen sus valores.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-114">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="f7bb3-115">Encabezado</span><span class="sxs-lookup"><span data-stu-id="f7bb3-115">Header</span></span>|<span data-ttu-id="f7bb3-116">Value</span><span class="sxs-lookup"><span data-stu-id="f7bb3-116">Value</span></span>|  
    |------------|-----------|  
    |\<blank>|<span data-ttu-id="f7bb3-117">Muestra una casilla para seleccionar la marca.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-117">Displays a checkbox for selecting the mark.</span></span>|  
    |<span data-ttu-id="f7bb3-118">**Marca de transacción**</span><span class="sxs-lookup"><span data-stu-id="f7bb3-118">**Transaction Mark**</span></span>|<span data-ttu-id="f7bb3-119">Nombre de la transacción marcada especificada por el usuario cuando se confirmó la transacción.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-119">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
    |<span data-ttu-id="f7bb3-120">**Date**</span><span class="sxs-lookup"><span data-stu-id="f7bb3-120">**Date**</span></span>|<span data-ttu-id="f7bb3-121">Fecha y hora de confirmación de la transacción.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-121">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="f7bb3-122">La fecha y hora de la transacción se muestran tal como están registradas en la tabla **msdbgmarkhistory** , no en la fecha y hora del equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-122">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
    |<span data-ttu-id="f7bb3-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f7bb3-123">**Description**</span></span>|<span data-ttu-id="f7bb3-124">Descripción de la transacción marcada especificada por el usuario al confirmar la transacción (si la hay).</span><span class="sxs-lookup"><span data-stu-id="f7bb3-124">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
    |<span data-ttu-id="f7bb3-125">**LSN**</span><span class="sxs-lookup"><span data-stu-id="f7bb3-125">**LSN**</span></span>|<span data-ttu-id="f7bb3-126">Número de flujo de registro de la transacción marcada.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-126">Log sequence number of the marked transaction.</span></span>|  
    |<span data-ttu-id="f7bb3-127">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="f7bb3-127">**Database**</span></span>|<span data-ttu-id="f7bb3-128">Nombre de la base de datos en la que se confirmó la transacción marcada.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-128">Name of the database where the marked transaction was committed.</span></span>|  
    |<span data-ttu-id="f7bb3-129">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="f7bb3-129">**User Name**</span></span>|<span data-ttu-id="f7bb3-130">Nombre del usuario de la base de datos que confirmó la transacción marcada.</span><span class="sxs-lookup"><span data-stu-id="f7bb3-130">Name of the database user who committed the marked transaction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7bb3-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7bb3-131">See Also</span></span>  
 <span data-ttu-id="f7bb3-132">[Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="f7bb3-132">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 [<span data-ttu-id="f7bb3-133">Restaurar una copia de seguridad de registros de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f7bb3-133">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
  
