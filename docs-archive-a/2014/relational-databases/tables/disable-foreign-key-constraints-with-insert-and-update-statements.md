---
title: Deshabilitar restricciones de clave externa con instrucciones INSERT y UPDATE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
- UPDATE statement [SQL Server], foreign key constraints
- INSERT statement [SQL Server], foreign key constraints
ms.assetid: 029168d7-085e-4b13-9b86-5644b67c6e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: e91328f4f12f2a0a27f397c7bd95390a505f3998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671956"
---
# <a name="disable-foreign-key-constraints-with-insert-and-update-statements"></a><span data-ttu-id="605ac-102">Deshabilitar restricciones FOREIGN KEY con instrucciones INSERT y UPDATE</span><span class="sxs-lookup"><span data-stu-id="605ac-102">Disable Foreign Key Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="605ac-103">Puede deshabilitar una restricción de clave externa durante las transacciones INSERT y UPDATE en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="605ac-103">You can disable a foreign key constraint during INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="605ac-104">Use esta opción si sabe que los nuevos datos infringirán la restricción existente o si la restricción solo se aplica a los datos que ya están en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="605ac-104">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="605ac-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="605ac-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="605ac-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="605ac-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="605ac-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="605ac-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="605ac-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="605ac-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="605ac-109">**Para deshabilitar una restricción de clave externa en las instrucciones INSERT y UPDATE, use:**</span><span class="sxs-lookup"><span data-stu-id="605ac-109">**To disable a foreign key constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="605ac-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="605ac-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="605ac-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="605ac-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="605ac-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="605ac-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="605ac-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="605ac-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="605ac-114">Después de deshabilitar estas restricciones, las posteriores inserciones o actualizaciones de la columna no se validan con las condiciones de la restricción.</span><span class="sxs-lookup"><span data-stu-id="605ac-114">After you disable these constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="605ac-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="605ac-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="605ac-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="605ac-116">Permissions</span></span>  
 <span data-ttu-id="605ac-117">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="605ac-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="605ac-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="605ac-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="605ac-119">Para deshabilitar una restricción FOREIGN KEY de instrucciones INSERT y UPDATE</span><span class="sxs-lookup"><span data-stu-id="605ac-119">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="605ac-120">En el **Explorador de objetos**, expanda la tabla que contiene la restricción y, a continuación, expanda la carpeta **Claves** .</span><span class="sxs-lookup"><span data-stu-id="605ac-120">In **Object Explorer**, expand the table with the constraint and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="605ac-121">Haga clic con el botón derecho en la restricción y seleccione **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="605ac-121">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="605ac-122">En la cuadrícula situada debajo de **Diseñador de tablas**, haga clic en **Exigir restricción de clave externa** y seleccione **No** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="605ac-122">In the grid under **Table Designer**, click **Enforce Foreign Key Constraint** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="605ac-123">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="605ac-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="605ac-124">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="605ac-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="605ac-125">Para deshabilitar una restricción FOREIGN KEY de instrucciones INSERT y UPDATE</span><span class="sxs-lookup"><span data-stu-id="605ac-125">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="605ac-126">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="605ac-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="605ac-127">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="605ac-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="605ac-128">Copie y pegue los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="605ac-128">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT FK_PurchaseOrderHeader_Employee_EmployeeID;  
    GO  
    ```  
  
 <span data-ttu-id="605ac-129">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="605ac-129">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
