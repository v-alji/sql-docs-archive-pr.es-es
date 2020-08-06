---
title: Establecer opciones de índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- ALLOW_ROW_LOCKS option
- SORT_IN_TEMPDB option
- DROP_EXISTING clause
- large data, indexes
- PAD_INDEX
- STATISTICS_NORECOMPUTE
- MAXDOP index option, setting
- index options [SQL Server]
- MAXDOP index option
- IGNORE_DUP_KEY option
- ALLOW_PAGE_LOCKS option
- ONLINE
ms.assetid: 7969af33-e94c-41f7-ab89-9d9a2747cd5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9f2d7f0bbbf0d152d3f510ae9ddbe3168634ef96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749317"
---
# <a name="set-index-options"></a><span data-ttu-id="d980d-102">Establecer opciones de índice</span><span class="sxs-lookup"><span data-stu-id="d980d-102">Set Index Options</span></span>
  <span data-ttu-id="d980d-103">En este tema se describe cómo modificar las propiedades de un índice en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d980d-103">This topic describes how to modify the properties of an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d980d-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d980d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d980d-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="d980d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d980d-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="d980d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d980d-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d980d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d980d-108">**Para modificar las propiedades de un índice, use:**</span><span class="sxs-lookup"><span data-stu-id="d980d-108">**To modify the properties of an index, using:**</span></span>  
  
     [<span data-ttu-id="d980d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d980d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d980d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d980d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d980d-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="d980d-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d980d-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="d980d-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d980d-113">Las siguientes opciones se aplican inmediatamente al índice mediante la cláusula SET de la instrucción ALTER INDEX: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY y STATISTICS_NORECOMPUTE.</span><span class="sxs-lookup"><span data-stu-id="d980d-113">The following options are immediately applied to the index by using the SET clause in the ALTER INDEX statement: ALLOW_PAGE_LOCKS, ALLOW_ROW_LOCKS, IGNORE_DUP_KEY, and STATISTICS_NORECOMPUTE.</span></span>  
  
-   <span data-ttu-id="d980d-114">Las opciones siguientes se pueden establecer cuando se vuelve a generar un índice mediante ALTER INDEX REBUILD o CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP y DROP_EXISTING (solo CREATE INDEX).</span><span class="sxs-lookup"><span data-stu-id="d980d-114">The following options can be set when you rebuild an index by using either ALTER INDEX REBUILD or CREATE INDEX WITH DROP_EXISTING: PAD_INDEX, FILLFACTOR, SORT_IN_TEMPDB, IGNORE_DUP_KEY, STATISTICS_NORECOMPUTE, ONLINE, ALLOW_ROW_LOCKS, ALLOW_PAGE_LOCKS, MAXDOP, and DROP_EXISTING (CREATE INDEX only).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d980d-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d980d-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d980d-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="d980d-116">Permissions</span></span>  
 <span data-ttu-id="d980d-117">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="d980d-117">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d980d-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d980d-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-table-designer"></a><span data-ttu-id="d980d-119">Para modificar las propiedades de un índice en el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="d980d-119">To modify the properties of an index in Table Designer</span></span>  
  
1.  <span data-ttu-id="d980d-120">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que quiere modificar las propiedades de un índice.</span><span class="sxs-lookup"><span data-stu-id="d980d-120">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="d980d-121">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="d980d-121">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="d980d-122">Haga clic con el botón derecho en la tabla en la que quiere modificar las propiedades de un índice y seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="d980d-122">Right-click the table on which you want to modify an index's properties and select **Design**.</span></span>  
  
4.  <span data-ttu-id="d980d-123">En el menú **Diseñador de tablas** , haga clic en **Índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="d980d-123">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="d980d-124">Seleccione el índice que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="d980d-124">Select the index that you want to modify.</span></span> <span data-ttu-id="d980d-125">Sus propiedades aparecerán en la cuadrícula principal.</span><span class="sxs-lookup"><span data-stu-id="d980d-125">Its properties will show up in the main grid.</span></span>  
  
6.  <span data-ttu-id="d980d-126">Cambie los valores de una o todas las propiedades para personalizar el índice.</span><span class="sxs-lookup"><span data-stu-id="d980d-126">Change the settings of any and all properties to customize the index.</span></span>  
  
7.  <span data-ttu-id="d980d-127">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d980d-127">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="d980d-128">En el menú **Archivo** , seleccione **Guardar**_nombre_tabla_.</span><span class="sxs-lookup"><span data-stu-id="d980d-128">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-modify-the-properties-of-an-index-in-object-explorer"></a><span data-ttu-id="d980d-129">Para modificar las propiedades de un índice en el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="d980d-129">To modify the properties of an index in Object Explorer</span></span>  
  
1.  <span data-ttu-id="d980d-130">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que quiere modificar las propiedades de un índice.</span><span class="sxs-lookup"><span data-stu-id="d980d-130">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to modify an index's properties.</span></span>  
  
2.  <span data-ttu-id="d980d-131">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="d980d-131">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="d980d-132">Haga clic en el signo más para expandir la tabla en la que quiera modificar las propiedades de un índice.</span><span class="sxs-lookup"><span data-stu-id="d980d-132">Click the plus sign to expand the table on which you want to modify an index's properties.</span></span>  
  
4.  <span data-ttu-id="d980d-133">Haga clic en el signo más para expandir la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="d980d-133">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="d980d-134">Haga clic con el botón derecho en el índice en el que quiere modificar las propiedades y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d980d-134">Right-click the index of which you want to modify the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="d980d-135">Debajo de **Seleccionar una página**, seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="d980d-135">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="d980d-136">Cambie los valores de una o todas las propiedades para personalizar el índice.</span><span class="sxs-lookup"><span data-stu-id="d980d-136">Change the settings of any and all properties to customize the index.</span></span>  
  
8.  <span data-ttu-id="d980d-137">Para agregar, quitar o cambiar la posición de una columna de índice, seleccione la página **General** del cuadro de diálogo **Propiedades del índice:** _nombre de índice_.</span><span class="sxs-lookup"><span data-stu-id="d980d-137">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties -** _index_name_ dialog box.</span></span> <span data-ttu-id="d980d-138">Para obtener más información, consulte [Index Properties F1 Help](index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="d980d-138">For more information, see [Index Properties F1 Help](index-properties-f1-help.md)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d980d-139">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d980d-139">Using Transact-SQL</span></span>  
  
#### <a name="to-see-the-properties-of-all-the-indexes-in-a-table"></a><span data-ttu-id="d980d-140">Para ver las propiedades de todos los índices en una tabla</span><span class="sxs-lookup"><span data-stu-id="d980d-140">To see the properties of all the indexes in a table</span></span>  
  
1.  <span data-ttu-id="d980d-141">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d980d-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d980d-142">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d980d-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d980d-143">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d980d-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT i.name AS index_name,   
        i.type_desc,   
        i.is_unique,   
        ds.type_desc AS filegroup_or_partition_scheme,   
        ds.name AS filegroup_or_partition_scheme_name,   
        i.ignore_dup_key,   
        i.is_primary_key,   
        i.is_unique_constraint,   
        i.fill_factor,   
        i.is_padded,   
        i.is_disabled,   
        i.allow_row_locks,   
        i.allow_page_locks,   
        i.has_filter,   
        i.filter_definition  
    FROM sys.indexes AS i  
       INNER JOIN sys.data_spaces AS ds ON i.data_space_id = ds.data_space_id  
    WHERE is_hypothetical = 0 AND i.index_id <> 0   
       AND i.object_id = OBJECT_ID('HumanResources.Employee');   
    GO  
  
    ```  
  
#### <a name="to-set-the-properties-of-an-index"></a><span data-ttu-id="d980d-144">Para establecer las propiedades de un índice</span><span class="sxs-lookup"><span data-stu-id="d980d-144">To set the properties of an index</span></span>  
  
1.  <span data-ttu-id="d980d-145">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d980d-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d980d-146">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d980d-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d980d-147">Copie y pegue los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="d980d-147">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
     [!code-sql[IndexDDL#AlterIndex2](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex2)]  
  
 <span data-ttu-id="d980d-148">Para obtener más información, vea [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d980d-148">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
