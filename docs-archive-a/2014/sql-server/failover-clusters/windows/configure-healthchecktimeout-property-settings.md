---
title: Configurar los valores de la propiedad HealthCheckTimeout | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 3bbeb979-e6fc-4184-ad6e-cca62108de74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a38cd6e9e4718a2f1c136e5412cde340e92f14c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672565"
---
# <a name="configure-healthchecktimeout-property-settings"></a><span data-ttu-id="04906-102">Configurar los valores de la propiedad HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="04906-102">Configure HealthCheckTimeout Property Settings</span></span>
  <span data-ttu-id="04906-103">El valor HealthCheckTimeout se emplea para especificar el tiempo, en milisegundos, que la DLL de recursos de SQL Server debe esperar la información devuelta por el procedimiento almacenado [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) antes de notificar a la instancia de clúster de conmutación por error (FCI) AlwaysOn que no ha recibido respuesta.</span><span class="sxs-lookup"><span data-stu-id="04906-103">The HealthCheckTimeout setting is used to specify the length of time, in milliseconds, that the SQL Server resource DLL should wait for information returned by the [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) stored procedure before reporting the AlwaysOn Failover Cluster Instance (FCI) as unresponsive.</span></span> <span data-ttu-id="04906-104">Los cambios que se realizan en la configuración del tiempo de espera son vigentes de forma inmediata y no requieren reiniciar el recurso de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04906-104">Changes that are made to the timeout settings are effective immediately and do not require a restart of the SQL Server resource.</span></span>  
  
-   <span data-ttu-id="04906-105">**Antes de empezar:**  [Limitaciones y restricciones](#Limits), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="04906-105">**Before you begin:**  [Limitations and Restrictions](#Limits), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="04906-106">**Para configurar el valor de HeathCheckTimeout, mediante:**  [PowerShell](#PowerShellProcedure), [Administrador de clústeres de conmutación por error](#WSFC), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="04906-106">**To Configure the HeathCheckTimeout setting, using:**  [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="04906-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="04906-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limits"></a> <span data-ttu-id="04906-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="04906-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="04906-109">El valor predeterminado para esta propiedad es 60.000 milisegundos (60 segundos).</span><span class="sxs-lookup"><span data-stu-id="04906-109">The default value for this property is 60,000 milliseconds (60 seconds).</span></span> <span data-ttu-id="04906-110">El valor mínimo es 15.000 milisegundos (15 segundos).</span><span class="sxs-lookup"><span data-stu-id="04906-110">The minimum value is 15,000 milliseconds (15 seconds).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="04906-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="04906-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="04906-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="04906-112">Permissions</span></span>  
 <span data-ttu-id="04906-113">Se necesitan los permisos ALTER SETTINGS y VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="04906-113">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="04906-114">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="04906-114">Using PowerShell</span></span>  
  
### <a name="to-configure-healthchecktimeout-settings"></a><span data-ttu-id="04906-115">Para configurar los valores de HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="04906-115">To configure HealthCheckTimeout settings</span></span>  
  
1.  <span data-ttu-id="04906-116">Inicie Windows PowerShell con derechos elevados mediante **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="04906-116">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="04906-117">Importe el módulo `FailoverClusters` para habilitar los cmdlets de clúster.</span><span class="sxs-lookup"><span data-stu-id="04906-117">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="04906-118">Use el `Get-ClusterResource` cmdlet para buscar el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] recurso y, después, use el `Set-ClusterParameter` cmdlet para establecer la propiedad **HealthCheckTimeout** para la instancia de clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="04906-118">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **HealthCheckTimeout** property for the failover cluster instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="04906-119">Cada vez que abre una nueva ventana de PowerShell, necesita importar el módulo `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="04906-119">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="04906-120">En el ejemplo siguiente se cambia el valor de HealthCheckTimeout en el recurso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] "`SQL Server (INST1)`" a 60000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="04906-120">The following example changes the HealthCheckTimeout setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to 60000 milliseconds.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter HealthCheckTimeout 60000  
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="04906-121">Contenido relacionado (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="04906-121">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="04906-122">[Clustering and High-Availability (Clústeres y alta disponibilidad)](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (blog del equipo de Agrupacion de clústeres de conmutación por error y equilibrio de carga de red)</span><span class="sxs-lookup"><span data-stu-id="04906-122">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="04906-123">[Introducción a Windows PowerShell en un clúster de conmutación por error](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="04906-123">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="04906-124">Comandos de recursos de clúster y cmdlets equivalentes de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="04906-124">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="04906-125">Usar el complemento Administrador de clústeres de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="04906-125">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="04906-126">**Para configurar el valor de HealthCheckTimeout**</span><span class="sxs-lookup"><span data-stu-id="04906-126">**To configure HealthCheckTimeout setting**</span></span>  
  
1.  <span data-ttu-id="04906-127">Abra el complemento Administrador de clústeres de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="04906-127">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="04906-128">Expanda **Servicios y aplicaciones** y seleccione la FCI.</span><span class="sxs-lookup"><span data-stu-id="04906-128">Expand **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="04906-129">Haga clic con el botón derecho en el **recurso de SQL Server** en **Otros recursos** y seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="04906-129">Right-click the **SQL Server resource** under **Other Resources** and select **Properties** from the right-click menu.</span></span> <span data-ttu-id="04906-130">Se abrirá el cuadro de diálogo **Propiedades** del recurso de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04906-130">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="04906-131">Seleccione la pestaña **Propiedades** , escriba el valor deseado para la propiedad **HealthCheckTimeout** y, a continuación, haga clic en **Aceptar** para aplicar el cambio.</span><span class="sxs-lookup"><span data-stu-id="04906-131">Select the **Properties** tab, enter the desired value for the **HealthCheckTimeout** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="04906-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="04906-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="04906-133">Con la instrucción [ALTER Server Configuration](/sql/t-sql/statements/alter-server-configuration-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] , puede especificar el valor de la propiedad HealthCheckTimeOut.</span><span class="sxs-lookup"><span data-stu-id="04906-133">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the HealthCheckTimeOut property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="04906-134">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="04906-134">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="04906-135">En el ejemplo siguiente se establece la opción HealthCheckTimeout en 15.000 milisegundos (15 segundos).</span><span class="sxs-lookup"><span data-stu-id="04906-135">The following example sets the HealthCheckTimeout option to 15,000 milliseconds (15 seconds).</span></span>  
  
```sql
ALTER SERVER CONFIGURATION   
SET FAILOVER CLUSTER PROPERTY HealthCheckTimeout = 15000;  
```  
  
## <a name="see-also"></a><span data-ttu-id="04906-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04906-136">See Also</span></span>  
 [<span data-ttu-id="04906-137">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="04906-137">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
