---
title: Modificación de un índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], modifying
- modifying indexes
- index changes [SQL Server]
ms.assetid: 97e3110d-fde7-4f5d-9309-dc1697960aeb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af9293966afce8372f5b83a579418c546c82816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749319"
---
# <a name="modify-an-index"></a><span data-ttu-id="1f489-102">Modificar un índice</span><span class="sxs-lookup"><span data-stu-id="1f489-102">Modify an Index</span></span>
  <span data-ttu-id="1f489-103">En este tema se describe cómo modificar un índice en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f489-103">This topic describes how to modify an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1f489-104">Los índices creados como resultado de una restricción PRIMARY KEY o UNIQUE no se pueden modificar con este método.</span><span class="sxs-lookup"><span data-stu-id="1f489-104">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be modified by using this method.</span></span> <span data-ttu-id="1f489-105">En su lugar, se debe modificar la restricción.</span><span class="sxs-lookup"><span data-stu-id="1f489-105">Instead, the constraint must be modified.</span></span>  
  
 <span data-ttu-id="1f489-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="1f489-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1f489-107">**Para modificar un índice, usando:**</span><span class="sxs-lookup"><span data-stu-id="1f489-107">**To modify an index, using:**</span></span>  
  
     [<span data-ttu-id="1f489-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f489-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1f489-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1f489-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1f489-110">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1f489-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="1f489-111">Para modificar un índice</span><span class="sxs-lookup"><span data-stu-id="1f489-111">To modify an index</span></span>  
  
1.  <span data-ttu-id="1f489-112">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="1f489-112">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1f489-113">Expanda **Bases de datos**, a continuación, la base de datos a la que pertenece la tabla y, por último, **Tablas**.</span><span class="sxs-lookup"><span data-stu-id="1f489-113">Expand **Databases**, expand the database in which the table belongs, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="1f489-114">Expanda la tabla a la que pertenece el índice y, a continuación, **Índices**.</span><span class="sxs-lookup"><span data-stu-id="1f489-114">Expand the table in which the index belongs and then expand **Indexes**.</span></span>  
  
4.  <span data-ttu-id="1f489-115">Haga clic con el botón derecho en el índice que quiera modificar y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1f489-115">Right-click the index that you want to modify and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="1f489-116">En el cuadro de diálogo **Propiedades del índice** , realice los cambios deseados.</span><span class="sxs-lookup"><span data-stu-id="1f489-116">In the **Index Properties** dialog box, make the desired changes.</span></span> <span data-ttu-id="1f489-117">Por ejemplo, puede agregar o quitar una columna de la clave de índice, o cambiar el valor de una opción de índice.</span><span class="sxs-lookup"><span data-stu-id="1f489-117">For example, you can add or remove a column from the index key, or change the setting of an index option.</span></span>  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="1f489-118">Para modificar columnas de índices</span><span class="sxs-lookup"><span data-stu-id="1f489-118">To modify index columns</span></span>  
  
1.  <span data-ttu-id="1f489-119">Para agregar, quitar o cambiar la posición de una columna de índice, seleccione la página **General** del cuadro de diálogo **Propiedades del índice** .</span><span class="sxs-lookup"><span data-stu-id="1f489-119">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties** dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1f489-120">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1f489-120">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="1f489-121">Para modificar un índice</span><span class="sxs-lookup"><span data-stu-id="1f489-121">To modify an index</span></span>  
  
1.  <span data-ttu-id="1f489-122">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f489-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1f489-123">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1f489-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1f489-124">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1f489-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1f489-125">En este ejemplo se quita y vuelve a crear un índice existente en la columna `ProductID` de la tabla `Production.WorkOrder` usando la opción `DROP_EXISTING` .</span><span class="sxs-lookup"><span data-stu-id="1f489-125">This example drops and re-creates an existing index on the `ProductID` column of the `Production.WorkOrder` table by using the `DROP_EXISTING` option.</span></span> <span data-ttu-id="1f489-126">También se establecen las opciones `FILLFACTOR` y `PAD_INDEX` .</span><span class="sxs-lookup"><span data-stu-id="1f489-126">The options `FILLFACTOR` and `PAD_INDEX` are also set.</span></span>  
  
     [!code-sql[IndexDDL#CreateIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/createindex.sql#createindex4)]  
  
     <span data-ttu-id="1f489-127">En el ejemplo siguiente se usa ALTER INDEX para establecer varias opciones del índice `AK_SalesOrderHeader_SalesOrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="1f489-127">The following example uses ALTER INDEX to set several options on the index `AK_SalesOrderHeader_SalesOrderNumber`.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="1f489-128">Para modificar columnas de índices</span><span class="sxs-lookup"><span data-stu-id="1f489-128">To modify index columns</span></span>  
  
1.  <span data-ttu-id="1f489-129">Para agregar, quitar o cambiar la posición de una columna de índice, debe quitar y volver a crear el índice.</span><span class="sxs-lookup"><span data-stu-id="1f489-129">To add, remove, or change the position of an index column, you must drop and recreate the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f489-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f489-130">See Also</span></span>  
 <span data-ttu-id="1f489-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1f489-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="1f489-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1f489-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="1f489-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1f489-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 <span data-ttu-id="1f489-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1f489-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span></span>  
 <span data-ttu-id="1f489-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1f489-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span></span>  
 <span data-ttu-id="1f489-136">[Establecer opciones de índice](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="1f489-136">[Set Index Options](set-index-options.md) </span></span>  
 [<span data-ttu-id="1f489-137">Cambiar el nombre a los índices</span><span class="sxs-lookup"><span data-stu-id="1f489-137">Rename Indexes</span></span>](indexes.md)  
  
  
