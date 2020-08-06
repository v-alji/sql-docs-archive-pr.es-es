---
title: Eliminación de estadísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], deleting
- deleting statistics
ms.assetid: eccce0aa-591e-4a1d-bd10-373b022f8749
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 36b74d7e1465c0742cda4fef9f34fb4b3930719c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676412"
---
# <a name="delete-statistics"></a><span data-ttu-id="63cf3-102">Eliminar estadísticas</span><span class="sxs-lookup"><span data-stu-id="63cf3-102">Delete Statistics</span></span>
  <span data-ttu-id="63cf3-103">Puede eliminar (quitar) las estadísticas de las tablas y de las vistas de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63cf3-103">You can delete (drop) statistics from tables and views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="63cf3-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="63cf3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="63cf3-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="63cf3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="63cf3-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="63cf3-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="63cf3-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="63cf3-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="63cf3-108">**Para quitar las estadísticas de una tabla o una vista, con:**</span><span class="sxs-lookup"><span data-stu-id="63cf3-108">**To drop statistics from a table or view, using:**</span></span>  
  
     [<span data-ttu-id="63cf3-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63cf3-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="63cf3-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="63cf3-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="63cf3-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="63cf3-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="63cf3-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="63cf3-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="63cf3-113">Tenga cuidado al quitar estadísticas,</span><span class="sxs-lookup"><span data-stu-id="63cf3-113">Be careful when you drop statistics.</span></span> <span data-ttu-id="63cf3-114">ya que puede verse afectado el plan de ejecución elegido por el optimizador de consultas.</span><span class="sxs-lookup"><span data-stu-id="63cf3-114">Doing so may affect the execution plan chosen by the query optimizer.</span></span>  
  
-   <span data-ttu-id="63cf3-115">Las estadísticas de índices no se pueden quitar mediante DROP STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="63cf3-115">Statistics on indexes cannot be dropped by using DROP STATISTICS.</span></span> <span data-ttu-id="63cf3-116">Las estadísticas permanecen mientras exista el índice.</span><span class="sxs-lookup"><span data-stu-id="63cf3-116">Statistics remain as long as the index exists.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="63cf3-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="63cf3-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="63cf3-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="63cf3-118">Permissions</span></span>  
 <span data-ttu-id="63cf3-119">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="63cf3-119">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="63cf3-120">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="63cf3-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="63cf3-121">Para quitar las estadísticas de una tabla o una vista</span><span class="sxs-lookup"><span data-stu-id="63cf3-121">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="63cf3-122">En el **Explorador de objetos**, haga clic en el signo más para expandir la base de datos en la que desea eliminar la estadística.</span><span class="sxs-lookup"><span data-stu-id="63cf3-122">In **Object Explorer**, click the plus sign to expand the database in which you want to delete a statistic.</span></span>  
  
2.  <span data-ttu-id="63cf3-123">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="63cf3-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="63cf3-124">Haga clic en el signo más para expandir la tabla en la que desea eliminar una estadística.</span><span class="sxs-lookup"><span data-stu-id="63cf3-124">Click the plus sign to expand the table in which you want to delete a statistic.</span></span>  
  
4.  <span data-ttu-id="63cf3-125">Haga clic en el signo más para expandir la carpeta **Estadísticas** .</span><span class="sxs-lookup"><span data-stu-id="63cf3-125">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="63cf3-126">Haga clic con el botón derecho en el objeto de estadísticas que quiera eliminar y, luego, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="63cf3-126">Right-click the statistics object that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="63cf3-127">En el cuadro de diálogo **Eliminar objeto** , asegúrese de que está seleccionada la estadística correcta y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63cf3-127">In the **Delete Object** dialog box, ensure that the correct statistic has been selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="63cf3-128">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="63cf3-128">Using Transact-SQL</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="63cf3-129">Para quitar las estadísticas de una tabla o una vista</span><span class="sxs-lookup"><span data-stu-id="63cf3-129">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="63cf3-130">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63cf3-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="63cf3-131">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="63cf3-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="63cf3-132">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="63cf3-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- First, create two statistics named VendorCredit and CustomerTotal  
    -- The first statistic uses a random 50% sample of information provided from the Name and CreditRating columns in the Purchasing.Vendor table.  
    CREATE STATISTICS VendorCredit  
        ON Purchasing.Vendor (Name, CreditRating)  
        WITH SAMPLE 50 PERCENT  
    -- The second statistic uses all of the information from the CustomerID and TotalDue columns in the Sales.SalesOrderHeader table  
    CREATE STATISTICS CustomerTotal  
        ON Sales.SalesOrderHeader (CustomerID, TotalDue)  
        WITH FULLSCAN;  
    GO  
    -- This next statement drops both of the statistics created above. Note that the naming convention is [table_name].[statistics_name].  
    DROP STATISTICS Purchasing.Vendor.VendorCredit, Sales.SalesOrderHeader.CustomerTotal;  
    GO  
    ```  
  
 <span data-ttu-id="63cf3-133">Para obtener más información, vea [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="63cf3-133">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span></span>  
  
  
