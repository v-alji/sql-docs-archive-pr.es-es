---
title: Agregar columnas a una tabla (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- adding columns
ms.assetid: abeb8d52-d562-4e29-9e1e-2923ae874859
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7e9294de10be0df9ef470c75d0934e9f8787b55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672875"
---
# <a name="add-columns-to-a-table-database-engine"></a><span data-ttu-id="de58e-102">Agregar columnas a una tabla (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="de58e-102">Add Columns to a Table (Database Engine)</span></span>
  <span data-ttu-id="de58e-103">En este tema se describe cómo agregar nuevas columnas a una tabla en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de58e-103">This topic describes how to add new columns to a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="de58e-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="de58e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="de58e-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="de58e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="de58e-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="de58e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="de58e-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="de58e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="de58e-108">**Para insertar columnas con:**</span><span class="sxs-lookup"><span data-stu-id="de58e-108">**To insert columns, using:**</span></span>  
  
     [<span data-ttu-id="de58e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de58e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="de58e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de58e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="de58e-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="de58e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="de58e-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="de58e-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="de58e-113">Al usar la instrucción ALTER TABLE para agregar columnas a una tabla, se agregan automáticamente las columnas al final de la tabla.</span><span class="sxs-lookup"><span data-stu-id="de58e-113">Using the ALTER TABLE statement to add columns to a table automatically adds those columns to the end of the table.</span></span> <span data-ttu-id="de58e-114">Si desea que las columnas aparezcan en un orden concreto en la tabla, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de58e-114">If you want the columns in a specific order in the table, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="de58e-115">Sin embargo, tenga en cuenta que esto no es un procedimiento recomendado del diseño de base de datos.</span><span class="sxs-lookup"><span data-stu-id="de58e-115">However, note that this is not a database design best practice.</span></span> <span data-ttu-id="de58e-116">El procedimiento recomendado es especificar el orden en que las columnas se devuelven en el nivel de aplicación y de consulta.</span><span class="sxs-lookup"><span data-stu-id="de58e-116">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="de58e-117">No debe confiar en el uso de SELECT \* para devolver todas las columnas en un orden esperado según el orden en que están definidos en la tabla.</span><span class="sxs-lookup"><span data-stu-id="de58e-117">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="de58e-118">Especifique siempre las columnas por nombre en las consultas y aplicaciones en el orden en que desea que aparezcan.</span><span class="sxs-lookup"><span data-stu-id="de58e-118">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="de58e-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="de58e-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="de58e-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="de58e-120">Permissions</span></span>  
 <span data-ttu-id="de58e-121">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="de58e-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="de58e-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="de58e-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-insert-columns-into-a-table-with-table-designer"></a><span data-ttu-id="de58e-123">Para insertar columnas en una tabla con el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="de58e-123">To insert columns into a table with Table Designer</span></span>  
  
1.  <span data-ttu-id="de58e-124">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla a la que quiera agregar columnas y elija **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="de58e-124">In **Object Explorer**, right-click the table to which you want to add columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="de58e-125">Haga clic en la primera celda vacía de la columna **Nombre de columna** .</span><span class="sxs-lookup"><span data-stu-id="de58e-125">Click in the first blank cell in the **Column Name** column.</span></span>  
  
3.  <span data-ttu-id="de58e-126">Escriba el nombre de columna en la celda.</span><span class="sxs-lookup"><span data-stu-id="de58e-126">Type the column name in the cell.</span></span> <span data-ttu-id="de58e-127">El nombre de la columna es un valor obligatorio.</span><span class="sxs-lookup"><span data-stu-id="de58e-127">The column name is a required value.</span></span>  
  
4.  <span data-ttu-id="de58e-128">Presione la tecla TAB para desplazarse a la celda **Tipo de datos** y seleccione un tipo de datos en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="de58e-128">Press the TAB key to go to the **Data Type** cell and select a data type from the dropdown.</span></span> <span data-ttu-id="de58e-129">Este valor también es obligatorio, por lo que si no elige ninguno, se le asignará un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="de58e-129">This too is a required value, and will be assigned the default value if you don't choose one.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de58e-130"> Puede cambiar el valor predeterminado en el cuadro de diálogo **Opciones** situado bajo **Herramientas para bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="de58e-130">You can change the default value in the **Options** dialog box under **Database Tools**.</span></span>  
  
5.  <span data-ttu-id="de58e-131">Continúe definiendo las propiedades de la columna en la pestaña **Propiedades de columna** .</span><span class="sxs-lookup"><span data-stu-id="de58e-131">Continue to define any other column properties in the **Column Properties** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de58e-132"> Los valores predeterminados de las propiedades de la columna se agregan cuando crea una columna nueva, pero se pueden cambiar en la pestaña **Propiedades de columna** .</span><span class="sxs-lookup"><span data-stu-id="de58e-132">The default values for your column properties are added when you create a new column, but you can change them in the **Column Properties** tab.</span></span>  
  
6.  <span data-ttu-id="de58e-133">Cuando haya terminado de agregar columnas, en el menú **Archivo**, seleccione **Guardar**_nombre de tabla_.</span><span class="sxs-lookup"><span data-stu-id="de58e-133">When you are finished adding columns, from the **File** menu, choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="de58e-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="de58e-134">Using Transact-SQL</span></span>  
  
#### <a name="to-insert-columns-into-a-table"></a><span data-ttu-id="de58e-135">Para insertar columnas en una tabla</span><span class="sxs-lookup"><span data-stu-id="de58e-135">To insert columns into a table</span></span>  
  
1.  <span data-ttu-id="de58e-136">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de58e-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="de58e-137">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="de58e-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="de58e-138">El ejemplo siguiente agrega dos columnas a la tabla `dbo.doc_exa`.</span><span class="sxs-lookup"><span data-stu-id="de58e-138">The following example adds two columns to the table `dbo.doc_exa`.</span></span> <span data-ttu-id="de58e-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="de58e-139">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
```  
ALTER TABLE dbo.doc_exa ADD column_b VARCHAR(20) NULL, column_c INT NULL ;  
```  
  
##  <a name="for-more-information-see-alter-table-40transact-sql41"></a><a name="FollowUp"></a><span data-ttu-id="de58e-140">Para obtener más información, vea [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="de58e-140">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
