---
title: Habilitar y deshabilitar Grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], disabling
- Availability Groups [SQL Server], enabling
ms.assetid: 7c326958-5ae9-4761-9c57-905972276a8f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 585f1d86d328b7c5027241310108d102b56ca327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663718"
---
# <a name="enable-and-disable-alwayson-availability-groups-sql-server"></a><span data-ttu-id="65a2f-102">Habilitar y deshabilitar grupos de disponibilidad de AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="65a2f-102">Enable and Disable AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="65a2f-103">Habilitar [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] es un requisito previo para que una instancia de servidor use grupos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="65a2f-103">Enabling [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is a prerequisite for a server instance to use availability groups.</span></span> <span data-ttu-id="65a2f-104">Para poder crear y configurar un grupo de disponibilidad, la característica de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] se debe haber habilitado en la cada instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospedará una réplica de disponibilidad para uno o varios grupos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="65a2f-104">Before you can create and configure any availability group, the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature must have been enabled on the each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that will host an availability replica for one or more availability groups.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="65a2f-105">Si elimina y vuelve a crear un clúster de WSFC, debe deshabilitar y volver a habilitar la característica de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en cada instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospedaba una réplica de disponibilidad en el clúster de WSFC original.</span><span class="sxs-lookup"><span data-stu-id="65a2f-105">If you delete and re-create a WSFC cluster, you must disable and re-enable the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature on each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosted an availability replica on the original WSFC cluster.</span></span>  
  
-   <span data-ttu-id="65a2f-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="65a2f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="65a2f-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="65a2f-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="65a2f-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="65a2f-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="65a2f-109">**Cómo:**</span><span class="sxs-lookup"><span data-stu-id="65a2f-109">**How To:**</span></span>  
  
    -   [<span data-ttu-id="65a2f-110">Determinar si los grupos de disponibilidad de AlwaysOn están habilitados</span><span class="sxs-lookup"><span data-stu-id="65a2f-110">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>](#IsEnabled)  
  
    -   [<span data-ttu-id="65a2f-111">Habilitar Grupos de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="65a2f-111">Enable AlwaysOn Availability Groups</span></span>](#EnableAOAG)  
  
    -   [<span data-ttu-id="65a2f-112">Deshabilitar los grupos de disponibilidad de AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="65a2f-112">Disable AlwaysOn Availability Groups</span></span>](#DisableAOAG)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="65a2f-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="65a2f-113">Before You Begin</span></span>  
  
###  <a name="prerequisites-for-enabling-alwayson-availability-groups"></a><a name="Prerequisites"></a><span data-ttu-id="65a2f-114">Requisitos previos para habilitar Grupos de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="65a2f-114">Prerequisites for Enabling AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="65a2f-115">La instancia de servidor debe residir en un nodo de clústeres de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="65a2f-115">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="65a2f-116">La instancia del servidor debe ejecutar una edición de SQL Server que admita [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65a2f-116">The server instance must be running an edition of SQL Server that supports [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="65a2f-117">Para obtener más información, vea [características compatibles con las ediciones de SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-117">For more information, see [Features Supported by the Editions of SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="65a2f-118">Habilite los grupos de disponibilidad de AlwaysOn solo en una instancia del servidor cada vez.</span><span class="sxs-lookup"><span data-stu-id="65a2f-118">Enable AlwaysOn Availability Groups on only one server instance at a time.</span></span> <span data-ttu-id="65a2f-119">Después de habilitar los grupos de disponibilidad de AlwaysOn, espere hasta que se haya reiniciado el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] antes de seguir con otra instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="65a2f-119">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
 <span data-ttu-id="65a2f-120">Para obtener información sobre los requisitos previos adicionales para crear y configurar grupos de disponibilidad, vea [requisitos previos, restricciones y recomendaciones para obtener Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-120">For information about additional prerequisites for creating and configuring availability groups, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="65a2f-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="65a2f-121">Security</span></span>  
 <span data-ttu-id="65a2f-122">Mientras los grupos de disponibilidad de AlwaysOn están habilitados en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], la instancia del servidor tiene control total del clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="65a2f-122">While AlwaysOn Availability Groups is enabled on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server instance has full control on the WSFC cluster.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="65a2f-123">Permisos</span><span class="sxs-lookup"><span data-stu-id="65a2f-123">Permissions</span></span>  
 <span data-ttu-id="65a2f-124">Requiere la pertenencia al grupo **Administrador** en el equipo local y control total del clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="65a2f-124">Requires membership in the **Administrator** group on the local computer and full control on the WSFC cluster.</span></span> <span data-ttu-id="65a2f-125">Cuando habilite AlwaysOn mediante PowerShell, abra la ventana del símbolo del sistema mediante la opción **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="65a2f-125">When enabling AlwaysOn by using PowerShell, open the Command Prompt window using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="65a2f-126">Requiere permisos para crear y administrar objetos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="65a2f-126">Requires Active Directory Create Objects and Manage Objects permissions.</span></span>  
  
##  <a name="determine-whether-alwayson-availability-groups-is-enabled"></a><a name="IsEnabled"></a><span data-ttu-id="65a2f-127">Determinar si Grupos de disponibilidad AlwaysOn está habilitado</span><span class="sxs-lookup"><span data-stu-id="65a2f-127">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>  
  
-   [<span data-ttu-id="65a2f-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65a2f-128">SQL Server Management Studio</span></span>](#SSMS1Procedure)  
  
-   [<span data-ttu-id="65a2f-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65a2f-129">Transact-SQL</span></span>](#Tsql1Procedure)  
  
-   [<span data-ttu-id="65a2f-130">PowerShell</span><span class="sxs-lookup"><span data-stu-id="65a2f-130">PowerShell</span></span>](#PowerShell1Procedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMS1Procedure"></a> <span data-ttu-id="65a2f-131">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="65a2f-131">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="65a2f-132">**Para determinar si los grupos de disponibilidad de AlwaysOn están habilitados**</span><span class="sxs-lookup"><span data-stu-id="65a2f-132">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="65a2f-133">En el Explorador de objetos, haga clic con el botón derecho en la instancia del servidor y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="65a2f-133">In Object Explorer, right-click the server instance, and  click **Properties**.</span></span>  
  
2.  <span data-ttu-id="65a2f-134">En el cuadro de diálogo **Propiedades del servidor** , haga clic en la página **General** .</span><span class="sxs-lookup"><span data-stu-id="65a2f-134">In the **Server Properties** dialog box, click the **General** page.</span></span> <span data-ttu-id="65a2f-135">La propiedad **Habilitado para HADR** muestra uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="65a2f-135">The **Is HADR Enabled** property displays one of the following values:</span></span>  
  
    -   <span data-ttu-id="65a2f-136">**True**si los grupos de disponibilidad de AlwaysOn están habilitados</span><span class="sxs-lookup"><span data-stu-id="65a2f-136">**True**, if AlwaysOn Availability Groups is enabled</span></span>  
  
    -   <span data-ttu-id="65a2f-137">**False**si los grupos de disponibilidad de AlwaysOn están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="65a2f-137">**False**, if AlwaysOn Availability Groups is disabled.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="Tsql1Procedure"></a> <span data-ttu-id="65a2f-138">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="65a2f-138">Using Transact-SQL</span></span>  
 <span data-ttu-id="65a2f-139">**Para determinar si los grupos de disponibilidad de AlwaysOn están habilitados**</span><span class="sxs-lookup"><span data-stu-id="65a2f-139">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="65a2f-140">Use la siguiente instrucción [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="65a2f-140">Use the following [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) statement:</span></span>  
  
    ```sql
    SELECT SERVERPROPERTY ('IsHadrEnabled');  
    ```  
  
     <span data-ttu-id="65a2f-141">El valor de la propiedad del servidor `IsHadrEnabled` indica si una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] está habilitada para los grupos de disponibilidad de AlwaysOn, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="65a2f-141">The setting of the `IsHadrEnabled` server property indicates whether an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is enabled for AlwaysOn Availability Groups, as follows:</span></span>  
  
    -   <span data-ttu-id="65a2f-142">Si `IsHadrEnabled` = 1, los grupos de disponibilidad de AlwaysOn están habilitados.</span><span class="sxs-lookup"><span data-stu-id="65a2f-142">If `IsHadrEnabled` = 1, AlwaysOn Availability Groups is enabled.</span></span>  
  
    -   <span data-ttu-id="65a2f-143">Si `IsHadrEnabled` = 0, los grupos de disponibilidad de AlwaysOn están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="65a2f-143">If `IsHadrEnabled` = 0, AlwaysOn Availability Groups is disabled.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65a2f-144">Para obtener más información acerca de la `IsHadrEnabled` propiedad de servidor, vea [SERVERPROPERTY &#40;TRANSACT-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65a2f-144">For more information about the `IsHadrEnabled` server property, see [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShell1Procedure"></a> <span data-ttu-id="65a2f-145">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="65a2f-145">Using PowerShell</span></span>  
 <span data-ttu-id="65a2f-146">**Para determinar si los grupos de disponibilidad de AlwaysOn están habilitados**</span><span class="sxs-lookup"><span data-stu-id="65a2f-146">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="65a2f-147">Establezca el valor predeterminado ( `cd` ) en la instancia del servidor (por ejemplo, `\SQL\NODE1\DEFAULT` ) en la que desea determinar si [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] está habilitado.</span><span class="sxs-lookup"><span data-stu-id="65a2f-147">Set default (`cd`) to the server instance (e.g. `\SQL\NODE1\DEFAULT`) on which you want to determine whether [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is enabled.</span></span>  
  
2.  <span data-ttu-id="65a2f-148">Escriba el siguiente comando `Get-Item` de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="65a2f-148">Enter the following PowerShell `Get-Item` command:</span></span>  
  
    ```powershell
    Get-Item . | Select IsHadrEnabled  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="65a2f-149">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65a2f-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="65a2f-150">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="65a2f-151">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="65a2f-151">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="65a2f-152">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="65a2f-152">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="enable-alwayson-availability-groups"></a><a name="EnableAOAG"></a> <span data-ttu-id="65a2f-153">Habilitar los grupos de disponibilidad de AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="65a2f-153">Enable AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="65a2f-154">**Para habilitar AlwaysOn, mediante:**</span><span class="sxs-lookup"><span data-stu-id="65a2f-154">**To enable AlwaysOn, using:**</span></span>  
  
-   [<span data-ttu-id="65a2f-155">Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="65a2f-155">SQL Server Configuration Manager</span></span>](#SQLCM2Procedure)  
  
-   [<span data-ttu-id="65a2f-156">PowerShell</span><span class="sxs-lookup"><span data-stu-id="65a2f-156">PowerShell</span></span>](#PScmd2Procedure)  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM2Procedure"></a> <span data-ttu-id="65a2f-157">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="65a2f-157">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="65a2f-158">**Para habilitar los grupos de disponibilidad de AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="65a2f-158">**To enable AlwaysOn Availability Groups**</span></span>  
  
1.  <span data-ttu-id="65a2f-159">Conéctese al nodo de clúster de conmutación por error de Windows Server (WSFC) que hospeda la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] donde desea habilitar los grupos de disponibilidad de AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="65a2f-159">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to enable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="65a2f-160">En el menú **Inicio** , seleccione **Todos los programas**, [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], **Herramientas de configuración**y haga clic en **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="65a2f-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and  click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="65a2f-161">En **Administrador de configuración de SQL Server**, haga clic en **servicios de SQL Server**, haga clic con el botón secundario en SQL Server (\*\* < *`instance name`*>)\*\*, donde **<*`instance name`*>** es el nombre de una instancia del servidor local para la que desea habilitar grupos de disponibilidad AlwaysOn y, a continuación, haga clic en **propiedades.**</span><span class="sxs-lookup"><span data-stu-id="65a2f-161">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to enable AlwaysOn Availability Groups, and click **Properties.**</span></span>  
  
4.  <span data-ttu-id="65a2f-162">Seleccione la pestaña **Alta disponibilidad de AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="65a2f-162">Select the **AlwaysOn High Availability** tab.</span></span>  
  
5.  <span data-ttu-id="65a2f-163">Compruebe que el campo **Nombre del clúster de conmutación por error de Windows** contiene el nombre del clúster de conmutación por error local.</span><span class="sxs-lookup"><span data-stu-id="65a2f-163">Verify that **Windows failover cluster name** field contains the name of the local failover cluster.</span></span> <span data-ttu-id="65a2f-164">Si este campo está en blanco, esta instancia del servidor no admite actualmente [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65a2f-164">If this field is blank, this server instance currently does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="65a2f-165">Puede ser que el equipo local no sea un nodo de clúster, que se haya cerrado el clúster de WSFC o que esta edición de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] que no admita [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65a2f-165">Either the local computer is not a cluster node, the WSFC cluster has been shut down, or this edition of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] that does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span>  
  
6.  <span data-ttu-id="65a2f-166">Active la casilla **habilitar grupos de disponibilidad AlwaysOn** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="65a2f-166">Select the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="65a2f-167">guarda el cambio.</span><span class="sxs-lookup"><span data-stu-id="65a2f-167">Configuration Manager saves your change.</span></span> <span data-ttu-id="65a2f-168">A continuación, debe reiniciarse manualmente el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65a2f-168">Then, you must manually restart the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="65a2f-169">Esto le permite elegir una hora de reinicio que sea la mejor para sus requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="65a2f-169">This enables you to choose a restart time that is best for your business requirements.</span></span> <span data-ttu-id="65a2f-170">Al reiniciar el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], AlwaysOn estará habilitado y la propiedad del servidor `IsHadrEnabled` se establecerá en 1.</span><span class="sxs-lookup"><span data-stu-id="65a2f-170">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be enabled, and the `IsHadrEnabled` server property will be set to 1.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd2Procedure"></a> <span data-ttu-id="65a2f-171">Usar SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="65a2f-171">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="65a2f-172">**Para habilitar AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="65a2f-172">**To enable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="65a2f-173">Cambie el directorio (`cd`) a una instancia del servidor que desee habilitar para los grupos de disponibilidad de AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="65a2f-173">Change directory (`cd`) to a server instance that you want to enable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="65a2f-174">Use el cmdlet `Enable-SqlAlwaysOn` para habilitar los grupos de disponibilidad de AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="65a2f-174">Use the `Enable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="65a2f-175">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65a2f-175">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="65a2f-176">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-176">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65a2f-177">Para obtener información sobre cómo controlar si el `Enable-SqlAlwaysOn` cmdlet reinicia el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] servicio, vea ¿ [Cuándo reinicia un cmdlet el servicio SQL Server?](#WhenCmdletRestartsSQL)más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="65a2f-177">For information about how to control whether the `Enable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
 <span data-ttu-id="65a2f-178">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="65a2f-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="65a2f-179">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="65a2f-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
####  <a name="example-enable-sqlalwayson"></a><a name="ExmplEnable-SqlHadrServic"></a> <span data-ttu-id="65a2f-180">Ejemplo: Enable-SqlAlwaysOn</span><span class="sxs-lookup"><span data-stu-id="65a2f-180">Example: Enable-SqlAlwaysOn</span></span>  
 <span data-ttu-id="65a2f-181">El siguiente comando de PowerShell habilita [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en una instancia de SQL Server (*Computer*\\*Instance*).</span><span class="sxs-lookup"><span data-stu-id="65a2f-181">The following PowerShell command enables [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  
  
```powershell
Enable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
```  
  
##  <a name="disable-alwayson-availability-groups"></a><a name="DisableAOAG"></a><span data-ttu-id="65a2f-182">Deshabilitar Grupos de disponibilidad AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="65a2f-182">Disable AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="65a2f-183">**Antes de deshabilitar AlwaysOn:**</span><span class="sxs-lookup"><span data-stu-id="65a2f-183">**Before you disable AlwaysOn:**</span></span>  
  
     [<span data-ttu-id="65a2f-184">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="65a2f-184">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="65a2f-185">**Para deshabilitar AlwaysOn, mediante:**</span><span class="sxs-lookup"><span data-stu-id="65a2f-185">**To disable AlwaysOn, using:**</span></span>  
  
    -   [<span data-ttu-id="65a2f-186">Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="65a2f-186">SQL Server Configuration Manager</span></span>](#SQLCM3Procedure)  
  
    -   [<span data-ttu-id="65a2f-187">PowerShell</span><span class="sxs-lookup"><span data-stu-id="65a2f-187">PowerShell</span></span>](#PScmd3Procedure)  
  
-   <span data-ttu-id="65a2f-188">**Seguimiento:**  [Después de deshabilitar AlwaysOn](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="65a2f-188">**Follow Up:**  [After Disabling AlwaysOn](#FollowUp)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="65a2f-189">Deshabilite AlwaysOn solamente en una instancia del servidor cada vez.</span><span class="sxs-lookup"><span data-stu-id="65a2f-189">Disable AlwaysOn on only one server instance at a time.</span></span> <span data-ttu-id="65a2f-190">Después de deshabilitar los grupos de disponibilidad de AlwaysOn, espere hasta que se haya reiniciado el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] antes de seguir con otra instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="65a2f-190">After disabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="65a2f-191">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="65a2f-191">Recommendations</span></span>  
 <span data-ttu-id="65a2f-192">Antes de deshabilitar AlwaysOn en una instancia de servidor, se recomienda realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="65a2f-192">Before you disable AlwaysOn on a server instance, we recommend that you do the following:</span></span>  
  
1.  <span data-ttu-id="65a2f-193">Si la instancia de servidor hospeda actualmente la réplica principal de un grupo de disponibilidad que desea conservar, se recomienda realizar una conmutación por error manual del grupo de disponibilidad a una réplica secundaria sincronizada, si es posible.</span><span class="sxs-lookup"><span data-stu-id="65a2f-193">If the server instance is currently hosting the primary replica of an availability group that you want to keep, we recommend that you manually fail over the availability group to a synchronized secondary replica, if possible.</span></span> <span data-ttu-id="65a2f-194">Para obtener más información, vea [Realizar una conmutación por error manual planeada de un grupo de disponibilidad &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-194">For more information, see [Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="65a2f-195">Quite todas las réplicas secundarias locales.</span><span class="sxs-lookup"><span data-stu-id="65a2f-195">Remove all local secondary replicas.</span></span> <span data-ttu-id="65a2f-196">Para obtener más información, vea [Quitar una réplica secundaria de un grupo de disponibilidad &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-196">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM3Procedure"></a> <span data-ttu-id="65a2f-197">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="65a2f-197">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="65a2f-198">**Para deshabilitar AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="65a2f-198">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="65a2f-199">Conéctese al nodo de clúster de conmutación por error de Windows Server (WSFC) que hospeda la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] donde desea deshabilitar los grupos de disponibilidad de AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="65a2f-199">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to disable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="65a2f-200">En el menú **Inicio** , seleccione **Todos los programas**, [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], **Herramientas de configuración**y haga clic en **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="65a2f-200">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="65a2f-201">En **Administrador de configuración de SQL Server**, haga clic en **servicios de SQL Server**, haga clic con el botón secundario en SQL Server (\*\* < *`instance name`*>)\*\*, donde **<*`instance name`*>** es el nombre de una instancia del servidor local para la que desea deshabilitar grupos de disponibilidad AlwaysOn y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="65a2f-201">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to disable AlwaysOn Availability Groups, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="65a2f-202">En la pestaña**Alta disponibilidad de AlwaysOn**, desactive la casilla **Habilitar los grupos de disponibilidad de AlwaysOn** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="65a2f-202">On the**AlwaysOn High Availability**tab, deselect the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="65a2f-203">guarda los cambios y reinicie el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65a2f-203">Configuration Manager saves your change and restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="65a2f-204">Cuando se reinicia el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], AlwaysOn estará deshabilitado y la propiedad del servidor `IsHadrEnabled` se establecerá en 0 para indicar que los grupos de disponibilidad de AlwaysOn están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="65a2f-204">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be disabled, and the `IsHadrEnabled` server property will be set to 0, to indicate that AlwaysOn Availability Groups is disabled.</span></span>  
  
5.  <span data-ttu-id="65a2f-205">Se recomienda leer la información de [Seguimiento: Después de deshabilitar AlwaysOn](#FollowUp), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="65a2f-205">We recommend that you read the information in [Follow Up: After Disabling AlwaysOn](#FollowUp), later in this topic.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd3Procedure"></a> <span data-ttu-id="65a2f-206">Usar SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="65a2f-206">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="65a2f-207">**Para deshabilitar AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="65a2f-207">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="65a2f-208">Cambie el directorio ( `cd` ) a una instancia de servidor habilitada actualmente que desee deshabilitar para grupos de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="65a2f-208">Change directory (`cd`) to a currently-enabled server instance that you want to disenable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="65a2f-209">Use el cmdlet `Disable-SqlAlwaysOn` para habilitar los grupos de disponibilidad de AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="65a2f-209">Use the `Disable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="65a2f-210">Por ejemplo, el comando siguiente deshabilita grupos de disponibilidad AlwaysOn en una instancia de SQL Server (*Computer* \\ *instancia*de equipo).</span><span class="sxs-lookup"><span data-stu-id="65a2f-210">For example, the following command disables AlwaysOn Availability Groups on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  <span data-ttu-id="65a2f-211">Este comando requiere reiniciar la instancia y le pedirá que confirme este reinicio.</span><span class="sxs-lookup"><span data-stu-id="65a2f-211">This command requires restarting the instance, and you will be prompted to confirm this restart.</span></span>  
  
    ```powershell
    Disable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="65a2f-212">Para obtener información sobre cómo controlar si el `Disable-SqlAlwaysOn` cmdlet reinicia el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] servicio, vea ¿ [Cuándo reinicia un cmdlet el servicio SQL Server?](#WhenCmdletRestartsSQL)más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="65a2f-212">For information about how to control whether the `Disable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
     <span data-ttu-id="65a2f-213">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65a2f-213">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="65a2f-214">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-214">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="65a2f-215">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="65a2f-215">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="65a2f-216">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="65a2f-216">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="follow-up-after-disabling-alwayson"></a><a name="FollowUp"></a><span data-ttu-id="65a2f-217">Seguimiento: después de deshabilitar AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="65a2f-217">Follow Up: After Disabling AlwaysOn</span></span>  
 <span data-ttu-id="65a2f-218">Después de deshabilitar grupos de disponibilidad de AlwaysOn, se debe reiniciar la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="65a2f-218">After you disable AlwaysOn Availability Groups, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must be restarted.</span></span> <span data-ttu-id="65a2f-219">El Administrador de configuración de SQL reinicia la instancia de servidor automáticamente.</span><span class="sxs-lookup"><span data-stu-id="65a2f-219">SQL Configuration Manager restarts the server instance automatically.</span></span> <span data-ttu-id="65a2f-220">Sin embargo, si utilizó el cmdlet `Disable-SqlAlwaysOn`, deberá reiniciar la instancia de servidor manualmente.</span><span class="sxs-lookup"><span data-stu-id="65a2f-220">However, if you used the `Disable-SqlAlwaysOn` cmdlet, you will need to restart the server instance manually.</span></span> <span data-ttu-id="65a2f-221">Para más información, consulte [sqlservr Application](../../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-221">For more information, see [sqlservr Application](../../../tools/sqlservr-application.md).</span></span>  
  
 <span data-ttu-id="65a2f-222">En la instancia del servidor reiniciada:</span><span class="sxs-lookup"><span data-stu-id="65a2f-222">On the restarted server instance:</span></span>  
  
-   <span data-ttu-id="65a2f-223">Las bases de datos de disponibilidad no se inician en el arranque de SQL Server, por lo que están inaccesibles.</span><span class="sxs-lookup"><span data-stu-id="65a2f-223">Availability databases do not start up at SQL Server startup, making them inaccessible.</span></span>  
  
-   <span data-ttu-id="65a2f-224">La única instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] compatible con AlwaysOn es [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="65a2f-224">The only supported AlwaysOn [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement is [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span></span> <span data-ttu-id="65a2f-225">Las opciones CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP y SET HADR de ALTER DATABASE no se admiten.</span><span class="sxs-lookup"><span data-stu-id="65a2f-225">CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP, and the SET HADR options of ALTER DATABASE are not supported.</span></span>  
  
-   <span data-ttu-id="65a2f-226">Los metadatos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y los datos de configuración de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] en WSFC no se ven afectados al deshabilitar los grupos de disponibilidad de AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="65a2f-226">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] metadata and [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration data in WSFC are unaffected by disabling AlwaysOn Availability Groups.</span></span>  
  
 <span data-ttu-id="65a2f-227">Si deshabilita de forma permanente grupos de disponibilidad de AlwaysOn en cada instancia de servidor que hospeda una réplica de disponibilidad para uno o varios grupos de disponibilidad, se recomienda completar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="65a2f-227">If you permanently disable AlwaysOn Availability Groups on every server instance that hosts an availability replica for one or more availability groups, we recommend that you complete the following steps:</span></span>  
  
1.  <span data-ttu-id="65a2f-228">Si no quitó las réplicas de disponibilidad locales antes de deshabilitar AlwaysOn, elimine (quite) cada grupo de disponibilidad para el que la instancia de servidor hospeda una réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="65a2f-228">If you did not remove the local availability replicas before disabling AlwaysOn, delete (drop) each availability group for which the server instance is hosting an availability replica.</span></span> <span data-ttu-id="65a2f-229">Para obtener información sobre cómo eliminar un grupo de disponibilidad, vea [Quitar un grupo de disponibilidad &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="65a2f-229">For information about deleting an availability group, see [Remove an Availability Group &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="65a2f-230">Para quitar los metadatos que quedan atrás, elimine (quite) cada grupo de disponibilidad afectado en una instancia de servidor que forme parte del clúster de WSFC original.</span><span class="sxs-lookup"><span data-stu-id="65a2f-230">To remove the metadata left behind, delete (drop) each affected availability group on a server instance that is part of the original WSFC cluster.</span></span>  
  
3.  <span data-ttu-id="65a2f-231">Cualquier base de datos principal continúa estando accesible para todas las conexiones, pero se detiene la sincronización de datos entre las bases de datos primaria y secundaria.</span><span class="sxs-lookup"><span data-stu-id="65a2f-231">Any primary databases continue to be accessible to all connections but the data synchronization between the primary and secondary databases stops.</span></span>  
  
4.  <span data-ttu-id="65a2f-232">Las bases de datos secundarias entran en el estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="65a2f-232">The secondary databases enter the RESTORING state.</span></span> <span data-ttu-id="65a2f-233">Puede eliminarlas o restaurarlas mediante RESTORE WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="65a2f-233">You can delete them, or you can restore them by using RESTORE WITH RECOVERY.</span></span> <span data-ttu-id="65a2f-234">Sin embargo, las bases de datos restauradas ya no participarán en la sincronización de datos del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="65a2f-234">However, restored databases are no longer participating in availability-group data synchronization.</span></span>  
  
##  <a name="when-does-a-cmdlet-restart-the-sql-server-service"></a><a name="WhenCmdletRestartsSQL"></a> <span data-ttu-id="65a2f-235">¿Cuándo reinicia un cmdlet el servicio SQL Server?</span><span class="sxs-lookup"><span data-stu-id="65a2f-235">When Does a Cmdlet Restart the SQL Server Service?</span></span>  
 <span data-ttu-id="65a2f-236">En una instancia del servidor que se esté ejecutando actualmente, el uso de `Enable-SqlAlwaysOn` o `Disable-SqlAlwaysOn` para cambiar el valor actual de AlwaysOn podría provocar que se reinicie el servicio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="65a2f-236">On a server instance that is currently running, using `Enable-SqlAlwaysOn` or `Disable-SqlAlwaysOn` to change the current AlwaysOn setting could cause the SQL Server service to restart.</span></span> <span data-ttu-id="65a2f-237">El comportamiento de reinicio depende de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="65a2f-237">The restart behavior on depends on the following conditions:</span></span>  
  
|<span data-ttu-id="65a2f-238">Parámetro -NoServiceRestart especificado</span><span class="sxs-lookup"><span data-stu-id="65a2f-238">-NoServiceRestart parameter specified</span></span>|<span data-ttu-id="65a2f-239">Parámetro -Force especificado</span><span class="sxs-lookup"><span data-stu-id="65a2f-239">-Force parameter specified</span></span>|<span data-ttu-id="65a2f-240">¿Se ha reiniciado el servicio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ?</span><span class="sxs-lookup"><span data-stu-id="65a2f-240">Is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarted?</span></span>|  
|--------------------------------------------|---------------------------------|---------------------------------------------------------|  
|<span data-ttu-id="65a2f-241">No</span><span class="sxs-lookup"><span data-stu-id="65a2f-241">No</span></span>|<span data-ttu-id="65a2f-242">No</span><span class="sxs-lookup"><span data-stu-id="65a2f-242">No</span></span>|<span data-ttu-id="65a2f-243">De forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="65a2f-243">By default.</span></span> <span data-ttu-id="65a2f-244">Pero el cmdlet indica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="65a2f-244">But the cmdlet prompts you as follows:</span></span><br /><br /> <span data-ttu-id="65a2f-245">**Para completar esta acción, debemos reiniciar el servicio SQL Server para la instancia del servidor '<nombre_instancia>'. ¿Desea continuar?**</span><span class="sxs-lookup"><span data-stu-id="65a2f-245">**To complete this action, we must restart the SQL Server service for server instance '<instance_name>'. Do you want to continue?**</span></span><br /><br /> <span data-ttu-id="65a2f-246">**[Y] Sí  [N] No  [S] Suspender  [?] Ayuda (el valor predeterminado es "Y"):**</span><span class="sxs-lookup"><span data-stu-id="65a2f-246">**[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):**</span></span><br /><br /> <span data-ttu-id="65a2f-247">Si especifica **N** o **S**, el servicio no se reinicia.</span><span class="sxs-lookup"><span data-stu-id="65a2f-247">If you specify **N** or **S**, the service is not restarted.</span></span>|  
|<span data-ttu-id="65a2f-248">No</span><span class="sxs-lookup"><span data-stu-id="65a2f-248">No</span></span>|<span data-ttu-id="65a2f-249">Sí</span><span class="sxs-lookup"><span data-stu-id="65a2f-249">Yes</span></span>|<span data-ttu-id="65a2f-250">El servicio se reinicia.</span><span class="sxs-lookup"><span data-stu-id="65a2f-250">Service is restarted.</span></span>|  
|<span data-ttu-id="65a2f-251">Sí</span><span class="sxs-lookup"><span data-stu-id="65a2f-251">Yes</span></span>|<span data-ttu-id="65a2f-252">No</span><span class="sxs-lookup"><span data-stu-id="65a2f-252">No</span></span>|<span data-ttu-id="65a2f-253">El servicio no se reinicia.</span><span class="sxs-lookup"><span data-stu-id="65a2f-253">Service is not restarted.</span></span>|  
|<span data-ttu-id="65a2f-254">Sí</span><span class="sxs-lookup"><span data-stu-id="65a2f-254">Yes</span></span>|<span data-ttu-id="65a2f-255">Sí</span><span class="sxs-lookup"><span data-stu-id="65a2f-255">Yes</span></span>|<span data-ttu-id="65a2f-256">El servicio no se reinicia.</span><span class="sxs-lookup"><span data-stu-id="65a2f-256">Service is not restarted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65a2f-257">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65a2f-257">See Also</span></span>  
 <span data-ttu-id="65a2f-258">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="65a2f-258">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="65a2f-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="65a2f-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
