---
title: Creación de un esquema de la base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.schemas.general.f1
helpviewer_keywords:
- creating schemas with Management Studio
- CREATE SCHEMA [Management Studio]
- database schemas
- schemas [SQL Server], creating
ms.assetid: ed2a5522-f4d2-4111-95a4-d3e1e5081739
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 3ac0c00768db6501c7d786c35758c1a9d75a5a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745152"
---
# <a name="create-a-database-schema"></a><span data-ttu-id="619e4-102">Crear un esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="619e4-102">Create a Database Schema</span></span>
  <span data-ttu-id="619e4-103">En este tema se describe cómo crear un esquema en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="619e4-103">This topic describes how to create a schema in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="619e4-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="619e4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="619e4-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="619e4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="619e4-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="619e4-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="619e4-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="619e4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="619e4-108">**Para crear un esquema, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="619e4-108">**To create a schema, using:**</span></span>  
  
     [<span data-ttu-id="619e4-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="619e4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="619e4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="619e4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="619e4-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="619e4-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="619e4-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="619e4-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="619e4-113">El esquema nuevo es propiedad de una de las siguientes entidades de seguridad de nivel de base de datos: usuario de base de datos, rol de base de datos o rol de aplicación.</span><span class="sxs-lookup"><span data-stu-id="619e4-113">The new schema is owned by one of the following database-level principals: database user, database role, or application role.</span></span> <span data-ttu-id="619e4-114">Los objetos creados dentro de un esquema son propiedad del esquema y tienen un **principal_id** NULL en **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="619e4-114">Objects created within a schema are owned by the owner of the schema, and have a NULL **principal_id** in **sys.objects**.</span></span> <span data-ttu-id="619e4-115">La propiedad de los objetos incluidos en el esquema puede transferirse a cualquier entidad de seguridad de nivel de base de datos, pero el propietario del esquema siempre mantiene el permiso CONTROL en los objetos del esquema.</span><span class="sxs-lookup"><span data-stu-id="619e4-115">Ownership of schema-contained objects can be transferred to any database-level principal, but the schema owner always retains CONTROL permission on objects within the schema.</span></span>  
  
-   <span data-ttu-id="619e4-116">Cuando se crea un objeto de base de datos, si especifica una entidad de seguridad de dominio válida (usuario o grupo) como la propietaria del objeto, la entidad de seguridad de dominio se agregará a la base de datos como esquema.</span><span class="sxs-lookup"><span data-stu-id="619e4-116">When creating a database object, if you specify a valid domain principal (user or group) as the object owner, the domain principal will be added to the database as a schema.</span></span> <span data-ttu-id="619e4-117">Esa entidad de seguridad de dominio será la propietaria del nuevo esquema.</span><span class="sxs-lookup"><span data-stu-id="619e4-117">The new schema will be owned by that domain principal.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="619e4-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="619e4-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="619e4-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="619e4-119">Permissions</span></span>  
  
-   <span data-ttu-id="619e4-120">Requiere el permiso CREATE SCHEMA en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="619e4-120">Requires CREATE SCHEMA permission on the database.</span></span>  
  
-   <span data-ttu-id="619e4-121">Para especificar otro usuario como el propietario del esquema que se está creando, el autor de la llamada debe tener el permiso IMPERSONATE sobre ese usuario.</span><span class="sxs-lookup"><span data-stu-id="619e4-121">To specify another user as the owner of the schema being created, the caller must have IMPERSONATE permission on that user.</span></span> <span data-ttu-id="619e4-122">Si se especifica un rol de base de datos como propietario, el autor de la llamada debe pertenecer al rol o debe tener el permiso ALTER para el rol.</span><span class="sxs-lookup"><span data-stu-id="619e4-122">If a database role is specified as the owner, the caller must have one of the following: membership in the role or ALTER permission on the role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="619e4-123">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="619e4-123">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-schema"></a><span data-ttu-id="619e4-124">Para crear un esquema</span><span class="sxs-lookup"><span data-stu-id="619e4-124">To create a schema</span></span>  
  
1.  <span data-ttu-id="619e4-125">En el Explorador de objetos, expanda la carpeta **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="619e4-125">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="619e4-126">Expanda la base de datos en la que se va a crear el esquema de la misma.</span><span class="sxs-lookup"><span data-stu-id="619e4-126">Expand the database in which to create the new database schema.</span></span>  
  
3.  <span data-ttu-id="619e4-127">Haga clic con el botón derecho en la carpeta **Seguridad** , seleccione **Nuevo**y seleccione **Esquema**.</span><span class="sxs-lookup"><span data-stu-id="619e4-127">Right-click the **Security** folder, point to **New**, and select **Schema**.</span></span>  
  
4.  <span data-ttu-id="619e4-128">En el cuadro de diálogo **Esquema - Nuevo** , en la página **General** , escriba un nombre para el nuevo esquema en el cuadro **Nombre de esquema** .</span><span class="sxs-lookup"><span data-stu-id="619e4-128">In the **Schema - New** dialog box, on the **General** page, enter a name for the new schema in the **Schema name** box.</span></span>  
  
5.  <span data-ttu-id="619e4-129">En el cuadro **Propietario del esquema** , escriba el nombre del usuario o rol de base de datos que va a poseer el esquema.</span><span class="sxs-lookup"><span data-stu-id="619e4-129">In the **Schema owner** box, enter the name of a database user or role to own the schema.</span></span> <span data-ttu-id="619e4-130">Como alternativa, haga clic en **Buscar** para abrir el cuadro de diálogo **Buscar roles y usuarios** .</span><span class="sxs-lookup"><span data-stu-id="619e4-130">Alternately, click **Search** to open the **Search Roles and Users** dialog box.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="619e4-131">Opciones adicionales</span><span class="sxs-lookup"><span data-stu-id="619e4-131">Additional Options</span></span>  
 <span data-ttu-id="619e4-132">En el cuadro de diálogo **Esquema - Nuevo** también se ofrecen opciones en dos páginas adicionales: **Permisos** y **Propiedades extendidas**.</span><span class="sxs-lookup"><span data-stu-id="619e4-132">The **Schema- New** dialog box also offers options on two additional pages: **Permissions** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="619e4-133">La página **Permisos** muestra todos los elementos protegibles posibles y los permisos en esos elementos protegibles que se pueden conceder al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="619e4-133">The **Permissions** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="619e4-134">La página **Propiedades extendidas** permite agregar propiedades personalizadas a los usuarios de base de datos.</span><span class="sxs-lookup"><span data-stu-id="619e4-134">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="619e4-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="619e4-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schema"></a><span data-ttu-id="619e4-136">Para crear un esquema</span><span class="sxs-lookup"><span data-stu-id="619e4-136">To create a schema</span></span>  
  
1.  <span data-ttu-id="619e4-137">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="619e4-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="619e4-138">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="619e4-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="619e4-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="619e4-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the schema Sprockets owned by Annik that contains table NineProngs.   
    -- The statement grants SELECT to Mandar and denies SELECT to Prasanna.  
  
    CREATE SCHEMA Sprockets AUTHORIZATION Annik  
        CREATE TABLE NineProngs (source int, cost int, partnumber int)  
        GRANT SELECT ON SCHEMA::Sprockets TO Mandar  
        DENY SELECT ON SCHEMA::Sprockets TO Prasanna;  
    GO  
    ```  
  
 <span data-ttu-id="619e4-140">Para obtener más información, vea [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="619e4-140">For more information, see [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span></span>  
  
  
