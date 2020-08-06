---
title: Usar PowerShell para cambiar y enumerar Reporting Services propietarios de suscripciones y ejecutar una suscripción | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0fa6cb36-68fc-4fb8-b1dc-ae4f12bf6ff0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b274dc190d8830a2cf7b55110f15267a00c581e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673461"
---
# <a name="use-powershell-to-change-and-list-reporting-services-subscription-owners-and-run-a-subscription"></a><span data-ttu-id="9934b-102">Use PowerShell para cambiar y enumerar a los propietarios de una suscripción de Reporting Services y ejecutar una suscripción</span><span class="sxs-lookup"><span data-stu-id="9934b-102">Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription</span></span>
  <span data-ttu-id="9934b-103">A partir de [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] , se puede transferir mediante programación la propiedad de una suscripción a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] de un usuario a otro.</span><span class="sxs-lookup"><span data-stu-id="9934b-103">Starting with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] you can programmatically transfer the ownership of a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription from one user to another.</span></span> <span data-ttu-id="9934b-104">En este tema se proporcionan varios scripts de Windows PowerShell que puede utilizar para cambiar o simplemente presentar la propiedad de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="9934b-104">This topic provides several Windows PowerShell scripts you can use to change or simply list subscription ownership.</span></span> <span data-ttu-id="9934b-105">Cada ejemplo incluye sintaxis de ejemplo para el modo nativo y para el modo SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9934b-105">Each sample includes sample syntax for both Native mode and SharePoint mode.</span></span> <span data-ttu-id="9934b-106">Después de cambiar el propietario de la suscripción, la suscripción se ejecutará en el contexto de seguridad del nuevo propietario, y el campo User!UserID del informe mostrará el valor del nuevo propietario.</span><span class="sxs-lookup"><span data-stu-id="9934b-106">After you change the subscription owner, the subscription will then execute in the security context of the new owner, and the User!UserID field in the report will display the value of new owner.</span></span> <span data-ttu-id="9934b-107">Para obtener más información sobre el modelo de objetos al que llaman los ejemplos de PowerShell, vea <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="9934b-107">For more information on the object model the PowerShell samples call, see <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span>

 <span data-ttu-id="9934b-108">![Contenido relacionado con PowerShell](../media/rs-powershellicon.jpg "Contenido relacionado con PowerShell")</span><span class="sxs-lookup"><span data-stu-id="9934b-108">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

||
|-|
|<span data-ttu-id="9934b-109">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] | Modo de SharePoint de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9934b-109">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="9934b-110">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="9934b-110">**In this topic:**</span></span>

-   [<span data-ttu-id="9934b-111">Cómo usar los scripts</span><span class="sxs-lookup"><span data-stu-id="9934b-111">How to use the scripts</span></span>](#bkmk_how_to)

-   [<span data-ttu-id="9934b-112">Script: Presenta la propiedad de todas las suscripciones</span><span class="sxs-lookup"><span data-stu-id="9934b-112">Script: List the ownership of all subscriptions</span></span>](#bkmk_list_ownership_all)

-   [<span data-ttu-id="9934b-113">Script: Presenta todas las suscripciones poseídas por un usuario específico</span><span class="sxs-lookup"><span data-stu-id="9934b-113">Script: List all subscriptions owned by a specific user</span></span>](#bkmk_list_all_one_user)

-   [<span data-ttu-id="9934b-114">Script: Cambia la propiedad de todas las suscripciones poseídas por un usuario específico</span><span class="sxs-lookup"><span data-stu-id="9934b-114">Script: Change ownership for all subscriptions owned by a specific user</span></span>](#bkmk_change_all)

-   [<span data-ttu-id="9934b-115">Script: Presenta todas las suscripciones asociadas a un informe específico</span><span class="sxs-lookup"><span data-stu-id="9934b-115">Script: List all subscriptions associated with a specific report</span></span>](#bkmk_list_for_1_report)

-   [<span data-ttu-id="9934b-116">Script: Cambia la propiedad de una suscripción específica</span><span class="sxs-lookup"><span data-stu-id="9934b-116">Script: Change ownership of a specific subscription</span></span>](#bkmk_change_all_1_subscription)

-   [<span data-ttu-id="9934b-117">Script: Ejecuta (desencadena) una suscripción única</span><span class="sxs-lookup"><span data-stu-id="9934b-117">Script: Run (fire) a single subscription</span></span>](#bkmk_run_1_subscription)

##  <a name="how-to-use-the-scripts"></a><a name="bkmk_how_to"></a> <span data-ttu-id="9934b-118">Cómo usar los scripts</span><span class="sxs-lookup"><span data-stu-id="9934b-118">How to use the scripts</span></span>

### <a name="permissions"></a><span data-ttu-id="9934b-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="9934b-119">Permissions</span></span>
 <span data-ttu-id="9934b-120">Esta sección resume los niveles de permiso requeridos para utilizar los métodos para el modo nativo y para el modo SharePoint de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9934b-120">This section summarizes the permission levels required to use each of the methods for both Native and SharePoint mode [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="9934b-121">Los scripts de este tema usan los siguientes métodos de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="9934b-121">The scripts in this topic use the following [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] methods:</span></span>

-   [<span data-ttu-id="9934b-122">Método ReportingService2010.ListSubscriptions</span><span class="sxs-lookup"><span data-stu-id="9934b-122">ReportingService2010.ListSubscriptions Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listsubscriptions.aspx)

-   [<span data-ttu-id="9934b-123">Método ReportingService2010.ChangeSubscriptionOwner</span><span class="sxs-lookup"><span data-stu-id="9934b-123">ReportingService2010.ChangeSubscriptionOwner Method</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.changesubscriptionowner.aspx)

-   [<span data-ttu-id="9934b-124">ReportingService2010.ListChildren</span><span class="sxs-lookup"><span data-stu-id="9934b-124">ReportingService2010.ListChildren</span></span>](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listchildren.aspx)

-   <span data-ttu-id="9934b-125">El método [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) solo se usa en el último script para activar la suscripción específica que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="9934b-125">The method [ReportingService2010.FireEvent](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.fireevent.aspx) is only used in the last script to trigger a specific subscription to run.</span></span> <span data-ttu-id="9934b-126">Si no tiene previsto utilizar este script, omita los requisitos de permiso para el método FireEvent.</span><span class="sxs-lookup"><span data-stu-id="9934b-126">If you do not plan to use that script you can ignore the permission requirements for the FireEvent method.</span></span>

 <span data-ttu-id="9934b-127">**Modo nativo:**</span><span class="sxs-lookup"><span data-stu-id="9934b-127">**Native mode:**</span></span>

-   <span data-ttu-id="9934b-128">Enumerar suscripciones: (HYPERLINK " https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx " ReadSubscription en el informe y el usuario es el propietario de la suscripción) o ReadAnySubscription</span><span class="sxs-lookup"><span data-stu-id="9934b-128">List Subscriptions: ( HYPERLINK "https://technet.microsoft.com/library/microsoft.reportingservices.interfaces.reportoperation.aspx" ReadSubscription on the report AND the user is the subscription owner) OR ReadAnySubscription</span></span>

-   <span data-ttu-id="9934b-129">Cambiar suscripciones: El usuario debe ser miembro del grupo BUILTIN\Administrators</span><span class="sxs-lookup"><span data-stu-id="9934b-129">Change Subscriptions: The user must be a member of the BUILTIN\Administrators group</span></span>

-   <span data-ttu-id="9934b-130">Presentar elementos secundarios: ReadProperties en el elemento</span><span class="sxs-lookup"><span data-stu-id="9934b-130">List Children: ReadProperties on Item</span></span>

-   <span data-ttu-id="9934b-131">Desencadenar evento: GenerateEvents (sistema)</span><span class="sxs-lookup"><span data-stu-id="9934b-131">Fire Event: GenerateEvents (System)</span></span>

 <span data-ttu-id="9934b-132">**Modo SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="9934b-132">**SharePoint mode:**</span></span>

-   <span data-ttu-id="9934b-133">Mostrar suscripciones: ManageAlerts o (HYPERLINK " https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx " CreateAlerts en el informe y el usuario es el propietario de la suscripción y la suscripción es una suscripción con tiempo).</span><span class="sxs-lookup"><span data-stu-id="9934b-133">List Subscriptions: ManageAlerts OR ( HYPERLINK "https://technet.microsoft.com/library/microsoft.sharepoint.spbasepermissions.aspx" CreateAlerts on the report AND the user is the subscription owner and the subscription is a timed subscription).</span></span>

-   <span data-ttu-id="9934b-134">Cambiar suscripciones: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="9934b-134">Change Subscriptions: ManageWeb</span></span>

-   <span data-ttu-id="9934b-135">Presentar elementos secundarios: ViewListItems</span><span class="sxs-lookup"><span data-stu-id="9934b-135">List Children: ViewListItems</span></span>

-   <span data-ttu-id="9934b-136">Desencadenar evento: ManageWeb</span><span class="sxs-lookup"><span data-stu-id="9934b-136">Fire Event: ManageWeb</span></span>

 <span data-ttu-id="9934b-137">Para obtener más información, vea [Comparación de roles y tareas en Reporting Services con grupos y permisos de SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9934b-137">For more information, see [Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md).</span></span>

### <a name="script-usage"></a><span data-ttu-id="9934b-138">Uso de scripts</span><span class="sxs-lookup"><span data-stu-id="9934b-138">Script usage</span></span>
 <span data-ttu-id="9934b-139">**Crear archivos de script (.ps1)**</span><span class="sxs-lookup"><span data-stu-id="9934b-139">**Create Script files (.ps1)**</span></span>

1.  <span data-ttu-id="9934b-140">Crear una carpeta con el nombre **c:\scripts**.</span><span class="sxs-lookup"><span data-stu-id="9934b-140">Create a folder named **c:\scripts**.</span></span> <span data-ttu-id="9934b-141">Si elige una carpeta diferente, modifique el nombre de la carpeta utilizada en las instrucciones de sintaxis de línea de comandos del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9934b-141">If you choose a different folder then modify the folder name used in the example command line syntax statements.</span></span>

2.  <span data-ttu-id="9934b-142">Cree un archivo de texto para cada script y guarde los archivos en la carpeta c:\scripts.</span><span class="sxs-lookup"><span data-stu-id="9934b-142">Create a text file for each script and save the files to the c:\scripts folder.</span></span> <span data-ttu-id="9934b-143">Cuando cree los archivos .ps1, use el nombre de la sintaxis de línea de comandos de cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9934b-143">When you create the .ps1 files, use the name from each example command line syntax.</span></span>

3.  <span data-ttu-id="9934b-144">Abra un símbolo del sistema con privilegio de administración.</span><span class="sxs-lookup"><span data-stu-id="9934b-144">Open a command prompt with administrative privileges.</span></span>

4.  <span data-ttu-id="9934b-145">Ejecute cada archivo de script utilizando la sintaxis de línea de comando proporcionada con cada ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9934b-145">Run each script file, using the sample command line syntax provided with each example.</span></span>

 <span data-ttu-id="9934b-146">**Entornos probados**</span><span class="sxs-lookup"><span data-stu-id="9934b-146">**Tested environments**</span></span>

 <span data-ttu-id="9934b-147">Los scripts de este tema se probaron en PowerShell versión 3 y con las siguientes versiones de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9934b-147">The scripts in this topic were tested on PowerShell version 3 and with the following versions of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]:</span></span>

-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]

-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]

-   [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)]

##  <a name="script-list-the-ownership-of-all-subscriptions"></a><a name="bkmk_list_ownership_all"></a> <span data-ttu-id="9934b-148">Script: Presenta la propiedad de todas las suscripciones</span><span class="sxs-lookup"><span data-stu-id="9934b-148">Script: List the ownership of all subscriptions</span></span>
 <span data-ttu-id="9934b-149">Este script presenta todas las suscripciones de un sitio.</span><span class="sxs-lookup"><span data-stu-id="9934b-149">This script lists all of the subscriptions on a site.</span></span> <span data-ttu-id="9934b-150">Puede utilizarlo para probar su conexión o para comprobar la ruta de acceso del informe y el identificador de la suscripción para su uso en los demás scripts.</span><span class="sxs-lookup"><span data-stu-id="9934b-150">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="9934b-151">Además, es un script útil para verificar qué suscripciones existen y quién las posee.</span><span class="sxs-lookup"><span data-stu-id="9934b-151">This is also a useful script to simply audit what subscriptions exist and who owns them.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9934b-152">Sintaxis del modo nativo</span><span class="sxs-lookup"><span data-stu-id="9934b-152">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9934b-153">Sintaxis del modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="9934b-153">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions.ps1 "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="9934b-154">Script</span><span class="sxs-lookup"><span data-stu-id="9934b-154">Script</span></span>

```powershell
# Parameters
#    server   - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)

Param(
    [string]$server,
    [string]$site
   )

$rs2010 += New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site); # use "/" for default native mode site

Write-Host " "
Write-Host "----- $server's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted, Status
```

> [!TIP]
>  <span data-ttu-id="9934b-155">Para comprobar las direcciones URL de los sitios en modo de SharePoint, use el cmdlet de SharePoint **Get-SPSite**.</span><span class="sxs-lookup"><span data-stu-id="9934b-155">To verify site URLS in SharePoint mode, use the SharePoint cmdlet **Get-SPSite**.</span></span> <span data-ttu-id="9934b-156">Para obtener más información, vea [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="9934b-156">For more information, see [Get-SPSite](https://technet.microsoft.com/library/ff607950\(v=office.15\).aspx).</span></span>

##  <a name="script-list-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_list_all_one_user"></a> <span data-ttu-id="9934b-157">Script: Presenta todas las suscripciones poseídas por un usuario específico</span><span class="sxs-lookup"><span data-stu-id="9934b-157">Script: List all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="9934b-158">Este script presenta todas las suscripciones poseídas por un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="9934b-158">This script lists all of the subscriptions owned by a specific user.</span></span> <span data-ttu-id="9934b-159">Puede utilizarlo para probar su conexión o para comprobar la ruta de acceso del informe y el identificador de la suscripción para su uso en los demás scripts.</span><span class="sxs-lookup"><span data-stu-id="9934b-159">You can use this script to test your connection or to verify the report path and subscription id for use in the other scripts.</span></span> <span data-ttu-id="9934b-160">Este script es útil si desea comprobar qué suscripciones poseía una persona que abandona su organización, para cambiar el propietario o eliminar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="9934b-160">This script is useful when someone in your organization leaves and you want to verify what subscriptions they owned so you can change the owner or delete the subscription.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9934b-161">Sintaxis del modo nativo</span><span class="sxs-lookup"><span data-stu-id="9934b-161">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]" "[server]/reportserver" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9934b-162">Sintaxis del modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="9934b-162">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ListAll_SSRS_Subscriptions4User.ps1 "[Domain]\[user]"  "[server]/_vti_bin/reportserver" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="9934b-163">Script</span><span class="sxs-lookup"><span data-stu-id="9934b-163">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
Param(
    [string]$currentOwner,
    [string]$server,
    [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $currentOwner's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.owner -eq $currentOwner}
```

##  <a name="script-change-ownership-for-all-subscriptions-owned-by-a-specific-user"></a><a name="bkmk_change_all"></a> <span data-ttu-id="9934b-164">Script: Cambia la propiedad de todas las suscripciones poseídas por un usuario específico</span><span class="sxs-lookup"><span data-stu-id="9934b-164">Script: Change ownership for all subscriptions owned by a specific user</span></span>
 <span data-ttu-id="9934b-165">Este script cambia la propiedad de todas las suscripciones poseídas por un usuario específico al nuevo parámetro de propietario.</span><span class="sxs-lookup"><span data-stu-id="9934b-165">This script changes the ownership for all subscriptions owned by a specific user to the new owner parameter.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9934b-166">Sintaxis del modo nativo</span><span class="sxs-lookup"><span data-stu-id="9934b-166">Native mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\current owner]" "[Domain]\[new owner]" "[server]/reportserver"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9934b-167">Sintaxis del modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="9934b-167">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\ChangeALL_SSRS_SubscriptionOwner.ps1 "[Domain]\{current owner]" "[Domain]\[new owner]" "[server]/_vti_bin/reportserver"
```

### <a name="script"></a><span data-ttu-id="9934b-168">Script</span><span class="sxs-lookup"><span data-stu-id="9934b-168">Script</span></span>

```powershell
# Parameters:
#    currentOwner - DOMAIN\USER that owns the subscriptions you wish to change
#    newOwner      - DOMAIN\USER that will own the subscriptions you wish to change
#    server        - server and instance name (e.g. myserver/reportserver, myserver/reportserver_db2, myserver/_vti_bin/reportserver)

Param(
    [string]$currentOwner,
    [string]$newOwner,
    [string]$server
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$items = $rs2010.ListChildren("/", $true);

$subscriptions = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $curRepSubs = $rs2010.ListSubscriptions($item.Path);
        ForEach ($curRepSub in $curRepSubs)
        {
            if ($curRepSub.Owner -eq $currentOwner)
            {
                $subscriptions += $curRepSub;
            }
        }
    }
}

Write-Host " "
Write-Host " "
Write-Host -foregroundcolor "green" "-----  $currentOwner's Subscriptions changing ownership to $newOwner : "
$subscriptions | select SubscriptionID, Owner, Path, Description,  Status  | format-table -AutoSize

ForEach ($sub in $subscriptions)
{
    $rs2010.ChangeSubscriptionOwner($sub.SubscriptionID, $newOwner);
}

$subs2 = @();

ForEach ($item in $items)
{
    if ($item.TypeName -eq "Report")
    {
        $subs2 += $rs2010.ListSubscriptions($item.Path);
    }
}
```

##  <a name="script-list-all-subscriptions-associated-with-a-specific-report"></a><a name="bkmk_list_for_1_report"></a> <span data-ttu-id="9934b-169">Script: Presenta todas las suscripciones asociadas a un informe específico</span><span class="sxs-lookup"><span data-stu-id="9934b-169">Script: List all subscriptions associated with a specific report</span></span>
 <span data-ttu-id="9934b-170">Este script presenta todas las suscripciones asociadas a un informe específico.</span><span class="sxs-lookup"><span data-stu-id="9934b-170">This script lists all of the subscriptions associated with a specific report.</span></span> <span data-ttu-id="9934b-171">La sintaxis de la ruta de acceso del informe es un modo SharePoint diferente que requiere una dirección URL completa.</span><span class="sxs-lookup"><span data-stu-id="9934b-171">The report path syntax is different SharePoint mode which requires a full URL.</span></span> <span data-ttu-id="9934b-172">En los ejemplos de sintaxis, el nombre del informe es "title only", que contiene un espacio, lo que obliga a usar comillas en el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="9934b-172">In the syntax examples, the report name used is "title only", which contains a space and therefore requires the single quotes around the report name.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9934b-173">Sintaxis del modo nativo</span><span class="sxs-lookup"><span data-stu-id="9934b-173">Native mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/reportserver" "'/reports/title only'" "/"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9934b-174">Sintaxis del modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="9934b-174">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\List_SSRS_One_Reports_Subscriptions.ps1 "[server]/_vti_bin/reportserver"  "'http://[server]/shared documents/title only.rdl'" "http://[server]"
```

### <a name="script"></a><span data-ttu-id="9934b-175">Script</span><span class="sxs-lookup"><span data-stu-id="9934b-175">Script</span></span>

```powershell
# Parameters:
#    server      - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    reportpath  - path to report in the report server, including report name e.g. /reports/test report >> pass in  "'/reports/title only'"
#    site        - use "/" for default native mode site
Param
(
      [string]$server,
      [string]$reportpath,
      [string]$site
)

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
$subscriptions += $rs2010.ListSubscriptions($site);

Write-Host " "
Write-Host " "
Write-Host "----- $reportpath 's Subscriptions: "
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status | where {$_.path -eq $reportpath}
```

##  <a name="script-change-ownership-of-a-specific-subscription"></a><a name="bkmk_change_all_1_subscription"></a> <span data-ttu-id="9934b-176">Script: Cambia la propiedad de una suscripción específica</span><span class="sxs-lookup"><span data-stu-id="9934b-176">Script: Change ownership of a specific subscription</span></span>
 <span data-ttu-id="9934b-177">Este script cambia la propiedad de una suscripción específica.</span><span class="sxs-lookup"><span data-stu-id="9934b-177">This script changes the ownership for a specific subscription.</span></span> <span data-ttu-id="9934b-178">La suscripción está identificada por el SubscriptionID que pasa al script.</span><span class="sxs-lookup"><span data-stu-id="9934b-178">The subscription is identified by the SubscriptionID that you pass into the script.</span></span> <span data-ttu-id="9934b-179">Puede utilizar uno de los scripts para presentar suscripciones para determinar el SubscriptionID correcto.</span><span class="sxs-lookup"><span data-stu-id="9934b-179">You can use one of the list subscription scripts to determine the correct SubscriptionID.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9934b-180">Sintaxis del modo nativo</span><span class="sxs-lookup"><span data-stu-id="9934b-180">Native mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/reportserver" "/" "ac5637a1-9982-4d89-9d69-a72a9c3b3150"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9934b-181">Sintaxis del modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="9934b-181">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\Change_SSRS_Owner_One_Subscription.ps1 "[Domain]\[new owner]" "[server]/_vti_bin/reportserver" "http://[server]" "9660674b-f020-453f-b1e3-d9ba37624519"
```

### <a name="script"></a><span data-ttu-id="9934b-182">Script</span><span class="sxs-lookup"><span data-stu-id="9934b-182">Script</span></span>

```powershell
# Parameters:
#    newOwner       - DOMAIN\USER that will own the subscriptions you wish to change
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site        - use "/" for default native mode site
#    subscriptionID - guid for the single subscription to change

Param(
    [string]$newOwner,
    [string]$server,
    [string]$site,
    [string]$subscriptionid
   )
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential;

$subscription += $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid};

Write-Host " "
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status

$rs2010.ChangeSubscriptionOwner($subscription.SubscriptionID, $newOwner)

#refresh the list
$subscription = $rs2010.ListSubscriptions($site) | where {$_.SubscriptionID -eq $subscriptionid}; # use "/" for default native mode site
Write-Host "----- $subscriptionid's Subscription properties: "
$subscription | select Path, report, Description, SubscriptionID, Owner, Status
```

##  <a name="script-run-fire-a-single-subscription"></a><a name="bkmk_run_1_subscription"></a> <span data-ttu-id="9934b-183">Script: Ejecuta (desencadena) una sola suscripción</span><span class="sxs-lookup"><span data-stu-id="9934b-183">Script: Run (fire) a single subscription</span></span>
 <span data-ttu-id="9934b-184">Este script ejecuta una suscripción específica mediante el método FireEvent.</span><span class="sxs-lookup"><span data-stu-id="9934b-184">This script will run a specific subscription using the FireEvent method.</span></span> <span data-ttu-id="9934b-185">El script ejecuta inmediatamente la suscripción independientemente de la programación configurada para la suscripción.</span><span class="sxs-lookup"><span data-stu-id="9934b-185">The script will immediately run the subscription regardless of the schedule configured for the subscription.</span></span> <span data-ttu-id="9934b-186">Se compara EventType con el conjunto de eventos conocido que se ha definido en el archivo de configurador del servidor de informes **rsreportserver.config** . El script utiliza el siguiente tipo de eventos para las suscripciones estándar:</span><span class="sxs-lookup"><span data-stu-id="9934b-186">The EventType is matched against the known set of events that are defined in the report server configuration file **rsreportserver.config** The script uses the following event type for standard subscriptions:</span></span>

 `<Event>`

 `<Type>TimedSubscription</Type>`

 `</Event>`

 <span data-ttu-id="9934b-187">Para obtener más información acerca del archivo de configuración, consulte [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="9934b-187">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>

 <span data-ttu-id="9934b-188">El script incluye la lógica de retraso "`Start-Sleep -s 6`" para que haya tiempo después de que se desencadene el evento, de modo que el estado actualizado esté disponible con el método ListSubscription.</span><span class="sxs-lookup"><span data-stu-id="9934b-188">The script includes delay logic "`Start-Sleep -s 6`" so there is time after the event fires, for the updated status to be available with the ListSubscription method.</span></span>

### <a name="native-mode-syntax"></a><span data-ttu-id="9934b-189">Sintaxis del modo nativo</span><span class="sxs-lookup"><span data-stu-id="9934b-189">Native mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/reportserver" $null "70366e82-2d3c-4edd-a216-b97e51e26de9"
```

### <a name="sharepoint-mode-syntax"></a><span data-ttu-id="9934b-190">Sintaxis del modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="9934b-190">SharePoint mode syntax</span></span>

```cmd
powershell c:\scripts\FireSubscription.ps1 "[server]/_vti_bin/reportserver" "http://[server]" "c3425c72-580d-423e-805a-41cf9799fd25"
```

### <a name="script"></a><span data-ttu-id="9934b-191">Script</span><span class="sxs-lookup"><span data-stu-id="9934b-191">Script</span></span>

```powershell
# Parameters
#    server         - server and instance name (e.g. myserver/reportserver or myserver/reportserver_db2)
#    site           - use $null for a native mode server
#    subscriptionid - subscription guid

Param(
  [string]$server,
  [string]$site,
  [string]$subscriptionid
  )

$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;
#event type is case sensative to what is in the rsreportserver.config
$rs2010.FireEvent("TimedSubscription",$subscriptionid,$site)

Write-Host " "
Write-Host "----- Subscription ($subscriptionid) status: "
#get list of subscriptions and filter to the specific ID to see the Status and LastExecuted
Start-Sleep -s 6 # slight delay in processing so ListSubscription returns the updated Status and LastExecuted
$subscriptions = $rs2010.ListSubscriptions($site); 
$subscriptions | select Status, Path, report, Description, Owner, SubscriptionID, EventType, lastexecuted | where {$_.SubscriptionID -eq $subscriptionid}
```

## <a name="see-also"></a><span data-ttu-id="9934b-192">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9934b-192">See Also</span></span>
 <span data-ttu-id="9934b-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span><span class="sxs-lookup"><span data-stu-id="9934b-193"><xref:ReportService2010.ReportingService2010.ListSubscriptions%2A> <xref:ReportService2010.ReportingService2010.ChangeSubscriptionOwner%2A></span></span> 
 <xref:ReportService2010.ReportingService2010.ListChildren%2A> 
 <xref:ReportService2010.ReportingService2010.FireEvent%2A>
