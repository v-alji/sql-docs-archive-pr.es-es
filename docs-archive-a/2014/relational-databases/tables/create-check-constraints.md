---
title: Creación de restricciones CHECK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table constraints [SQL Server]
- attaching check constraints
- columns [SQL Server], constraints
- constraints [SQL Server], check
- CHECK constraints, attaching
ms.assetid: b8756304-9454-4d39-996a-64516831b7df
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7795ee6eca85a22bdd4e84c90ce49a9449ddff28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678136"
---
# <a name="create-check-constraints"></a><span data-ttu-id="2dd70-102">Crear restricciones CHECK</span><span class="sxs-lookup"><span data-stu-id="2dd70-102">Create Check Constraints</span></span>
  <span data-ttu-id="2dd70-103">Puede crear una restricción CHECK en una tabla para especificar los valores de datos aceptables en una o más columnas de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dd70-103">You can create a check constraint in a table to specify the data values that are acceptable in one or more columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2dd70-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2dd70-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2dd70-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="2dd70-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2dd70-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2dd70-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2dd70-107">**Para crear una restricción CHECK nueva con:**</span><span class="sxs-lookup"><span data-stu-id="2dd70-107">**To create a new check constraint using:**</span></span>  
  
     [<span data-ttu-id="2dd70-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2dd70-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2dd70-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2dd70-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2dd70-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="2dd70-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2dd70-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2dd70-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2dd70-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="2dd70-112">Permissions</span></span>  
 <span data-ttu-id="2dd70-113">Requiere permisos ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2dd70-113">Requires ALTER permissions on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2dd70-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2dd70-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="2dd70-115">Para crear una restricción CHECK nueva</span><span class="sxs-lookup"><span data-stu-id="2dd70-115">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="2dd70-116">En el **Explorador de objetos**, expanda la tabla a la que quiera agregar una restricción CHECK, haga clic con el botón derecho en **Restricciones** y haga clic en **Nueva restricción**.</span><span class="sxs-lookup"><span data-stu-id="2dd70-116">In **Object Explorer**, expand the table to which you want to add a check constraint, right-click **Constraints** and click **New Constraint**.</span></span>  
  
2.  <span data-ttu-id="2dd70-117">En el cuadro de diálogo **Comprobar restricciones**, haga clic en el campo **Expresión** y luego en los puntos suspensivos **(...)** .</span><span class="sxs-lookup"><span data-stu-id="2dd70-117">In the **Check Constraints** dialog box, click in the **Expression** field and then click the ellipses **(...)**.</span></span>  
  
3.  <span data-ttu-id="2dd70-118">En el cuadro de diálogo **Expresión de restricción CHECK** , escriba expresiones SQL para la restricción CHECK.</span><span class="sxs-lookup"><span data-stu-id="2dd70-118">In the **Check Constraint Expression** dialog box, type the SQL expressions for the check constraint.</span></span> <span data-ttu-id="2dd70-119">Por ejemplo, para limitar las entradas de la columna `SellEndDate` de la tabla `Product` a un valor que sea mayor o igual que la fecha de la columna `SellStartDate` o que sea un valor NULL, escriba:</span><span class="sxs-lookup"><span data-stu-id="2dd70-119">For example, to limit the entries in the `SellEndDate` column of the `Product` table to a value that is either greater than or equal to the date in the `SellStartDate` column or is a NULL value, type:</span></span>  
  
    ```  
    SellEndDate >= SellStartDate OR SellEndDate IS NULL  
    ```  
  
     <span data-ttu-id="2dd70-120">O bien, para exigir que las entradas que se escriben en la columna `zip` tengan 5 dígitos, escriba:</span><span class="sxs-lookup"><span data-stu-id="2dd70-120">Or, to require entries in the `zip` column to be 5 digits, type:</span></span>  
  
    ```  
    zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2dd70-121">Asegúrese de que escribe los valores de restricción no numéricos entre comillas sencillas (').</span><span class="sxs-lookup"><span data-stu-id="2dd70-121">Make sure to enclose any non-numeric constraint values in single quotation marks (').</span></span>  
  
4.  <span data-ttu-id="2dd70-122">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="2dd70-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2dd70-123">En la categoría **Identidad** , puede cambiar el nombre de la restricción CHECK y agregar una descripción (propiedad extendida) para la restricción.</span><span class="sxs-lookup"><span data-stu-id="2dd70-123">In the **Identity** category, you can change the name of the check constraint and add a description (extended property) for the constraint.</span></span>  
  
6.  <span data-ttu-id="2dd70-124">En la categoría **Diseñador de tablas** , puede definir cuándo debe exigirse la restricción.</span><span class="sxs-lookup"><span data-stu-id="2dd70-124">In the **Table Designer** category, you can set when the constraint is enforced.</span></span>  
  
    |<span data-ttu-id="2dd70-125">**Para**:</span><span class="sxs-lookup"><span data-stu-id="2dd70-125">**To:**</span></span>|<span data-ttu-id="2dd70-126">**Seleccione Sí en los campos siguientes:**</span><span class="sxs-lookup"><span data-stu-id="2dd70-126">**Select Yes in the Following Fields:**</span></span>|  
    |-------------|---------------------------------------------|  
    |<span data-ttu-id="2dd70-127">Pruebe la restricción en los datos existentes antes de que se creara la restricción</span><span class="sxs-lookup"><span data-stu-id="2dd70-127">Test the constraint on data that existed before you created the constraint</span></span>|<span data-ttu-id="2dd70-128">**Comprobar los datos existentes al crear o habilitar**</span><span class="sxs-lookup"><span data-stu-id="2dd70-128">**Check Existing Data On Creation Or Enabling**</span></span>|  
    |<span data-ttu-id="2dd70-129">Exigir la restricción siempre que se produzca una operación de replicación en esta tabla</span><span class="sxs-lookup"><span data-stu-id="2dd70-129">Enforce the constraint whenever a replication operation occurs on this table</span></span>|<span data-ttu-id="2dd70-130">**Exigir para replicación**</span><span class="sxs-lookup"><span data-stu-id="2dd70-130">**Enforce For Replication**</span></span>|  
    |<span data-ttu-id="2dd70-131">Exigir la restricción siempre que se inserte o actualice una fila de esta tabla</span><span class="sxs-lookup"><span data-stu-id="2dd70-131">Enforce the constraint whenever a row of this table is inserted or updated</span></span>|<span data-ttu-id="2dd70-132">**Exigir para comandos INSERT y UPDATE**</span><span class="sxs-lookup"><span data-stu-id="2dd70-132">**Enforce For INSERTs And UPDATEs**</span></span>|  
  
7.  <span data-ttu-id="2dd70-133">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2dd70-133">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2dd70-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2dd70-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="2dd70-135">Para crear una restricción CHECK nueva</span><span class="sxs-lookup"><span data-stu-id="2dd70-135">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="2dd70-136">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dd70-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2dd70-137">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="2dd70-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2dd70-138">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2dd70-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
       ADD ColumnD int NULL   
       CONSTRAINT CHK_ColumnD_DocExc   
       CHECK (ColumnD > 10 AND ColumnD < 50);  
    GO  
    -- Adding values that will pass the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (49);  
    GO  
    -- Adding values that will fail the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (55);  
    GO  
  
    ```  
  
 <span data-ttu-id="2dd70-139">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2dd70-139">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
