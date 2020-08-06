---
title: MSSQLSERVER_2020 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2020 (Database Engine error)
ms.assetid: 4a8bf90f-a083-4c53-84f0-d23c711c8081
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5939267c37e90e7b8456dc01a4af79545e775656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675918"
---
# <a name="mssqlserver_2020"></a><span data-ttu-id="61698-102">MSSQLSERVER_2020</span><span class="sxs-lookup"><span data-stu-id="61698-102">MSSQLSERVER_2020</span></span>
    
## <a name="details"></a><span data-ttu-id="61698-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="61698-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="61698-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="61698-104">Product Name</span></span>|<span data-ttu-id="61698-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="61698-105">SQL Server</span></span>|  
|<span data-ttu-id="61698-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="61698-106">Event ID</span></span>|<span data-ttu-id="61698-107">2020</span><span class="sxs-lookup"><span data-stu-id="61698-107">2020</span></span>|  
|<span data-ttu-id="61698-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="61698-108">Event Source</span></span>|<span data-ttu-id="61698-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="61698-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="61698-110">Componente</span><span class="sxs-lookup"><span data-stu-id="61698-110">Component</span></span>|<span data-ttu-id="61698-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="61698-111">SQLEngine</span></span>|  
|<span data-ttu-id="61698-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="61698-112">Symbolic Name</span></span>||  
|<span data-ttu-id="61698-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="61698-113">Message Text</span></span>|<span data-ttu-id="61698-114">Las dependencias notificadas para la entidad "%.\*ls" no incluyen referencias a las columnas.</span><span class="sxs-lookup"><span data-stu-id="61698-114">The dependencies reported for entity "%.\*ls" do not include references to columns.</span></span> <span data-ttu-id="61698-115">Esto se debe a que la entidad hace referencia a un objeto que no existe o a un error de una o varias instrucciones de la entidad.</span><span class="sxs-lookup"><span data-stu-id="61698-115">This is either because the entity references an object that does not exist or because of an error in one or more statements in the entity.</span></span>  <span data-ttu-id="61698-116">Antes de volver a ejecutar la consulta, asegúrese de que no hay errores en la entidad y que existen todos los objetos a los que hace referencia la entidad.</span><span class="sxs-lookup"><span data-stu-id="61698-116">Before rerunning the query, ensure that there are no errors in the entity and that all objects referenced by the entity exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="61698-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="61698-117">Explanation</span></span>  
 <span data-ttu-id="61698-118">La función de sistema **sys.dm_sql_referenced_entities** notificará cualquier dependencia de nivel de columna para las referencias enlazadas a esquemas.</span><span class="sxs-lookup"><span data-stu-id="61698-118">The **sys.dm_sql_referenced_entities** system function will report any column-level dependency for schema-bound references.</span></span> <span data-ttu-id="61698-119">Por ejemplo, la función notificará todas las dependencias de nivel de columna de una vista indizada, ya que una vista indizada requiere que se establezcan enlaces de esquema.</span><span class="sxs-lookup"><span data-stu-id="61698-119">For example, the function will report all column-level dependencies for an indexed view because an indexed view requires schema binding.</span></span> <span data-ttu-id="61698-120">Sin embargo, cuando la entidad a la que se hace referencia no está enlazada a un esquema, las dependencias de columna se notifican exclusivamente cuando todas las instrucciones incluidas en las columnas a las que se hace referencia se pueden enlazar.</span><span class="sxs-lookup"><span data-stu-id="61698-120">However, when the referenced entity is not schema-bound, column dependencies are reported only when all statements in which the columns are referenced can be bound.</span></span> <span data-ttu-id="61698-121">Las instrucciones se pueden enlazar correctamente solo si se analizan todos los objetos que contienen en ese momento.</span><span class="sxs-lookup"><span data-stu-id="61698-121">Statements can be successfully bound only if all objects exist at the time the statements are parsed.</span></span> <span data-ttu-id="61698-122">Si alguna instrucción definida en la entidad no se puede enlazar, las dependencias de columna no se notificarán y la columna **referenced_minor_id** devolverá 0.</span><span class="sxs-lookup"><span data-stu-id="61698-122">If any statement defined in the entity fails to bind, column dependencies will not be reported and the **referenced_minor_id** column will return 0.</span></span> <span data-ttu-id="61698-123">Cuando las dependencias de columna no se pueden devolver, se produce el error 2020.</span><span class="sxs-lookup"><span data-stu-id="61698-123">When column dependencies cannot be resolved, error 2020 is raised.</span></span> <span data-ttu-id="61698-124">Este error no impide que la consulta devuelva dependencias de nivel de objeto.</span><span class="sxs-lookup"><span data-stu-id="61698-124">This error does not prevent the query from returning object-level dependencies.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="61698-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="61698-125">User Action</span></span>  
 <span data-ttu-id="61698-126">Corrija los errores identificados en el mensaje antes que el error 2020.</span><span class="sxs-lookup"><span data-stu-id="61698-126">Correct any errors identified in the message before error 2020.</span></span> <span data-ttu-id="61698-127">Por ejemplo, en el siguiente ejemplo de código, la vista `Production.ApprovedDocuments` se define en las columnas `Title`, `ChangeNumber` y `Status` de la tabla `Production.Document`.</span><span class="sxs-lookup"><span data-stu-id="61698-127">For example, in the following code example the view `Production.ApprovedDocuments` is defined on the columns `Title`, `ChangeNumber`, and `Status` in the `Production.Document` table.</span></span> <span data-ttu-id="61698-128">La función de sistema **sys.dm_sql_referenced_entities** recibe consultas relacionadas con los objetos y las columnas de los que dependa la vista `ApprovedDocuments`.</span><span class="sxs-lookup"><span data-stu-id="61698-128">The **sys.dm_sql_referenced_entities** system function is queried for the objects and columns on which the `ApprovedDocuments` view depends.</span></span> <span data-ttu-id="61698-129">Como la vista no se crea utilizando la cláusula WITH SCHEMA_BINDING, las columnas a las que se hace referencia en la vista se pueden modificar en la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="61698-129">Because the view is not created using the WITH SCHEMA_BINDING clause, the columns referenced in the view can be modified in the referenced table.</span></span> <span data-ttu-id="61698-130">En el ejemplo se modifica la columna `ChangeNumber` de la tabla `Production.Document` al cambiar el nombre a `TrackingNumber`.</span><span class="sxs-lookup"><span data-stu-id="61698-130">The example alters the column `ChangeNumber` in the `Production.Document` table by renaming it to `TrackingNumber`.</span></span> <span data-ttu-id="61698-131">La vista de catálogo recibe de nuevo consultas de la vista `ApprovedDocuments`; sin embargo, no puede enlazarse a todas las columnas definidas en la vista.</span><span class="sxs-lookup"><span data-stu-id="61698-131">The catalog view is queried again for the `ApprovedDocuments` view; however it cannot bind to all the columns defined in the view.</span></span> <span data-ttu-id="61698-132">Se devuelven los errores 207 y 2020, que identifican el problema.</span><span class="sxs-lookup"><span data-stu-id="61698-132">Errors 207 and 2020 are returned identifying the problem.</span></span> <span data-ttu-id="61698-133">A fin de resolver el problema, la vista debe modificarse para que refleje el nuevo nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="61698-133">To resolve the problem, the view must be altered to reflect the new name of the column.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `CREATE VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title, ChangeNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 `EXEC sp_rename 'Production.Document.ChangeNumber', 'TrackingNumber', 'COLUMN';`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 <span data-ttu-id="61698-134">La consulta devuelve los siguientes mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="61698-134">The query returns the following error messages.</span></span>  
  
 `Msg 207, Level 16, State 1, Procedure ApprovedDocuments, Line 3`  
  
 `Invalid column name 'ChangeNumber'.`  
  
 `Msg 2020, Level 16, State 1, Line 1`  
  
 `The dependencies reported for entity`  
  
 `"Production.ApprovedDocuments" do not include references to`  
  
 `columns. This is either because the entity references an`  
  
 `object that does not exist or because of an error in one or`  
  
 `more statements in the entity. Before rerunning the query,`  
  
 `ensure that there are no errors in the entity and that all`  
  
 `objects referenced by the entity exist.`  
  
 <span data-ttu-id="61698-135">En el ejemplo siguiente se corrige el nombre de la columna en la vista.</span><span class="sxs-lookup"><span data-stu-id="61698-135">The following example corrects the column name in the view.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `ALTER VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title,TrackingNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
## <a name="see-also"></a><span data-ttu-id="61698-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61698-136">See Also</span></span>  
 [<span data-ttu-id="61698-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61698-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
  
