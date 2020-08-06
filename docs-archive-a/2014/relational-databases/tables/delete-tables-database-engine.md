---
title: Eliminación de tablas (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table deletions [SQL Server]
- deleting tables
- removing tables
- dropping tables
ms.assetid: ca6aa3e9-9885-44c3-bafc-aec441fd97ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1e361456534f565f854d348bbef5751c7d66c0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748716"
---
# <a name="delete-tables-database-engine"></a><span data-ttu-id="af140-102">Eliminar tablas (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="af140-102">Delete Tables (Database Engine)</span></span>
  <span data-ttu-id="af140-103">Puede eliminar (quitar) una tabla de la base de datos de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af140-103">You can delete (drop) a table from your database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="af140-104">Piénselo bien antes de eliminar una tabla.</span><span class="sxs-lookup"><span data-stu-id="af140-104">Think carefully before you delete a table.</span></span> <span data-ttu-id="af140-105">Si las consultas, las vistas, las funciones definidas por el usuario, los procedimientos almacenados o los programas existentes hacen referencia a la tabla, la eliminación de la tabla hará que estos objetos dejen de ser válidos.</span><span class="sxs-lookup"><span data-stu-id="af140-105">If existing queries, views, user-defined functions, stored procedures, or programs refer to that table, the deletion will make these objects invalid.</span></span>  
  
 <span data-ttu-id="af140-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="af140-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="af140-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="af140-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="af140-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="af140-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="af140-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="af140-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="af140-110">**Para eliminar una tabla con:**</span><span class="sxs-lookup"><span data-stu-id="af140-110">**To Delete a Table, using:**</span></span>  
  
     [<span data-ttu-id="af140-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af140-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="af140-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af140-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="af140-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="af140-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="af140-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="af140-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="af140-115">No se puede eliminar una tabla a la que haga referencia una restricción FOREIGN KEY.</span><span class="sxs-lookup"><span data-stu-id="af140-115">You cannot drop a table that is referenced by a FOREIGN KEY constraint.</span></span> <span data-ttu-id="af140-116">Primero se debe quitar la restricción FOREIGN KEY o la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="af140-116">The referencing FOREIGN KEY constraint or the referencing table must first be dropped.</span></span> <span data-ttu-id="af140-117">Si la tabla de referencia y la tabla que tiene la clave principal se van a quitar en la misma instrucción DROP TABLE, la tabla de referencia debe aparecer primero.</span><span class="sxs-lookup"><span data-stu-id="af140-117">If both the referencing table and the table that holds the primary key are being dropped in the same DROP TABLE statement, the referencing table must be listed first.</span></span>  
  
-   <span data-ttu-id="af140-118">Cuando se quita la tabla, las reglas o valores predeterminados de la tabla pierden sus enlaces y se quitan automáticamente las restricciones o desencadenadores asociados con la tabla.</span><span class="sxs-lookup"><span data-stu-id="af140-118">When a table is dropped, rules or defaults on the table lose their binding, and any constraints or triggers associated with the table are automatically dropped.</span></span> <span data-ttu-id="af140-119">Si vuelve a crear una tabla, debe volver a enlazar las reglas y valores predeterminados apropiados, volver a crear los desencadenadores y agregar todas las restricciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="af140-119">If you re-create a table, you must rebind the appropriate rules and defaults, re-create any triggers, and add all required constraints.</span></span>  
  
-   <span data-ttu-id="af140-120">Si quita una tabla que contiene una columna `varbinary (max)` con el atributo FILESTREAM, los datos almacenados en el sistema de archivos no se quitarán.</span><span class="sxs-lookup"><span data-stu-id="af140-120">If you drop a table that contains a `varbinary (max)` column with the FILESTREAM attribute, any data stored in the file system will not be removed.</span></span>  
  
-   <span data-ttu-id="af140-121">DROP TABLE y CREATE TABLE no se deberían ejecutar en la misma tabla en el mismo lote.</span><span class="sxs-lookup"><span data-stu-id="af140-121">DROP TABLE and CREATE TABLE should not be executed on the same table in the same batch.</span></span> <span data-ttu-id="af140-122">De lo contrario, podría producirse un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="af140-122">Otherwise an unexpected error may occur.</span></span>  
  
-   <span data-ttu-id="af140-123">Las vistas o procedimientos almacenados que hagan referencia a la tabla quitada se deben eliminar o modificar explícitamente para quitar la referencia a la tabla.</span><span class="sxs-lookup"><span data-stu-id="af140-123">Any view or stored procedure that references the dropped table must be explicitly deleted or modified to remove the reference to the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="af140-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="af140-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="af140-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="af140-125">Permissions</span></span>  
 <span data-ttu-id="af140-126">Se requiere el permiso ALTER en el esquema al que pertenece la tabla, el permiso CONTROL en la tabla o la pertenencia al rol fijo de base de datos **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="af140-126">Requires ALTER permission on the schema to which the table belongs, CONTROL permission on the table, or membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="af140-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af140-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-table-from-the-database"></a><span data-ttu-id="af140-128">Para eliminar una tabla de la base de datos</span><span class="sxs-lookup"><span data-stu-id="af140-128">To delete a table from the database</span></span>  
  
1.  <span data-ttu-id="af140-129">En el Explorador de objetos, seleccione la tabla que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="af140-129">In Object Explorer, select the table you want to delete.</span></span>  
  
2.  <span data-ttu-id="af140-130">Haga clic con el botón derecho en la tabla y elija **Eliminar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="af140-130">Right-click the table and choose **Delete** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="af140-131">Un cuadro de mensaje le pedirá que confirme la eliminación.</span><span class="sxs-lookup"><span data-stu-id="af140-131">A message box prompts you to confirm the deletion.</span></span> <span data-ttu-id="af140-132">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="af140-132">Click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="af140-133">Al eliminar una tabla, se suprimirán automáticamente todas relaciones que mantenga.</span><span class="sxs-lookup"><span data-stu-id="af140-133">Deleting a table automatically removes any relationships to it.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="af140-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="af140-134">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-table-in-query-editor"></a><span data-ttu-id="af140-135">Para eliminar una tabla en el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="af140-135">To delete a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="af140-136">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af140-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="af140-137">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="af140-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="af140-138">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="af140-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    DROP TABLE dbo.PurchaseOrderDetail;  
  
    ```  
  
 <span data-ttu-id="af140-139">Para obtener más información, vea [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="af140-139">For more information, see [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql)</span></span>  
  
  
