---
title: Creación de tablas (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table creation [SQL Server], Visual Database Tools
ms.assetid: 6f7c6ac5-e6d3-4dca-831e-b28442ba535b
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d84a4da6a10fbcbae311fe1bf738c03b85a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678125"
---
# <a name="create-tables-database-engine"></a><span data-ttu-id="99c76-102">Crear tablas (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="99c76-102">Create Tables (Database Engine)</span></span>
  <span data-ttu-id="99c76-103">Puede crear una nueva tabla, asignarle un nombre y agregarla a una base de datos existente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99c76-103">You can create a new table, name it, and add it to an existing database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>

> [!NOTE]
>  <span data-ttu-id="99c76-104">Si está conectado a una base de datos de SQL Azure, la opción de nueva tabla inicia un script de plantilla de creación de tabla.</span><span class="sxs-lookup"><span data-stu-id="99c76-104">If you are connected to a SQL Azure database, the new table option launches a create table template script.</span></span> <span data-ttu-id="99c76-105">Modifique los parámetros y, a continuación, ejecute el script para crear una nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="99c76-105">Edit the parameters, then run the script to create a new table.</span></span> <span data-ttu-id="99c76-106">Para obtener más información, vea [Introducción a SQL Azure](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span><span class="sxs-lookup"><span data-stu-id="99c76-106">For more information, see [SQL Azure Overview](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span></span>

 <span data-ttu-id="99c76-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="99c76-107">**In This Topic**</span></span>

-   <span data-ttu-id="99c76-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="99c76-108">**Before you begin:**</span></span>

     [<span data-ttu-id="99c76-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="99c76-109">Security</span></span>](#Security)

-   <span data-ttu-id="99c76-110">**Para crear una tabla con:**</span><span class="sxs-lookup"><span data-stu-id="99c76-110">**To create a table, using:**</span></span>

     [<span data-ttu-id="99c76-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99c76-111">SQL Server Management Studio</span></span>](#SSMSProcedure)

     [<span data-ttu-id="99c76-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99c76-112">Transact-SQL</span></span>](#TsqlProcedure)

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="99c76-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="99c76-113">Before You Begin</span></span>

###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="99c76-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="99c76-114">Security</span></span>

####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="99c76-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="99c76-115">Permissions</span></span>
 <span data-ttu-id="99c76-116">Se necesita el permiso CREATE TABLE en la base de datos y el permiso ALTER en el esquema en que se crea la tabla.</span><span class="sxs-lookup"><span data-stu-id="99c76-116">Requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>

 <span data-ttu-id="99c76-117">Si alguna columna de la instrucción CREATE TABLE se define como un tipo definido por el usuario de CLR, se necesita la propiedad del tipo o el permiso REFERENCES.</span><span class="sxs-lookup"><span data-stu-id="99c76-117">If any columns in the CREATE TABLE statement are defined as a CLR user-defined type, either ownership of the type or REFERENCES permission on it is required.</span></span>

 <span data-ttu-id="99c76-118">Si las columnas de la instrucción CREATE TABLE tienen asociada una colección de esquemas XML, se necesita la propiedad de la colección de esquemas XML o el permiso REFERENCES.</span><span class="sxs-lookup"><span data-stu-id="99c76-118">If any columns in the CREATE TABLE statement have an XML schema collection associated with them, either ownership of the XML schema collection or REFERENCES permission on it is required.</span></span>

##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="99c76-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99c76-119">Using SQL Server Management Studio</span></span>

#### <a name="to-create-a-table-with-table-designer"></a><span data-ttu-id="99c76-120">Para crear una tabla con el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="99c76-120">To create a table with Table Designer</span></span>

1.  <span data-ttu-id="99c76-121">En el **Explorador de objetos**, conéctese a la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que contiene la base de datos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="99c76-121">In **Object Explorer**, connect to the instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] that contains the database to be modified.</span></span>

2.  <span data-ttu-id="99c76-122">En el **Explorador de objetos**, expanda el nodo **Bases de datos** y, a continuación, expanda la base de datos que contendrá la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="99c76-122">In **Object Explorer**, expand the **Databases** node and then expand the database that will contain the new table.</span></span>

3.  <span data-ttu-id="99c76-123">En el Explorador de objetos, haga clic con el botón derecho en el nodo **Tablas** de la base de datos y, después, haga clic en **Nueva tabla**.</span><span class="sxs-lookup"><span data-stu-id="99c76-123">In Object Explorer, right-click the **Tables** node of your database and then click **New Table**.</span></span>

4.  <span data-ttu-id="99c76-124">Escriba los nombres de columna, elija los tipos de datos y elija si desea permitir valores NULL para cada columna como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="99c76-124">Type column names, choose data types, and choose whether to allow nulls for each column as shown in the following illustration.</span></span>

     <span data-ttu-id="99c76-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span><span class="sxs-lookup"><span data-stu-id="99c76-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span></span>

5.  <span data-ttu-id="99c76-126">Para especificar más propiedades para una columna, como la identidad o valores de columna calculada, haga clic en la columna y después, en la pestaña de propiedades de la columna, elija las propiedades adecuadas.</span><span class="sxs-lookup"><span data-stu-id="99c76-126">To specify more properties for a column, such as identity or computed column values, click the column and in the column properties tab, choose the appropriate properties.</span></span> <span data-ttu-id="99c76-127">Para obtener más información sobre las propiedades de columna, vea [Propiedades de columnas de tablas &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="99c76-127">For more information about column properties, see [Table Column Properties &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span></span>

6.  <span data-ttu-id="99c76-128">Para especificar una columna como clave principal, haga clic con el botón derecho en la columna y seleccione **Establecer clave principal**.</span><span class="sxs-lookup"><span data-stu-id="99c76-128">To specify a column as a primary key, right-click the column and select **Set Primary Key**.</span></span> <span data-ttu-id="99c76-129">Para obtener más información, consulte [Create Primary Keys](../tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="99c76-129">For more information, see [Create Primary Keys](../tables/create-primary-keys.md).</span></span>

7.  <span data-ttu-id="99c76-130">Para crear relaciones de clave externa, restricciones CHECK o índices, haga clic con el botón secundario en el panel Diseñador de tablas y seleccione un objeto de la lista como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="99c76-130">To create foreign key relationships, check constraints, or indexes, right-click in the Table Designer pane and select an object from the list as shown in the following illustration.</span></span>

     <span data-ttu-id="99c76-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span><span class="sxs-lookup"><span data-stu-id="99c76-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span></span>

     <span data-ttu-id="99c76-132">Para obtener más información acerca de estos objetos, vea [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) e [Indexes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="99c76-132">For more information about these objects, see [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) and [Indexes](../indexes/indexes.md).</span></span>

8.  <span data-ttu-id="99c76-133">De forma predeterminada, la tabla está contenida en el esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="99c76-133">By default, the table is contained in the **dbo** schema.</span></span> <span data-ttu-id="99c76-134">Para especificar un esquema diferente para la tabla, haga clic con el botón derecho en el panel Diseñador de tablas y seleccione **Propiedades** como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="99c76-134">To specify a different schema for the table, right-click in the Table Designer pane and select **Properties** as shown in the following illustration.</span></span> <span data-ttu-id="99c76-135">En la lista desplegable **Esquema** , seleccione el esquema adecuado.</span><span class="sxs-lookup"><span data-stu-id="99c76-135">From the **Schema** drop-down list, select the appropriate schema.</span></span>

     <span data-ttu-id="99c76-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span><span class="sxs-lookup"><span data-stu-id="99c76-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span></span>

     <span data-ttu-id="99c76-137">Para obtener más información acerca de los esquemas, vea [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span><span class="sxs-lookup"><span data-stu-id="99c76-137">For more information about schemas, see [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span></span>

9. <span data-ttu-id="99c76-138">En el menú **Archivo**, seleccione **Guardar** *nombre de tabla*.</span><span class="sxs-lookup"><span data-stu-id="99c76-138">From the **File** menu, choose **Save** *table name*.</span></span>

10. <span data-ttu-id="99c76-139">En el cuadro de diálogo **Elegir nombre** , escriba un nombre para la tabla y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="99c76-139">In the **Choose Name** dialog box, type a name for the table and click **OK**.</span></span>

11. <span data-ttu-id="99c76-140">Para ver la nueva tabla, en el **Explorador de objetos**, expanda el nodo **Tablas** y presione **F5** para actualizar la lista de objetos.</span><span class="sxs-lookup"><span data-stu-id="99c76-140">To view the new table, in **Object Explorer**, expand the **Tables** node and press **F5** to refresh the list of objects.</span></span> <span data-ttu-id="99c76-141">La nueva tabla se mostrará en la lista de tablas.</span><span class="sxs-lookup"><span data-stu-id="99c76-141">The new table is displayed in the list of tables.</span></span>

##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="99c76-142">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99c76-142">Using Transact-SQL</span></span>

#### <a name="to-create-a-table-in-the-query-editor"></a><span data-ttu-id="99c76-143">Para crear una tabla en el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="99c76-143">To create a table in the Query Editor</span></span>

1.  <span data-ttu-id="99c76-144">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99c76-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>

2.  <span data-ttu-id="99c76-145">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="99c76-145">On the Standard bar, click **New Query**.</span></span>

3.  <span data-ttu-id="99c76-146">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="99c76-146">Copy and paste the following example into the query window and click **Execute**.</span></span>

    ```
    CREATE TABLE dbo.PurchaseOrderDetail
    (
        PurchaseOrderID int NOT NULL
        ,LineNumber smallint NOT NULL
        ,ProductID int NULL
        ,UnitPrice money NULL
        ,OrderQty smallint NULL
        ,ReceivedQty float NULL
        ,RejectedQty float NULL
        ,DueDate datetime NULL
    );
    ```

 <span data-ttu-id="99c76-147">Para obtener más ejemplos, vea [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="99c76-147">For more examples, see [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>


