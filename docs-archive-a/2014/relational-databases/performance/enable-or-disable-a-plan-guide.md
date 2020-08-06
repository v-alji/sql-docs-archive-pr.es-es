---
title: Habilitar o deshabilitar una guía de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], disabling
- enabling plan guides
- plan guides [SQL Server], enabling
- disabling plan guides
ms.assetid: b00ab550-5308-4cb8-8330-483cd1d25654
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2611697e479d318245d8306b28c826e744ae85ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748088"
---
# <a name="enable-or-disable-a-plan-guide"></a><span data-ttu-id="203e1-102">Habilitar o deshabilitar una guía de plan</span><span class="sxs-lookup"><span data-stu-id="203e1-102">Enable or Disable a Plan Guide</span></span>
  <span data-ttu-id="203e1-103">Puede deshabilitar y habilitar las guías de plan de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203e1-103">You can disable and enable plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="203e1-104">Se puede habilitar o deshabilitar una única guía de plan o todas las guías de plan de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="203e1-104">Either a single plan guides or all plan guides in a database can be enabled or disabled.</span></span>  
  
 <span data-ttu-id="203e1-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="203e1-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="203e1-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="203e1-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="203e1-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="203e1-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="203e1-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="203e1-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="203e1-109">**Para deshabilitar y habilitar guías de plan mediante:**</span><span class="sxs-lookup"><span data-stu-id="203e1-109">**To disable and enable plan guides, using:**</span></span>  
  
     [<span data-ttu-id="203e1-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="203e1-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="203e1-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="203e1-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="203e1-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="203e1-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="203e1-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="203e1-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="203e1-114">Se producirá un error si se intenta quitar o modificar una función, procedimiento almacenado o desencadenador DML al que una guía de plan, habilitada o deshabilitada, haga referencia.</span><span class="sxs-lookup"><span data-stu-id="203e1-114">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="203e1-115">Compruebe siempre las dependencias antes de quitar o modificar alguno de los objetos enumerados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="203e1-115">Always check for dependencies before dropping or modifying any of the objects listed above.</span></span>  
  
-   <span data-ttu-id="203e1-116">Al deshabilitar una guía de plan deshabilitada o habilitar una guía de plan habilitada, no se produce ningún cambio o error.</span><span class="sxs-lookup"><span data-stu-id="203e1-116">Disabling a disabled plan guide or enabling an enabled plan guide has no effect and runs without error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="203e1-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="203e1-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="203e1-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="203e1-118">Permissions</span></span>  
 <span data-ttu-id="203e1-119">La deshabilitación o habilitación de una guía de plan OBJECT requiere el permiso ALTER en el objeto (por ejemplo: función, procedimiento almacenado) al que hace referencia la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="203e1-119">Disabling or enabling an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="203e1-120">Todas las demás guías de plan requieren el permiso ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="203e1-120">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="203e1-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="203e1-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="203e1-122">Para deshabilitar o habilitar una guía de plan</span><span class="sxs-lookup"><span data-stu-id="203e1-122">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="203e1-123">Haga clic en el signo más para expandir la base de datos en que desea deshabilitar o habilitar una guía de plan y, a continuación, haga clic en el signo más para expandir la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="203e1-123">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="203e1-124">Haga clic en el signo más para expandir la carpeta **Guías de plan** .</span><span class="sxs-lookup"><span data-stu-id="203e1-124">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="203e1-125">Haga clic con el botón derecho en la guía de plan que quiera deshabilitar o habilitar y seleccione **Deshabilitar** o **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="203e1-125">Right-click the plan guide you want to disable or enable and select either **Disable** or **Enable**.</span></span>  
  
4.  <span data-ttu-id="203e1-126">En el cuadro de diálogo **Deshabilitar guía de plan** o **Habilitar guía de plan** , compruebe que la acción elegida se ha realizado correctamente y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="203e1-126">In either the **Disable Plan Guide** or **Enable Plan Guide** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="203e1-127">Para habilitar o deshabilitar todas las guías de plan de una base de datos</span><span class="sxs-lookup"><span data-stu-id="203e1-127">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="203e1-128">Haga clic en el signo más para expandir la base de datos en que desea deshabilitar o habilitar una guía de plan y, a continuación, haga clic en el signo más para expandir la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="203e1-128">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="203e1-129">Haga clic con el botón derecho en la carpeta **Guías de plan** y, después, seleccione **Habilitar todo** o **Deshabilitar todo**.</span><span class="sxs-lookup"><span data-stu-id="203e1-129">Right-click the **Plan Guides** folder and then select either **Enable All** or **Disable All**.</span></span>  
  
3.  <span data-ttu-id="203e1-130">En el cuadro de diálogo **Deshabilitar todas las guías de plan** o **Habilitar todas las guías de plan** , compruebe que la acción elegida se ha realizado correctamente y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="203e1-130">In either the **Disable all Plan Guides** or **Enable all Plan Guides** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="203e1-131">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="203e1-131">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="203e1-132">Para deshabilitar o habilitar una guía de plan</span><span class="sxs-lookup"><span data-stu-id="203e1-132">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="203e1-133">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203e1-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="203e1-134">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="203e1-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="203e1-135">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="203e1-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
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
    --Disable the plan guide.  
    EXEC sp_control_plan_guide N'DISABLE', N'Guide3';  
    GO  
    --Enable the plan guide.  
    EXEC sp_control_plan_guide N'ENABLE', N'Guide3';  
    GO  
  
    ```  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="203e1-136">Para habilitar o deshabilitar todas las guías de plan de una base de datos</span><span class="sxs-lookup"><span data-stu-id="203e1-136">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="203e1-137">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203e1-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="203e1-138">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="203e1-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="203e1-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="203e1-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Disable all plan guides in the database.  
    EXEC sp_control_plan_guide N'DISABLE ALL';  
    GO  
    --Enable all plan guides in the database.  
    EXEC sp_control_plan_guide N'ENABLE ALL';  
    GO  
  
    ```  
  
 <span data-ttu-id="203e1-140">Para obtener más información, vea [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="203e1-140">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
