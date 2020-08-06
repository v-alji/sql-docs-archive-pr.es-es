---
title: Crear una credencial | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- credentials [SQL Server], creating
- authentication [SQL Server], credentials
- logins [SQL Server], credentials
ms.assetid: c1e77e91-2a69-40d9-b8b3-97cffc710586
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23221424699449ac3775b0e805bb02ae0ad233f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745154"
---
# <a name="create-a-credential"></a><span data-ttu-id="b2772-102">Create a Credential</span><span class="sxs-lookup"><span data-stu-id="b2772-102">Create a Credential</span></span>
  <span data-ttu-id="b2772-103">En este tema se describe cómo crear una credencial en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2772-103">This topic describes how to create a credential in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b2772-104">Las credenciales proporcionan un método para permitir que los usuarios de la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dispongan de una identidad fuera de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2772-104">Credentials provide a way to allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication users to have an identity outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b2772-105">Se utilizan principalmente para ejecutar código en ensamblados con el conjunto de permisos EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="b2772-105">This is primarily used to execute code in Assemblies with EXTERNAL_ACCESS permission set.</span></span> <span data-ttu-id="b2772-106">También se pueden utilizar cuando un usuario de la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] necesita obtener acceso a un recurso de dominio, como una ubicación de archivo para almacenar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b2772-106">Credentials can also be used when a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication user needs access to a domain resource, such as a file location to store a backup.</span></span>  
  
 <span data-ttu-id="b2772-107">Una credencial se puede asignar a varios inicios de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a la vez.</span><span class="sxs-lookup"><span data-stu-id="b2772-107">A credential can be mapped to several [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins at the same time.</span></span> <span data-ttu-id="b2772-108">Un inicio de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] solo se puede asignar a una credencial a la vez.</span><span class="sxs-lookup"><span data-stu-id="b2772-108">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can only be mapped to one credential at a time.</span></span> <span data-ttu-id="b2772-109">Después de crear la credencial, use **Propiedades de inicio de sesión (página General)** para asignar un inicio de sesión a una credencial.</span><span class="sxs-lookup"><span data-stu-id="b2772-109">After a credential is created, use the **Login Properties (General Page)** to map a login to a credential.</span></span>  
  
 <span data-ttu-id="b2772-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="b2772-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b2772-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="b2772-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b2772-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b2772-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b2772-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b2772-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b2772-114">**Para crear una credencial, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="b2772-114">**To create a credential, using:**</span></span>  
  
     [<span data-ttu-id="b2772-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2772-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b2772-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2772-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b2772-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b2772-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b2772-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b2772-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b2772-119">Si no hay ninguna credencial de inicio de sesión asignada para el proveedor, se utiliza la credencial asignada a la cuenta de servicio de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2772-119">If there is no login mapped credential for the provider, the credential mapped to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account is used.</span></span>  
  
-   <span data-ttu-id="b2772-120">Un inicio de sesión puede tener asignadas varias credenciales, siempre y cuando se utilicen con proveedores distintos.</span><span class="sxs-lookup"><span data-stu-id="b2772-120">A login can have multiple credentials mapped to it as long as they are used with distinctive providers.</span></span> <span data-ttu-id="b2772-121">Solo debe haber una credencial asignada por cada proveedor y por cada inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b2772-121">There must be only one mapped credential per provider per login.</span></span> <span data-ttu-id="b2772-122">La misma credencial puede estar asignada a otros inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="b2772-122">The same credential can be mapped to other logins.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b2772-123">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b2772-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b2772-124">Permisos</span><span class="sxs-lookup"><span data-stu-id="b2772-124">Permissions</span></span>  
 <span data-ttu-id="b2772-125">Requiere el permiso ALTER ANY CREDENTIAL para crear o modificar una credencial y el permiso ALTER ANY LOGIN para asignar un inicio de sesión a una credencial.</span><span class="sxs-lookup"><span data-stu-id="b2772-125">Requires ALTER ANY CREDENTIAL permission to create or modify a credential and ALTER ANY LOGIN permission to map a login to a credential.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b2772-126">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2772-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-credential"></a><span data-ttu-id="b2772-127">Para crear una credencial</span><span class="sxs-lookup"><span data-stu-id="b2772-127">To create a credential</span></span>  
  
1.  <span data-ttu-id="b2772-128">En el Explorador de objetos, expanda la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="b2772-128">In Object Explorer, expand  the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="b2772-129">Haga clic con el botón derecho en la carpeta **Credenciales** y seleccione **Nueva credencial...** .</span><span class="sxs-lookup"><span data-stu-id="b2772-129">Right-click the **Credentials** folder and select **New Credential...**.</span></span>  
  
3.  <span data-ttu-id="b2772-130">En el cuadro de diálogo **Nueva credencial** , en el cuadro **Nombre de credencial** , escriba un nombre para la credencial.</span><span class="sxs-lookup"><span data-stu-id="b2772-130">In the **New Credential** dialog box, in the **Credential Name** box, type a name for the credential.</span></span>  
  
4.  <span data-ttu-id="b2772-131">En el cuadro **Identidad** , escriba el nombre de la cuenta empleada en las conexiones salientes (cuando salga del contexto de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b2772-131">In the **Identity** box, type the name of the account used for outgoing connections (when leaving the context of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="b2772-132">Normalmente, será una cuenta de usuario de Windows, pero la identidad puede ser una cuenta de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="b2772-132">Typically, this will be a Windows user account, but the identity can be an account of another type.</span></span>  
  
     <span data-ttu-id="b2772-133">También puede hacer clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Seleccionar usuarios o grupos**.</span><span class="sxs-lookup"><span data-stu-id="b2772-133">Alternately, click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
5.  <span data-ttu-id="b2772-134">En los cuadros **Contraseña** y **Confirmar contraseña** , escriba la contraseña de la cuenta especificada en el cuadro **Identidad** .</span><span class="sxs-lookup"><span data-stu-id="b2772-134">In the **Password** and **Confirm password** boxes, type the password of the account specified in the **Identity** box.</span></span> <span data-ttu-id="b2772-135">Si se ha especificado una cuenta de usuario de Windows en **Identidad** , ésta será la contraseña de Windows.</span><span class="sxs-lookup"><span data-stu-id="b2772-135">If **Identity** is a Windows user account, this is the Windows password.</span></span> <span data-ttu-id="b2772-136">Se puede dejar **Contraseña** en blanco si no se requiere ninguna.</span><span class="sxs-lookup"><span data-stu-id="b2772-136">The **Password** can be blank, if no password is required.</span></span>  
  
6.  <span data-ttu-id="b2772-137">Seleccione **Usar proveedor de cifrado** para establecer la credencial que debe ser comprobada por un proveedor de Administración extensible de claves (EKM).</span><span class="sxs-lookup"><span data-stu-id="b2772-137">Select **Use Encryption Provider** to set the credential to be verified by an Extensible Key Management (EKM) Provider.</span></span> <span data-ttu-id="b2772-138">Para obtener más información, vea [Administración extensible de claves &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md)</span><span class="sxs-lookup"><span data-stu-id="b2772-138">For more information, see [Extensible Key Management &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b2772-139">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2772-139">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-credential"></a><a name="Credential"></a><span data-ttu-id="b2772-140">Para crear una credencial</span><span class="sxs-lookup"><span data-stu-id="b2772-140">To create a credential</span></span>  
  
1.  <span data-ttu-id="b2772-141">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2772-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b2772-142">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="b2772-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b2772-143">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b2772-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the credential called "AlterEgo.".   
    -- The credential contains the Windows user "Mary5" and a password.  
    CREATE CREDENTIAL AlterEgo WITH IDENTITY = 'Mary5',   
        SECRET = '<EnterStrongPasswordHere>';  
    GO  
    ```  
  
 <span data-ttu-id="b2772-144">Para obtener más información, vea [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2772-144">For more information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
  
