---
title: Creación de un inicio de sesión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating a login
ms.assetid: a2512310-bdb6-41dc-858a-e866b2b58afc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 400a57693fbea10270a51f5735a19b9639112ce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748448"
---
# <a name="creating-a-login"></a><span data-ttu-id="570bc-102">Crear un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="570bc-102">Creating a Login</span></span>
  <span data-ttu-id="570bc-103">Para tener acceso a [!INCLUDE[ssDE](../includes/ssde-md.md)], los usuarios necesitan un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="570bc-103">To access the [!INCLUDE[ssDE](../includes/ssde-md.md)], users require a login.</span></span> <span data-ttu-id="570bc-104">El inicio de sesión puede representar la identidad del usuario como una cuenta de Windows o como un miembro de un grupo de Windows, o el inicio de sesión puede ser un inicio de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que solo exista en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="570bc-104">The login can represent the user's identity as a Windows account or as a member of a Windows group, or the login can be a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login that exists only in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="570bc-105">Siempre que sea posible, use la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="570bc-105">Whenever possible you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="570bc-106">De forma predeterminada, los administradores del equipo tienen acceso total a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="570bc-106">By default, administrators on your computer have full access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="570bc-107">Para esta lección, deseamos tener un usuario con menos privilegios; por tanto, creará una nueva cuenta de autenticación de Windows local en el equipo.</span><span class="sxs-lookup"><span data-stu-id="570bc-107">For this lesson, we want to have a less privileged user; therefore, you will create a new local Windows Authentication account on your computer.</span></span> <span data-ttu-id="570bc-108">Para hacerlo, debe ser un administrador del equipo.</span><span class="sxs-lookup"><span data-stu-id="570bc-108">To do this, you must be an administrator on your computer.</span></span> <span data-ttu-id="570bc-109">A continuación, concederá al nuevo usuario acceso a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="570bc-109">Then you will grant that new user access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-create-a-new-windows-account"></a><span data-ttu-id="570bc-110">Para crear una cuenta de Windows nueva</span><span class="sxs-lookup"><span data-stu-id="570bc-110">To create a new Windows account</span></span>  
  
1.  <span data-ttu-id="570bc-111">Haga clic en **Inicio**, haga clic en **Ejecutar**, en el cuadro **abrir** , escriba `%SystemRoot%\system32\compmgmt.msc /s` y, a continuación, haga clic en **Aceptar** para abrir el programa administración de equipos.</span><span class="sxs-lookup"><span data-stu-id="570bc-111">Click **Start**, click **Run**, in the **Open** box, type `%SystemRoot%\system32\compmgmt.msc /s`, and then click **OK** to open the Computer Management program.</span></span>  
  
2.  <span data-ttu-id="570bc-112">En **Herramientas del sistema**, expanda **Usuarios y grupos locales**, haga clic con el botón derecho en **Usuarios**y luego haga clic en **Nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="570bc-112">Under **System Tools**, expand **Local Users and Groups**, right-click **Users**, and then click **New User**.</span></span>  
  
3.  <span data-ttu-id="570bc-113">En el cuadro **Nombre de usuario** , escriba **Mary**.</span><span class="sxs-lookup"><span data-stu-id="570bc-113">In the **User name** box type **Mary**.</span></span>  
  
4.  <span data-ttu-id="570bc-114">En los cuadros **Contraseña** y **Confirmar contraseña** , escriba una contraseña segura y, a continuación, haga clic en **Crear** para crear un nuevo usuario de Windows local.</span><span class="sxs-lookup"><span data-stu-id="570bc-114">In the **Password** and **Confirm password** box, type a strong password, and then click **Create** to create a new local Windows user.</span></span>  
  
### <a name="to-create-a-login"></a><span data-ttu-id="570bc-115">Para crear un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="570bc-115">To create a login</span></span>  
  
1.  <span data-ttu-id="570bc-116">En una ventana del Editor de consultas de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], escriba y ejecute el siguiente código reemplazando `computer_name` con el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="570bc-116">In a Query Editor window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], type and execute the following code replacing `computer_name` with the name of your computer.</span></span> <span data-ttu-id="570bc-117">`FROM WINDOWS` indica que Windows autenticará al usuario.</span><span class="sxs-lookup"><span data-stu-id="570bc-117">`FROM WINDOWS` indicates that Windows will authenticate the user.</span></span> <span data-ttu-id="570bc-118">El argumento opcional `DEFAULT_DATABASE` conecta `Mary` con la base de datos `TestData` , a menos que la cadena de conexión indique otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="570bc-118">The optional `DEFAULT_DATABASE` argument connects `Mary` to the `TestData` database, unless her connection string indicates another database.</span></span> <span data-ttu-id="570bc-119">Esta instrucción introduce el punto y coma como una terminación opcional de una instrucción [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="570bc-119">This statement introduces the semicolon as an optional termination for a [!INCLUDE[tsql](../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    CREATE LOGIN [computer_name\Mary]  
        FROM WINDOWS  
        WITH DEFAULT_DATABASE = [TestData];  
    GO  
    ```  
  
     <span data-ttu-id="570bc-120">Esto autoriza al nombre de usuario `Mary`, autenticado por el equipo, a tener acceso a esta instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="570bc-120">This authorizes a user name `Mary`, authenticated by your computer, to access this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="570bc-121">Si existe más de una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en el equipo, debe crear el inicio de sesión en cada instancia a la que `Mary` deba tener acceso.</span><span class="sxs-lookup"><span data-stu-id="570bc-121">If there is more than one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the computer, you must create the login on each instance that `Mary` must access.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="570bc-122">Puesto que `Mary` no es una cuenta de dominio, este nombre de usuario solo puede autenticarse en este equipo.</span><span class="sxs-lookup"><span data-stu-id="570bc-122">Because `Mary` is not a domain account, this user name can only be authenticated on this computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="570bc-123">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="570bc-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="570bc-124">Conceder acceso a una base de datos</span><span class="sxs-lookup"><span data-stu-id="570bc-124">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="570bc-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="570bc-125">See Also</span></span>  
 <span data-ttu-id="570bc-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="570bc-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 [<span data-ttu-id="570bc-127">Elegir un modo de autenticación</span><span class="sxs-lookup"><span data-stu-id="570bc-127">Choose an Authentication Mode</span></span>](../relational-databases/security/choose-an-authentication-mode.md)  
  
  
