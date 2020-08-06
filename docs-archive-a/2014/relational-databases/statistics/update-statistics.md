---
title: Actualizar estadísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- updating statistics
- statistics [SQL Server], updating
ms.assetid: 4b97c0b4-03ff-4cfb-9c3f-3b33290b7a2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 28491dda23c2ba9402e91dc051249f5bdcdf28d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676401"
---
# <a name="update-statistics"></a><span data-ttu-id="477be-102">Actualizar estadísticas</span><span class="sxs-lookup"><span data-stu-id="477be-102">Update Statistics</span></span>
  <span data-ttu-id="477be-103">Puede actualizar las estadísticas de optimización de consultas en una tabla o en una vista indizada de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="477be-103">You can update query optimization statistics on a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="477be-104">De forma predeterminada, el optimizador de consultas ya actualiza las estadísticas como requisito para mejorar el plan de consulta; en algunos casos puede mejorar el rendimiento de las consultas utilizando UPDATE STATISTICS o el procedimiento almacenado `sp_updatestats` para actualizar las estadísticas con más frecuencia que la de las actualizaciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="477be-104">By default, the query optimizer already updates statistics as necessary to improve the query plan; in some cases you can improve query performance by using UPDATE STATISTICS or the stored procedure `sp_updatestats` to update statistics more frequently than the default updates.</span></span>  
  
 <span data-ttu-id="477be-105">La actualización de las estadísticas asegura que las consultas se compilan con estadísticas actualizadas.</span><span class="sxs-lookup"><span data-stu-id="477be-105">Updating statistics ensures that queries compile with up-to-date statistics.</span></span> <span data-ttu-id="477be-106">Sin embargo, la actualización de las estadísticas hace que las consultas se vuelvan a compilar.</span><span class="sxs-lookup"><span data-stu-id="477be-106">However, updating statistics causes queries to recompile.</span></span> <span data-ttu-id="477be-107">Recomendamos no actualizar las estadísticas con demasiada frecuencia, porque hay que elegir el punto válido entre la mejora de los planes de consulta y el tiempo empleado en volver a compilar las consultas.</span><span class="sxs-lookup"><span data-stu-id="477be-107">We recommend not updating statistics too frequently because there is a performance tradeoff between improving query plans and the time it takes to recompile queries.</span></span> <span data-ttu-id="477be-108">Las compensaciones específicas dependen de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="477be-108">The specific tradeoffs depend on your application.</span></span> <span data-ttu-id="477be-109">UPDATE STATISTICS puede usar tempdb para ordenar la muestra de filas con fines de creación de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="477be-109">UPDATE STATISTICS can use tempdb to sort the sample of rows for building statistics.</span></span>  
  
 <span data-ttu-id="477be-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="477be-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="477be-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="477be-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="477be-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="477be-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="477be-113">**Para actualizar un objeto de estadísticas, con:**</span><span class="sxs-lookup"><span data-stu-id="477be-113">**To update a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="477be-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="477be-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="477be-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="477be-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="477be-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="477be-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="477be-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="477be-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="477be-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="477be-118">Permissions</span></span>  
 <span data-ttu-id="477be-119">Si usa UPDATE STATISTICS o realiza cambios con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], es necesario el permiso ALTER en la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="477be-119">If using UPDATE STATISTICS or making changes through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], requires ALTER permission on the table or view.</span></span> <span data-ttu-id="477be-120">Si usa `sp_updatestats`, necesita pertenecer al rol fijo de servidor **sysadmin** o ser propietario de la base de datos (**dbo**).</span><span class="sxs-lookup"><span data-stu-id="477be-120">If using `sp_updatestats`, requires membership in the **sysadmin** fixed server role, or ownership of the database (**dbo**).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="477be-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="477be-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-update-a-statistics-object"></a><span data-ttu-id="477be-122">Para actualizar un objeto de estadísticas</span><span class="sxs-lookup"><span data-stu-id="477be-122">To update a statistics object</span></span>  
  
1.  <span data-ttu-id="477be-123">En el **Explorador de objetos**, haga clic en el signo más para expandir la base de datos en la que desea actualizar la estadística.</span><span class="sxs-lookup"><span data-stu-id="477be-123">In **Object Explorer**, click the plus sign to expand the database in which you want to update the statistic.</span></span>  
  
2.  <span data-ttu-id="477be-124">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="477be-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="477be-125">Haga clic en el signo más para expandir la tabla en la que desea actualizar la estadística.</span><span class="sxs-lookup"><span data-stu-id="477be-125">Click the plus sign to expand the table in which you want to update the statistic.</span></span>  
  
4.  <span data-ttu-id="477be-126">Haga clic en el signo más para expandir la carpeta **Estadísticas** .</span><span class="sxs-lookup"><span data-stu-id="477be-126">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="477be-127">Haga clic con el botón derecho en el objeto de estadísticas que quiere actualizar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="477be-127">Right-click the statistics object you wish to update and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="477be-128">En el cuadro de diálogo **propiedades de estadísticas-**_statistics_name_ , active la casilla **actualizar estadísticas de estas columnas** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="477be-128">In the **Statistics Properties -**_statistics_name_ dialog box, select the **Update statistics for these columns** check box and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="477be-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="477be-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-a-specific-statistics-object"></a><span data-ttu-id="477be-130">Para actualizar un objeto concreto de estadísticas</span><span class="sxs-lookup"><span data-stu-id="477be-130">To update a specific statistics object</span></span>  
  
1.  <span data-ttu-id="477be-131">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="477be-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="477be-132">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="477be-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="477be-133">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="477be-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example updates the statistics for the AK_SalesOrderDetail_rowguid index of the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail AK_SalesOrderDetail_rowguid;   
    GO  
    ```  
  
#### <a name="to-update-all-statistics-in-a-table"></a><span data-ttu-id="477be-134">Para actualizar todas las estadísticas en una tabla</span><span class="sxs-lookup"><span data-stu-id="477be-134">To update all statistics in a table</span></span>  
  
1.  <span data-ttu-id="477be-135">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="477be-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="477be-136">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="477be-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="477be-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="477be-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all indexes on the SalesOrderDetail table.   
    UPDATE STATISTICS Sales.SalesOrderDetail;   
    GO  
    ```  
  
 <span data-ttu-id="477be-138">Para obtener más información, vea [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="477be-138">For more information, see [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
#### <a name="to-update-all-statistics-in-a-database"></a><span data-ttu-id="477be-139">Para actualizar todas las estadísticas de una base de datos</span><span class="sxs-lookup"><span data-stu-id="477be-139">To update all statistics in a database</span></span>  
  
1.  <span data-ttu-id="477be-140">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="477be-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="477be-141">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="477be-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="477be-142">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="477be-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- The following example updates the statistics for all tables in the database.   
    EXEC sp_updatestats;  
    ```  
  
 <span data-ttu-id="477be-143">Para obtener más información, vea [sp_updatestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="477be-143">For more information, see [sp_updatestats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-updatestats-transact-sql).</span></span>  
  
  
