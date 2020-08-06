---
title: Creación de restricciones UNIQUE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- UNIQUE constraints [SQL Server], creating
- constraints [SQL Server], creating
- constraints [SQL Server], unique
ms.assetid: a86f9d6f-f242-43be-b65d-b3435b71b62a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 252de63f965f98734a6d62d94bfff9dc5774cab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748719"
---
# <a name="create-unique-constraints"></a><span data-ttu-id="1297f-102">Crear restricciones UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1297f-102">Create Unique Constraints</span></span>
  <span data-ttu-id="1297f-103">Puede crear una restricción UNIQUE en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] para asegurarse de que no se escribirán valores duplicados en columnas específicas que no participan en una clave principal.</span><span class="sxs-lookup"><span data-stu-id="1297f-103">You can create a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] to ensure no duplicate values are entered in specific columns that do not participate in a primary key.</span></span> <span data-ttu-id="1297f-104">Crear una restricción UNIQUE crea automáticamente un índice único correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1297f-104">Creating a unique constraint automatically creates a corresponding unique index.</span></span>  
  
 <span data-ttu-id="1297f-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="1297f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1297f-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="1297f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1297f-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1297f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1297f-108">**Para crear una restricción UNIQUE con:**</span><span class="sxs-lookup"><span data-stu-id="1297f-108">**To create a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="1297f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1297f-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1297f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1297f-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1297f-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1297f-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1297f-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1297f-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1297f-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="1297f-113">Permissions</span></span>  
 <span data-ttu-id="1297f-114">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="1297f-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1297f-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1297f-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="1297f-116">Para crear una restricción UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1297f-116">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="1297f-117">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla a la que quiera agregar una restricción UNIQUE y haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="1297f-117">In **Object Explorer**, right-click the table to which you want to add a unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="1297f-118">En el menú **Diseñador de tablas** , haga clic en **índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="1297f-118">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="1297f-119">En el cuadro de diálogo **Índices o claves** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1297f-119">In the **Indexes/Keys** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="1297f-120">En la cuadrícula situada debajo de **General**, haga clic en **Tipo** y elija **Clave UNIQUE** en el cuadro de lista desplegable situado a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1297f-120">In the grid under **General**, click **Type** and choose **Unique Key** from the drop-down list box to the right of the property.</span></span>  
  
5.  <span data-ttu-id="1297f-121">En el menú **Archivo**, haga clic en \***Guardar**_nombre de tabla_.</span><span class="sxs-lookup"><span data-stu-id="1297f-121">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1297f-122">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1297f-122">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-unique-constraint"></a><span data-ttu-id="1297f-123">Para crear una restricción UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1297f-123">To create a unique constraint</span></span>  
  
1.  <span data-ttu-id="1297f-124">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1297f-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1297f-125">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1297f-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1297f-126">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1297f-126">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1297f-127">El ejemplo crea la tabla `TransactionHistoryArchive4` y crea una restricción UNIQUE en la columna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="1297f-127">The example creates the table `TransactionHistoryArchive4` and creates a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive4  
     (  
       TransactionID int NOT NULL,   
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)   
    );   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-on-an-existing-table"></a><span data-ttu-id="1297f-128">Para crear una restricción UNIQUE en una tabla existente</span><span class="sxs-lookup"><span data-stu-id="1297f-128">To create a unique constraint on an existing table</span></span>  
  
1.  <span data-ttu-id="1297f-129">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1297f-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1297f-130">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1297f-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1297f-131">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1297f-131">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1297f-132">El ejemplo crea una restricción UNIQUE en las columnas `PasswordHash` y `PasswordSalt` en la tabla `Person.Password`.</span><span class="sxs-lookup"><span data-stu-id="1297f-132">The example creates a unique constraint on the columns `PasswordHash` and `PasswordSalt` in the table `Person.Password`.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    ALTER TABLE Person.Password   
    ADD CONSTRAINT AK_Password UNIQUE (PasswordHash, PasswordSalt);   
    GO  
  
    ```  
  
#### <a name="to-create-a-unique-constraint-in-an-new-table"></a><span data-ttu-id="1297f-133">Para crear una restricción UNIQUE en una tabla nueva</span><span class="sxs-lookup"><span data-stu-id="1297f-133">To create a unique constraint in an new table</span></span>  
  
1.  <span data-ttu-id="1297f-134">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1297f-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1297f-135">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1297f-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1297f-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1297f-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1297f-137">El ejemplo crea una tabla y define una restricción UNIQUE en la columna `TransactionID`.</span><span class="sxs-lookup"><span data-stu-id="1297f-137">The example creates a table and defines a unique constraint on the column `TransactionID`.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Production.TransactionHistoryArchive2  
    (  
       TransactionID int NOT NULL,  
       CONSTRAINT AK_TransactionID UNIQUE(TransactionID)  
    );  
    GO  
  
    ```  
  
     <span data-ttu-id="1297f-138">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) y [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1297f-138">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
