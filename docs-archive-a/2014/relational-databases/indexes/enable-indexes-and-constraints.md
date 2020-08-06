---
title: Habilitar índices y restricciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], enabling
- nonclustered indexes [SQL Server], enabling a disabled index
- index enabling [SQL Server]
- disabled indexes [SQL Server], how to enable
- constraints [SQL Server], enabling
- clustered indexes, enabling disabled indexes
ms.assetid: c55c8865-322e-4ab0-ba04-ea1f56735353
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4e79689b80a40d00958fa557fe51df2adf9c14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677100"
---
# <a name="enable-indexes-and-constraints"></a><span data-ttu-id="baa7b-102">Habilitar índices y restricciones</span><span class="sxs-lookup"><span data-stu-id="baa7b-102">Enable Indexes and Constraints</span></span>
  <span data-ttu-id="baa7b-103">En este tema se describe cómo habilitar un índice deshabilitado en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa7b-103">This topic describes how to enable a disabled index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="baa7b-104">Cuando se deshabilita un índice, sigue deshabilitado hasta que se vuelve a generar o se quita.</span><span class="sxs-lookup"><span data-stu-id="baa7b-104">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped</span></span>  
  
 <span data-ttu-id="baa7b-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="baa7b-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="baa7b-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="baa7b-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="baa7b-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="baa7b-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="baa7b-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="baa7b-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="baa7b-109">**Para habilitar un índice deshabilitado, use:**</span><span class="sxs-lookup"><span data-stu-id="baa7b-109">**To enable a disabled index, using:**</span></span>  
  
     [<span data-ttu-id="baa7b-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="baa7b-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="baa7b-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="baa7b-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="baa7b-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="baa7b-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="baa7b-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="baa7b-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="baa7b-114">Después de volver a generar el índice, deben volver a habilitarse manualmente las restricciones deshabilitadas debido a la deshabilitación del índice.</span><span class="sxs-lookup"><span data-stu-id="baa7b-114">After rebuilding the index, any constraints that were disabled because of disabling the index must be manually enabled.</span></span> <span data-ttu-id="baa7b-115">Las restricciones PRIMARY KEY y UNIQUE se habilitan cuando se regenera el índice asociado.</span><span class="sxs-lookup"><span data-stu-id="baa7b-115">PRIMARY KEY and UNIQUE constraints are enabled by rebuilding the associated index.</span></span> <span data-ttu-id="baa7b-116">Este índice debe volver a generarse (habilitarse) para poder habilitar las restricciones FOREIGN KEY que hacen referencia a la restricción PRIMARY KEY o UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="baa7b-116">This index must be rebuilt (enabled) before you can enable FOREIGN KEY constraints that reference the PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="baa7b-117">Las restricciones FOREIGN KEY se habilitan con la instrucción ALTER TABLE CHECK CONSTRAINT.</span><span class="sxs-lookup"><span data-stu-id="baa7b-117">FOREIGN KEY constraints are enabled by using the ALTER TABLE CHECK CONSTRAINT statement.</span></span>  
  
-   <span data-ttu-id="baa7b-118">No es posible volver a generar un índice clúster deshabilitado si la opción ONLINE está establecida en ON.</span><span class="sxs-lookup"><span data-stu-id="baa7b-118">Rebuilding a disabled clustered index cannot be performed when the ONLINE option is set to ON.</span></span>  
  
-   <span data-ttu-id="baa7b-119">Si el índice clúster está deshabilitado o habilitado y el índice no clúster está deshabilitado, la acción del índice clúster tiene los siguientes resultados en el índice no clúster deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="baa7b-119">When the clustered index is disabled or enabled and the nonclustered index is disabled, the clustered index action has the following results on the disabled nonclustered index.</span></span>  
  
    |<span data-ttu-id="baa7b-120">Acción del índice clúster</span><span class="sxs-lookup"><span data-stu-id="baa7b-120">Clustered Index Action</span></span>|<span data-ttu-id="baa7b-121">Índice no agrupado deshabilitado ...</span><span class="sxs-lookup"><span data-stu-id="baa7b-121">Disabled Nonclustered Index ...</span></span>|  
    |----------------------------|-----------------------------------|  
    |<span data-ttu-id="baa7b-122">ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="baa7b-122">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="baa7b-123">Sigue deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="baa7b-123">Remains disabled.</span></span>|  
    |<span data-ttu-id="baa7b-124">ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="baa7b-124">ALTER INDEX ALL REBUILD.</span></span>|<span data-ttu-id="baa7b-125">Se vuelve a generar y se habilita.</span><span class="sxs-lookup"><span data-stu-id="baa7b-125">Is rebuilt and enabled.</span></span>|  
    |<span data-ttu-id="baa7b-126">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="baa7b-126">DROP INDEX.</span></span>|<span data-ttu-id="baa7b-127">Sigue deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="baa7b-127">Remains disabled.</span></span>|  
    |<span data-ttu-id="baa7b-128">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="baa7b-128">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="baa7b-129">Sigue deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="baa7b-129">Remains disabled.</span></span>|  
  
     <span data-ttu-id="baa7b-130">La creación de un índice clúster se comporta igual que ALTER INDEX ALL REBUILD.</span><span class="sxs-lookup"><span data-stu-id="baa7b-130">Creating a new clustered index, behaves the same as ALTER INDEX ALL REBUILD.</span></span>  
  
-   <span data-ttu-id="baa7b-131">Las acciones permitidas en índices no clúster asociados con un índice clúster dependen del estado, deshabilitado o habilitado, de ambos tipos de índice.</span><span class="sxs-lookup"><span data-stu-id="baa7b-131">Allowed actions on nonclustered indexes associated with a clustered index depend on the state, whether disabled or enabled, of both index types.</span></span> <span data-ttu-id="baa7b-132">La tabla siguiente resume las acciones permitidas en índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="baa7b-132">The following table summarizes the allowed actions on nonclustered indexes.</span></span>  
  
    |<span data-ttu-id="baa7b-133">Acción del índice no clúster</span><span class="sxs-lookup"><span data-stu-id="baa7b-133">Nonclustered Index Action</span></span>|<span data-ttu-id="baa7b-134">Cuando los índices clúster y no clúster están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="baa7b-134">When both the clustered and nonclustered indexes are disabled.</span></span>|<span data-ttu-id="baa7b-135">Cuando el índice clúster está habilitado y el índice no clúster está deshabilitado o habilitado.</span><span class="sxs-lookup"><span data-stu-id="baa7b-135">When the clustered index is enabled and the nonclustered index is in either state.</span></span>|  
    |-------------------------------|--------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
    |<span data-ttu-id="baa7b-136">ALTER INDEX REBUILD.</span><span class="sxs-lookup"><span data-stu-id="baa7b-136">ALTER INDEX REBUILD.</span></span>|<span data-ttu-id="baa7b-137">Se produce un error en la acción.</span><span class="sxs-lookup"><span data-stu-id="baa7b-137">The action fails.</span></span>|<span data-ttu-id="baa7b-138">La acción se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="baa7b-138">The action succeeds.</span></span>|  
    |<span data-ttu-id="baa7b-139">DROP INDEX.</span><span class="sxs-lookup"><span data-stu-id="baa7b-139">DROP INDEX.</span></span>|<span data-ttu-id="baa7b-140">La acción se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="baa7b-140">The action succeeds.</span></span>|<span data-ttu-id="baa7b-141">La acción se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="baa7b-141">The action succeeds.</span></span>|  
    |<span data-ttu-id="baa7b-142">CREATE INDEX WITH DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="baa7b-142">CREATE INDEX WITH DROP_EXISTING.</span></span>|<span data-ttu-id="baa7b-143">Se produce un error en la acción.</span><span class="sxs-lookup"><span data-stu-id="baa7b-143">The action fails.</span></span>|<span data-ttu-id="baa7b-144">La acción se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="baa7b-144">The action succeeds.</span></span>|  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="baa7b-145">Seguridad</span><span class="sxs-lookup"><span data-stu-id="baa7b-145">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="baa7b-146">Permisos</span><span class="sxs-lookup"><span data-stu-id="baa7b-146">Permissions</span></span>  
 <span data-ttu-id="baa7b-147">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="baa7b-147">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="baa7b-148">Si se usa DBCC DBREINDEX, el usuario debe ser el propietario de la tabla o debe ser miembro del rol fijo de servidor **sysadmin** , o de los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="baa7b-148">If using DBCC DBREINDEX, eser must either own the table or be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="baa7b-149">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="baa7b-149">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-a-disabled-index"></a><span data-ttu-id="baa7b-150">Para habilitar un índice deshabilitado</span><span class="sxs-lookup"><span data-stu-id="baa7b-150">To enable a disabled index</span></span>  
  
1.  <span data-ttu-id="baa7b-151">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea habilitar un índice.</span><span class="sxs-lookup"><span data-stu-id="baa7b-151">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable an index.</span></span>  
  
2.  <span data-ttu-id="baa7b-152">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="baa7b-152">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="baa7b-153">Haga clic en el signo más para expandir la tabla en la que desea habilitar un índice.</span><span class="sxs-lookup"><span data-stu-id="baa7b-153">Click the plus sign to expand the table on which you want to enable an index.</span></span>  
  
4.  <span data-ttu-id="baa7b-154">Haga clic en el signo más para expandir la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="baa7b-154">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="baa7b-155">Haga clic con el botón derecho en el índice que quiera habilitar y seleccione **Volver a generar**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-155">Right-click the index you want to enable and select **Rebuild**.</span></span>  
  
6.  <span data-ttu-id="baa7b-156">En el cuadro de diálogo **Volver a generar índices** , compruebe que el índice correcto se encuentra en la cuadrícula **Índices que se volverán a generar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-156">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
#### <a name="to-enable-all-indexes-on-a-table"></a><span data-ttu-id="baa7b-157">Para habilitar todos los índices de una tabla</span><span class="sxs-lookup"><span data-stu-id="baa7b-157">To enable all indexes on a table</span></span>  
  
1.  <span data-ttu-id="baa7b-158">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea habilitar los índices.</span><span class="sxs-lookup"><span data-stu-id="baa7b-158">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to enable the indexes.</span></span>  
  
2.  <span data-ttu-id="baa7b-159">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="baa7b-159">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="baa7b-160">Haga clic en el signo más para expandir la tabla en la que desea habilitar los índices.</span><span class="sxs-lookup"><span data-stu-id="baa7b-160">Click the plus sign to expand the table on which you want to enable the indexes.</span></span>  
  
4.  <span data-ttu-id="baa7b-161">Haga clic con el botón derecho en la carpeta **Índices** y seleccione **Volver a generar todo**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-161">Right-click the **Indexes** folder and select **Rebuild All**.</span></span>  
  
5.  <span data-ttu-id="baa7b-162">En el cuadro de diálogo **Volver a generar índices** , compruebe que los índices correctos se encuentran en la cuadrícula **Índices que se volverán a generar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-162">In the **Rebuild Indexes** dialog box, verify that the correct indexes are in the **Indexes to rebuild** grid and click **OK**.</span></span> <span data-ttu-id="baa7b-163">Para quitar un índice de la cuadrícula **Índices que se volverán a generar** , seleccione el índice y, a continuación, presione la tecla SUPRIMIR.</span><span class="sxs-lookup"><span data-stu-id="baa7b-163">To remove an index from the **Indexes to rebuild** grid, select the index and then press the Delete key.</span></span>  
  
 <span data-ttu-id="baa7b-164">La siguiente información está disponible en el cuadro de diálogo **Volver a generar índices** :</span><span class="sxs-lookup"><span data-stu-id="baa7b-164">The following information is available in the **Rebuild Indexes** dialog box:</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="baa7b-165">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="baa7b-165">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-a-disabled-index-using-alter-index"></a><span data-ttu-id="baa7b-166">Para habilitar un índice deshabilitado mediante ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="baa7b-166">To enable a disabled index using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="baa7b-167">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa7b-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="baa7b-168">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="baa7b-169">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD;   
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-create-index"></a><span data-ttu-id="baa7b-170">Para habilitar un índice deshabilitado mediante CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="baa7b-170">To enable a disabled index using CREATE INDEX</span></span>  
  
1.  <span data-ttu-id="baa7b-171">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa7b-171">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="baa7b-172">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-172">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="baa7b-173">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-173">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- re-creates the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    -- using the OrganizationLevel and OrganizationNode columns  
    -- and then deletes the existing IX_Employee_OrganizationLevel_OrganizationNode index  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)  
    WITH (DROP_EXISTING = ON);  
    GO  
    ```  
  
#### <a name="to-enable-a-disabled-index-using-dbcc-dbreindex"></a><span data-ttu-id="baa7b-174">Para habilitar un índice deshabilitado mediante DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="baa7b-174">To enable a disabled index using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="baa7b-175">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa7b-175">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="baa7b-176">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-176">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="baa7b-177">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-177">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables the IX_Employee_OrganizationLevel_OrganizationNode index  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", IX_Employee_OrganizationLevel_OrganizationNode);  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-alter-index"></a><span data-ttu-id="baa7b-178">Para habilitar todos los índices de una tabla mediante ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="baa7b-178">To enable all indexes on a table using ALTER INDEX</span></span>  
  
1.  <span data-ttu-id="baa7b-179">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa7b-179">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="baa7b-180">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-180">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="baa7b-181">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-181">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    ALTER INDEX ALL ON HumanResources.Employee  
    REBUILD;  
    GO  
    ```  
  
#### <a name="to-enable-all-indexes-on-a-table-using-dbcc-dbreindex"></a><span data-ttu-id="baa7b-182">Para habilitar todos los índices de una tabla mediante DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="baa7b-182">To enable all indexes on a table using DBCC DBREINDEX</span></span>  
  
1.  <span data-ttu-id="baa7b-183">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa7b-183">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="baa7b-184">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-184">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="baa7b-185">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="baa7b-185">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- enables all indexes  
    -- on the HumanResources.Employee table  
    DBCC DBREINDEX ("HumanResources.Employee", " ");  
    GO  
    ```  
  
 <span data-ttu-id="baa7b-186">Para obtener más información, vea [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql), y [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="baa7b-186">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql), [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql), and [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql).</span></span>  
  
  
