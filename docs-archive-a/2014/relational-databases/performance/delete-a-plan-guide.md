---
title: Eliminación de una guía de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], deleting
ms.assetid: aa4d3188-6927-43de-a3e3-90fc16eeaca7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 303ad6f59cbe24265aec66f3cb780a5b4ad4f157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745229"
---
# <a name="delete-a-plan-guide"></a><span data-ttu-id="1a43c-102">Eliminar una guía de plan</span><span class="sxs-lookup"><span data-stu-id="1a43c-102">Delete a Plan Guide</span></span>
  <span data-ttu-id="1a43c-103">Puede eliminar (quitar) una guía de plan en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a43c-103">You can delete (drop) a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1a43c-104">Mediante [!INCLUDE[tsql](../../includes/tsql-md.md)], también puede eliminar todas las guías de plan de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="1a43c-104">Using [!INCLUDE[tsql](../../includes/tsql-md.md)], you can also delete all of the plan guides in a database.</span></span>  
  
 <span data-ttu-id="1a43c-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="1a43c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1a43c-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="1a43c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1a43c-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1a43c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1a43c-108">**Para eliminar una guía de plan mediante:**</span><span class="sxs-lookup"><span data-stu-id="1a43c-108">**To delete a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="1a43c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a43c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1a43c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a43c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1a43c-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1a43c-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1a43c-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1a43c-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1a43c-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="1a43c-113">Permissions</span></span>  
 <span data-ttu-id="1a43c-114">La eliminación de una guía de plan OBJECT requiere el permiso ALTER en el objeto (por ejemplo: función, procedimiento almacenado) al que hace referencia la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="1a43c-114">Deleting an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="1a43c-115">Todas las demás guías de plan requieren el permiso ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="1a43c-115">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1a43c-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a43c-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-plan-guide"></a><span data-ttu-id="1a43c-117">Para eliminar una guía de plan</span><span class="sxs-lookup"><span data-stu-id="1a43c-117">To delete a plan guide</span></span>  
  
1.  <span data-ttu-id="1a43c-118">Haga clic en el signo más para expandir la base de datos en que desea eliminar una guía de plan y, a continuación, haga clic en el signo más para expandir la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="1a43c-118">Click the plus sign to expand the database in which you want to delete a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="1a43c-119">Haga clic en el signo más para expandir la carpeta **Guías de plan** .</span><span class="sxs-lookup"><span data-stu-id="1a43c-119">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="1a43c-120">Haga clic con el botón derecho en la guía de plan que quiera eliminar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="1a43c-120">Right-click the plan guide you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="1a43c-121">En el cuadro de diálogo **Eliminar objeto** , asegúrese de que está seleccionada la guía de plan correcta y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1a43c-121">In the **Delete Object** dialog box, ensure that the correct plan guide is selected and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1a43c-122">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a43c-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-single-plan-guide"></a><span data-ttu-id="1a43c-123">Para eliminar una guía de plan única</span><span class="sxs-lookup"><span data-stu-id="1a43c-123">To delete a single plan guide</span></span>  
  
1.  <span data-ttu-id="1a43c-124">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a43c-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1a43c-125">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1a43c-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1a43c-126">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1a43c-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Create a procedure on which to define the plan guide.  
    IF OBJECT_ID(N'Sales.GetSalesOrderByCountry', N'P') IS NOT NULL  
        DROP PROCEDURE Sales.GetSalesOrderByCountry;  
    GO  
    CREATE PROCEDURE Sales.GetSalesOrderByCountry   
        (@Country nvarchar(60))  
    AS  
    BEGIN  
        SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country;  
    END  
    GO  
    --Create the plan guide.  
    EXEC sp_create_plan_guide N'Guide3',  
        N'SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country',  
        N'OBJECT',  
        N'Sales.GetSalesOrderByCountry',  
        NULL,  
        N'OPTION (OPTIMIZE FOR (@Country = N''US''))';  
    GO  
    --Drop the plan guide.  
    EXEC sp_control_plan_guide N'DROP', N'Guide3';  
    GO  
    ```  
  
#### <a name="to-delete-all-plan-guides-in-a-database"></a><span data-ttu-id="1a43c-127">Para eliminar todas las guías de plan de una base de datos</span><span class="sxs-lookup"><span data-stu-id="1a43c-127">To delete all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="1a43c-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a43c-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1a43c-129">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1a43c-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1a43c-130">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1a43c-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_control_plan_guide N'DROP ALL';  
    GO  
    ```  
  
 <span data-ttu-id="1a43c-131">Para obtener más información, vea [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a43c-131">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
