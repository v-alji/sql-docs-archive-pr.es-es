---
title: 'Lista de comprobación: Use PowerShell para comprobar PowerPivot para SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 07/20/2020
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 73a13f05-3450-411f-95f9-4b6167cc7607
author: minewiskan
ms.author: owend
ms.openlocfilehash: 001b3fae82851b9ec08b0383bb3db9e6d011ae32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744937"
---
# <a name="checklist-use-powershell-to-verify-powerpivot-for-sharepoint"></a><span data-ttu-id="318f6-102">Lista de comprobación: Usar PowerShell para comprobar PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="318f6-102">CheckList: Use PowerShell to Verify PowerPivot for SharePoint</span></span>
  <span data-ttu-id="318f6-103">Ninguna operación de instalación o recuperación de [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] está completa sin un paso sólido de comprobación que confirme que los servicios y los datos son operativos.</span><span class="sxs-lookup"><span data-stu-id="318f6-103">No [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] installation or recovery operation is complete without a solid verification test pass that confirms your services and data are operational.</span></span> <span data-ttu-id="318f6-104">En este artículo, le mostramos cómo realizar estos pasos con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="318f6-104">In this article, we show you how to perform these steps using Windows PowerShell.</span></span> <span data-ttu-id="318f6-105">Cada paso tiene su propia sección para que pueda ir directamente a determinadas tareas.</span><span class="sxs-lookup"><span data-stu-id="318f6-105">We put each step into its own section so that you can go straight to specific tasks.</span></span> <span data-ttu-id="318f6-106">Por ejemplo, ejecute el script de la sección [Bases de datos](#bkmk_databases) de este tema para comprobar el nombre de la aplicación de servicio y las bases de datos de contenido si desea programar su mantenimiento o copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="318f6-106">For example, run the script in the [Databases](#bkmk_databases) section of this topic to verify the name of the service application and content databases if you want to schedule them for maintenance or backup.</span></span>

|||
|-|-|
|<span data-ttu-id="318f6-107">![Contenido relacionado con PowerShell](../../../reporting-services/media/rs-powershellicon.jpg "Contenido relacionado con PowerShell")</span><span class="sxs-lookup"><span data-stu-id="318f6-107">![PowerShell related content](../../../reporting-services/media/rs-powershellicon.jpg "PowerShell related content")</span></span>|<span data-ttu-id="318f6-108">Al final del tema se incluye un script completo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="318f6-108">A full PowerShell script is included at the bottom of the topic.</span></span> <span data-ttu-id="318f6-109">Use el script completo como punto de partida para generar un script personalizado con el fin de auditar toda la implementación de [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="318f6-109">Use the full script as a starting point to build a custom script for auditing your full [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] deployment.</span></span>|

||
|-|
|<span data-ttu-id="318f6-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="318f6-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="318f6-111">**En este tema**: los elementos indicados con letras en la tabla de contenido siguiente corresponden a las áreas del diagrama.</span><span class="sxs-lookup"><span data-stu-id="318f6-111">**In this topic**: The lettered items in the following the TOC correspond to areas of the diagram.</span></span> <span data-ttu-id="318f6-112">El diagrama muestra</span><span class="sxs-lookup"><span data-stu-id="318f6-112">The diagram illustrates the</span></span>

|||
|-|-|
|[<span data-ttu-id="318f6-113">Preparar el entorno de PowerShell</span><span class="sxs-lookup"><span data-stu-id="318f6-113">Prepare your PowerShell environment</span></span>](#bkmk_prerequisites)<br /><br /> [<span data-ttu-id="318f6-114">Síntomas y acciones recomendadas</span><span class="sxs-lookup"><span data-stu-id="318f6-114">Symptoms and Recommended Actions</span></span>](#bkmk_symptoms)<br /><br /> <span data-ttu-id="318f6-115">**(A)** [Servicio Windows de Analysis Services](#bkmk_windows_service)</span><span class="sxs-lookup"><span data-stu-id="318f6-115">**(A)** [Analysis Services Windows Service](#bkmk_windows_service)</span></span><br /><br /> <span data-ttu-id="318f6-116">**(B)** [PowerPivotSystemService y PowerPivotEngineService](#bkmk_engine_and_system_service)</span><span class="sxs-lookup"><span data-stu-id="318f6-116">**(B)** [PowerPivotSystemService and PowerPivotEngineService](#bkmk_engine_and_system_service)</span></span><br /><br /> <span data-ttu-id="318f6-117">**(C)** [Aplicaciones de servicio y servidores proxy PowerPivot](#bkmk_powerpivot_service_application)</span><span class="sxs-lookup"><span data-stu-id="318f6-117">**(C)** [PowerPivot Service Application(s) and proxies](#bkmk_powerpivot_service_application)</span></span><br /><br /> <span data-ttu-id="318f6-118">**(D)** [Bases de datos](#bkmk_databases)</span><span class="sxs-lookup"><span data-stu-id="318f6-118">**(D)** [Databases](#bkmk_databases)</span></span><br /><br /> [<span data-ttu-id="318f6-119">Características de SharePoint</span><span class="sxs-lookup"><span data-stu-id="318f6-119">SharePoint Features</span></span>](#bkmk_features)<br /><br /> [<span data-ttu-id="318f6-120">Trabajos del temporizador</span><span class="sxs-lookup"><span data-stu-id="318f6-120">Timer Jobs</span></span>](#bkmk_timer_jobs)<br /><br /> [<span data-ttu-id="318f6-121">Reglas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="318f6-121">Health Rules</span></span>](#bkmk_health_rules)<br /><br /> <span data-ttu-id="318f6-122">**(E)** [Registros de Windows y ULS](#bkmk_logs)</span><span class="sxs-lookup"><span data-stu-id="318f6-122">**(E)** [Windows and ULS Logs](#bkmk_logs)</span></span><br /><br /> [<span data-ttu-id="318f6-123">Proveedor MSOLAP</span><span class="sxs-lookup"><span data-stu-id="318f6-123">MSOLAP Provider</span></span>](#bkmk_msolap)<br /><br /> [<span data-ttu-id="318f6-124">Biblioteca cliente ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="318f6-124">ADOMD.Net client Library</span></span>](#bkmk_adomd)<br /><br /> [<span data-ttu-id="318f6-125">Reglas de recopilación de datos de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="318f6-125">Health Data Collection Rules</span></span>](#bkmk_health_collection)<br /><br /> [<span data-ttu-id="318f6-126">Soluciones</span><span class="sxs-lookup"><span data-stu-id="318f6-126">Solutions</span></span>](#bkmk_solutions)<br /><br /> [<span data-ttu-id="318f6-127">Pasos de comprobación manual</span><span class="sxs-lookup"><span data-stu-id="318f6-127">Manual Verification Steps</span></span>](#bkmk_manual)<br /><br /> [<span data-ttu-id="318f6-128">Más recursos</span><span class="sxs-lookup"><span data-stu-id="318f6-128">More Resources</span></span>](#bkmk_more_resources)<br /><br /> [<span data-ttu-id="318f6-129">Script completo de PowerShell</span><span class="sxs-lookup"><span data-stu-id="318f6-129">Full PowerShell Script</span></span>](#bkmk_full_script)|<span data-ttu-id="318f6-130">![comprobación de powershell de powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "comprobación de powershell de powerpivot")</span><span class="sxs-lookup"><span data-stu-id="318f6-130">![powershell verification of powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "powershell verification of powerpivot")</span></span>|

##  <a name="prepare-your-powershell-environment"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="318f6-131">Preparar el entorno de PowerShell</span><span class="sxs-lookup"><span data-stu-id="318f6-131">Prepare your PowerShell environment</span></span>
 <span data-ttu-id="318f6-132">Los pasos de esta sección sirven para preparar el entorno de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="318f6-132">The steps in this section prepare your PowerShell environment.</span></span> <span data-ttu-id="318f6-133">Puede que estos pasos no sean necesarios, en función de cómo esté configurado actualmente el entorno de scripting.</span><span class="sxs-lookup"><span data-stu-id="318f6-133">The steps may not be required, depending on how your scripting environment is currently configured.</span></span>

 <span data-ttu-id="318f6-134">**Permisos de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="318f6-134">**PowerShell Permissions**</span></span>

 <span data-ttu-id="318f6-135">Abra una ventana de Powershell o ISE (Entorno de scripting integrado) de PowerShell con **privilegios administrativos**.</span><span class="sxs-lookup"><span data-stu-id="318f6-135">Open a Powershell window or the PowerShell ISE (Integrated Scripting Environment) with **administrative privileges**.</span></span> <span data-ttu-id="318f6-136">Si no tiene privilegios administrativos al ejecutar comandos, verá un mensaje de error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="318f6-136">If you do not have administrative privileges when you run commands, you will see an error message similar to the following:</span></span>

 <span data-ttu-id="318f6-137">Get-SPLogEvent: Debe tener **privilegios de administrador** del equipo para ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="318f6-137">Get-SPLogEvent : You need to have Machine **administrator privileges** to run this cmdlet.</span></span>

 <span data-ttu-id="318f6-138">**SharePoint y módulo [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="318f6-138">**SharePoint and [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]** Module</span></span>

 <span data-ttu-id="318f6-139">Si ve un mensaje de error similar al siguiente al ejecutar cmdlets relacionados de SharePoint, ejecute el comando Add-PSSnapin:</span><span class="sxs-lookup"><span data-stu-id="318f6-139">If you see an error message similar to the following when you run SharePoint related cmdlets, run the Add-PSSnapin command:</span></span>

 <span data-ttu-id="318f6-140">El término 'Get-PowerPivotSystemService' **no se reconoce como nombre de un cmdlet**, función, archivo de script o programa ejecutable.</span><span class="sxs-lookup"><span data-stu-id="318f6-140">The term 'Get-PowerPivotSystemService' **is not recognized as the name of a cmdlet**, function, script file, or operable program.</span></span> <span data-ttu-id="318f6-141">Compruebe si escribió correctamente el nombre o, si incluyó una ruta de acceso, compruebe que dicha ruta es correcta e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="318f6-141">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>

```
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0
```

 <span data-ttu-id="318f6-142">**Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="318f6-142">**Windows PowerShell**</span></span>

 <span data-ttu-id="318f6-143">Para obtener más información sobre el ISE de PowerShell, vea [Introducción a ISE de Windows PowerShell](https://technet.microsoft.com/library/dd315244.aspx) y [Usar Windows PowerShell para administrar SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="318f6-143">For more information on the PowerShell ISE, see [Introducing the Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) and [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span></span>

|||
|-|-|
|<span data-ttu-id="318f6-144">![powerpivot en conjunto de aplicaciones general de sharepoint](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot en conjunto de aplicaciones general de sharepoint")</span><span class="sxs-lookup"><span data-stu-id="318f6-144">![powerpivot in sharepoint general application set](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot in sharepoint general application set")</span></span>|<span data-ttu-id="318f6-145">Si lo desea, puede comprobar la mayoría de los componentes en Administración central, con el panel de administración de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="318f6-145">You can optionally verify a majority of the components in Central Administration, using the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] management dashboard.</span></span> <span data-ttu-id="318f6-146">Para abrir el panel en Administración central, haga clic en **Configuración de aplicación general**y, a continuación, haga clic en **Panel de administración** en **PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="318f6-146">To open the dashboard in Central Administration, click **General Application Settings**, and then click **Management Dashboard** in the **PowerPivot**.</span></span> <span data-ttu-id="318f6-147">Para obtener más información sobre el panel, vea [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="318f6-147">For more information on the dashboard, see [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span></span>|

##  <a name="symptoms-and-recommended-actions"></a><a name="bkmk_symptoms"></a><span data-ttu-id="318f6-148">Síntomas y acciones recomendadas</span><span class="sxs-lookup"><span data-stu-id="318f6-148">Symptoms and Recommended Actions</span></span>
 <span data-ttu-id="318f6-149">En la tabla siguiente se muestra una lista de síntomas o problemas y la sección sugerida de este tema que puede consultar para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="318f6-149">The following table is a list of symptoms or issues and the suggested section of this topic to consult to help you resolve the issue.</span></span>

|<span data-ttu-id="318f6-150">Síntoma</span><span class="sxs-lookup"><span data-stu-id="318f6-150">Symptom</span></span>|<span data-ttu-id="318f6-151">Vea la sección</span><span class="sxs-lookup"><span data-stu-id="318f6-151">See section</span></span>|
|-------------|-----------------|
|<span data-ttu-id="318f6-152">La actualización de datos no está en ejecución</span><span class="sxs-lookup"><span data-stu-id="318f6-152">Data refresh is not running</span></span>|<span data-ttu-id="318f6-153">Vea la sección [Timer Jobs](#bkmk_timer_jobs) y compruebe que el **Trabajo de temporizador de actualización de datos de PowerPivot** está en línea.</span><span class="sxs-lookup"><span data-stu-id="318f6-153">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Online PowerPivot Data Refresh Timer Job** is online.</span></span>|
|<span data-ttu-id="318f6-154">Los datos del panel de administración son antiguos</span><span class="sxs-lookup"><span data-stu-id="318f6-154">Management dashboard data is old</span></span>|<span data-ttu-id="318f6-155">Vea la sección [Trabajos del temporizador](#bkmk_timer_jobs) y compruebe que el **Trabajo de temporizador de procesamiento del panel de administración** está en línea.</span><span class="sxs-lookup"><span data-stu-id="318f6-155">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Management Dashboard Processing Timer Job** is online.</span></span>|
|<span data-ttu-id="318f6-156">Algunas partes del panel de administración</span><span class="sxs-lookup"><span data-stu-id="318f6-156">Some portions of the Management Dashboard</span></span>|<span data-ttu-id="318f6-157">Si instala PowerPivot para SharePoint en una granja que tiene la topología de Administración central, sin Excel Services o PowerPivot para SharePoint, debe descargar e instalar la biblioteca de cliente de Microsoft ADOMD.NET si desea acceso total a los informes integrados en el panel de administración de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="318f6-157">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, you must download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="318f6-158">Algunos informes del panel usan ADOMD.NET para tener acceso a los datos internos que proporcionan los datos de errores en el procesamiento de las consultas de PowerPivot y el estado del servidor en la granja.</span><span class="sxs-lookup"><span data-stu-id="318f6-158">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span> <span data-ttu-id="318f6-159">Vea la sección [Biblioteca de cliente de ADOMD.NET](#bkmk_adomd) y el tema [Instalar ADOMD.NET en servidores front-end web ejecutando Administración central](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="318f6-159">See the section [ADOMD.Net client Library](#bkmk_adomd) and the topic [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>|
|\<future content>||

##  <a name="analysis-services-windows-service"></a><a name="bkmk_windows_service"></a> <span data-ttu-id="318f6-160">Servicio Windows de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="318f6-160">Analysis Services Windows Service</span></span>
 <span data-ttu-id="318f6-161">El script de esta sección comprueba la instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="318f6-161">The script in this section verifies the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="318f6-162">Compruebe que el servicio se está **ejecutando**.</span><span class="sxs-lookup"><span data-stu-id="318f6-162">Verify the service is **running**.</span></span>

```powershell
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name              DisplayName                                Status
----              -----------                                ------
MSOLAP$POWERPIVOT SQL Server Analysis Services (POWERPIVOT) Running
```

##  <a name="powerpivotsystemservice-and-powerpivotengineservice"></a><a name="bkmk_engine_and_system_service"></a><span data-ttu-id="318f6-163">PowerPivotSystemService y PowerPivotEngineService</span><span class="sxs-lookup"><span data-stu-id="318f6-163">PowerPivotSystemService and PowerPivotEngineService</span></span>
 <span data-ttu-id="318f6-164">Los scripts de esta sección comprueban los servicios del sistema de [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="318f6-164">The scripts in this section verify the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] system services.</span></span> <span data-ttu-id="318f6-165">Hay un servicio del sistema para una implementación de SharePoint 2013 y dos servicios para una implementación de SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="318f6-165">There is one system service for a SharePoint 2013 deployment and two services for a SharePoint 2010 deployment.</span></span>

 <span data-ttu-id="318f6-166">**PowerPivotSystemService**</span><span class="sxs-lookup"><span data-stu-id="318f6-166">**PowerPivotSystemService**</span></span>

 <span data-ttu-id="318f6-167">Compruebe que el estado es **en línea**.</span><span class="sxs-lookup"><span data-stu-id="318f6-167">Verify the Status is **Online**.</span></span>

```powershell
Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                  Status Applications                             Farm
--------                                  ------ ------------                             ----
SQL Server PowerPivot Service Application Online {Default PowerPivot Service Application} SPFarm Name=SharePoint_Config_77d8ab0744a34e8aa27c806a2b8c760c
```

 <span data-ttu-id="318f6-168">**PowerPivotEngineService**</span><span class="sxs-lookup"><span data-stu-id="318f6-168">**PowerPivotEngineService**</span></span>

> [!NOTE]
>  <span data-ttu-id="318f6-169">**Omita este script si** está usando SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="318f6-169">**Skip this script if** you are using SharePoint 2013.</span></span> <span data-ttu-id="318f6-170">PowerPivotEngineService no forma parte de una implementación de SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="318f6-170">The PowerPivotEngineService is not part of a SharePoint 2013 deployment.</span></span> <span data-ttu-id="318f6-171">Si ejecuta el cmdlet Get-PowerPivot**Engine**Service en SharePoint 2013, verá un mensaje de error similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="318f6-171">If you run the Get-PowerPivot**Engine**Service cmdlet on SharePoint 2013, you will see an error message similar to the following.</span></span> <span data-ttu-id="318f6-172">Este mensaje de error aparece aunque haya ejecutado el comando Add-PSSnapin que se describe en la sección de requisitos previos de este tema.</span><span class="sxs-lookup"><span data-stu-id="318f6-172">This error message is returned even if you have run the Add-PSSnapin command described in the prerequisites section of this topic.</span></span>
> 
>  <span data-ttu-id="318f6-173">El término 'Get-PowerPivotEngineService' no se reconoce como nombre de un cmdlet</span><span class="sxs-lookup"><span data-stu-id="318f6-173">The term 'Get-PowerPivotEngineService' is not recognized as the name of a cmdlet</span></span>

 <span data-ttu-id="318f6-174">En una implementación de SharePoint 2010, compruebe que el estado es **En línea**.</span><span class="sxs-lookup"><span data-stu-id="318f6-174">In a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName  : SQL Server Analysis Services
Status    : Online
Name      : MSOLAP$POWERPIVOT
Instances : {POWERPIVOT}
Farm      : SPFarm Name=SharePoint_Config
```

##  <a name="powerpivot-service-applications-and-proxies"></a><a name="bkmk_powerpivot_service_application"></a><span data-ttu-id="318f6-175">Aplicaciones de servicio PowerPivot y servidores proxy</span><span class="sxs-lookup"><span data-stu-id="318f6-175">PowerPivot Service Application(s) and proxies</span></span>
 <span data-ttu-id="318f6-176">Compruebe que el estado es **En línea**.</span><span class="sxs-lookup"><span data-stu-id="318f6-176">Verify the status is **Online**.</span></span> <span data-ttu-id="318f6-177">La Aplicación de Servicios de Excel no usa una base de datos de aplicación de servicio y por tanto el cmdlet no devuelve un nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="318f6-177">The Excel Services Application does not use a service application database and therefore the cmdlet does not return a database name.</span></span> <span data-ttu-id="318f6-178">Anote la base de datos usada por la aplicación de servicio de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] para que pueda comprobar que está en línea en la sección de base de datos más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="318f6-178">Note the database used by the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] service application so you can verify the database is online in the database section later in this topic.</span></span>

 <span data-ttu-id="318f6-179">**PowerPivot y aplicaciones de servicio de Excel**</span><span class="sxs-lookup"><span data-stu-id="318f6-179">**PowerPivot and Excel Service Application(s)**</span></span>

 <span data-ttu-id="318f6-180">En una implementación de SharePoint 2010, compruebe que el estado es **En línea**.</span><span class="sxs-lookup"><span data-stu-id="318f6-180">For a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename, DisplayName, status
```

```Output
TypeName          : PowerPivot Service Application
Name              : PowerPivotServiceApplication1
Status            : Online
UnattendedAccount : PowerPivotUnattendedAccount
ApplicationPool   : SPIisWebServiceApplicationPool Name=sqlbi_serviceapp
Farm              : SPFarm Name=SharePoint_Config
Database          : GeminiServiceDatabase Name=PowerPivotServiceApplication1_19648f3f2c944e27acdc6c20aab8487a

TypeName    : Excel Services Application Web Service Application
DisplayName : Excel Services Application
Status      : Online
```

 <span data-ttu-id="318f6-181">**Grupo de aplicaciones de servicio**</span><span class="sxs-lookup"><span data-stu-id="318f6-181">**Service Application Pool**</span></span>

> [!NOTE]
>  <span data-ttu-id="318f6-182">El ejemplo de código siguiente devuelve la propiedad applicationpool de la aplicación de servicio de [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] predeterminada.</span><span class="sxs-lookup"><span data-stu-id="318f6-182">The following code sample first returns the applicationpool property of the default [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] service application.</span></span> <span data-ttu-id="318f6-183">El nombre se analiza de la cadena y se usa para obtener el estado del objeto de grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="318f6-183">The name is parsed from the string and used to get the status of the application pool object.</span></span>
> 
>  <span data-ttu-id="318f6-184">Compruebe que el estado es **en línea**.</span><span class="sxs-lookup"><span data-stu-id="318f6-184">Verify the Status is **Online**.</span></span> <span data-ttu-id="318f6-185">Si el estado no es en línea o ve "error http" al examinar el [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] sitio, compruebe que las credenciales de identidad de los grupos de aplicaciones de IIS siguen siendo correctas.</span><span class="sxs-lookup"><span data-stu-id="318f6-185">If the status is not Online or you see "http error" when you browse the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] site, verify the identity credentials in the IIS application pools are still correct.</span></span> <span data-ttu-id="318f6-186">El nombre del grupo de aplicaciones de IIS es el valor de la propiedad ID devuelto por el comando Get-SPServiceApplicationPool.</span><span class="sxs-lookup"><span data-stu-id="318f6-186">The IIS pool name will is the value of the ID property returned by the Get-SPServiceApplicationPool command.</span></span>

```powershell
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)

Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                           Status ProcessAccountName Id
----                           ------ ------------------ ------- 
SharePoint Web Services System Online DOMAIN\account     89b50ec3-49e3-4de7-881a-2cec4b8b73ea
```

 ![Nota:](../../../reporting-services/media/rs-fyinote.png "nota") El grupo de aplicaciones también se puede comprobar en la página Administración central administración de **aplicaciones de servicio**. <span data-ttu-id="318f6-188">Haga clic el nombre de la aplicación de servicio y, a continuación, haga clic en **Propiedades** en la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="318f6-188">Click the name of the service application and then click **properties** in the ribbon.</span></span>

 <span data-ttu-id="318f6-189">**Servidores proxy de aplicaciones de servicio de Excel y PowerPivot**</span><span class="sxs-lookup"><span data-stu-id="318f6-189">**PowerPivot and Excel Service Application proxies**</span></span>

 <span data-ttu-id="318f6-190">Compruebe que el estado es **en línea**.</span><span class="sxs-lookup"><span data-stu-id="318f6-190">Verify the Status is **Online**.</span></span>

```powershell
Get-SPServiceApplicationProxy | Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -Like "*powerpivot*" -Or $_.TypeName -Like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                                 Status UnattendedAccount           DisplayName
--------                                                 ------ -----------------           -----------
PowerPivot Service Application Proxy                     Online PowerPivotUnattendedAccount PowerPivotServiceApplication1
Excel Services Application Web Service Application Proxy Online                             Excel Services Application
```

##  <a name="databases"></a><a name="bkmk_databases"></a> <span data-ttu-id="318f6-191">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="318f6-191">Databases</span></span>
 <span data-ttu-id="318f6-192">El script siguiente devuelve el estado de las bases de datos de aplicación de servicio y todas las bases de datos de contenido.</span><span class="sxs-lookup"><span data-stu-id="318f6-192">The following script returns the status of the service application databases and all content databases.</span></span> <span data-ttu-id="318f6-193">Compruebe que el estado es **En línea**.</span><span class="sxs-lookup"><span data-stu-id="318f6-193">Verify the status is **Online**.</span></span>

```powershell
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -Or $_.TypeName -Like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                                                                       Status Server                  TypeName 
----                                                                       ------ ------                  -------- 
DefaultPowerPivotServiceApplicationDB-38422181-2b68-4ab2-b2bb-9c00c39e5a5e Online SPServer Name=TESTSERVER Microsoft.AnalysisServices.SPAddin.GeminiServiceDatabase
DefaultWebApplicationDB-f0db1a8e-4c22-408c-b9b9-153bd74b0312               Online TESTSERVER\POWERPIVOT    Content Database 
SharePoint_Admin_3cadf0b098bf49e0bb15abd487f5c684                          Online TESTSERVER\POWERPIVOT    Content Database
```

##  <a name="sharepoint-features"></a><a name="bkmk_features"></a><span data-ttu-id="318f6-194">Características de SharePoint</span><span class="sxs-lookup"><span data-stu-id="318f6-194">SharePoint Features</span></span>
 <span data-ttu-id="318f6-195">Compruebe que las características de sitio, web y granja están en línea.</span><span class="sxs-lookup"><span data-stu-id="318f6-195">Verify the site, web, and farm features are online.</span></span>

```powershell
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
DisplayName     Status Scope Farm                         
-----------     ------ ----- ----                         
PowerPivotSite  Online  Site SPFarm Name=SharePoint_Config
PowerPivotAdmin Online   Web SPFarm Name=SharePoint_Config
PowerPivot      Online  Farm SPFarm Name=SharePoint_Config
```

##  <a name="timer-jobs"></a><a name="bkmk_timer_jobs"></a><span data-ttu-id="318f6-196">Trabajos de temporizador</span><span class="sxs-lookup"><span data-stu-id="318f6-196">Timer Jobs</span></span>
 <span data-ttu-id="318f6-197">Compruebe que los trabajos del temporizador están **En línea**.</span><span class="sxs-lookup"><span data-stu-id="318f6-197">Verify the Time Jobs are **Online**.</span></span> <span data-ttu-id="318f6-198">El EngineService de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] no está instalado en SharePoint 2013, por lo que el script no mostrará los trabajos del temporizador de EngineService en una implementación de SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="318f6-198">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] EngineService is not installed on SharePoint 2013, therefore the script will not list EngineService timer jobs in a SharePoint 2013 deployment.</span></span>

```powershell
Get-SPTimerJob | Where {$_.service -Like "*power*" -Or $_.service -Like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default
```

```Output
      Status DisplayName                                                                          LastRunTime          Service                             
------ -----------                                                                          -----------          -------                             
Online Health Analysis Job (Daily, SQL Server Analysis Services, All Servers)               4/9/2014 12:00:01 AM EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Hourly, SQL Server Analysis Services, All Servers)              4/9/2014 1:00:01 PM  EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Weekly, SQL Server Analysis Services, All Servers)              4/6/2014 12:00:10 AM EngineService Name=MSOLAP$POWERPIVOT
Online PowerPivot Management Dashboard Processing Timer Job                                 4/8/2014 3:45:38 AM  MidTierService
Online PowerPivot Health Statistics Collector Timer Job                                     4/9/2014 1:00:12 PM  MidTierService
Online PowerPivot Data Refresh Timer Job                                                    4/9/2014 1:09:36 PM  MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, All Servers)  4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, Any Server)   4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, All Servers) 4/6/2014 12:00:03 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, Any Server)  4/6/2014 12:00:03 AM MidTierService
Online PowerPivot Setup Extension Timer Job                                                 4/1/2014 1:40:31 AM  MidTierService
```

##  <a name="health-rules"></a><a name="bkmk_health_rules"></a><span data-ttu-id="318f6-199">Reglas de estado</span><span class="sxs-lookup"><span data-stu-id="318f6-199">Health Rules</span></span>
 <span data-ttu-id="318f6-200">Hay menos reglas en una implementación de SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="318f6-200">There are fewer rules in a SharePoint 2013 deployment.</span></span> <span data-ttu-id="318f6-201">Para obtener una lista completa de reglas para cada entorno de SharePoint y una explicación de cómo usar las reglas, consulte [reglas de estado de PowerPivot-configurar](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span><span class="sxs-lookup"><span data-stu-id="318f6-201">For a full list of rules for each SharePoint environment and an explanation of how to use the rules, see [PowerPivot Health Rules - Configure](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span></span>

```powershell
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                          Enabled Summary
----                          ------- -------         
SecondaryLogonHealthRule         True PowerPivot:  Secondary Logon service (seclogon) is disabled
DataRefreshTimerJobHealthRule    True PowerPivot: The PowerPivot Data Refresh timer job is disabled.
ASUsageLoadHealthRule            True PowerPivot: The ratio of load events to connections is too high.
ASMiniDumpHealthRule             True PowerPivot: One or more minidump files were found in the Logs directory, indicating a program crash
ASUsageCubeRule                  True PowerPivot: Usage data is not getting updated at the expected frequency.
ASADOMDNETHealthRule             True PowerPivot: ADOMD.NET is not installed on a standalone WFE that is configured for central admin
MidTierAcctReadPermissionRule    True PowerPivot: MidTier process account should have 'Full Read' permission on all associated SPWebApplications.
```

##  <a name="windows-and-uls-logs"></a><a name="bkmk_logs"></a><span data-ttu-id="318f6-202">Registros de Windows y ULS</span><span class="sxs-lookup"><span data-stu-id="318f6-202">Windows and ULS Logs</span></span>
 <span data-ttu-id="318f6-203">**Registro de eventos de Windows**</span><span class="sxs-lookup"><span data-stu-id="318f6-203">**Windows event log**</span></span>

 <span data-ttu-id="318f6-204">El comando siguiente buscará en el registro de eventos de Windows los eventos relacionados con la instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="318f6-204">The following command will search the windows event log for events related to the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="318f6-205">Para obtener información sobre cómo deshabilitar eventos o cambiar el nivel de evento, vea [configurar y ver archivos de registro de SharePoint y el registro de diagnósticos &#40;PowerPivot para SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span><span class="sxs-lookup"><span data-stu-id="318f6-205">For information on disabling events or changing the event level, see [Configure and View SharePoint Log Files  and Diagnostic Logging &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span></span>

 <span data-ttu-id="318f6-206">**Nombre de servicio:** MSOLAP$POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="318f6-206">**Service Name:** MSOLAP$POWERPIVOT</span></span>

 <span data-ttu-id="318f6-207">**Nombre para mostrar en Servicios de Windows:** SQL Server Analysis Services (POWERPIVOT)</span><span class="sxs-lookup"><span data-stu-id="318f6-207">**Display name in Windows Services:** SQL Server Analysis Services (POWERPIVOT)</span></span>

```powershell
Get-EventLog "application" | Where-Object {$_.source -Like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -property * -AutoSize | Out-Default
```

```Output
TimeGenerated           EntryType Source            Message
-------------           --------- ------            -------
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Service started. Microsoft SQL Server Analysis Services 64 Bit Evaluation (x64) RTM 12.0.1997.5.
4/16/2014 1:45:18 PM  Information MSOLAP$POWERPIVOT The flight recorder was started.
4/14/2014 6:45:37 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
```

 <span data-ttu-id="318f6-208">**Registro de ULS de SharePoint, últimas 48 horas**</span><span class="sxs-lookup"><span data-stu-id="318f6-208">**SharePoint ULS Log, last 48 hours**</span></span>

 <span data-ttu-id="318f6-209">El comando siguiente devolverá mensajes de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] del registro de ULS creados en las últimas 48 horas.</span><span class="sxs-lookup"><span data-stu-id="318f6-209">The following command will return [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] messages from the ULS log that were created in the last 48 hours.</span></span> <span data-ttu-id="318f6-210">Ajuste el parámetro addhours según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="318f6-210">Adjust the addhours parameter for your need.</span></span>

```powershell
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid,level, message | Format-Table -Property * -AutoSize | Out-Default
```

 <span data-ttu-id="318f6-211">La variación siguiente del comando solo devuelve eventos del registro para la categoría de **actualización de datos** .</span><span class="sxs-lookup"><span data-stu-id="318f6-211">The following variation of the command only returns log events for the **data refresh** category.</span></span>

```powershell
Get-SPLogEvent -starttime(Get-Date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message
```

```Output
Timestamp   : 4/14/2014 7:15:01 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 43
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : The following error occurred when working with the service application, Default PowerPivot Service Application. Skipping the service application..

Timestamp   : 4/14/2014 7:15:02 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 99
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : EXCEPTION: System.TimeoutException: The request channel timed out while waiting for a reply after 00:00:47.0625313. Increase the timeout value passed to 
              the call to Request or increase the SendTimeout value on the Binding. The time allotted to this operation may have been a portion of a longer timeout. 
              ---> System.TimeoutException: The HTTP request to 'http://localhost:32843/SecurityTokenServiceApplication/securitytoken.svc/actas' has exceeded the 
              allotted timeout of 00:00:54.5930000. The time allotted to this operation may have been a portion of a longer timeout. ---> System.Net.WebException: The 
              operation has timed out     at System.Net.HttpWebRequest.GetResponse()     at 
              System.ServiceModel.Channels.HttpChannelFactory`1.HttpRequestChannel.HttpChannelRequest.WaitForReply(TimeSpan timeout...
```

##  <a name="msolap-provider"></a><a name="bkmk_msolap"></a><span data-ttu-id="318f6-212">Proveedor MSOLAP</span><span class="sxs-lookup"><span data-stu-id="318f6-212">MSOLAP Provider</span></span>
 <span data-ttu-id="318f6-213">Compruebe el proveedor MSOLAP.</span><span class="sxs-lookup"><span data-stu-id="318f6-213">Verify the provider MSOLAP provider.</span></span> [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]<span data-ttu-id="318f6-214">y [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] requieren msolap. 5.</span><span class="sxs-lookup"><span data-stu-id="318f6-214">and [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] require MSOLAP.5.</span></span>

```powershell
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default
```

```Output
ProviderId ProviderType Description
---------- ------------ -----------
MSOLAP     Oledb        Microsoft OLE DB Provider for OLAP Services     
MSOLAP.3   Oledb        Microsoft OLE DB Provider for OLAP Services 9.0 
MSOLAP.4   Oledb        Microsoft OLE DB Provider for OLAP Services 10.0
MSOLAP.5   Oledb        Microsoft OLE DB Provider for OLAP Services 11.0
```

 <span data-ttu-id="318f6-215">Para más información, consulte [Instalar el proveedor OLE DB de Analysis Services en servidores de SharePoint](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) y [Agregar MSOLAP.5 como proveedor de datos de confianza en Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span><span class="sxs-lookup"><span data-stu-id="318f6-215">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) and [Add MSOLAP.5 as a Trusted Data Provider in Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span></span>

##  <a name="adomdnet-client-library"></a><a name="bkmk_adomd"></a><span data-ttu-id="318f6-216">Biblioteca de cliente de ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="318f6-216">ADOMD.Net client Library</span></span>

```powershell
Get-WMIObject -Class win32_product | Where-Object {$_.name -Like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | out-default
```

```Output
name                                                  version      vendor
----                                                  -------      ------
Microsoft SQL Server 2008 Analysis Services ADOMD.NET 10.1.2531.0  Microsoft Corporation
Microsoft SQL Server 2005 Analysis Services ADOMD.NET 9.00.1399.06 Microsoft Corporation
```

 <span data-ttu-id="318f6-217">Para obtener más información, vea [Instalar ADOMD.NET en servidores front-end web ejecutando Administración central](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="318f6-217">For more information, see [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>

##  <a name="health-data-collection-rules"></a><a name="bkmk_health_collection"></a><span data-ttu-id="318f6-218">Reglas de recopilación de datos de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="318f6-218">Health Data Collection Rules</span></span>
 <span data-ttu-id="318f6-219">Compruebe que el **Estado** está en línea y que **Habilitado** es True.</span><span class="sxs-lookup"><span data-stu-id="318f6-219">Verify the **Status** is Online and **Enabled** is True.</span></span>

```powershell
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -Like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                         Status Enabled TableName                   DaysToKeepDetailedData
----                         ------ ------- ---------                   ----------------------
PowerPivot Connections       OnlineTrue AnalysisServicesConnections  14
PowerPivot Load Data Usage   Online    True AnalysisServicesLoads                           14
PowerPivot Query Usage       Online    True AnalysisServicesRequests                        14
PowerPivot Unload Data Usage Online    True AnalysisServicesUnloads                         14
```

 <span data-ttu-id="318f6-220">Para obtener más información, consulte [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="318f6-220">For more information, see [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span></span>

##  <a name="solutions"></a><a name="bkmk_solutions"></a><span data-ttu-id="318f6-221">Solución</span><span class="sxs-lookup"><span data-stu-id="318f6-221">Solutions</span></span>
 <span data-ttu-id="318f6-222">Si los demás componentes están en línea, puede omitir la comprobación de las soluciones.</span><span class="sxs-lookup"><span data-stu-id="318f6-222">If the other components are online then you can skip verifying the solutions.</span></span> <span data-ttu-id="318f6-223">Sin embargo, si faltan reglas de mantenimiento, compruebe que las dos soluciones existen y mostraban Compruebe que las dos soluciones de PowerPivot están **En línea** e **Implementada**.</span><span class="sxs-lookup"><span data-stu-id="318f6-223">If however the Health rules are missing, verify the two solutions exist and showed Verify the two PowerPivot solutions are **Online** and **Deployed**.</span></span>

```powershell
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

<span data-ttu-id="318f6-224">SharePoint 2013:</span><span class="sxs-lookup"><span data-stu-id="318f6-224">SharePoint 2013:</span></span>

```Output
Name                                 Status Deployed        DeploymentState DeployedServers
----                                 ------ --------        --------------- ---------------
powerpivotfarm14solution.wsp         Online     True         GlobalDeployed {UETESTA00}
powerpivotfarmsolution.wsp           Online     True         GlobalDeployed {UETESTA00}
powerpivotwebapplicationsolution.wsp Online     True WebApplicationDeployed {UETESTA00}
```

<span data-ttu-id="318f6-225">SharePoint 2010:</span><span class="sxs-lookup"><span data-stu-id="318f6-225">SharePoint 2010:</span></span>

```Output
Name                 Status Deployed        DeploymentState DeployedServers 
----                 ------ --------        --------------- --------------- 
powerpivotfarm.wsp   Online     True         GlobalDeployed {uesql11spoint2}
powerpivotwebapp.wsp Online     True WebApplicationDeployed {uesql11spoint2}
```

 <span data-ttu-id="318f6-226">Para obtener más información sobre cómo implementar soluciones de SharePoint, vea [Implementación de paquetes de solución (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span><span class="sxs-lookup"><span data-stu-id="318f6-226">For more information on how to deploy SharePoint solutions, see [Deploy solution packages (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span></span>

##  <a name="manual-verification-steps"></a><a name="bkmk_manual"></a><span data-ttu-id="318f6-227">Pasos de comprobación manual</span><span class="sxs-lookup"><span data-stu-id="318f6-227">Manual Verification Steps</span></span>
 <span data-ttu-id="318f6-228">En esta sección se describen los pasos de comprobación que no se pueden completar mediante cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="318f6-228">This section describes verification steps that cannot be completed with PowerShell cmdlets.</span></span>

 <span data-ttu-id="318f6-229">**Actualización de datos programada:** configure la programación de actualización de un libro en **También actualizar lo más rápido posible**.</span><span class="sxs-lookup"><span data-stu-id="318f6-229">**Scheduled Data Refresh:** Configure the refresh schedule a workbook to **Also refresh as soon as possible**.</span></span>  <span data-ttu-id="318f6-230">Para obtener más información, vea la sección "comprobar la actualización de datos" de [programación de actualización de datos y orígenes de datos que no admiten la autenticación de Windows &#40;PowerPivot para SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="318f6-230">For more information, see the "Verify Data Refresh" section of [Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span></span>

##  <a name="more-resources"></a><a name="bkmk_more_resources"></a><span data-ttu-id="318f6-231">Más recursos</span><span class="sxs-lookup"><span data-stu-id="318f6-231">More Resources</span></span>
 <span data-ttu-id="318f6-232">[Cmdlets de administración de servidor web (IIS) en Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span><span class="sxs-lookup"><span data-stu-id="318f6-232">[Web Server (IIS) Administration Cmdlets in Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span></span>

 <span data-ttu-id="318f6-233">[PowerShell para comprobar el estado de servicios, sitios de IIS y grupos de aplicaciones en SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span><span class="sxs-lookup"><span data-stu-id="318f6-233">[PowerShell to check services, IIS sites and Application Pool status in SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span></span>

 <span data-ttu-id="318f6-234">[Referencia de Windows PowerShell para SharePoint 2013](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span><span class="sxs-lookup"><span data-stu-id="318f6-234">[Windows PowerShell for SharePoint 2013 reference](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span></span>

 <span data-ttu-id="318f6-235">[Referencia de Windows PowerShell para SharePoint Foundation 2010](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="318f6-235">[Windows PowerShell for SharePoint Foundation 2010 reference](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span></span>

 <span data-ttu-id="318f6-236">[Administración de Servicios de Excel con Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="318f6-236">[Manage Excel Services with Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span></span>

 [<span data-ttu-id="318f6-237">Ver y leer los archivos de registro de instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="318f6-237">View and Read SQL Server Setup Log Files</span></span>](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)

 [<span data-ttu-id="318f6-238">Usar el cmdlet Get-Eventlog</span><span class="sxs-lookup"><span data-stu-id="318f6-238">Use the Get-EvenLog cmdlet</span></span>](https://technet.microsoft.com/library/ee176846.aspx)

##  <a name="full-powershell-script"></a><a name="bkmk_full_script"></a><span data-ttu-id="318f6-239">Script completo de PowerShell</span><span class="sxs-lookup"><span data-stu-id="318f6-239">Full PowerShell Script</span></span>
 <span data-ttu-id="318f6-240">El siguiente script contiene todos los comandos de las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="318f6-240">The Following script contains all of the commands from the previous sections.</span></span> <span data-ttu-id="318f6-241">El script ejecuta los comandos en el mismo orden en que se presentan en este tema.</span><span class="sxs-lookup"><span data-stu-id="318f6-241">The script runs the commands in the same order as they are presented in this topic.</span></span> <span data-ttu-id="318f6-242">El script contiene alguna variaciones opcionales de los comandos indicadas en este tema por si necesita algún filtrado adicional.</span><span class="sxs-lookup"><span data-stu-id="318f6-242">The script contains some optional variations of the commands noted in this topic in case you need additional filtering.</span></span> <span data-ttu-id="318f6-243">Las variaciones se deshabilitan con un carácter de comentario (#).</span><span class="sxs-lookup"><span data-stu-id="318f6-243">The variations are disabled with a comment character (#).</span></span> <span data-ttu-id="318f6-244">El script también incluye algunas instrucciones para comprobar el modo de SharePoint de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="318f6-244">The script also includes some statements for verifying [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="318f6-245">Las instrucciones de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] se deshabilitan con un carácter de comentario (#).</span><span class="sxs-lookup"><span data-stu-id="318f6-245">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] statements are disabled with a comment character (#).</span></span>

```powershell
# This script audits services related to PowerPivot for SharePoint
$starttime = Get-Date
write-host -foregroundcolor DarkGray StartTime $starttime

Write-Host  "Import the SharePoint PowerShell snappin"
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0

Write-Host -ForegroundColor Green "Analysis Services Windows Service"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "PowerPivotEngineService and PowerPivotSystemService"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"

Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotSystemService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotEngineService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

#Write-Host -ForegroundColor Green "Service Instances - optional if you want to associate services with the server"
#Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
#Get-SPServiceInstance | select typename, status, server, service, instance | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel*" -or $_.TypeName -like "*Analysis Services*"} | format-table -property * -autosize | out-default
#Get-PowerPivotEngineServiceInstance  | select typename, ASServername, status, server, service, instance
#Get-PowerPivotSystemServiceInstance  | select typename, ASSServerName, status, server, service, instance

Write-Host -ForegroundColor Green "PowerPivot And Excel Service Applications"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename,  DisplayName, status

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot Service Application pool"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
# the following assumes there is only 1 PowerPivot Service Application, and returns that application's pool name.  if you have more than one, use the 2nd version
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)
Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot and Excel Service Application Proxy"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPServiceApplicationProxy |  Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPServiceApplicationProxy |  select typename, status, unattendedaccount, displayname | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*Reporting Services*" -or $_.TypeName -like "*excel services*"} | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "DATABASES"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPDatabase | select name, status, server, typename | where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*" -or $_.TypeName -like "*ReportingServices*"}

Write-Host -ForegroundColor Green "features"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPFeature | select displayname, status, scope, farm | where {$_.displayName -like "*powerpivot*" -or $_.displayName -like "*ReportServer*"}  | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "Timer Jobs (Job Definitions) -- list is the same as seen in the 'Review timer job definitions' section of the management dashboard"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPTimerJob | Where {$_.service -like "*power*" -or $_.service -like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "health rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "Windows Event Log data MSSQL$POWERPIVOT and "
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -Property * -autosize | Out-Default
#The following is the same command but with the Inforamtion events filtered out.
#Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*" -and ($_.entrytype -match "error" -or $_.entrytype -match "critical" -or $_.entrytype -match "warning")}  |select timegenerated, entrytype , source, message | format-table -property * -autosize | out-default

#Write-Host ""
Write-Host -ForegroundColor Green "ULS Log data"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message | Format-Table -Property * -AutoSize | Out-Default
#the following example filters for the category 'data refresh'
#Get-SPLogEvent -starttime(get-date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | select timestamp, area, category, eventid, level, correlation, message

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "MSOLAP data provider for Excel Servivces, service application"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "ADOMD.net client library"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-WMIObject -Class win32_product | Where-Object {$_.name -like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Usage Data Rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Solutions"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time
```
