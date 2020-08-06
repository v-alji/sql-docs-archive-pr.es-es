---
title: Aplicar un plan de consulta fijo a una guía de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: bbf401f9-af7c-48e7-8a43-bf25e8af2fd7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 318955c4d0550e311873d8b4a6f79f72e04ac8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744651"
---
# <a name="apply-a-fixed-query-plan-to-a-plan-guide"></a><span data-ttu-id="7553b-102">Aplicar un plan de consulta fijo a una guía de plan</span><span class="sxs-lookup"><span data-stu-id="7553b-102">Apply a Fixed Query Plan to a Plan Guide</span></span>
  <span data-ttu-id="7553b-103">Puede aplicar un plan de consulta fijo a una guía de plan del tipo OBJECT o SQL.</span><span class="sxs-lookup"><span data-stu-id="7553b-103">You can apply a fixed query plan to a plan guide of type OBJECT or SQL.</span></span> <span data-ttu-id="7553b-104">Las guías de plan que se aplican a un plan de consulta fijo resultan útiles cuando ya se tiene constancia de un plan de ejecución existente cuyo rendimiento es mejor que el del seleccionado por el optimizador para una consulta determinada.</span><span class="sxs-lookup"><span data-stu-id="7553b-104">Plan guides that apply a fixed query plan are useful when you know about an existing execution plan that performs better than the one selected by the optimizer for a particular query.</span></span>  
  
 <span data-ttu-id="7553b-105">El ejemplo siguiente crea una guía de plan para una instrucción SQL ad hoc sencilla.</span><span class="sxs-lookup"><span data-stu-id="7553b-105">The following example creates a plan guide for a simple ad hoc SQL statement.</span></span> <span data-ttu-id="7553b-106">El plan de consulta deseado para esta instrucción se proporciona en la guía de plan si se especifica el plan de presentación XML para la consulta directamente en el parámetro `@hints` .</span><span class="sxs-lookup"><span data-stu-id="7553b-106">The desired query plan for this statement is provided in the plan guide by specifying the XML Showplan for the query directly in the `@hints` parameter.</span></span> <span data-ttu-id="7553b-107">El ejemplo ejecuta primero la instrucción SQL para generar un plan en la memoria caché del plan.</span><span class="sxs-lookup"><span data-stu-id="7553b-107">The example first executes the SQL statement to generate a plan in the plan cache.</span></span> <span data-ttu-id="7553b-108">Para los fines de este ejemplo, se supone que el plan generado es el plan deseado y que no se requiere ninguna optimización adicional de la consulta.</span><span class="sxs-lookup"><span data-stu-id="7553b-108">For the purposes of this example, it is assumed that the generated plan is the desired plan and no additional query tuning is required.</span></span> <span data-ttu-id="7553b-109">El plan de presentación XML para la consulta se obtiene consultando las vistas de administración dinámica `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`y `sys.dm_exec_text_query_plan` y está asignado a la variable `@xml_showplan` .</span><span class="sxs-lookup"><span data-stu-id="7553b-109">The XML Showplan for the query is obtained by querying the `sys.dm_exec_query_stats`, `sys.dm_exec_sql_text`, and `sys.dm_exec_text_query_plan` dynamic management views and is assigned to the `@xml_showplan` variable.</span></span> <span data-ttu-id="7553b-110">A continuación, la variable `@xml_showplan` se pasa a la instrucción `sp_create_plan_guide` en el parámetro `@hints` .</span><span class="sxs-lookup"><span data-stu-id="7553b-110">The `@xml_showplan` variable is then passed to the `sp_create_plan_guide` statement in the `@hints` parameter.</span></span> <span data-ttu-id="7553b-111">O bien, puede crear una guía de plan a partir de un plan de consulta de la memoria caché del plan con el procedimiento almacenado [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="7553b-111">Or, you can create a plan guide from a query plan in the plan cache by using the [sp_create_plan_guide_from_handle](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql) stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;  
GO  
DECLARE @xml_showplan nvarchar(max);  
SET @xml_showplan = (SELECT query_plan  
    FROM sys.dm_exec_query_stats AS qs   
    CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
    CROSS APPLY sys.dm_exec_text_query_plan(qs.plan_handle, DEFAULT, DEFAULT) AS qp  
    WHERE st.text LIKE N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;%');  
  
EXEC sp_create_plan_guide   
    @name = N'Guide1_from_XML_showplan',   
    @stmt = N'SELECT City, StateProvinceID, PostalCode FROM Person.Address ORDER BY PostalCode DESC;',   
    @type = N'SQL',  
    @module_or_batch = NULL,   
    @params = NULL,   
    @hints = @xml_showplan;  
GO  
```  
  
  
