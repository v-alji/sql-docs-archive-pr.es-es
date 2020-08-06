---
title: Habilitar y deshabilitar el seguimiento de cambios (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], disabling
- data changes [SQL Server]
- change tracking [SQL Server], enabling
- tracking data changes [SQL Server]
- change tracking [SQL Server], configuring
- data [SQL Server], changing
ms.assetid: 1c92ec7e-ae53-4498-8bfd-c66a42a24d54
author: rothja
ms.author: jroth
ms.openlocfilehash: 402c63ae03df14e3a725fbc440575f5233d502f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671948"
---
# <a name="enable-and-disable-change-tracking-sql-server"></a><span data-ttu-id="96278-102">Habilitar y deshabilitar el seguimiento de cambios (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="96278-102">Enable and Disable Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="96278-103">En este tema se describe cómo habilitar y deshabilitar el seguimiento de cambios para una tabla y una base de datos.</span><span class="sxs-lookup"><span data-stu-id="96278-103">This topic describes how to enable and disable change tracking for a database and a table.</span></span>  
  
## <a name="enable-change-tracking-for-a-database"></a><span data-ttu-id="96278-104">Habilitar el seguimiento de cambios para una base de datos</span><span class="sxs-lookup"><span data-stu-id="96278-104">Enable Change Tracking for a Database</span></span>  
 <span data-ttu-id="96278-105">Para poder utilizarlo, el seguimiento de cambios se debe habilitar previamente en el nivel de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="96278-105">Before you can use change tracking, you must enable change tracking at the database level.</span></span> <span data-ttu-id="96278-106">En el ejemplo siguiente se muestra cómo habilitar el seguimiento de cambios mediante [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="96278-106">The following example shows how to enable change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = ON  
(CHANGE_RETENTION = 2 DAYS, AUTO_CLEANUP = ON)  
```  
  
 <span data-ttu-id="96278-107">También puede habilitar el seguimiento de cambios en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mediante el cuadro de diálogo [Propiedades de la base de datos &#40;página ChangeTracking&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="96278-107">You can also enable change tracking in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="96278-108">Puede especificar las opciones CHANGE_RETENTION y AUTO_CLEANUP al habilitar el seguimiento de cambios, y puede cambiar los valores en cualquier momento una vez que esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="96278-108">You can specify the CHANGE_RETENTION and AUTO_CLEANUP options when you enable change tracking, and you can change the values at any time after change tracking is enabled.</span></span>  
  
 <span data-ttu-id="96278-109">El valor de retención de los cambios especifica el período de tiempo para el cual se conserva la información del seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="96278-109">The change retention value specifies the time period for which change tracking information is kept.</span></span> <span data-ttu-id="96278-110">La información del seguimiento de cambios anterior a este período de tiempo se quita periódicamente.</span><span class="sxs-lookup"><span data-stu-id="96278-110">Change tracking information that is older than this time period is removed periodically.</span></span> <span data-ttu-id="96278-111">A la hora de establecer este valor, debería tener en cuenta la frecuencia con que las aplicaciones se sincronizarán con las tablas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="96278-111">When you are setting this value, you should consider how often applications will synchronize with the tables in the database.</span></span> <span data-ttu-id="96278-112">El período de retención especificado debe ser como mínimo igual al período máximo de tiempo entre sincronizaciones.</span><span class="sxs-lookup"><span data-stu-id="96278-112">The specified retention period must be at least as long as the maximum time period between synchronizations.</span></span> <span data-ttu-id="96278-113">Si una aplicación obtiene los cambios en intervalos más prolongados, los resultados que se devuelven podrían ser incorrectos, puesto que es posible que parte de la información de los cambios se haya quitado.</span><span class="sxs-lookup"><span data-stu-id="96278-113">If an application obtains changes at longer intervals, the results that are returned might be incorrect because some of the change information has probably been removed.</span></span> <span data-ttu-id="96278-114">Para evitar obtener resultados incorrectos, una aplicación puede utilizar la función del sistema CHANGE_TRACKING_MIN_VALID_VERSION con el fin de determinar si el intervalo entre las sincronizaciones ha sido demasiado largo.</span><span class="sxs-lookup"><span data-stu-id="96278-114">To avoid obtaining incorrect results, an application can use the CHANGE_TRACKING_MIN_VALID_VERSION system function to determine whether the interval between synchronizations has been too long.</span></span>  
  
 <span data-ttu-id="96278-115">Puede usar la opción AUTO_CLEANUP para habilitar o deshabilitar la tarea de limpieza que quita la información de seguimiento de cambios antigua.</span><span class="sxs-lookup"><span data-stu-id="96278-115">You can use the AUTO_CLEANUP option to enable or disable the cleanup task that removes old change tracking information.</span></span> <span data-ttu-id="96278-116">Se trata de algo que puede ser útil en los casos en que haya un problema temporal que evite que las aplicaciones se sincronicen y sea necesario paralizar el proceso de eliminación de información del seguimiento de cambios anterior al período de retención hasta que se resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="96278-116">This can be useful when there is a temporary problem that prevents applications from synchronizing and the process for removing change tracking information older than the retention period must be paused until the problem is resolved.</span></span>  
  
 <span data-ttu-id="96278-117">Tenga en cuenta lo siguiente para cualquier base de datos que utilice seguimiento de cambios:</span><span class="sxs-lookup"><span data-stu-id="96278-117">For any database that uses change tracking, be aware of the following:</span></span>  
  
-   <span data-ttu-id="96278-118">Para utilizar el seguimiento de cambios, el nivel de compatibilidad de la base de datos debe establecerse en 90 o mayor.</span><span class="sxs-lookup"><span data-stu-id="96278-118">To use change tracking, the database compatibility level must be set to 90 or greater.</span></span> <span data-ttu-id="96278-119">Si una base de datos tiene un nivel de compatibilidad menor que 90, puede configurar el seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="96278-119">If a database has a compatibility level of less than 90, you can configure change tracking.</span></span> <span data-ttu-id="96278-120">Sin embargo, la función CHANGETABLE, que se utiliza para obtener información del seguimiento de cambios, devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="96278-120">However, the CHANGETABLE function, which is used to obtain change tracking information, will return an error.</span></span>  
  
-   <span data-ttu-id="96278-121">El uso del aislamiento de instantánea es la manera más fácil de ayudarle a asegurarse de que toda la información del seguimiento de cambios es coherente.</span><span class="sxs-lookup"><span data-stu-id="96278-121">Using snapshot isolation is the easiest way for you to help ensure that all change tracking information is consistent.</span></span> <span data-ttu-id="96278-122">Por esta razón, recomendamos encarecidamente activar el aislamiento de instantánea para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="96278-122">For this reason, we strongly recommend that snapshot isolation be set to ON for the database.</span></span> <span data-ttu-id="96278-123">Para obtener más información, vea [Trabajar con el seguimiento de cambios &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="96278-123">For more information, see [Work with Change Tracking &#40;SQL Server&#41;](work-with-change-tracking-sql-server.md).</span></span>  
  
## <a name="enable-change-tracking-for-a-table"></a><span data-ttu-id="96278-124">Habilitar el seguimiento de cambios para una tabla</span><span class="sxs-lookup"><span data-stu-id="96278-124">Enable Change Tracking for a Table</span></span>  
 <span data-ttu-id="96278-125">El seguimiento de cambios debe estar habilitado para cada tabla en la que desea realizar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="96278-125">Change tracking must be enabled for each table that you want tracked.</span></span> <span data-ttu-id="96278-126">Cuando el seguimiento de cambios se habilita, su información correspondiente se mantiene para todas las filas de la tabla a las que afecta una operación DML.</span><span class="sxs-lookup"><span data-stu-id="96278-126">When change tracking is enabled, change tracking information is maintained for all rows in the table that are affected by a DML operation.</span></span>  
  
 <span data-ttu-id="96278-127">En el ejemplo siguiente se muestra cómo habilitar el seguimiento de cambios para una tabla utilizando [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="96278-127">The following example shows how to enable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
ENABLE CHANGE_TRACKING  
WITH (TRACK_COLUMNS_UPDATED = ON)  
```  
  
 <span data-ttu-id="96278-128">También puede habilitar el seguimiento de cambios para una tabla en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mediante el cuadro de diálogo [Propiedades de la base de datos &#40;página ChangeTracking&#41;](../databases/database-properties-changetracking-page.md) .</span><span class="sxs-lookup"><span data-stu-id="96278-128">You can also enable change tracking for a table in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] by using the [Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="96278-129">Cuando la opción TRACK_COLUMNS_UPDATED se activa, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] almacena información adicional sobre las columnas que se actualizaron en la tabla de seguimiento de cambios interna.</span><span class="sxs-lookup"><span data-stu-id="96278-129">When the TRACK_COLUMNS_UPDATED option is set to ON, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] stores extra information about which columns were updated to the internal change tracking table.</span></span> <span data-ttu-id="96278-130">El seguimiento de columnas puede permitir a una aplicación sincronizar solo las columnas que fueron actualizadas,</span><span class="sxs-lookup"><span data-stu-id="96278-130">Column tracking can enable an application to synchronize only those columns that were updated.</span></span> <span data-ttu-id="96278-131">lo cual puede mejorar la eficacia y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="96278-131">This can improve efficiency and performance.</span></span> <span data-ttu-id="96278-132">Sin embargo, dado que el mantenimiento de la información de seguimiento de las columnas agrega una sobrecarga adicional de almacenamiento, esta opción está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="96278-132">However, because maintaining column tracking information adds some extra storage overhead, this option is set to OFF by default.</span></span>  
  
## <a name="disable-change-tracking-for-a-database-or-table"></a><span data-ttu-id="96278-133">Deshabilitar el seguimiento de cambios para una base de datos o una tabla</span><span class="sxs-lookup"><span data-stu-id="96278-133">Disable Change Tracking for a Database or Table</span></span>  
 <span data-ttu-id="96278-134">El seguimiento de cambios para todas las tablas sometidas al seguimiento de cambios debe deshabilitarse antes de poder deshabilitar el seguimiento de cambios para toda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="96278-134">Change tracking must first be disabled for all change-tracked tables before change tracking can be set to OFF for the database.</span></span> <span data-ttu-id="96278-135">Para determinar qué tablas de una base de datos tienen habilitado el seguimiento de cambios, use la vista de catálogo [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) .</span><span class="sxs-lookup"><span data-stu-id="96278-135">To determine the tables that have change tracking enabled for a database, use the [sys.change_tracking_tables](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) catalog view.</span></span>  
  
 <span data-ttu-id="96278-136">Cuando ninguna de las tablas de una base de datos está sometida a seguimiento de cambios, es posible deshabilitar el seguimiento de cambios para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="96278-136">When no tables in a database track changes, you can disable change tracking for the database.</span></span> <span data-ttu-id="96278-137">En el ejemplo siguiente se muestra cómo deshabilitar el seguimiento de cambios para una base de datos mediante [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="96278-137">The following example shows how to disable change tracking for a database by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET CHANGE_TRACKING = OFF  
```  
  
 <span data-ttu-id="96278-138">En el siguiente ejemplo se muestra cómo deshabilitar el seguimiento de cambios para una tabla utilizando [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="96278-138">The following example shows how to disable change tracking for a table by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
```sql  
ALTER TABLE Person.Contact  
DISABLE CHANGE_TRACKING;  
```  
  
## <a name="see-also"></a><span data-ttu-id="96278-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96278-139">See Also</span></span>  
 <span data-ttu-id="96278-140">[Propiedades de la base de datos &#40;página ChangeTracking&#41;](../databases/database-properties-changetracking-page.md) </span><span class="sxs-lookup"><span data-stu-id="96278-140">[Database Properties &#40;ChangeTracking Page&#41;](../databases/database-properties-changetracking-page.md) </span></span>  
 <span data-ttu-id="96278-141">[Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span><span class="sxs-lookup"><span data-stu-id="96278-141">[ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options) </span></span>  
 <span data-ttu-id="96278-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span><span class="sxs-lookup"><span data-stu-id="96278-142">[sys.change_tracking_databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-databases) </span></span>  
 <span data-ttu-id="96278-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span><span class="sxs-lookup"><span data-stu-id="96278-143">[sys.change_tracking_tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/change-tracking-catalog-views-sys-change-tracking-tables) </span></span>  
 <span data-ttu-id="96278-144">[Seguimiento de cambios de datos &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="96278-144">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="96278-145">[Acerca del seguimiento de cambios &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="96278-145">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="96278-146">[Trabajar con datos modificados &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="96278-146">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="96278-147">Administrar el seguimiento de cambios &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="96278-147">Manage Change Tracking &#40;SQL Server&#41;</span></span>](manage-change-tracking-sql-server.md)  
  
  
