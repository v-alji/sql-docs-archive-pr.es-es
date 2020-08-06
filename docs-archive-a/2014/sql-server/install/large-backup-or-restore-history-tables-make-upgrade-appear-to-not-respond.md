---
title: Las tablas de historial de restauración o copia de seguridad de gran tamaño parecen no responder | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- backup history tables
- history tables
ms.assetid: f88d86ec-324b-4518-b6d7-1af7e7265812
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 918c20f58c00c535d8ed41d887e9671f5e821a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663288"
---
# <a name="large-backup-or-restore-history-tables-make-upgrade-appear-to-not-respond"></a><span data-ttu-id="0efc2-102">Las tablas de historial de restauración o copia de seguridad de gran tamaño hacen que la actualización aparentemente no responda</span><span class="sxs-lookup"><span data-stu-id="0efc2-102">Large backup or restore history tables make upgrade appear to not respond</span></span>
  <span data-ttu-id="0efc2-103">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], se han agregado nuevas columnas a algunas de las tablas de historial de restauración y copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0efc2-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], new columns were added to some of the backup and restore history tables.</span></span> <span data-ttu-id="0efc2-104">Al actualizar estas tablas, es necesario modificarlas para agregar las nuevas columnas.</span><span class="sxs-lookup"><span data-stu-id="0efc2-104">Upgrading these tables requires altering them to add the new columns.</span></span> <span data-ttu-id="0efc2-105">Si una o varias de estas tablas contienen un gran número de filas, la actualización se detendrá durante un periodo de tiempo importante cuando se ejecute la instrucción ALTER TABLE que agrega las columnas a esa tabla.</span><span class="sxs-lookup"><span data-stu-id="0efc2-105">If one or more of these tables contains a large number of rows, the upgrade will stall for a substantial amount of time on the ALTER TABLE statement that adds columns to that table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="0efc2-106">Componente</span><span class="sxs-lookup"><span data-stu-id="0efc2-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="0efc2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0efc2-107">Description</span></span>  
 <span data-ttu-id="0efc2-108">Puede parecer que la actualización deja de responder si alguna de las siguientes tablas de historial de copias de seguridad o restauración contiene un gran número de filas:</span><span class="sxs-lookup"><span data-stu-id="0efc2-108">Upgrade can appear to stop responding if any of the following backup or restore history tables contains a large number of rows:</span></span>  
  
-   <span data-ttu-id="0efc2-109">**backupfile**</span><span class="sxs-lookup"><span data-stu-id="0efc2-109">**backupfile**</span></span>  
  
-   <span data-ttu-id="0efc2-110">**backupmediafamily**</span><span class="sxs-lookup"><span data-stu-id="0efc2-110">**backupmediafamily**</span></span>  
  
-   <span data-ttu-id="0efc2-111">**backupmediaset**</span><span class="sxs-lookup"><span data-stu-id="0efc2-111">**backupmediaset**</span></span>  
  
-   <span data-ttu-id="0efc2-112">**backupset**</span><span class="sxs-lookup"><span data-stu-id="0efc2-112">**backupset**</span></span>  
  
-   <span data-ttu-id="0efc2-113">**restorefile**</span><span class="sxs-lookup"><span data-stu-id="0efc2-113">**restorefile**</span></span>  
  
-   <span data-ttu-id="0efc2-114">**restorefilegroup**</span><span class="sxs-lookup"><span data-stu-id="0efc2-114">**restorefilegroup**</span></span>  
  
-   <span data-ttu-id="0efc2-115">**restorehistory**</span><span class="sxs-lookup"><span data-stu-id="0efc2-115">**restorehistory**</span></span>  
  
 <span data-ttu-id="0efc2-116">Si alguna de estas tablas tiene 10.000 o más filas, el Asesor de actualizaciones notificará que se ha producido un error al no poder cumplir con su tarea.</span><span class="sxs-lookup"><span data-stu-id="0efc2-116">If any of these tables has 10,000 or more rows, Upgrade Advisor reports a noncompliance failure.</span></span> <span data-ttu-id="0efc2-117">No notificará qué tabla supera el número permitido de filas.</span><span class="sxs-lookup"><span data-stu-id="0efc2-117">It does not report which table exceeds the allowed number of rows.</span></span> <span data-ttu-id="0efc2-118">La primera tabla que supere las 10.000 filas generará el error.</span><span class="sxs-lookup"><span data-stu-id="0efc2-118">The first table that exceeds 10,000 rows causes the failure.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="0efc2-119">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="0efc2-119">Corrective Action</span></span>  
 <span data-ttu-id="0efc2-120">Antes de actualizar una base de datos, si alguna de estas tablas supera las 10.000 filas, recomendamos reducir su número a menos de 10.000 filas.</span><span class="sxs-lookup"><span data-stu-id="0efc2-120">Before you upgrade a database, if any of these tables exceeds 10,000 rows, we recommend that you reduce the number to less than 10,000.</span></span> <span data-ttu-id="0efc2-121">Para reducir las filas de todas estas tablas, puede ejecutar el **sp_delete_backuphistory** procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0efc2-121">To reduce rows in all of these tables, you can run the **sp_delete_backuphistory** stored procedure.</span></span> <span data-ttu-id="0efc2-122">Este procedimiento elimina las entradas de todas las tablas de historial de restauración y copia de seguridad correspondientes a los conjuntos de copia de seguridad que sean anteriores a una fecha dada.</span><span class="sxs-lookup"><span data-stu-id="0efc2-122">This procedure deletes the entries in all of the backup and restore history tables for backup sets older than a specified date.</span></span> <span data-ttu-id="0efc2-123">Para más información, vea [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0efc2-123">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0efc2-124">Puede actualizar una base de datos cuyas tablas de historial de restauración y copia de seguridad tengan más de 10.000 filas.</span><span class="sxs-lookup"><span data-stu-id="0efc2-124">You can upgrade a database whose backup and restore history tables are larger than 10,000 rows.</span></span> <span data-ttu-id="0efc2-125">Sin embargo, puede parecer que la actualización se detiene mientras se modifican esas tablas de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="0efc2-125">But the upgrade may appear to stall while large tables are being altered.</span></span> <span data-ttu-id="0efc2-126">Cuanto mayor sea el tamaño de las tablas, más tiempo necesitará el programa de instalación para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="0efc2-126">The larger the tables, the longer that Setup takes to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0efc2-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0efc2-127">See Also</span></span>  
 <span data-ttu-id="0efc2-128">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="0efc2-128">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="0efc2-129">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="0efc2-129">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
