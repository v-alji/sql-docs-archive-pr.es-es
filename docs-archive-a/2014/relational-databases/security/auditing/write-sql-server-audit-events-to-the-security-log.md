---
title: Escribir eventos de auditoría de SQL Server en el registro de seguridad | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], Security Log
- server audit [SQL Server]
- audits [SQL Server], writing to Security Log
- security logs [SQL Server]
ms.assetid: 6fabeea3-7a42-4769-a0f3-7e04daada314
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d59134b278f29c9b604208d8cab7e982144b9c9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669565"
---
# <a name="write-sql-server-audit-events-to-the-security-log"></a><span data-ttu-id="79682-102">Escribir eventos de auditoría de SQL Server en el registro de seguridad</span><span class="sxs-lookup"><span data-stu-id="79682-102">Write SQL Server Audit Events to the Security Log</span></span>
  <span data-ttu-id="79682-103">En un entorno de alta seguridad, el registro de seguridad de Windows es la ubicación adecuada para escribir los eventos que registran el acceso a los objetos.</span><span class="sxs-lookup"><span data-stu-id="79682-103">In a high security environment, the Windows Security log is the appropriate location to write events that record object access.</span></span> <span data-ttu-id="79682-104">Se admiten otras ubicaciones de auditoría pero están más expuestas a alteraciones.</span><span class="sxs-lookup"><span data-stu-id="79682-104">Other audit locations are supported but are more subject to tampering.</span></span>  
  
 <span data-ttu-id="79682-105">Hay dos requisitos clave para escribir las auditorías del servidor [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en el registro de seguridad de Windows:</span><span class="sxs-lookup"><span data-stu-id="79682-105">There are two key requirements for writing [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] server audits to the Windows Security log:</span></span>  
  
-   <span data-ttu-id="79682-106">El valor Auditar el acceso a objetos se debe configurar para capturar los eventos.</span><span class="sxs-lookup"><span data-stu-id="79682-106">The audit object access setting must be configured to capture the events.</span></span> <span data-ttu-id="79682-107">La herramienta de directiva de auditoría (`auditpol.exe`) expone diversos valores de subdirectivas en la categoría **Auditar el acceso a objetos** .</span><span class="sxs-lookup"><span data-stu-id="79682-107">The audit policy tool (`auditpol.exe`) exposes a variety of sub-policies settings in the **audit object access** category.</span></span> <span data-ttu-id="79682-108">Para permitir que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] audite el acceso a los objetos, configure el valor **Aplicación generada** .</span><span class="sxs-lookup"><span data-stu-id="79682-108">To allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to audit object access, configure the **application generated** setting.</span></span>  
  
-   <span data-ttu-id="79682-109">La cuenta en la que el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se esté ejecutando debe tener el permiso **Generar auditorías de seguridad** para escribir en el registro de seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="79682-109">The account that the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service is running under must have the **generate security audits** permission to write to the Windows Security log.</span></span> <span data-ttu-id="79682-110">De forma predeterminada, las cuentas LOCAL SERVICE y NETWORK SERVICE tienen este permiso.</span><span class="sxs-lookup"><span data-stu-id="79682-110">By default, the LOCAL SERVICE and the NETWORK SERVICE accounts have this permission.</span></span> <span data-ttu-id="79682-111">No se requiere este paso si [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se está ejecutando en alguna de esas cuentas.</span><span class="sxs-lookup"><span data-stu-id="79682-111">This step is not required if [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running under one of those accounts.</span></span>  
  
 <span data-ttu-id="79682-112">La directiva de auditoría de Windows puede afectar a la auditoría de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] si se configura para escribir en el registro de seguridad de Windows, con la posibilidad de perder eventos si la directiva de auditoría se configura incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="79682-112">The Windows audit policy can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auditing if it is configured to write to the Windows Security log, with the potential of losing events if the audit policy is incorrectly configured.</span></span> <span data-ttu-id="79682-113">Por lo general, el registro de seguridad de Windows se establece para sobrescribir los eventos más antiguos.</span><span class="sxs-lookup"><span data-stu-id="79682-113">Typically, the Windows Security log is set to overwrite the older events.</span></span> <span data-ttu-id="79682-114">De esta forma se conservan los eventos más recientes.</span><span class="sxs-lookup"><span data-stu-id="79682-114">This preserves the most recent events.</span></span> <span data-ttu-id="79682-115">Sin embargo, si el registro de seguridad de Windows no se establece para sobrescribir los eventos más antiguos, entonces, si el registro de seguridad se llena, el sistema emitirá el evento 1104 de Windows (el registro está lleno).</span><span class="sxs-lookup"><span data-stu-id="79682-115">However, if the Windows Security log is not set to overwrite older events, then if the Security log is full, the system will issue Windows event 1104 (Log is full).</span></span> <span data-ttu-id="79682-116">En ese punto:</span><span class="sxs-lookup"><span data-stu-id="79682-116">At that point:</span></span>  
  
-   <span data-ttu-id="79682-117">No se registrará ningún evento de seguridad más</span><span class="sxs-lookup"><span data-stu-id="79682-117">No further security events will be recorded</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="79682-118">no podrá detectar que el sistema no puede grabar eventos en el registro de seguridad, lo que provoca la posible pérdida de eventos de auditoría</span><span class="sxs-lookup"><span data-stu-id="79682-118">will not be able to detect that the system is not able to record the events in the Security log, resulting in the potential loss of audit events</span></span>  
  
-   <span data-ttu-id="79682-119">Después de que el administrador corrija el registro de seguridad, el comportamiento de registro volverá a la normalidad.</span><span class="sxs-lookup"><span data-stu-id="79682-119">After the box administrator fixes the Security log, the logging behavior will return to normal.</span></span>  
  
 <span data-ttu-id="79682-120">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="79682-120">**In This Topic**</span></span>  
  
-   <span data-ttu-id="79682-121">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="79682-121">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="79682-122">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="79682-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="79682-123">Seguridad</span><span class="sxs-lookup"><span data-stu-id="79682-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="79682-124">**Para escribir eventos de auditoría de SQL Server en el registro de seguridad:**</span><span class="sxs-lookup"><span data-stu-id="79682-124">**To write SQL Server audit events to the Security Log:**</span></span>  
  
     [<span data-ttu-id="79682-125">Configurar el valor Auditar el acceso a objetos en Windows utilizando auditpol</span><span class="sxs-lookup"><span data-stu-id="79682-125">Configure the audit object access setting in Windows using auditpol</span></span>](#auditpolAccess)  
  
     [<span data-ttu-id="79682-126">Configurar el valor Auditar el acceso a objetos en Windows utilizando secpol</span><span class="sxs-lookup"><span data-stu-id="79682-126">Configure the audit object access setting in Windows using secpol</span></span>](#secpolAccess)  
  
     [<span data-ttu-id="79682-127">Conceder el permiso Generar auditorías de seguridad a una cuenta utilizando secpol</span><span class="sxs-lookup"><span data-stu-id="79682-127">Grant the generate security audits permission to an account using secpol</span></span>](#secpolPermission)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="79682-128">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="79682-128">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="79682-129">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="79682-129">Limitations and Restrictions</span></span>  
 <span data-ttu-id="79682-130">Los administradores del equipo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deberían saber que una directiva de dominio puede sobrescribir la configuración regional del registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="79682-130">Administrators of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer should understand that local settings for the Security log can be overwritten by a domain policy.</span></span> <span data-ttu-id="79682-131">En este caso, la directiva de dominio puede sobrescribir el valor de subcategoría (**auditpol /get /subcategory:"aplicación generada"** ).</span><span class="sxs-lookup"><span data-stu-id="79682-131">In this case, the domain policy might overwrite the subcategory setting (**auditpol /get /subcategory:"application generated"**).</span></span> <span data-ttu-id="79682-132">Esto puede afectar a la capacidad de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de registrar los eventos sin que haya ninguna manera de detectar que los eventos que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] está intentando auditar no van a ser grabados.</span><span class="sxs-lookup"><span data-stu-id="79682-132">This can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ability to log events without having any way to detect that the events that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is trying to audit are not going to be recorded.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="79682-133">Seguridad</span><span class="sxs-lookup"><span data-stu-id="79682-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="79682-134">Permisos</span><span class="sxs-lookup"><span data-stu-id="79682-134">Permissions</span></span>  
 <span data-ttu-id="79682-135">Debe ser administrador de Windows para configurar estos valores.</span><span class="sxs-lookup"><span data-stu-id="79682-135">You must be a Windows administrator to configure these settings.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-auditpol"></a><a name="auditpolAccess"></a> <span data-ttu-id="79682-136">Para configurar el valor Auditar el acceso a objetos en Windows utilizando auditpol</span><span class="sxs-lookup"><span data-stu-id="79682-136">To configure the audit object access setting in Windows using auditpol</span></span>  
  
1.  <span data-ttu-id="79682-137">Abra un símbolo del sistema con permisos administrativos.</span><span class="sxs-lookup"><span data-stu-id="79682-137">Open a command prompt with administrative permissions.</span></span>  
  
    1.  <span data-ttu-id="79682-138">En el menú **Inicio** , seleccione **Todos los programas**, **Accesorios**, haga clic con el botón derecho en **Símbolo del sistema**y, después, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="79682-138">On the **Start** menu, point to **All Programs**, point to **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>  
  
    2.  <span data-ttu-id="79682-139">Si se abre el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="79682-139">If the **User Account Control** dialog box opens, click **Continue**.</span></span>  
  
2.  <span data-ttu-id="79682-140">Ejecute la instrucción siguiente para habilitar la auditoría de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79682-140">Execute the following statement to enable auditing from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
    ```  
    auditpol /set /subcategory:"application generated" /success:enable /failure:enable  
    ```  
  
3.  <span data-ttu-id="79682-141">Cierre la ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="79682-141">Close the command prompt window.</span></span>  
  
##  <a name="to-grant-the-generate-security-audits-permission-to-an-account-using-secpol"></a><a name="secpolAccess"></a> <span data-ttu-id="79682-142">Para conceder el permiso Generar auditorías de seguridad a una cuenta utilizando secpol</span><span class="sxs-lookup"><span data-stu-id="79682-142">To grant the generate security audits permission to an account using secpol</span></span>  
  
1.  <span data-ttu-id="79682-143">En cualquier sistema operativo Windows, en el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="79682-143">For any Windows operating system, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="79682-144">Escriba **secpol.msc** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="79682-144">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="79682-145">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="79682-145">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="79682-146">En la herramienta Directiva de seguridad local, expanda **Configuración de seguridad**, expanda **Directivas locales**y, a continuación, haga clic en **Asignación de derechos de usuario**.</span><span class="sxs-lookup"><span data-stu-id="79682-146">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
4.  <span data-ttu-id="79682-147">En el panel de resultados, haga doble clic en **Generar auditorías de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="79682-147">In the results pane, double-click **Generate security audits**.</span></span>  
  
5.  <span data-ttu-id="79682-148">En la pestaña **Configuración de seguridad local** , haga clic en **Agregar usuario o grupo**.</span><span class="sxs-lookup"><span data-stu-id="79682-148">On the **Local Security Setting** tab, click **Add User or Group**.</span></span>  
  
6.  <span data-ttu-id="79682-149">En el cuadro de diálogo **Seleccionar usuarios, equipos o grupos** , escriba el nombre de la cuenta de usuario, como **domain1\user1** y, después, haga clic en **Aceptar**, o haga clic en **Opciones avanzadas** y busque la cuenta.</span><span class="sxs-lookup"><span data-stu-id="79682-149">In the **Select Users, Computers, or Groups** dialog box, either type the name of the user account, such as **domain1\user1** and then click **OK**, or click **Advanced** and search for the account.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="79682-150">Cierre la herramienta Directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="79682-150">Close the Security Policy tool.</span></span>  
  
9. <span data-ttu-id="79682-151">Reinicie [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para habilitar este valor.</span><span class="sxs-lookup"><span data-stu-id="79682-151">Restart [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to enable this setting.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-secpol"></a><a name="secpolPermission"></a> <span data-ttu-id="79682-152">Para configurar el valor Auditar el acceso a objetos en Windows utilizando secpol</span><span class="sxs-lookup"><span data-stu-id="79682-152">To configure the audit object access setting in Windows using secpol</span></span>  
  
1.  <span data-ttu-id="79682-153">Si el sistema operativo es anterior a [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] o Windows Server 2008, en el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="79682-153">If the operating system is earlier than [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] or Windows Server 2008, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="79682-154">Escriba **secpol.msc** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="79682-154">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="79682-155">Si aparece el cuadro de diálogo **Control de cuentas de usuario** , haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="79682-155">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="79682-156">En la herramienta Directiva de seguridad local, expanda **Configuración de seguridad**, expanda **Directivas locales**y, a continuación, haga clic en **Directiva de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="79682-156">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **Audit Policy**.</span></span>  
  
4.  <span data-ttu-id="79682-157">En el panel de resultados, haga doble clic en **Auditar el acceso a objetos**.</span><span class="sxs-lookup"><span data-stu-id="79682-157">In the results pane, double-click **Audit object access**.</span></span>  
  
5.  <span data-ttu-id="79682-158">En la pestaña **Configuración de seguridad local** , en el área **Auditar estos intentos** , seleccione **Correcto** y **Error**.</span><span class="sxs-lookup"><span data-stu-id="79682-158">On the **Local Security Setting** tab, in the **Audit these attempts** area, select both **Success** and **Failure**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="79682-159">Cierre la herramienta Directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="79682-159">Close the Security Policy tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79682-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79682-160">See Also</span></span>  
 [<span data-ttu-id="79682-161">SQL Server Audit &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="79682-161">SQL Server Audit &#40;Database Engine&#41;</span></span>](sql-server-audit-database-engine.md)  
  
  
