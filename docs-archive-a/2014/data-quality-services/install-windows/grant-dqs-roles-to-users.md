---
title: Conceder roles de DQS a los usuarios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: afb445b5-bdbe-4bfe-844f-344766cdc2b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 62ff5eb03fa46279ee1b8a1329c58bd69361ef82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748260"
---
# <a name="grant-dqs-roles-to-users"></a><span data-ttu-id="2c1f0-102">Conceder roles de DQS a los usuarios</span><span class="sxs-lookup"><span data-stu-id="2c1f0-102">Grant DQS Roles to Users</span></span>
  <span data-ttu-id="2c1f0-103">En este tema se describe cómo crear los inicios de sesión de SQL según una entidad de seguridad de Windows y cómo conceder roles de [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) en la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-103">This topic describes how to create SQL logins based on a Windows principal, and grant [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2c1f0-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2c1f0-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="2c1f0-105">Debe haber completado la instalación del [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] ejecutando el archivo DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-105">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="2c1f0-106">Para obtener más información, vea [Ejecutar DQSInstaller.exe para completar la instalación del servidor de calidad de datos](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="2c1f0-106">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="2c1f0-107">La cuenta de usuario de Windows debe ser miembro del rol fijo de servidor adecuado (como securityadmin, serveradmin o sysadmin) para crear el inicio de sesión de SQL y concederle los roles de DQS.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant them DQS roles.</span></span>  
  
### <a name="to-create-sql-login-and-grant-dqs-roles"></a><span data-ttu-id="2c1f0-108">Para crear un inicio de sesión de SQL y conceder los roles de DQS</span><span class="sxs-lookup"><span data-stu-id="2c1f0-108">To create SQL login and grant DQS roles</span></span>  
  
1.  <span data-ttu-id="2c1f0-109">Inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c1f0-109">Start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="2c1f0-110">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda la instancia de SQL Server y, a continuación expanda **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="2c1f0-111">Haga clic con el botón derecho en la carpeta **Seguridad** , seleccione **Nuevo**y, después, haga clic en **Inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="2c1f0-112">En el cuadro de diálogo **Inicio de sesión-nuevo** , especifique el nombre de un usuario de Windows en el cuadro **nombre de inicio de sesión** , especifique el tipo de autenticación como autenticación de **Windows**y haga clic en **Buscar** para validar el usuario.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
5.  <span data-ttu-id="2c1f0-113">Después de validar el usuario, haga clic en la página **Asignación de usuarios** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-113">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="2c1f0-114">En el panel derecho, active la casilla en la columna **Asignar** para la base de datos **DQS_MAIN** y, después, active la casilla **dqs_administrator**, **dqs_kb_editor**o **dqs_kb_operator** en el panel **Pertenencia al rol de base de datos para: DQS_MAIN** , dependiendo del nivel de acceso necesario para el usuario.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-114">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span> <span data-ttu-id="2c1f0-115">Para obtener más información acerca de los tres roles de DQS, vea [Seguridad DQS](../dqs-security.md).</span><span class="sxs-lookup"><span data-stu-id="2c1f0-115">For information about the three DQS roles, see [DQS Security](../dqs-security.md).</span></span>  
  
7.  <span data-ttu-id="2c1f0-116">En el cuadro de diálogo **Inicio de sesión - Nuevo**, haga clic en **Aceptar** para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2c1f0-117">Si concede el rol **dqs_administrator** a un usuario, aplica los cambios y, tras ello, vuelve a revisar los permisos de usuario, las otras dos casillas de roles de DQS (**dq_kb_editor** y **dqs_kb_operator**) también se activan.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2c1f0-118">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2c1f0-118">Next Steps</span></span>  
 <span data-ttu-id="2c1f0-119">Intente iniciar sesión en el [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] con la cuenta de usuario de Windows para la que ha creado un inicio de sesión de SQL y a la que ha concedido un rol de DQS.</span><span class="sxs-lookup"><span data-stu-id="2c1f0-119">Try logging on to [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] by using the Windows user account for which you just created a SQL login, and granted a DQS role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1f0-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c1f0-120">See Also</span></span>  
 <span data-ttu-id="2c1f0-121">[Instalar Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="2c1f0-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="2c1f0-122">Crear un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="2c1f0-122">Create a Login</span></span>](../../relational-databases/security/authentication-access/create-a-login.md)  
  
  
