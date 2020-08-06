---
title: Administrar usuarios de DQS en SSMS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 955af01d-00da-4c51-9311-f3848749df54
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bf8789abb59d168f39562f6486bb5c54bfc0fc50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676669"
---
# <a name="manage-dqs-users-in-ssms"></a><span data-ttu-id="0d6fd-102">Administrar usuarios de DQS en SSMS</span><span class="sxs-lookup"><span data-stu-id="0d6fd-102">Manage DQS Users in SSMS</span></span>
  <span data-ttu-id="0d6fd-103">En este tema se describe cómo crear usuarios adicionales en la instancia de SQL Server con SQL Server Management Studio y cómo concederles roles de [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) adecuados en la base de datos DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-103">This topic describes how to create additional users in the SQL Server instance using SQL Server Management Studio, and grant them appropriate [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) roles on the DQS_MAIN database.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0d6fd-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="0d6fd-104">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0d6fd-105">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0d6fd-105">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0d6fd-106">Permisos</span><span class="sxs-lookup"><span data-stu-id="0d6fd-106">Permissions</span></span>  
 <span data-ttu-id="0d6fd-107">Para crear el inicio de sesión de SQL y concederle los roles de DQS adecuados, debe usarse una cuenta de usuario de Windows que sea miembro del rol fijo de servidor adecuado (como securityadmin, serveradmin o sysadmin).</span><span class="sxs-lookup"><span data-stu-id="0d6fd-107">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) to create SQL login, and grant appropriate DQS roles.</span></span>  
  
##  <a name="create-a-sql-login-and-grant-dqs-role"></a><a name="GrantRoles"></a><span data-ttu-id="0d6fd-108">Crear un inicio de sesión de SQL y conceder el rol de DQS</span><span class="sxs-lookup"><span data-stu-id="0d6fd-108">Create a SQL Login and Grant DQS Role</span></span>  
  
1.  <span data-ttu-id="0d6fd-109">Inicie Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-109">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="0d6fd-110">En Microsoft SQL Server Management Studio, expanda la instancia de SQL Server y, a continuación, expanda **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-110">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and then expand **Security**.</span></span>  
  
3.  <span data-ttu-id="0d6fd-111">Haga clic con el botón derecho en la carpeta **Seguridad** , seleccione **Nuevo**y, después, haga clic en **Inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-111">Right-click the **Security** folder, point to **New**, and then click **Login**.</span></span>  
  
4.  <span data-ttu-id="0d6fd-112">En el cuadro de diálogo **Inicio de sesión-nuevo** , especifique el nombre de un usuario de Windows en el cuadro **nombre de inicio de sesión** , especifique el tipo de autenticación como autenticación de **Windows**y haga clic en **Buscar** para validar el usuario.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-112">In the **Login - New** dialog box, specify the name of a Windows user in the **Login name** box, specify the type of authentication as **Windows authentication**, and click **Search** to validate the user.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d6fd-113">DQS solo admite la autenticación de Windows; la autenticación de SQL Server no se admite.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-113">DQS only supports Windows authentication; SQL Server authentication is not supported.</span></span>  
  
5.  <span data-ttu-id="0d6fd-114">Después de validar el usuario, haga clic en la página **Asignación de usuarios** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-114">After the user is validated, click the **User Mapping** page in the left pane.</span></span>  
  
6.  <span data-ttu-id="0d6fd-115">En el panel derecho, active la casilla en la columna **Asignar** para la base de datos **DQS_MAIN** y, después, active la casilla **dqs_administrator**, **dqs_kb_editor**o **dqs_kb_operator** en el panel **Pertenencia al rol de base de datos para: DQS_MAIN** , dependiendo del nivel de acceso necesario para el usuario.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-115">In the right pane, select the check box under the **Map** column for the **DQS_MAIN** database, and then select the **dqs_administrator**, **dqs_kb_editor**, or **dqs_kb_operator** check box in the **Database role membership for: DQS_MAIN** pane, depending on the access level needed for the user.</span></span>  
  
7.  <span data-ttu-id="0d6fd-116">En el cuadro de diálogo **Inicio de sesión - Nuevo**, haga clic en **Aceptar** para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-116">In the **Login - New** dialog box, click **OK** to apply the changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d6fd-117">Si concede el rol **dqs_administrator** a un usuario, aplica los cambios y, tras ello, vuelve a revisar los permisos de usuario, las otras dos casillas de roles de DQS (**dq_kb_editor** y **dqs_kb_operator**) también se activan.</span><span class="sxs-lookup"><span data-stu-id="0d6fd-117">If you grant the **dqs_administrator** role to a user, apply the changes, and then recheck the user permissions, the other two DQS roles check boxes (**dq_kb_editor** and **dqs_kb_operator**) are also selected.</span></span>  
  
  
