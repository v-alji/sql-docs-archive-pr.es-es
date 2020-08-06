---
title: Eliminación de un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- removing stored procedures
- stored procedures [SQL Server], deleting
- deleting stored procedures
ms.assetid: 232dbf4d-392a-406f-af3a-579518cd8e46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 418e68d4bb7c6ba6632767a554aea72e85726840
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676393"
---
# <a name="delete-a-stored-procedure"></a><span data-ttu-id="ff430-102">Eliminar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="ff430-102">Delete a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-delete-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="ff430-103">En este tema se describe cómo eliminar un procedimiento almacenado [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff430-103">This topic describes how to delete a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="ff430-104">**Antes de empezar:**  [Limitaciones y restricciones](#Restrictions), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="ff430-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="ff430-105">**Para eliminar un procedimiento con:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="ff430-105">**To delete a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ff430-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ff430-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ff430-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ff430-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ff430-108">Eliminar un procedimiento puede hacer que los objetos y scripts dependientes produzcan un error cuando los objetos y scripts no se han actualizado para reflejar la eliminación del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ff430-108">Deleting a procedure can cause dependent objects and scripts to fail when the objects and scripts are not updated to reflect the removal of the procedure.</span></span> <span data-ttu-id="ff430-109">No obstante, si se crea un nuevo procedimiento con el mismo nombre y los mismos parámetros para reemplazar al que se eliminó, los objetos que hagan referencia a él antiguo se procesarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff430-109">However, if a new procedure of the same name and the same parameters is created to replace the one that was deleted, other objects that reference it will still process successfully.</span></span> <span data-ttu-id="ff430-110">Para obtener más información, vea [Ver las dependencias de un procedimiento almacenado](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="ff430-110">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ff430-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ff430-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ff430-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="ff430-112">Permissions</span></span>  
 <span data-ttu-id="ff430-113">Requiere el permiso ALTER en el esquema al que pertenece el procedimiento o el permiso CONTROL en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ff430-113">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span>  
  
##  <a name="how-to-delete-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="ff430-114">Cómo eliminar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="ff430-114">How to Delete a Stored Procedure</span></span>  
 <span data-ttu-id="ff430-115">Puede usar cualquiera de los siguientes medios:</span><span class="sxs-lookup"><span data-stu-id="ff430-115">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="ff430-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ff430-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="ff430-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ff430-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ff430-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ff430-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ff430-119">**Para eliminar un procedimiento en el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="ff430-119">**To delete a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="ff430-120">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="ff430-120">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ff430-121">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento y, a continuación, expanda **Programación**.</span><span class="sxs-lookup"><span data-stu-id="ff430-121">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="ff430-122">Expanda **Procedimientos almacenados**, haga clic con el botón derecho en el procedimiento que quiera eliminar y, luego, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ff430-122">Expand **Stored Procedures**, right-click the procedure to remove, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="ff430-123">Para ver los objetos que dependen del procedimiento, haga clic en **Mostrar dependencias**.</span><span class="sxs-lookup"><span data-stu-id="ff430-123">To view objects that depend on the procedure, click **Show Dependencies**.</span></span>  
  
5.  <span data-ttu-id="ff430-124">Confirme que haya seleccionado el procedimiento correcto y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff430-124">Confirm the correct procedure is selected, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="ff430-125">Quite las referencias al procedimiento de cualquier objeto y script dependientes.</span><span class="sxs-lookup"><span data-stu-id="ff430-125">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ff430-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ff430-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="ff430-127">**Para eliminar un procedimiento en el Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="ff430-127">**To delete a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="ff430-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="ff430-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ff430-129">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento o bien, en la barra de herramientas, seleccione la base de datos en la lista de bases de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="ff430-129">Expand **Databases**, expand the database in which the procedure belongs, or, from the tool bar, select the database from the list of available databases.</span></span>  
  
3.  <span data-ttu-id="ff430-130">En el menú Archivo, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="ff430-130">On the File menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="ff430-131">Obtenga el nombre del procedimiento almacenado para quitar en la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="ff430-131">Obtain the name of stored procedure to remove in the current database.</span></span> <span data-ttu-id="ff430-132">En el Explorador de objetos, expanda **Programación** y, a continuación, **Procedimientos almacenados**.</span><span class="sxs-lookup"><span data-stu-id="ff430-132">From Object Explorer, expand **Programmability** and then expand **Stored Procedures**.</span></span> <span data-ttu-id="ff430-133">Como alternativa, en el editor de consultas, ejecute la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="ff430-133">Alternatively, in the query editor, run the following statement.</span></span>  
  
    ```sql  
    SELECT name AS procedure_name   
        ,SCHEMA_NAME(schema_id) AS schema_name  
        ,type_desc  
        ,create_date  
        ,modify_date  
    FROM sys.procedures;  
    ```  
  
5.  <span data-ttu-id="ff430-134">Copie y pegue el ejemplo siguiente en el editor de consultas e inserte un procedimiento almacenado para eliminarlo de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="ff430-134">Copy and paste the following example into the query editor and insert a stored procedure name to delete from the current database.</span></span>  
  
    ```sql  
    DROP PROCEDURE <stored procedure name>;  
    GO  
    ```  
  
6.  <span data-ttu-id="ff430-135">Quite las referencias al procedimiento de cualquier objeto y script dependientes.</span><span class="sxs-lookup"><span data-stu-id="ff430-135">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff430-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff430-136">See Also</span></span>  
 <span data-ttu-id="ff430-137">[Crear un procedimiento almacenado](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ff430-137">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="ff430-138">[Modificar un procedimiento almacenado](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ff430-138">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="ff430-139">[Cambiar el nombre de un procedimiento almacenado](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ff430-139">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="ff430-140">[Ver la definición de un procedimiento almacenado](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ff430-140">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="ff430-141">[Ver las dependencias de un procedimiento almacenado](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ff430-141">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="ff430-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ff430-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
