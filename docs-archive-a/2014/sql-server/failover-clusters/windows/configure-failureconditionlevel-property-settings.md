---
title: Configurar los valores de la propiedad FailureConditionLevel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 513dd179-9a46-46da-9fdd-7632cf6d0816
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8924b864d7cc8be078b370e3182713114f54ff6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672567"
---
# <a name="configure-failureconditionlevel-property-settings"></a><span data-ttu-id="4593f-102">Configurar los valores de la propiedad FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4593f-102">Configure FailureConditionLevel Property Settings</span></span>
  <span data-ttu-id="4593f-103">Utilice la propiedad FailureConditionLevel para establecer las condiciones para que la instancia de clúster de conmutación por error AlwaysOn (FCI) conmute por error o se reinicie.</span><span class="sxs-lookup"><span data-stu-id="4593f-103">Use the FailureConditionLevel property to set the conditions for the AlwaysOn Failover Cluster Instance (FCI) to fail over or restart.</span></span> <span data-ttu-id="4593f-104">Los cambios en esta propiedad se aplican inmediatamente sin tener que reiniciar el servicio de Clúster de conmutación por error de Windows Server (WSFC) o el recurso FCI.</span><span class="sxs-lookup"><span data-stu-id="4593f-104">Changes to this property are applied immediately without requiring a restart of the Windows Server Failover Cluster (WSFC) service or the FCI resource.</span></span>  
  
-   <span data-ttu-id="4593f-105">**Antes de empezar:**  [Valores de propiedad FailureConditionLevel](#Restrictions), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="4593f-105">**Before you begin:**  [FailureConditionLevel Property Settings](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="4593f-106">**Para configurar la propiedad FailureConditionLevel mediante**  [PowerShell](#PowerShellProcedure), [Administrador de clústeres de conmutación por error](#WSFC), [Transact-SQL](#TsqlProcedure).</span><span class="sxs-lookup"><span data-stu-id="4593f-106">**To configure the FailureConditionLevel property settings using,** [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4593f-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4593f-107">Before You Begin</span></span>  
  
###  <a name="failureconditionlevel-property-settings"></a><a name="Restrictions"></a> <span data-ttu-id="4593f-108">Valores de propiedad FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4593f-108">FailureConditionLevel Property Settings</span></span>  
 <span data-ttu-id="4593f-109">Las condiciones de error se establecen en una escala creciente.</span><span class="sxs-lookup"><span data-stu-id="4593f-109">The failure conditions are set on an increasing scale.</span></span> <span data-ttu-id="4593f-110">Para los niveles 1 a 5, cada nivel incluye todas las condiciones de los niveles anteriores además de sus propias condiciones.</span><span class="sxs-lookup"><span data-stu-id="4593f-110">For levels 1-5, each level includes all the conditions from the previous levels in addition to its own conditions.</span></span> <span data-ttu-id="4593f-111">Esto significa que con cada nivel, hay mayor probabilidad de que se produzca una conmutación por error o un reinicio.</span><span class="sxs-lookup"><span data-stu-id="4593f-111">This means that with each level, there is an increased probability of a failover or restart.</span></span>  <span data-ttu-id="4593f-112">Para obtener más información, vea la sección "Determinar los errores" del tema [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) .</span><span class="sxs-lookup"><span data-stu-id="4593f-112">For more information, see the "Determining Failures" section of the [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4593f-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4593f-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4593f-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="4593f-114">Permissions</span></span>  
 <span data-ttu-id="4593f-115">Se necesitan los permisos ALTER SETTINGS y VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="4593f-115">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4593f-116">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="4593f-116">Using PowerShell</span></span>  
  
### <a name="to-configure-failureconditionlevel-settings"></a><span data-ttu-id="4593f-117">Para configurar los valores de FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4593f-117">To configure FailureConditionLevel settings</span></span>  
  
1.  <span data-ttu-id="4593f-118">Inicie Windows PowerShell con derechos elevados mediante **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="4593f-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="4593f-119">Importe el módulo `FailoverClusters` para habilitar los cmdlets de clúster.</span><span class="sxs-lookup"><span data-stu-id="4593f-119">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="4593f-120">Use el `Get-ClusterResource` cmdlet para buscar el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] recurso y, después, use el `Set-ClusterParameter` cmdlet para establecer la propiedad **FailureConditionLevel** para una instancia de clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="4593f-120">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **FailureConditionLevel** property for a Failover Cluster Instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="4593f-121">Cada vez que abre una nueva ventana de PowerShell, necesita importar el módulo `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="4593f-121">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="4593f-122">En el ejemplo siguiente se cambia el valor de FailureConditionLevel en el recurso " [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] " de`SQL Server (INST1)`para la conmutación por error o el reinicio en caso de que se produzcan errores críticos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4593f-122">The following example changes the FailureConditionLevel setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to fail over or restart on critical server errors.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter FailureConditionLevel 3
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="4593f-123">Contenido relacionado (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4593f-123">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="4593f-124">[Clustering and High-Availability (Clústeres y alta disponibilidad)](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (blog del equipo de Agrupacion de clústeres de conmutación por error y equilibrio de carga de red)</span><span class="sxs-lookup"><span data-stu-id="4593f-124">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="4593f-125">[Introducción a Windows PowerShell en un clúster de conmutación por error](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4593f-125">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="4593f-126">Comandos de recursos de clúster y cmdlets equivalentes de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4593f-126">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="4593f-127">Usar el complemento Administrador de clústeres de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="4593f-127">Using the Failover Cluster Manager Snap-in</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="4593f-128">Para configurar los valores de la propiedad FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4593f-128">To configure FailureConditionLevel property settings</span></span>
  
1.  <span data-ttu-id="4593f-129">Abra el complemento Administrador de clústeres de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="4593f-129">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="4593f-130">Expanda **Servicios y aplicaciones** y seleccione la FCI.</span><span class="sxs-lookup"><span data-stu-id="4593f-130">Expand the **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="4593f-131">Haga clic con el botón derecho en el **recurso de SQL Server** en **Otros recursos**y seleccione **Propiedades** en el menú.</span><span class="sxs-lookup"><span data-stu-id="4593f-131">Right-click the **SQL Server resource** under **Other Resources**, and then select **Properties** from the menu.</span></span> <span data-ttu-id="4593f-132">Se abrirá el cuadro de diálogo **Propiedades** del recurso de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4593f-132">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="4593f-133">Seleccione la pestaña **Propiedades** , escriba el valor deseado para la propiedad **FaliureConditionLevel** y, a continuación, haga clic en **Aceptar** para aplicar el cambio.</span><span class="sxs-lookup"><span data-stu-id="4593f-133">Select the **Properties** tab, enter the desired value for the **FaliureConditionLevel** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4593f-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4593f-134">Using Transact-SQL</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="4593f-135">Para configurar los valores de la propiedad FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="4593f-135">To configure FailureConditionLevel property settings</span></span>
  
 <span data-ttu-id="4593f-136">Con la instrucción [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] puede especificar el valor de la propiedad FailureConditionLevel.</span><span class="sxs-lookup"><span data-stu-id="4593f-136">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the FailureConditionLevel property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="4593f-137">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4593f-137">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="4593f-138">En el ejemplo siguiente se establece la propiedad FailureConditionLevel en 0, lo que indica que no se desencadenará automáticamente una conmutación por error o un reinicio si se produce algún error.</span><span class="sxs-lookup"><span data-stu-id="4593f-138">The following example sets the FailureConditionLevel property to 0, indicating that failover or restart will not be triggered automatically on any failure conditions.</span></span>  
  
```sql
ALTER SERVER CONFIGURATION SET FAILOVER CLUSTER PROPERTY FailureConditionLevel = 0;  
```  
  
## <a name="see-also"></a><span data-ttu-id="4593f-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4593f-139">See Also</span></span>  
 <span data-ttu-id="4593f-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4593f-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span></span>  
 [<span data-ttu-id="4593f-141">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="4593f-141">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
