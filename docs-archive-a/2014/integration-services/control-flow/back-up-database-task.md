---
title: Tarea Copia de seguridad de la base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.backupdatabasetask.f1
helpviewer_keywords:
- database backups [Integration Services]
- Back Up Database task [Integration Services]
- backing up databases [Integration Services]
- transaction log backups [Integration Services]
- backing up transaction logs [Integration Services]
ms.assetid: b8839d71-13b7-41f2-a434-cb95020e79d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b0980d89cc915121414dd7d3c89be6f4d72eb715
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670499"
---
# <a name="back-up-database-task"></a><span data-ttu-id="7a4ef-102">Tarea Copia de seguridad de la base de datos</span><span class="sxs-lookup"><span data-stu-id="7a4ef-102">Back Up Database Task</span></span>
  <span data-ttu-id="7a4ef-103">La tarea Copia de seguridad de la base de datos realiza distintos tipos de copias de seguridad de bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a4ef-103">The Back Up Database task performs different types of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database backups.</span></span> <span data-ttu-id="7a4ef-104">Para obtener más información, consulte [Realizar copias de seguridad y restaurar bases de datos de SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7a4ef-104">For more information, see [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="7a4ef-105">Un paquete puede utilizar la tarea Copia de seguridad de la base de datos para realizar una copia de seguridad de una o varias bases de datos.</span><span class="sxs-lookup"><span data-stu-id="7a4ef-105">By using the Back Up Database task, a package can back up a single database or multiple databases.</span></span> <span data-ttu-id="7a4ef-106">Si la tarea solo realiza una copia de seguridad de una única base de datos, puede elegir el componente de copia de seguridad: la base de datos o sus archivos y grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="7a4ef-106">If the task backs up only a single database, you can choose the backup component: the database, or its files and filegroups.</span></span>  
  
## <a name="supported-recover-models-and-backup-types"></a><span data-ttu-id="7a4ef-107">Tipos de copia de seguridad y modelos de recuperación admitidos</span><span class="sxs-lookup"><span data-stu-id="7a4ef-107">Supported Recover Models and Backup Types</span></span>  
 <span data-ttu-id="7a4ef-108">En la tabla siguiente se muestran los modelos de recuperación y los tipos de copia de seguridad compatibles con la tarea Copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a4ef-108">The following table lists the recovery models and backup types that the Back Up Database task supports.</span></span>  
  
|<span data-ttu-id="7a4ef-109">modelo de recuperación</span><span class="sxs-lookup"><span data-stu-id="7a4ef-109">Recovery model</span></span>|<span data-ttu-id="7a4ef-110">Base de datos</span><span class="sxs-lookup"><span data-stu-id="7a4ef-110">Database</span></span>|<span data-ttu-id="7a4ef-111">Diferencial de base de datos</span><span class="sxs-lookup"><span data-stu-id="7a4ef-111">Database differential</span></span>|<span data-ttu-id="7a4ef-112">Registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="7a4ef-112">Transaction log</span></span>|<span data-ttu-id="7a4ef-113">Archivos o diferencial de archivos</span><span class="sxs-lookup"><span data-stu-id="7a4ef-113">File or file differential</span></span>|  
|--------------------|--------------|---------------------------|---------------------|-------------------------------|  
|<span data-ttu-id="7a4ef-114">Simple</span><span class="sxs-lookup"><span data-stu-id="7a4ef-114">Simple</span></span>|<span data-ttu-id="7a4ef-115">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="7a4ef-115">Required</span></span>|<span data-ttu-id="7a4ef-116">Opcional</span><span class="sxs-lookup"><span data-stu-id="7a4ef-116">Optional</span></span>|<span data-ttu-id="7a4ef-117">No compatible</span><span class="sxs-lookup"><span data-stu-id="7a4ef-117">Not supported</span></span>|<span data-ttu-id="7a4ef-118">No compatible</span><span class="sxs-lookup"><span data-stu-id="7a4ef-118">Not supported</span></span>|  
|<span data-ttu-id="7a4ef-119">Completo</span><span class="sxs-lookup"><span data-stu-id="7a4ef-119">Full</span></span>|<span data-ttu-id="7a4ef-120">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="7a4ef-120">Required</span></span>|<span data-ttu-id="7a4ef-121">Opcional</span><span class="sxs-lookup"><span data-stu-id="7a4ef-121">Optional</span></span>|<span data-ttu-id="7a4ef-122">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="7a4ef-122">Required</span></span>|<span data-ttu-id="7a4ef-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="7a4ef-123">Optional</span></span>|  
|<span data-ttu-id="7a4ef-124">Registro masivo</span><span class="sxs-lookup"><span data-stu-id="7a4ef-124">Bulk-logged</span></span>|<span data-ttu-id="7a4ef-125">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="7a4ef-125">Required</span></span>|<span data-ttu-id="7a4ef-126">Opcional</span><span class="sxs-lookup"><span data-stu-id="7a4ef-126">Optional</span></span>|<span data-ttu-id="7a4ef-127">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="7a4ef-127">Required</span></span>|<span data-ttu-id="7a4ef-128">Opcional</span><span class="sxs-lookup"><span data-stu-id="7a4ef-128">Optional</span></span>|  
  
 <span data-ttu-id="7a4ef-129">La tarea Copia de seguridad de la base de datos encapsula una instrucción BACKUP de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="7a4ef-129">The Back Up Database task encapsulates a Transact-SQL BACKUP statement.</span></span> <span data-ttu-id="7a4ef-130">Para obtener más información, vea [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a4ef-130">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
## <a name="configuration-of-the-back-up-database-task"></a><span data-ttu-id="7a4ef-131">Configuración de la tarea Copia de seguridad de la base de datos</span><span class="sxs-lookup"><span data-stu-id="7a4ef-131">Configuration of the Back Up Database Task</span></span>  
 <span data-ttu-id="7a4ef-132">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a4ef-132">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="7a4ef-133">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a4ef-133">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7a4ef-134">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a4ef-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7a4ef-135">Tarea Copia de seguridad de base de datos &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="7a4ef-135">Back Up Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/options-in-the-back-up-database-task-for-maintenance-plan.md)  
  
 <span data-ttu-id="7a4ef-136">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="7a4ef-136">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7a4ef-137">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="7a4ef-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
