---
title: Deshabilitar restricciones CHECK con instrucciones INSERT y UPDATE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: c7287ad1-50d2-4e80-bc0c-b5570f7e5f69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 780a2c1bfd9f21c71367ad61f200ec19ab44a608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672862"
---
# <a name="disable-check-constraints-with-insert-and-update-statements"></a><span data-ttu-id="4fc3a-102">Deshabilitar restricciones CHECK con instrucciones INSERT y UPDATE</span><span class="sxs-lookup"><span data-stu-id="4fc3a-102">Disable Check Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="4fc3a-103">Puede deshabilitar una restricción CHECK para las transacciones INSERT y UPDATE de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fc3a-103">You can disable a check constraint for INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4fc3a-104">Después de deshabilitar las restricciones CHECK, las posteriores inserciones o actualizaciones de la columna no se validan con las condiciones de la restricción.</span><span class="sxs-lookup"><span data-stu-id="4fc3a-104">After you disable the check constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span> <span data-ttu-id="4fc3a-105">Use esta opción si sabe que los nuevos datos infringirán la restricción existente o si la restricción solo se aplica a los datos que ya están en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4fc3a-105">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="4fc3a-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4fc3a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4fc3a-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4fc3a-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4fc3a-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4fc3a-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4fc3a-109">**Para deshabilitar una restricción CHECK para las instrucciones INSERT y UPDATE con:**</span><span class="sxs-lookup"><span data-stu-id="4fc3a-109">**To disable a check constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="4fc3a-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4fc3a-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4fc3a-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4fc3a-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4fc3a-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4fc3a-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4fc3a-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4fc3a-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4fc3a-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="4fc3a-114">Permissions</span></span>  
 <span data-ttu-id="4fc3a-115">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="4fc3a-115">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4fc3a-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4fc3a-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="4fc3a-117">Para deshabilitar una restricción CHECK para las instrucciones INSERT y UPDATE</span><span class="sxs-lookup"><span data-stu-id="4fc3a-117">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="4fc3a-118">En el **Explorador de objetos**, expanda la tabla que contiene la restricción y, a continuación, expanda la carpeta **Restricciones** .</span><span class="sxs-lookup"><span data-stu-id="4fc3a-118">In **Object Explorer**, expand the table with the constraint and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="4fc3a-119">Haga clic con el botón derecho en la restricción y seleccione **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="4fc3a-119">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="4fc3a-120">En la cuadrícula situada debajo de **Diseñador de tablas**, haga clic en **Exigir para comandos INSERTs y UPDATEs** y seleccione **No** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="4fc3a-120">In the grid under **Table Designer**, click **Enforce For INSERTs And UPDATEs** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="4fc3a-121">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4fc3a-121">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4fc3a-122">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4fc3a-122">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="4fc3a-123">Para deshabilitar una restricción CHECK para las instrucciones INSERT y UPDATE</span><span class="sxs-lookup"><span data-stu-id="4fc3a-123">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="4fc3a-124">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fc3a-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4fc3a-125">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4fc3a-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4fc3a-126">Copie y pegue los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4fc3a-126">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT CK_PurchaseOrderHeader_Freight;   
    GO  
    ```  
  
 <span data-ttu-id="4fc3a-127">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4fc3a-127">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
