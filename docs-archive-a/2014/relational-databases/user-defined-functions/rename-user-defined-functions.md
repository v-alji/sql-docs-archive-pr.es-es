---
title: Cambio de nombre de las funciones definidas por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: c2695a5c-9cc5-4b18-8771-53027ca9a9af
author: rothja
ms.author: jroth
ms.openlocfilehash: ec923be64cf7819c4018ebda71a472f58b29cf8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678113"
---
# <a name="rename-user-defined-functions"></a><span data-ttu-id="e9741-102">Cambiar el nombre de las funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="e9741-102">Rename User-defined Functions</span></span>
  <span data-ttu-id="e9741-103">Puede cambiar el nombre de las funciones definidas por el usuario en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9741-103">You can rename user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e9741-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="e9741-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e9741-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="e9741-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e9741-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="e9741-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e9741-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e9741-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e9741-108">**Para cambiar el nombre de las funciones definidas por el usuario, con:**</span><span class="sxs-lookup"><span data-stu-id="e9741-108">**To rename user-defined functions, using:**</span></span>  
  
     [<span data-ttu-id="e9741-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9741-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e9741-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9741-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e9741-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e9741-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e9741-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="e9741-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e9741-113">Los nombres de las funciones deben ajustarse a las reglas de los [identificadores](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="e9741-113">Function names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="e9741-114">Al cambiar el nombre de una función definida por el usuario no se cambiará el nombre del objeto correspondiente en la columna de definición de la vista de catálogo **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="e9741-114">Renaming a user-defined function will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="e9741-115">Por tanto, se recomienda no cambiar este tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="e9741-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="e9741-116">En su lugar, quite el procedimiento almacenado y vuelva a crearlo con su nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="e9741-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="e9741-117">El hecho de cambiar el nombre o la definición de una función definida por el usuario puede provocar errores en los objetos dependientes si no se actualizan con arreglo a los cambios realizados en la función.</span><span class="sxs-lookup"><span data-stu-id="e9741-117">Changing the name or definition of a user-defined function can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the function.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e9741-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e9741-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e9741-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="e9741-119">Permissions</span></span>  
 <span data-ttu-id="e9741-120">Para quitar la función, se requiere el permiso ALTER en el esquema al que pertenece la función o un permiso CONTROL en la función.</span><span class="sxs-lookup"><span data-stu-id="e9741-120">To drop the function, requires either ALTER permission on the schema to which the function belongs or CONTROL permission on the function.</span></span> <span data-ttu-id="e9741-121">Para volver a crear la función, se requiere el permiso CREATE FUNCTION en la base de datos y el permiso ALTER en el esquema en el que se va a crear la función.</span><span class="sxs-lookup"><span data-stu-id="e9741-121">To re-create the function, requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e9741-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e9741-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-user-defined-functions"></a><span data-ttu-id="e9741-123">Para cambiar el nombre de las funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="e9741-123">To rename user-defined functions</span></span>  
  
1.  <span data-ttu-id="e9741-124">En el **Explorador de objetos**, haga clic en el signo más situado junto a la base de datos que contiene la función a la que desea cambiar el nombre y</span><span class="sxs-lookup"><span data-stu-id="e9741-124">In **Object Explorer**, click the plus sign next to the database that contains the function you wish to rename and then</span></span>  
  
2.  <span data-ttu-id="e9741-125">Haga clic en el signo más junto a la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="e9741-125">Click the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="e9741-126">Haga clic en el signo más junto a la carpeta que contenga la función cuyo nombre desea cambiar:</span><span class="sxs-lookup"><span data-stu-id="e9741-126">Click the plus sign next to the folder that contains the function you wish to rename:</span></span>  
  
    -   <span data-ttu-id="e9741-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="e9741-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="e9741-128">Función con valor escalar</span><span class="sxs-lookup"><span data-stu-id="e9741-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="e9741-129">Función de agregado</span><span class="sxs-lookup"><span data-stu-id="e9741-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="e9741-130">Haga clic con el botón derecho en la función cuyo nombre quiere cambiar y seleccione **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="e9741-130">Right-click the function you wish to rename and select **Rename**.</span></span>  
  
5.  <span data-ttu-id="e9741-131">Escriba el nuevo nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="e9741-131">Enter the function's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e9741-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e9741-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="e9741-133">**Para cambiar el nombre de las funciones definidas por el usuario**</span><span class="sxs-lookup"><span data-stu-id="e9741-133">**To rename user-defined functions**</span></span>  
  
 <span data-ttu-id="e9741-134">Esta tarea no se puede realizar mediante instrucciones Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="e9741-134">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="e9741-135">Para cambiar una función definida por el usuario mediante Transact-SQL, debe eliminar la función existente y volver a crearla con el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="e9741-135">To rename a user-defined function using Transact-SQL, you must first delete the existing function and then re-create it with the new name.</span></span> <span data-ttu-id="e9741-136">Asegúrese de que todo el código y las aplicaciones que usaban el nombre antiguo de la función usan el nuevo.</span><span class="sxs-lookup"><span data-stu-id="e9741-136">Ensure that all code and applications that used the function's old name now use the new name.</span></span>  
  
 <span data-ttu-id="e9741-137">Para obtener más información, vea [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) y [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9741-137">For more information, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) and [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9741-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9741-138">See Also</span></span>  
 <span data-ttu-id="e9741-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e9741-139">[sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) </span></span>  
 [<span data-ttu-id="e9741-140">Ver funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="e9741-140">View User-defined Functions</span></span>](user-defined-functions.md)  
  
  
