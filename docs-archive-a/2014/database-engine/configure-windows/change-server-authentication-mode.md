---
title: Cambiar el modo de autenticación del servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- sa account
- authentication [SQL Server], changing modes
- server authentication mode [SQL Server]
- modifying server authentication mode
ms.assetid: 79babcf8-19fd-4495-b8eb-453dc575cac0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8bda31ca7d0c5949173a9a3e5ea656c1757c04f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749481"
---
# <a name="change-server-authentication-mode"></a><span data-ttu-id="221b9-102">Cambiar el modo de autenticación del servidor</span><span class="sxs-lookup"><span data-stu-id="221b9-102">Change Server Authentication Mode</span></span>
  <span data-ttu-id="221b9-103">En este tema se describe cómo cambiar el modo de autenticación del servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="221b9-103">This topic describes how to change the server authentication mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="221b9-104">Durante la instalación, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] se establece en **Modo de autenticación de Windows** o **Modo de autenticación de Windows y SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="221b9-104">During installation, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] is set to either **Windows Authentication mode** or **SQL Server and Windows Authentication mode**.</span></span> <span data-ttu-id="221b9-105">Tras la instalación, puede cambiar el modo de autenticación en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="221b9-105">After installation, you can change the authentication mode at any time.</span></span>  
  
 <span data-ttu-id="221b9-106">Si se selecciona **Modo de autenticación de Windows** durante la instalación, el inicio de sesión de sa está deshabilitado y el programa de instalación asigna una contraseña.</span><span class="sxs-lookup"><span data-stu-id="221b9-106">If **Windows Authentication mode** is selected during installation, the sa login is disabled and a password is assigned by setup.</span></span> <span data-ttu-id="221b9-107">Si posteriormente se cambia al **Modo de autenticación de Windows y SQL Server**, el inicio de sesión de sa permanece deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="221b9-107">If you later change authentication mode to **SQL Server and Windows Authentication mode**, the sa login remains disabled.</span></span> <span data-ttu-id="221b9-108">Para usar el inicio de sesión de sa, use la instrucción ALTER LOGIN para habilitar el inicio de sesión de sa y asignar una nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="221b9-108">To use the sa login, use the ALTER LOGIN statement to enable the sa login and assign a new password.</span></span> <span data-ttu-id="221b9-109">El inicio de sesión de sa solo se puede conectar al servidor mediante la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="221b9-109">The sa login can only connect to the server by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="221b9-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="221b9-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="221b9-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="221b9-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="221b9-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="221b9-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="221b9-113">**Para cambiar el modo de autenticación del servidor, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="221b9-113">**To change server authentication mode, using:**</span></span>  
  
     [<span data-ttu-id="221b9-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="221b9-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="221b9-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="221b9-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="221b9-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="221b9-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="221b9-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="221b9-117">Security</span></span>  
 <span data-ttu-id="221b9-118">La cuenta sa es una cuenta conocida de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y suele ser el objetivo de los usuarios malintencionados.</span><span class="sxs-lookup"><span data-stu-id="221b9-118">The sa account is a well-known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account and it is often targeted by malicious users.</span></span> <span data-ttu-id="221b9-119">No habilite la cuenta sa a menos que su aplicación lo requiera.</span><span class="sxs-lookup"><span data-stu-id="221b9-119">Do not enable the sa account unless your application requires it.</span></span> <span data-ttu-id="221b9-120">Es muy importante que utilice una contraseña segura para el inicio de sesión de sa.</span><span class="sxs-lookup"><span data-stu-id="221b9-120">It is very important that you use a strong password for the sa login.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="221b9-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="221b9-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-security-authentication-mode"></a><span data-ttu-id="221b9-122">Para cambiar el modo de autenticación de seguridad</span><span class="sxs-lookup"><span data-stu-id="221b9-122">To change security authentication mode</span></span>  
  
1.  <span data-ttu-id="221b9-123">En el Explorador de objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , haga clic con el botón derecho en el servidor y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="221b9-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, right-click the server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="221b9-124">En la página **Seguridad** , bajo **Autenticación de servidor**, seleccione el nuevo modo de autenticación del servidor y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="221b9-124">On the **Security** page, under **Server authentication**, select the new server authentication mode, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="221b9-125">En el cuadro de diálogo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , haga clic en **Aceptar** para confirmar el requisito de reiniciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="221b9-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialog box, click **OK** to acknowledge the requirement to restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="221b9-126">En el Explorador de objetos, haga clic con el botón derecho en el servidor y, después, haga clic en **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="221b9-126">In Object Explorer, right-click your server, and then click **Restart**.</span></span> <span data-ttu-id="221b9-127">Si el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se está ejecutando, también debe reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="221b9-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running, it must also be restarted.</span></span>  
  
#### <a name="to-enable-the-sa-login"></a><span data-ttu-id="221b9-128">Para habilitar el inicio de sesión sa</span><span class="sxs-lookup"><span data-stu-id="221b9-128">To enable the sa login</span></span>  
  
1.  <span data-ttu-id="221b9-129">En Explorador de objetos, expanda **seguridad**, inicios de sesión, haga clic con el botón secundario `sa` y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="221b9-129">In Object Explorer, expand **Security**, expand Logins, right-click `sa`, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="221b9-130">En la página **General** , quizás tenga que crear y confirmar una contraseña para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="221b9-130">On the **General** page, you might have to create and confirm a password for the  login.</span></span>  
  
3.  <span data-ttu-id="221b9-131">En la página **Estado** , en la sección **Inicio de sesión** , haga clic en **Habilitado**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="221b9-131">On the **Status** page, in the **Login** section, click **Enabled**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="221b9-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="221b9-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="221b9-133">**Para habilitar el inicio de sesión sa**</span><span class="sxs-lookup"><span data-stu-id="221b9-133">**To enable the sa login**</span></span>  
  
1.  <span data-ttu-id="221b9-134">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="221b9-134">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="221b9-135">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="221b9-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="221b9-136">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="221b9-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="221b9-137">En el ejemplo siguiente se habilita el inicio de sesión de sa y se establece una nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="221b9-137">The following example enables the sa login and sets a new password.</span></span>  
  
    ```  
    ALTER LOGIN sa ENABLE ;  
    GO  
    ALTER LOGIN sa WITH PASSWORD = '<enterStrongPasswordHere>' ;  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="221b9-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="221b9-138">See Also</span></span>  
 <span data-ttu-id="221b9-139">[Contraseñas seguras](../../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="221b9-139">[Strong Passwords](../../relational-databases/security/strong-passwords.md) </span></span>  
 <span data-ttu-id="221b9-140">[Consideraciones de seguridad para una instalación de SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="221b9-140">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="221b9-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="221b9-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 [<span data-ttu-id="221b9-142">Conectarse a SQL Server cuando los administradores del sistema no tienen acceso</span><span class="sxs-lookup"><span data-stu-id="221b9-142">Connect to SQL Server When System Administrators Are Locked Out</span></span>](connect-to-sql-server-when-system-administrators-are-locked-out.md)  
  
  
