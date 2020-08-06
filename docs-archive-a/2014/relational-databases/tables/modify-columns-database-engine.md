---
title: Modificación de columnas (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying data types
- column data types [SQL Server]
- data types [SQL Server], columns
ms.assetid: b67b95c5-61ef-4bd8-9a3e-1640eb7583ac
author: stevestein
ms.author: sstein
ms.openlocfilehash: a73c25d91b742f1cc1f7edcc8a95cdf226b2683c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674025"
---
# <a name="modify-columns-database-engine"></a><span data-ttu-id="42085-102">Modificar columnas (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="42085-102">Modify Columns (Database Engine)</span></span>
  <span data-ttu-id="42085-103">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , el tipo de datos de una columna se puede modificar mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42085-103">You can modify the data type of a column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="42085-104">Al modificar el tipo de datos de una columna que ya contiene datos, estos datos se pueden perder definitivamente cuando los datos existentes se convierten al nuevo tipo.</span><span class="sxs-lookup"><span data-stu-id="42085-104">Modifying the data type of a column that already contains data can result in the permanent loss of data when the existing data is converted to the new type.</span></span> <span data-ttu-id="42085-105">Se pueden producir además errores en el código y las aplicaciones que dependen de la columna modificada.</span><span class="sxs-lookup"><span data-stu-id="42085-105">In addition, code and applications that depend on the modified column may fail.</span></span> <span data-ttu-id="42085-106">Los elementos afectados pueden ser consultas, vistas, procedimientos almacenados, funciones definidas por el usuario y aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="42085-106">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="42085-107">Tenga en cuenta que estos errores se producirán en cascada.</span><span class="sxs-lookup"><span data-stu-id="42085-107">Note that these failures will cascade.</span></span> <span data-ttu-id="42085-108">Por ejemplo, puede producirse un error en un procedimiento almacenado que llama a una función definida por el usuario que, a su vez, depende de la columna modificada.</span><span class="sxs-lookup"><span data-stu-id="42085-108">For example, a stored procedure that calls a user-defined function that depends on the modified column may fail.</span></span> <span data-ttu-id="42085-109">Tenga en cuenta las consecuencias antes de realizar cualquier cambio en una columna.</span><span class="sxs-lookup"><span data-stu-id="42085-109">Carefully consider any changes you want to make to a column before making it.</span></span>  
  
 <span data-ttu-id="42085-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="42085-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="42085-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="42085-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="42085-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="42085-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="42085-113">**Para modificar el tipo de datos de una columna con:**</span><span class="sxs-lookup"><span data-stu-id="42085-113">**To modify the data type of a column, using:**</span></span>  
  
     [<span data-ttu-id="42085-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="42085-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="42085-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42085-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="42085-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="42085-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="42085-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="42085-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="42085-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="42085-118">Permissions</span></span>  
 <span data-ttu-id="42085-119">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="42085-119">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="42085-120">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="42085-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="42085-121">Para modificar el tipo de datos de una columna</span><span class="sxs-lookup"><span data-stu-id="42085-121">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="42085-122">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla que contenga columnas cuya escala quiera cambiar y, después, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="42085-122">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="42085-123">Seleccione la columna en la que desea modificar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="42085-123">Select the column for which you want to modify the data type.</span></span>  
  
3.  <span data-ttu-id="42085-124">En la pestaña **Propiedades de columna** , haga clic en la celda de la cuadrícula de la propiedad **Tipo de datos** y elija un tipo de datos en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="42085-124">In the **Column Properties** tab, click the grid cell for the **Data Type** property and choose a new data type from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="42085-125">En el menú **Archivo** , haga clic en **Guardar**_table name_.</span><span class="sxs-lookup"><span data-stu-id="42085-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42085-126">Cuando se modifica el tipo de datos de una columna, el Diseñador de tablas aplica la longitud del tipo de datos predeterminada que se ha seleccionado, aunque ya se haya especificado otra.</span><span class="sxs-lookup"><span data-stu-id="42085-126">When you modify the data type of a column, Table Designer applies the default length of the data type you selected, even if you have already specified another.</span></span> <span data-ttu-id="42085-127">Defina siempre la longitud del tipo de datos del valor deseado después de especificar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="42085-127">Always set the data type length for to the desired value after specifying the data type.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="42085-128">Si intenta modificar el tipo de datos de una columna relacionada con otras tablas, el Diseñador de tablas le pide que confirme que el cambio tenga que realizarse también en las columnas de otras tablas.</span><span class="sxs-lookup"><span data-stu-id="42085-128">If you attempt to modify the data type of a column that relates to other tables, Table Designer asks you to confirm that the change should be made to the columns in the other tables as well.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="42085-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42085-129">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="42085-130">Para modificar el tipo de datos de una columna</span><span class="sxs-lookup"><span data-stu-id="42085-130">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="42085-131">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42085-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="42085-132">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="42085-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="42085-133">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="42085-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exy (column_a INT ) ;  
    GO  
    INSERT INTO dbo.doc_exy (column_a) VALUES (10) ;  
    GO  
    ALTER TABLE dbo.doc_exy ALTER COLUMN column_a DECIMAL (5, 2) ;  
    GO  
  
    ```  
  
 <span data-ttu-id="42085-134">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="42085-134">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
