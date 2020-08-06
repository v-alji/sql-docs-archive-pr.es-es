---
title: Creación de un rol de aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.approle.general.f1
helpviewer_keywords:
- application roles [SQL Server], creating
ms.assetid: 6b8da1f5-3d8e-4f88-b111-b915788b06f1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 51272dad57558cdb771f9b98a2f5e5b3da7609cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675777"
---
# <a name="create-an-application-role"></a><span data-ttu-id="687da-102">Crear un rol de aplicación</span><span class="sxs-lookup"><span data-stu-id="687da-102">Create an Application Role</span></span>
  <span data-ttu-id="687da-103">En este tema se describe cómo crear un rol de aplicación en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="687da-103">This topic describes how to create an application role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="687da-104">Los roles de aplicación limitan el acceso de los usuarios a una base de datos excepto a través de aplicaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="687da-104">Application roles restrict user access to a database except through specific applications.</span></span> <span data-ttu-id="687da-105">Los roles de aplicación no tienen usuarios, de modo que no aparece la lista **Miembros del rol** cuando se selecciona **Rol de aplicación** .</span><span class="sxs-lookup"><span data-stu-id="687da-105">Application roles have no users, so the **Role Members** list is not displayed when **Application role** is selected.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="687da-106">Al establecer las contraseñas de los roles de aplicación se comprueba la complejidad de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="687da-106">Password complexity is checked when application role passwords are set.</span></span> <span data-ttu-id="687da-107">Las aplicaciones que invocan roles de aplicación deben almacenar sus propias contraseñas.</span><span class="sxs-lookup"><span data-stu-id="687da-107">Applications that invoke application roles must store their passwords.</span></span> <span data-ttu-id="687da-108">Las contraseñas de roles de aplicación deben almacenarse cifradas.</span><span class="sxs-lookup"><span data-stu-id="687da-108">Application role passwords should always be stored encrypted.</span></span>  
  
 <span data-ttu-id="687da-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="687da-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="687da-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="687da-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="687da-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="687da-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="687da-112">**Para crear un rol de aplicación, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="687da-112">**To create an application role, using:**</span></span>  
  
     [<span data-ttu-id="687da-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="687da-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="687da-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="687da-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="687da-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="687da-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="687da-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="687da-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="687da-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="687da-117">Permissions</span></span>  
 <span data-ttu-id="687da-118">Requiere el permiso ALTER ANY APPLICATION ROLE en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="687da-118">Requires ALTER ANY APPLICATION ROLE permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="687da-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="687da-119">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-an-application-role"></a><span data-ttu-id="687da-120">Para crear un rol de aplicación</span><span class="sxs-lookup"><span data-stu-id="687da-120">To create an application role</span></span>  
  
1.  <span data-ttu-id="687da-121">En el Explorador de objetos, expanda la base de datos donde desea crear un rol de aplicación.</span><span class="sxs-lookup"><span data-stu-id="687da-121">In Object Explorer, expand the database where you want to create an application role.</span></span>  
  
2.  <span data-ttu-id="687da-122">Expanda la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="687da-122">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="687da-123">Expanda la carpeta **Roles** .</span><span class="sxs-lookup"><span data-stu-id="687da-123">Expand the **Roles** folder.</span></span>  
  
4.  <span data-ttu-id="687da-124">Haga clic con el botón derecho en la carpeta **Roles de aplicación** y seleccione **Nuevo rol de aplicación...** .</span><span class="sxs-lookup"><span data-stu-id="687da-124">Right-click the **Application Roles** folder and select **New Application Role...**.</span></span>  
  
5.  <span data-ttu-id="687da-125">En el cuadro de diálogo **Rol de aplicación - Nuevo**, en la página **General**, escriba el nuevo nombre del nuevo rol de aplicación en el cuadro **Nombre de rol**.</span><span class="sxs-lookup"><span data-stu-id="687da-125">In the **Application Role - New** dialog box, on the **General Page**, enter the new name of the new application role in the **Role name** box.</span></span>  
  
6.  <span data-ttu-id="687da-126">En el cuadro **Esquema predeterminado** , determine el esquema al que pertenecerán los objetos creados por este rol especificando los nombres de objeto.</span><span class="sxs-lookup"><span data-stu-id="687da-126">In the **Default Schema** box, specify the schema that will own objects created by this role by entering the object names.</span></span> <span data-ttu-id="687da-127">Como alternativa, haga clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Buscar esquema**.</span><span class="sxs-lookup"><span data-stu-id="687da-127">Alternately, click the ellipsis **(...)** to open the **Locate Schema** dialog box.</span></span>  
  
7.  <span data-ttu-id="687da-128">En el cuadro **Contraseña** , escriba una contraseña para el nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="687da-128">In the **Password** box, enter a password for the new role.</span></span> <span data-ttu-id="687da-129">Vuelva a escribir esa contraseña en el cuadro **Confirmar contraseña** .</span><span class="sxs-lookup"><span data-stu-id="687da-129">Enter that password again into the **Confirm Password** box.</span></span>  
  
8.  <span data-ttu-id="687da-130">En **Esquemas propiedad de este rol**, seleccione o vea los esquemas que pertenecerán a este rol.</span><span class="sxs-lookup"><span data-stu-id="687da-130">Under **Schemas owned by this role**, select or view schemas that will be owned by this role.</span></span> <span data-ttu-id="687da-131">Un esquema solo puede ser propiedad de otro esquema o de un rol.</span><span class="sxs-lookup"><span data-stu-id="687da-131">A schema can be owned by only one schema or role.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="687da-132">Opciones adicionales</span><span class="sxs-lookup"><span data-stu-id="687da-132">Additional Options</span></span>  
 <span data-ttu-id="687da-133">En el cuadro de diálogo **rol de aplicación - Nuevo** también se ofrecen opciones en dos páginas adicionales: **Elementos protegibles** y **Propiedades extendidas**.</span><span class="sxs-lookup"><span data-stu-id="687da-133">The **Application Role - New** dialog box also offers options on two additional pages: **Securables** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="687da-134">La página **Elementos protegibles** muestra todos los elementos protegibles posibles y los permisos en esos elementos protegibles que se pueden conceder al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="687da-134">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="687da-135">La página **Propiedades extendidas** permite agregar propiedades personalizadas a los usuarios de base de datos.</span><span class="sxs-lookup"><span data-stu-id="687da-135">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="687da-136">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="687da-136">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-application-role"></a><span data-ttu-id="687da-137">Para crear un rol de aplicación</span><span class="sxs-lookup"><span data-stu-id="687da-137">To create an application role</span></span>  
  
1.  <span data-ttu-id="687da-138">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="687da-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="687da-139">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="687da-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="687da-140">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="687da-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates an application role called "weekly_receipts" that has the password "987Gbv876sPYY5m23" and "Sales" as its default schema.  
  
    CREATE APPLICATION ROLE weekly_receipts   
        WITH PASSWORD = '987G^bv876sPY)Y5m23'   
        , DEFAULT_SCHEMA = Sales;  
    GO  
    ```  
  
 <span data-ttu-id="687da-141">Para obtener más información, vea [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="687da-141">For more information, see [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span></span>  
  
  
