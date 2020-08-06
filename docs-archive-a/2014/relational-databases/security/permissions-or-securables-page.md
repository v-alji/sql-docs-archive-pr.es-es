---
title: Página Permisos o Elementos protegibles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.permissions.f1
- sql12.swb.SecurableAndEffectPermissions.f1
- sql12.swb.availabilitygroupproperties.permission.f1
- sql12.swb.common.columnperm.f1
- sql12.swb.SecurableAndEffectivePermission.f1
ms.assetid: b3bf077a-bec2-4161-ac0c-460586199906
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 80417c720258833850f07eb67f83f5c47f487ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745133"
---
# <a name="permissions-or-securables-page"></a><span data-ttu-id="e2bb7-102">Página Permisos o Elementos protegibles</span><span class="sxs-lookup"><span data-stu-id="e2bb7-102">Permissions or Securables Page</span></span>
  <span data-ttu-id="e2bb7-103">Utilice la página **Permisos** o la página **Elementos protegibles** para ver o establecer los permisos de los elementos protegibles.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-103">Use the **Permissions** page or the **Securables** page to view or set the permissions for securables.</span></span> <span data-ttu-id="e2bb7-104">Esta página se puede abrir desde varias ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-104">This page can be opened from many locations.</span></span> <span data-ttu-id="e2bb7-105">El contenido de la página puede cambiar ligeramente, dependiendo de cómo se abra la página y de su contenido.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-105">The contents of the page can change slightly, depending on how the page is opened and what it contains.</span></span> <span data-ttu-id="e2bb7-106">La cuadrícula superior de la página puede estar rellena al abrir la página, o bien puede estar vacía.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-106">The top grid of the page might be populated when the page opens, or it might be empty.</span></span> <span data-ttu-id="e2bb7-107">Para agregar elementos a la cuadrícula superior, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-107">To add items to the upper grid, click **Search**.</span></span> <span data-ttu-id="e2bb7-108">En la cuadrícula superior, seleccione un elemento y luego establezca los permisos apropiados en la pestaña **Explícito** . Para ver los permisos agregados, use la pestaña **Vigente** .</span><span class="sxs-lookup"><span data-stu-id="e2bb7-108">In the upper grid, select an item, and then set the appropriate permissions on the **Explicit** tab. To view aggregated permissions, use the **Effective** tab.</span></span>  
  
 <span data-ttu-id="e2bb7-109">Para comprender las combinaciones posibles de elementos protegibles y de entidades de seguridad, vea los vínculos de sintaxis específica de los elementos protegibles en el tema [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e2bb7-109">To understand the possible combinations of securables and principals, see the securable-specific syntax links in the topic [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="e2bb7-110">Para más información, consulte [Securables](securables.md).</span><span class="sxs-lookup"><span data-stu-id="e2bb7-110">For more information, see [Securables](securables.md).</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="e2bb7-111">Encabezado de página</span><span class="sxs-lookup"><span data-stu-id="e2bb7-111">Page Header</span></span>  
 <span data-ttu-id="e2bb7-112">El encabezado de la página **Permisos** o **Elementos protegibles** varía en función del elemento protegible o la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-112">The header of the **Permissions** or **Securables** page varies depending on the securable or principal.</span></span> <span data-ttu-id="e2bb7-113">Muestra información correspondiente al elemento, como su nombre.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-113">It displays information relevant to the item, such as its name.</span></span>  
  
## <a name="upper-grid"></a><span data-ttu-id="e2bb7-114">Cuadrícula superior</span><span class="sxs-lookup"><span data-stu-id="e2bb7-114">Upper Grid</span></span>  
 <span data-ttu-id="e2bb7-115">La cuadrícula superior contiene uno o más elementos para los que se pueden establecer permisos.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-115">The upper grid contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="e2bb7-116">Este cuadro de diálogo incluye el botón **Buscar** para seleccionar los objetos o entidades de seguridad que se desean agregar a la cuadrícula superior.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-116">This dialog box provides the **Search** button for selecting objects or principals to add to the upper grid.</span></span> <span data-ttu-id="e2bb7-117">El nombre de la cuadrícula puede mostrar **Elementos protegibles** o uno o varios tipos de elementos protegibles o entidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-117">The name of the grid might display **Securables** or one or more types of securables or principals.</span></span> <span data-ttu-id="e2bb7-118">Las columnas mostradas en la cuadrícula superior varían dependiendo de la entidad de seguridad o el elemento protegible.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-118">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="e2bb7-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-119">**Name**</span></span>  
 <span data-ttu-id="e2bb7-120">El nombre de cada entidad de seguridad o elemento protegible que se agrega a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-120">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="e2bb7-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-121">**Type**</span></span>  
 <span data-ttu-id="e2bb7-122">Describe el tipo de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-122">Describes the type of each item.</span></span>  
  
## <a name="explicit-tab"></a><span data-ttu-id="e2bb7-123">Pestaña Explícito</span><span class="sxs-lookup"><span data-stu-id="e2bb7-123">Explicit Tab</span></span>  
 <span data-ttu-id="e2bb7-124">La pestaña **Explícito** presenta los posibles permisos del elemento protegible seleccionados en la cuadrícula superior.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-124">The **Explicit** tab lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="e2bb7-125">Para configurar los permisos, active o desactive las casillas **Conceder** (o **Permitir**), **WITH GRANT**y **Denegar** .</span><span class="sxs-lookup"><span data-stu-id="e2bb7-125">To configure the permissions, select or clear the **Grant** (or **Allow**), **With Grant**, and **Deny** check boxes.</span></span> <span data-ttu-id="e2bb7-126">No todas las opciones de están disponibles para la totalidad de los permisos explícitos.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-126">All options are not available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="e2bb7-127">**Permisos**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-127">**Permissions**</span></span>  
 <span data-ttu-id="e2bb7-128">Nombre del permiso.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-128">The name of the permission.</span></span>  
  
 <span data-ttu-id="e2bb7-129">**Otorgante de permisos**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-129">**Grantor**</span></span>  
 <span data-ttu-id="e2bb7-130">La entidad de seguridad que concedió el permiso.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-130">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="e2bb7-131">**Conceder**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-131">**Grant**</span></span>  
 <span data-ttu-id="e2bb7-132">Active esta casilla para conceder el permiso al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-132">Select to grant this permission to the login.</span></span> <span data-ttu-id="e2bb7-133">Desactívela para revocar el permiso.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-133">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="e2bb7-134">**WITH GRANT**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-134">**With Grant**</span></span>  
 <span data-ttu-id="e2bb7-135">Refleja el estado de la opción WITH GRANT para el permiso indicado.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-135">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="e2bb7-136">Este cuadro es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-136">This box is read-only.</span></span> <span data-ttu-id="e2bb7-137">Para aplicar este permiso, use la instrucción [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e2bb7-137">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="e2bb7-138">**Deny**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-138">**Deny**</span></span>  
 <span data-ttu-id="e2bb7-139">Active esta casilla para denegar el permiso al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-139">Select to deny this permission to the login.</span></span> <span data-ttu-id="e2bb7-140">Desactívela para revocar el permiso.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-140">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="e2bb7-141">**Permisos de columna**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-141">**Column Permissions**</span></span>  
 <span data-ttu-id="e2bb7-142">Para los objetos que contienen columnas (como tablas, vistas o funciones con valores de tabla), el botón **Permisos de columna** abre el cuadro de diálogo **Permisos de columna** .</span><span class="sxs-lookup"><span data-stu-id="e2bb7-142">For objects that contain columns (such as tables, views, or table-valued functions), the **Column Permissions** button opens the **Column Permissions** dialog box.</span></span> <span data-ttu-id="e2bb7-143">En este cuadro de diálogo, puede establecer las opciones **Conceder**, **Permitir**o **Denegar** para columnas individuales de la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-143">In this dialog box, you can set **Grant**, **Allow**, or **Deny** permissions on individual columns of a table or view.</span></span> <span data-ttu-id="e2bb7-144">Esta opción no está disponible para todos los tipos de objetos o permisos.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-144">This option is not available for all object types or permissions.</span></span>  
  
## <a name="effective-tab"></a><span data-ttu-id="e2bb7-145">Pestaña Vigente</span><span class="sxs-lookup"><span data-stu-id="e2bb7-145">Effective Tab</span></span>  
 <span data-ttu-id="e2bb7-146">Los permisos que una entidad de seguridad ha relacionado con un elemento protegible pueden proceder de permisos establecidos para varias entidades de seguridad distintas.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-146">The permissions that a principal has related to a securable may come from permissions that are set for several different principals.</span></span> <span data-ttu-id="e2bb7-147">Por ejemplo, un inicio de sesión podría recibir permisos de forma individual y también como miembro de un grupo.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-147">For example, a login might be granted permissions individually and also as a member of a group.</span></span> <span data-ttu-id="e2bb7-148">La pestaña **Vigente** muestra el resultado de combinar los permisos explícitos y los permisos recibidos de pertenencia a grupos o roles.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-148">The **Effective** tab shows the result of combining explicit permissions and the permissions that are received from group or role memberships.</span></span> <span data-ttu-id="e2bb7-149">Los permisos Grant están agregados.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-149">Grant permissions are aggregated.</span></span> <span data-ttu-id="e2bb7-150">Un permiso Deny invalida todos los permisos Grant.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-150">A deny permission overrides all grant permissions.</span></span>  
  
 <span data-ttu-id="e2bb7-151">**Permisos**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-151">**Permissions**</span></span>  
 <span data-ttu-id="e2bb7-152">Nombre del permiso.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-152">The name of the permission.</span></span>  
  
 <span data-ttu-id="e2bb7-153">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e2bb7-153">**Column**</span></span>  
 <span data-ttu-id="e2bb7-154">Los nombres de las columnas afectadas por el permiso.</span><span class="sxs-lookup"><span data-stu-id="e2bb7-154">The names of columns that are affected by the permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2bb7-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2bb7-155">See Also</span></span>  
 <span data-ttu-id="e2bb7-156">[Roles de nivel de base de datos](authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="e2bb7-156">[Database-Level Roles](authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="e2bb7-157">Centro de seguridad para el Motor de base de datos de SQL Server y Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="e2bb7-157">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
