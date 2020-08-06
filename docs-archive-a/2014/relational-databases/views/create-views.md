---
title: Creación de vistas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], creating
ms.assetid: 0b7bd2a1-544c-42ba-8e7b-4822f34d7b64
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8280f6d65d7252cad423abef849207111492c044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662732"
---
# <a name="create-views"></a><span data-ttu-id="ed0d6-102">Crear vistas</span><span class="sxs-lookup"><span data-stu-id="ed0d6-102">Create Views</span></span>
  <span data-ttu-id="ed0d6-103">Puede crear vistas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed0d6-103">You can create views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ed0d6-104">Se puede usar una vista para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed0d6-104">A view can be used for the following purposes:</span></span>  
  
-   <span data-ttu-id="ed0d6-105">Para centrar, simplificar y personalizar la percepción de la base de datos para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-105">To focus, simplify, and customize the perception each user has of the database.</span></span>  
  
-   <span data-ttu-id="ed0d6-106">Como mecanismo de seguridad, que permite a los usuarios obtener acceso a los datos por medio de la vista, pero no les conceden el permiso de obtener acceso directo a las tablas base subyacentes de la vista.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-106">As a security mechanism by allowing users to access data through the view, without granting the users permissions to directly access the underlying base tables.</span></span>  
  
-   <span data-ttu-id="ed0d6-107">Para proporcionar una interfaz compatible con versiones anteriores para emular una tabla cuyo esquema ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-107">To provide a backward compatible interface to emulate a table whose schema has changed.</span></span>  
  
 <span data-ttu-id="ed0d6-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ed0d6-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ed0d6-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="ed0d6-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ed0d6-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ed0d6-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ed0d6-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ed0d6-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ed0d6-112">**Para crear una vista, use:**</span><span class="sxs-lookup"><span data-stu-id="ed0d6-112">**To create a view, using:**</span></span>  
  
     [<span data-ttu-id="ed0d6-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed0d6-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ed0d6-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ed0d6-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ed0d6-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ed0d6-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ed0d6-116">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ed0d6-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="ed0d6-117">Una vista solo se puede crear en la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-117">A view can be created only in the current database.</span></span>  
  
 <span data-ttu-id="ed0d6-118">Una vista puede tener un máximo de 1.024 columnas.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-118">A view can have a maximum of 1,024 columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ed0d6-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ed0d6-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ed0d6-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="ed0d6-120">Permissions</span></span>  
 <span data-ttu-id="ed0d6-121">Se necesita el permiso CREATE VIEW en la base de datos y el permiso ALTER en el esquema en que se crea la vista.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-121">Requires CREATE VIEW permission in the database and ALTER permission on the schema in which the view is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ed0d6-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed0d6-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-view-by-using-the-query-and-view-designer"></a><span data-ttu-id="ed0d6-123">Para crear una vista mediante el Diseñador de consultas y vistas</span><span class="sxs-lookup"><span data-stu-id="ed0d6-123">To create a view by using the Query and View Designer</span></span>  
  
1.  <span data-ttu-id="ed0d6-124">En el **Explorador de objetos**, expanda la base de datos donde desea crear la nueva vista.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-124">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="ed0d6-125">Haga clic con el botón derecho en la carpeta **Vistas** y después haga clic en **Nueva vista...** .</span><span class="sxs-lookup"><span data-stu-id="ed0d6-125">Right-click the **Views** folder, then click **New View...**.</span></span>  
  
3.  <span data-ttu-id="ed0d6-126">En el cuadro de diálogo **Agregar tabla** , seleccione el elemento o elementos que desea incluir en la nueva vista desde una de las siguientes pestañas: Tablas, Vistas, Funciones y Sinónimos.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-126">In the **Add Table** dialog box, select the element or elements that you want to include in your new view from one of the following tabs: Tables, Views, Functions, and Synonyms.</span></span>  
  
4.  <span data-ttu-id="ed0d6-127">Haga clic en **Agregar**y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-127">Click **Add**, then click **Close**.</span></span>  
  
5.  <span data-ttu-id="ed0d6-128">En el **Panel de diagrama**, seleccione las columnas u otros elementos que desee incluir en la nueva vista.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-128">In the **Diagram Pane**, select the columns or other elements to include in the new view.</span></span>  
  
6.  <span data-ttu-id="ed0d6-129">En el **Panel de criterios**, seleccione criterios de ordenación o filtro adicionales para las columnas.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-129">In the **Criteria Pane**, select additional sort or filter criteria for the columns.</span></span>  
  
7.  <span data-ttu-id="ed0d6-130">En el menú **Archivo** , haga clic en **Guardar**_view name_.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-130">On the **File** menu, click **Save**_view name_.</span></span>  
  
8.  <span data-ttu-id="ed0d6-131">En el cuadro de diálogo **Elegir nombre** , especifique un nombre para la nueva vista y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-131">In the **Choose Name** dialog box, enter a name for the new view and click **OK**.</span></span>  
  
     <span data-ttu-id="ed0d6-132">Para obtener más información sobre el Diseñador de consultas y vistas, vea [Herramientas Diseñador de consultas y vistas &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ed0d6-132">For more information about the query and view designer, see [Query and View Designer Tools &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ed0d6-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ed0d6-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-view"></a><span data-ttu-id="ed0d6-134">Para crear una vista</span><span class="sxs-lookup"><span data-stu-id="ed0d6-134">To create a view</span></span>  
  
1.  <span data-ttu-id="ed0d6-135">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed0d6-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ed0d6-136">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ed0d6-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ed0d6-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
    GO  
    -- Query the view  
    SELECT FirstName, LastName, HireDate  
    FROM HumanResources.EmployeeHireDate  
    ORDER BY LastName;  
  
    ```  
  
 <span data-ttu-id="ed0d6-138">Para obtener más información, vea [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ed0d6-138">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
  
