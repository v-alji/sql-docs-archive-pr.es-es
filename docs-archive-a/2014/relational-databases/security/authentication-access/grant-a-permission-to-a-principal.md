---
title: Conceder un permiso a una entidad de seguridad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Grant permission to a principal
ms.assetid: 4107389d-05b6-4aa3-9fa8-95b40cdf05dc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4256d62bdeac2d79c51e5f3792c991e0e3b15096
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750633"
---
# <a name="grant-a-permission-to-a-principal"></a><span data-ttu-id="9a282-102">Conceder un permiso a una entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="9a282-102">Grant a Permission to a Principal</span></span>
  <span data-ttu-id="9a282-103">En este tema se describe cómo conceder permiso a una entidad de seguridad en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a282-103">This topic describes how to grant permission to a principal in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9a282-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9a282-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9a282-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9a282-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9a282-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9a282-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9a282-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9a282-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9a282-108">**Para conceder permiso a una entidad de seguridad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="9a282-108">**To grant permission to a principal, using:**</span></span>  
  
     [<span data-ttu-id="9a282-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a282-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9a282-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a282-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9a282-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9a282-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9a282-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="9a282-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="9a282-113">Tenga en cuenta las siguientes prácticas recomendadas que pueden facilitar la administración de permisos.</span><span class="sxs-lookup"><span data-stu-id="9a282-113">Consider the following best practices that can make managing permissions easier.</span></span>  
  
-   <span data-ttu-id="9a282-114">Conceda permiso a los roles, en lugar de a inicios de sesión o usuarios.</span><span class="sxs-lookup"><span data-stu-id="9a282-114">Grant permission to roles, instead of individual logins or users.</span></span> <span data-ttu-id="9a282-115">Cuando un individuo es reemplazado por otro, quite del rol al individuo que se va y agregue al nuevo.</span><span class="sxs-lookup"><span data-stu-id="9a282-115">When one individual is replaced by another, remove the departing individual from the role and add the new individual to the role.</span></span> <span data-ttu-id="9a282-116">Los permisos que puedan estar asociados al rol estarán disponibles automáticamente para el nuevo individuo.</span><span class="sxs-lookup"><span data-stu-id="9a282-116">The many permissions that might be associated with the role will automatically be available to the new individual.</span></span> <span data-ttu-id="9a282-117">Si varias personas de una organización requieren los mismos permisos, al agregar cada uno de ellos al rol les concederá los mismos permisos.</span><span class="sxs-lookup"><span data-stu-id="9a282-117">If several people in an organization require the same permissions, adding each of them to the role will grant them the same permissions.</span></span>  
  
-   <span data-ttu-id="9a282-118">Configure elementos protegibles similares (tablas, vistas y procedimientos) para que sean propiedad de un esquema y, a continuación, conceda permisos al esquema.</span><span class="sxs-lookup"><span data-stu-id="9a282-118">Configure similar securables (tables, views, and procedures) to be owned by a schema, then grant permissions to the schema.</span></span> <span data-ttu-id="9a282-119">Por ejemplo, el esquema de nóminas puede poseer varias tablas, vistas y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="9a282-119">For example, the payroll schema might own several tables, views, and stored procedures.</span></span> <span data-ttu-id="9a282-120">Al conceder acceso al esquema, todos los permisos necesarios para realizar la función de nómina se pueden conceder al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="9a282-120">By granting access to the schema, all the necessary permissions to perform the payroll function can be granted at the same time.</span></span> <span data-ttu-id="9a282-121">Para obtener más información acerca de a qué elementos protegibles pueden concederse permisos, vea [Securables](../securables.md).</span><span class="sxs-lookup"><span data-stu-id="9a282-121">For more information about what securables can be granted permissions, see [Securables](../securables.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9a282-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9a282-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9a282-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="9a282-123">Permissions</span></span>  
 <span data-ttu-id="9a282-124">El otorgante de permisos (o la entidad de seguridad especificada con la opción AS) debe tener asignado el mismo permiso con GRANT OPTION o un permiso superior que implique el permiso que se va a conceder.</span><span class="sxs-lookup"><span data-stu-id="9a282-124">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="9a282-125">Los miembros del rol fijo de servidor **sysadmin** pueden conceder cualquier permiso.</span><span class="sxs-lookup"><span data-stu-id="9a282-125">Members of the **sysadmin** fixed server role can grant any permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9a282-126">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9a282-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="9a282-127">Para conceder un permiso a una entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="9a282-127">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="9a282-128">En el Explorador de objetos, expanda la base de datos que contiene el objeto al que desea conceder permisos.</span><span class="sxs-lookup"><span data-stu-id="9a282-128">In Object Explorer, expand the database that contains the object to which you want to grant permissions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a282-129">Estos pasos abordan específicamente la concesión de permisos a un procedimiento almacenado, pero puede utilizar pasos similares para agregar permisos a tablas, vistas, funciones y ensamblados, así como a otros elementos protegibles.</span><span class="sxs-lookup"><span data-stu-id="9a282-129">These steps deal specifically with granting permissions to a stored procedure, but you can use similar steps to add permissions to tables, views, functions, and assemblies, as well as other securables.</span></span> <span data-ttu-id="9a282-130">Para obtener más información, vea [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a282-130">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)</span></span>  
  
2.  <span data-ttu-id="9a282-131">Expanda la carpeta **Programación** .</span><span class="sxs-lookup"><span data-stu-id="9a282-131">Expand the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="9a282-132">Expanda la carpeta **Procedimientos almacenados** .</span><span class="sxs-lookup"><span data-stu-id="9a282-132">Expand the **Stored Procedures** folder.</span></span>  
  
4.  <span data-ttu-id="9a282-133">Haga clic con el botón derecho en un procedimiento almacenado y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9a282-133">Right-click a stored procedure and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="9a282-134">En el cuadro de diálogo **propiedades del procedimiento almacenado-**_stored_procedure_name_ , en seleccionar una página, seleccione **permisos**.</span><span class="sxs-lookup"><span data-stu-id="9a282-134">In the **Stored Procedure Properties -**_stored_procedure_name_ dialog box, under select a page, select **Permissions**.</span></span> <span data-ttu-id="9a282-135">Utilice esta página para agregar usuarios o roles al procedimiento almacenado y especificar los permisos que los usuarios o los roles tienen.</span><span class="sxs-lookup"><span data-stu-id="9a282-135">Use this page to add users or roles to the stored procedure and specify the permissions those users or roles have.</span></span>  
  
6.  <span data-ttu-id="9a282-136">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9a282-136">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9a282-137">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a282-137">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permission-to-a-principal"></a><span data-ttu-id="9a282-138">Para conceder un permiso a una entidad de seguridad</span><span class="sxs-lookup"><span data-stu-id="9a282-138">To grant permission to a principal</span></span>  
  
1.  <span data-ttu-id="9a282-139">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a282-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9a282-140">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="9a282-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9a282-141">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9a282-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Grants EXECUTE permission on stored procedure HumanResources.uspUpdateEmployeeHireInfo to an application role called Recruiting11.   
    USE AdventureWorks2012;  
    GO  
    GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
        TO Recruiting11;  
    GO  
    ```  
  
 <span data-ttu-id="9a282-142">Para obtener más información, vea [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) y [GRANT &#40;permisos de objeto de Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a282-142">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a282-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a282-143">See Also</span></span>  
 [<span data-ttu-id="9a282-144">Entidades de seguridad &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="9a282-144">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
