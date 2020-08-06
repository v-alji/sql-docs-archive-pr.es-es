---
title: Creación de claves principales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- primary keys [SQL Server], creating
ms.assetid: 85c623ca-4656-4d70-a9db-ee4d897cd214
author: stevestein
ms.author: sstein
ms.openlocfilehash: c515ef8f978b41225ff45e87646b0aa7a9706a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678133"
---
# <a name="create-primary-keys"></a><span data-ttu-id="5b9cf-102">Crear claves principales</span><span class="sxs-lookup"><span data-stu-id="5b9cf-102">Create Primary Keys</span></span>
  <span data-ttu-id="5b9cf-103">Puede definir una clave principal en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b9cf-103">You can define a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5b9cf-104">Al crear una clave principal, se crea automáticamente un índice único, índice clúster o no clúster correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-104">Creating a primary key automatically creates a corresponding unique, clustered or nonclustered index.</span></span>  
  
 <span data-ttu-id="5b9cf-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5b9cf-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5b9cf-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5b9cf-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5b9cf-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5b9cf-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5b9cf-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5b9cf-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5b9cf-109">**Para crear una clave principal con:**</span><span class="sxs-lookup"><span data-stu-id="5b9cf-109">**To create a primary key, using:**</span></span>  
  
     [<span data-ttu-id="5b9cf-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b9cf-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5b9cf-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b9cf-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b9cf-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="5b9cf-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5b9cf-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="5b9cf-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5b9cf-114">Una tabla solo puede incluir una restricción PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-114">A table can contain only one PRIMARY KEY constraint.</span></span>  
  
-   <span data-ttu-id="5b9cf-115">Todas las columnas definidas en una restricción PRIMARY KEY se deben definir como NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-115">All columns defined within a PRIMARY KEY constraint must be defined as NOT NULL.</span></span> <span data-ttu-id="5b9cf-116">Si no se especifica nulabilidad, la nulabilidad de todas las columnas que participan en una restricción PRIMARY KEY se establece en NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-116">If nullability is not specified, all columns participating in a PRIMARY KEY constraint have their nullability set to NOT NULL.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b9cf-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5b9cf-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5b9cf-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="5b9cf-118">Permissions</span></span>  
 <span data-ttu-id="5b9cf-119">La creación de una tabla nueva con una clave principal requiere el permiso CREATE TABLE en la base de datos y el permiso ALTER en el esquema en el que se crea la tabla.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-119">Creating a new table with a primary key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="5b9cf-120">La creación de una clave principal de una tabla existente requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-120">Creating a primary key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5b9cf-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b9cf-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-primary-key"></a><span data-ttu-id="5b9cf-122">Para crear una clave principal</span><span class="sxs-lookup"><span data-stu-id="5b9cf-122">To create a primary key</span></span>  
  
1.  <span data-ttu-id="5b9cf-123">En Explorador de objetos, haga clic con el botón secundario en la tabla a la que desea agregar una restricción UNIQUE y haga clic en **diseño**.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-123">In Object Explorer, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="5b9cf-124">En el **Diseñador de tablas**, haga clic en el selector de filas de la columna de base de datos que desea definir como clave principal.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-124">In **Table Designer**, click the row selector for the database column you want to define as the primary key.</span></span> <span data-ttu-id="5b9cf-125">Si desea seleccionar varias columnas, mantenga presionada la tecla CTRL mientras hace clic en los selectores de fila de las otras columnas.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-125">If you want to select multiple columns, hold down the CTRL key while you click the row selectors for the other columns.</span></span>  
  
3.  <span data-ttu-id="5b9cf-126">Haga clic con el botón derecho en el selector de fila para la columna y seleccione **Establecer clave principal**.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-126">Right-click the row selector for the column and select **Set Primary Key**.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="5b9cf-127">Si desea volver a definir la clave principal, debe eliminar las relaciones establecidas con la clave principal existente antes de crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-127">If you want to redefine the primary key, any relationships to the existing primary key must be deleted before the new primary key can be created.</span></span> <span data-ttu-id="5b9cf-128">Un mensaje le advertirá de que las relaciones existentes se eliminarán automáticamente durante este proceso.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-128">A message will warn you that existing relationships will be automatically deleted as part of this process.</span></span>  
  
 <span data-ttu-id="5b9cf-129">Las columnas de clave principal se indican mediante un símbolo de clave principal en el selector de fila.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-129">A primary key column is identified by a primary key symbol in its row selector.</span></span>  
  
 <span data-ttu-id="5b9cf-130">Si una clave principal consta de más de una columna, se admitirán valores duplicados en una columna, pero cada combinación de valores de todas las columnas de la clave principal debe ser única.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-130">If a primary key consists of more than one column, duplicate values are allowed in one column, but each combination of values from all the columns in the primary key must be unique.</span></span>  
  
 <span data-ttu-id="5b9cf-131">Si define una clave compuesta, el orden de las columnas de la clave principal coincide con el de las columnas mostradas en la tabla.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-131">If you define a compound key, the order of columns in the primary key matches the order of columns as shown in the table.</span></span> <span data-ttu-id="5b9cf-132">Sin embargo, puede cambiar el orden de las columnas después de crear la clave principal.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-132">However, you can change the order of columns after the primary key is created.</span></span> <span data-ttu-id="5b9cf-133">Para obtener más información, vea [Modificar claves principales](modify-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="5b9cf-133">For more information, see [Modify Primary Keys](modify-primary-keys.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5b9cf-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5b9cf-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-primary-key-in-an-existing-table"></a><span data-ttu-id="5b9cf-135">Para crear una clave principal en una tabla existente</span><span class="sxs-lookup"><span data-stu-id="5b9cf-135">To create a primary key in an existing table</span></span>  
  
1.  <span data-ttu-id="5b9cf-136">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b9cf-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b9cf-137">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b9cf-138">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5b9cf-139">El ejemplo crea una clave principal en la columna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-139">The example creates a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Production.TransactionHistoryArchive   
    ADD CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID);  
    GO  
  
    ```  
  
#### <a name="to-create-a-primary-key-in-a-new-table"></a><span data-ttu-id="5b9cf-140">Para crear una clave principal en una nueva tabla</span><span class="sxs-lookup"><span data-stu-id="5b9cf-140">To create a primary key in a new table</span></span>  
  
1.  <span data-ttu-id="5b9cf-141">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b9cf-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b9cf-142">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5b9cf-143">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5b9cf-144">El ejemplo crea una tabla y define una clave principal en la columna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="5b9cf-144">The example creates a table and defines a primary key on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive1  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT PK_TransactionHistoryArchive_TransactionID PRIMARY KEY CLUSTERED (TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="5b9cf-145">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) y [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b9cf-145">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
