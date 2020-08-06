---
title: Realización de operaciones de índice en línea | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index online operations [SQL Server]
- online index operations
- ONLINE option
ms.assetid: 1e43537c-bf67-4db3-9908-3cb45c6fdaa1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d09bd99a0eaec5fdb433bd8c33351d7622957a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677084"
---
# <a name="perform-index-operations-online"></a><span data-ttu-id="1dea9-102">Realizar operaciones de índice en línea</span><span class="sxs-lookup"><span data-stu-id="1dea9-102">Perform Index Operations Online</span></span>
  <span data-ttu-id="1dea9-103">En este tema se describe cómo crear, volver a generar o quitar índices en línea en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1dea9-103">This topic describes how to create, rebuild, or drop indexes online in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1dea9-104">Gracias a la opción ONLINE, es posible que usuarios simultáneos obtengan acceso a los datos de la tabla subyacente o del índice clúster, así como a los índices no clúster asociados durante estas operaciones de índices.</span><span class="sxs-lookup"><span data-stu-id="1dea9-104">The ONLINE option allows concurrent user access to the underlying table or clustered index data and any associated nonclustered indexes during these index operations.</span></span> <span data-ttu-id="1dea9-105">Por ejemplo, cuando un usuario vuelve a generar un índice clúster, dicho usuario y los demás pueden seguir actualizando los datos subyacentes y realizando consultas sobre los mismos.</span><span class="sxs-lookup"><span data-stu-id="1dea9-105">For example, while a clustered index is being rebuilt by one user, that user and others can continue to update and query the underlying data.</span></span> <span data-ttu-id="1dea9-106">Al realizar operaciones DDL (lenguaje de definición de datos) sin conexión, como generar o volver a generar un índice clúster, estas operaciones mantienen bloqueos exclusivos de los datos subyacentes y los índices asociados.</span><span class="sxs-lookup"><span data-stu-id="1dea9-106">When you perform data definition language (DDL) operations offline, such as building or rebuilding a clustered index; these operations hold exclusive locks on the underlying data and associated indexes.</span></span> <span data-ttu-id="1dea9-107">Es un modo de evitar modificaciones de los datos subyacentes y consultas sobre los mismos hasta que no finalice la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="1dea9-107">This prevents modifications and queries to the underlying data until the index operation is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1dea9-108">Las operaciones de índices en línea no están disponibles en todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1dea9-108">Online index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="1dea9-109">Para obtener más información, vea [características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="1dea9-109">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="1dea9-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="1dea9-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1dea9-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="1dea9-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1dea9-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="1dea9-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1dea9-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1dea9-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1dea9-114">**Para volver a generar un índice en línea, usando:**</span><span class="sxs-lookup"><span data-stu-id="1dea9-114">**To rebuild an index online, using:**</span></span>  
  
     [<span data-ttu-id="1dea9-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1dea9-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1dea9-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1dea9-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1dea9-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1dea9-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1dea9-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="1dea9-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1dea9-119">Se recomienda realizar operaciones de índices en línea en entornos empresariales que funcionan 24 horas al día, siete días a la semana, y en los que resulta fundamental la actividad simultánea de los usuarios durante las operaciones de índices.</span><span class="sxs-lookup"><span data-stu-id="1dea9-119">We recommend performing online index operations for business environments that operate 24 hours a day, seven days a week, in which the need for concurrent user activity during index operations is vital.</span></span>  
  
-   <span data-ttu-id="1dea9-120">La opción ONLINE está disponible en las siguientes instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1dea9-120">The ONLINE option is available in the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
    -   [<span data-ttu-id="1dea9-121">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="1dea9-121">CREATE INDEX</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
    -   [<span data-ttu-id="1dea9-122">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="1dea9-122">ALTER INDEX</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    -   [<span data-ttu-id="1dea9-123">DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="1dea9-123">DROP INDEX</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
    -   <span data-ttu-id="1dea9-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (para agregar o quitar restricciones UNIQUE o PRIMARY KEY con la opción de índice CLUSTERED)</span><span class="sxs-lookup"><span data-stu-id="1dea9-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (To add or drop UNIQUE or PRIMARY KEY constraints with CLUSTERED index option)</span></span>  
  
-   <span data-ttu-id="1dea9-125">Para conocer más limitaciones y restricciones relacionadas con la creación, nueva generación o eliminación de índices en línea, vea [Directrices para operaciones de índices en línea](guidelines-for-online-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="1dea9-125">For more limitations and restrictions concerning creating, rebuilding, or dropping indexes online, see [Guidelines for Online Index Operations](guidelines-for-online-index-operations.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1dea9-126">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1dea9-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1dea9-127">Permisos</span><span class="sxs-lookup"><span data-stu-id="1dea9-127">Permissions</span></span>  
 <span data-ttu-id="1dea9-128">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="1dea9-128">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1dea9-129">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1dea9-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rebuild-an-index-online"></a><span data-ttu-id="1dea9-130">Para volver a generar un índice en línea</span><span class="sxs-lookup"><span data-stu-id="1dea9-130">To rebuild an index online</span></span>  
  
1.  <span data-ttu-id="1dea9-131">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea volver a generar un índice en línea.</span><span class="sxs-lookup"><span data-stu-id="1dea9-131">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rebuild an index online.</span></span>  
  
2.  <span data-ttu-id="1dea9-132">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="1dea9-132">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="1dea9-133">Haga clic en el signo más para expandir la tabla en la que desea volver a generar un índice en línea.</span><span class="sxs-lookup"><span data-stu-id="1dea9-133">Click the plus sign to expand the table on which you want to rebuild an index online.</span></span>  
  
4.  <span data-ttu-id="1dea9-134">Expanda la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="1dea9-134">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="1dea9-135">Haga clic con el botón derecho en el índice que quiere volver a generar en línea y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1dea9-135">Right-click the index that you want to rebuild online and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="1dea9-136">Debajo de **Seleccionar una página**, seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="1dea9-136">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="1dea9-137">Seleccione **Permitir procesamiento DML en línea**y, a continuación, seleccione **True** en la lista.</span><span class="sxs-lookup"><span data-stu-id="1dea9-137">Select **Allow online DML processing**, and then select **True** from the list.</span></span>  
  
8.  <span data-ttu-id="1dea9-138">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="1dea9-138">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1dea9-139">Haga clic con el botón derecho en el índice que quiere volver a generar en línea y seleccione **Volver a generar**.</span><span class="sxs-lookup"><span data-stu-id="1dea9-139">Right-click the index that you want to rebuild online and select **Rebuild**.</span></span>  
  
10. <span data-ttu-id="1dea9-140">En el cuadro de diálogo **Volver a generar índices** , compruebe que el índice correcto se encuentra en la cuadrícula **Índices que se volverán a generar** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1dea9-140">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1dea9-141">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1dea9-141">Using Transact-SQL</span></span>  
  
#### <a name="to-create-rebuild-or-drop-an-index-online"></a><span data-ttu-id="1dea9-142">Para crear, volver a generar o quitar un índice en línea</span><span class="sxs-lookup"><span data-stu-id="1dea9-142">To create, rebuild, or drop an index online</span></span>  
  
1.  <span data-ttu-id="1dea9-143">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1dea9-143">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1dea9-144">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1dea9-144">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1dea9-145">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="1dea9-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1dea9-146">En el ejemplo se vuelve a generar un índice en línea existente.</span><span class="sxs-lookup"><span data-stu-id="1dea9-146">The example rebuilds an existing online</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee  
    REBUILD WITH (ONLINE = ON);  
    GO  
    ```  
  
     <span data-ttu-id="1dea9-147">En el ejemplo siguiente se elimina un índice clúster en línea y se mueve la tabla resultante (montón) al grupo de archivos `NewGroup` mediante la cláusula `MOVE TO` .</span><span class="sxs-lookup"><span data-stu-id="1dea9-147">The following example deletes a clustered index online and moves the resulting table (heap) to the filegroup `NewGroup` by using the `MOVE TO` clause.</span></span> <span data-ttu-id="1dea9-148">Las vistas de catálogo `sys.indexes`, `sys.tables`y `sys.filegroups` se consultan para comprobar la ubicación del índice y la tabla en los grupos de archivos antes y después del desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="1dea9-148">The `sys.indexes`, `sys.tables`, and `sys.filegroups` catalog views are queried to verify the index and table placement in the filegroups before and after the move.</span></span>  
  
     [!code-sql[IndexDDL#DropIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/dropindex.sql#dropindex4)]  
  
 <span data-ttu-id="1dea9-149">Para obtener más información, vea [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1dea9-149">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
