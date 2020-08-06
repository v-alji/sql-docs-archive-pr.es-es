---
title: Creación de una guía de plan para consultas parametrizadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- parameterized queries, plan guides for
- plan guides [SQL Server], parameterized queries
ms.assetid: b532ae16-66e7-4641-9bc8-b0d805853477
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 565610826f704274724ea05d821205a5b3391060
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677606"
---
# <a name="create-a-plan-guide-for-parameterized-queries"></a><span data-ttu-id="d99e1-102">Crear una guía de plan para consultas parametrizadas</span><span class="sxs-lookup"><span data-stu-id="d99e1-102">Create a Plan Guide for Parameterized Queries</span></span>
  <span data-ttu-id="d99e1-103">Una guía de plan TEMPLATE compara consultas independientes que se parametrizan en un formulario especificado.</span><span class="sxs-lookup"><span data-stu-id="d99e1-103">A TEMPLATE plan guide matches stand-alone queries that parameterize to a specified form.</span></span>  
  
 <span data-ttu-id="d99e1-104">En el ejemplo siguiente se crea una guía de plan que coincida con cualquier consulta que se parametrice de una forma específica, e indica a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que fuerce la parametrización de la consulta.</span><span class="sxs-lookup"><span data-stu-id="d99e1-104">The following example creates a plan guide that matches any query that parameterizes to a specified form, and directs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to force parameterization of the query.</span></span> <span data-ttu-id="d99e1-105">Las dos consultas siguientes son equivalentes desde el punto de vista sintáctico, pero se diferencian solo en los valores literales de las constantes.</span><span class="sxs-lookup"><span data-stu-id="d99e1-105">The following two queries are syntactically equivalent, but differ only in their constant literal values.</span></span>  
  
```  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45639;  
  
SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
    ON h.SalesOrderID = d.SalesOrderID  
WHERE h.SalesOrderID = 45640;  
```  
  
 <span data-ttu-id="d99e1-106">Ésta es una guía de plan creada en la consulta con parámetros:</span><span class="sxs-lookup"><span data-stu-id="d99e1-106">Here is the plan guide on the parameterized form of the query:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'TemplateGuide1',  
    @stmt = N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
              INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
                  ON h.SalesOrderID = d.SalesOrderID  
              WHERE h.SalesOrderID = @0',  
    @type = N'TEMPLATE',  
    @module_or_batch = NULL,  
    @params = N'@0 int',  
    @hints = N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="d99e1-107">En el ejemplo anterior, el valor del parámetro `@stmt` representa la forma de la consulta con parámetros.</span><span class="sxs-lookup"><span data-stu-id="d99e1-107">In the previous example, the value for the `@stmt` parameter is the parameterized form of the query.</span></span> <span data-ttu-id="d99e1-108">La única manera confiable de obtener este valor para usarlo en sp_create_plan_guide es recurrir al procedimiento almacenado del sistema [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d99e1-108">The only reliable way to obtain this value for use in sp_create_plan_guide is to use the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span> <span data-ttu-id="d99e1-109">El script siguiente se puede utilizar para obtener la consulta con parámetros y, después crear una guía de plan basada en ella.</span><span class="sxs-lookup"><span data-stu-id="d99e1-109">The following script can be used both to obtain the parameterized query and then create a plan guide on it.</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT * FROM AdventureWorks2012.Sales.SalesOrderHeader AS h  
      INNER JOIN AdventureWorks2012.Sales.SalesOrderDetail AS d   
          ON h.SalesOrderID = d.SalesOrderID  
      WHERE h.SalesOrderID = 45639;',  
    @stmt OUTPUT,   
    @params OUTPUT  
EXEC sp_create_plan_guide N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d99e1-110">El valor de los literales de constante del parámetro `@stmt` pasado a `sp_get_query_template` podría afectar al tipo de datos elegido para el parámetro que reemplaza al valor literal.</span><span class="sxs-lookup"><span data-stu-id="d99e1-110">The value of the constant literals in the `@stmt` parameter passed to `sp_get_query_template` might affect the data type that is chosen for the parameter that replaces the literal.</span></span> <span data-ttu-id="d99e1-111">Esto afectaría a la correspondencia de la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="d99e1-111">This will affect plan guide matching.</span></span> <span data-ttu-id="d99e1-112">Puede que tenga que crear más de una guía de plan para abarcar los distintos intervalos de valores de parámetros.</span><span class="sxs-lookup"><span data-stu-id="d99e1-112">You may have to create more than one plan guide to handle different parameter value ranges.</span></span>  
  
 <span data-ttu-id="d99e1-113">También puede utilizar las guías de plan TEMPLATE junto con guías de plan SQL.</span><span class="sxs-lookup"><span data-stu-id="d99e1-113">You can also use TEMPLATE plan guides together with SQL plan guides.</span></span> <span data-ttu-id="d99e1-114">Por ejemplo, puede crear una guía de plan TEMPLATE para asegurarse de que se parametriza una clase de consultas.</span><span class="sxs-lookup"><span data-stu-id="d99e1-114">For example, you can create a TEMPLATE plan guide to make sure that a class of queries is parameterized.</span></span> <span data-ttu-id="d99e1-115">A continuación, puede crear una guía de plan SQL en el formulario parametrizado de esa consulta.</span><span class="sxs-lookup"><span data-stu-id="d99e1-115">You can then create an SQL plan guide on the parameterized form of that query.</span></span>  
  
  
