---
title: Implementar soluciones de PowerPivot en SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f202a2b7-34e0-43aa-90d5-c9a085a37c32
author: minewiskan
ms.author: owend
ms.openlocfilehash: 043647988598f932b70cc06e6bb5492d66864372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675007"
---
# <a name="deploy-powerpivot-solutions-to-sharepoint"></a><span data-ttu-id="d13fe-102">Implementar las soluciones de PowerPivot en SharePoint</span><span class="sxs-lookup"><span data-stu-id="d13fe-102">Deploy PowerPivot Solutions to SharePoint</span></span>
  <span data-ttu-id="d13fe-103">Use las instrucciones siguientes para implementar manualmente dos paquetes de soluciones que agregan características de PowerPivot a un entorno de SharePoint Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d13fe-103">Use the following instructions to manually deploy two solution packages that add PowerPivot features to a SharePoint Server 2010 environment.</span></span> <span data-ttu-id="d13fe-104">La implementación de soluciones es un paso necesario para configurar PowerPivot para SharePoint en un servidor SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="d13fe-104">Deploying the solutions is a required step for configuring PowerPivot for SharePoint on a SharePoint 2010 server.</span></span> <span data-ttu-id="d13fe-105">Para ver la lista completa de los pasos necesarios, consulte [Administración y configuración de servidores de PowerPivot en administración central](power-pivot-server-administration-and-configuration-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="d13fe-105">To view the complete list of required steps, see [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md).</span></span>  
  
 <span data-ttu-id="d13fe-106">O bien, puede usar la Herramienta de configuración de PowerPivot para implementar las soluciones.</span><span class="sxs-lookup"><span data-stu-id="d13fe-106">Alternatively, you can use the PowerPivot Configuration Tool to deploy the solutions.</span></span> <span data-ttu-id="d13fe-107">Usar la herramienta de configuración es más fácil y más eficiente para una única instalación de servidor, pero podría ser conveniente usar Administración central y PowerShell si prefiere usar una herramienta conocida o si va a configurar varias características al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d13fe-107">Using the configuration tool is easier and more efficient for a single server installation, but you might want to use Central Administration and PowerShell if you prefer using a familiar tool or if you are configuring multiple features at the same time.</span></span> <span data-ttu-id="d13fe-108">Para obtener más información acerca del uso de la herramienta de configuración, vea [PowerPivot herramientas de configuración](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d13fe-108">For more information about using the configuration tool, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
 <span data-ttu-id="d13fe-109">Antes de implementar las soluciones, primero debe instalar PowerPivot para SharePoint usando los medios de instalación de SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="d13fe-109">Before deploying the solutions, you must first install PowerPivot for SharePoint using the SQL Server 2012 installation media.</span></span> <span data-ttu-id="d13fe-110">El programa de instalación de SQL Server instala los paquetes de soluciones que está a punto de implementar.</span><span class="sxs-lookup"><span data-stu-id="d13fe-110">SQL Server Setup installs the solution packages that you are about to deploy.</span></span>  
  
 <span data-ttu-id="d13fe-111">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="d13fe-111">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="d13fe-112">Requisito previo: comprobar que la aplicación Web usa la autenticación de modo clásico</span><span class="sxs-lookup"><span data-stu-id="d13fe-112">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>](#bkmk_classic)  
  
 [<span data-ttu-id="d13fe-113">Paso 1: implementar la solución de granja de servidores</span><span class="sxs-lookup"><span data-stu-id="d13fe-113">Step 1: Deploy the Farm Solution</span></span>](#bkmk_farm)  
  
 [<span data-ttu-id="d13fe-114">Pas 2: implementar la solución de aplicación web de PowerPivot para Administración central</span><span class="sxs-lookup"><span data-stu-id="d13fe-114">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>](#deployCA)  
  
 [<span data-ttu-id="d13fe-115">Paso 3: implementar la solución de aplicación web de PowerPivot en otras aplicaciones web</span><span class="sxs-lookup"><span data-stu-id="d13fe-115">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>](#deployUI)  
  
 [<span data-ttu-id="d13fe-116">Volver a implementar o retirar la solución</span><span class="sxs-lookup"><span data-stu-id="d13fe-116">Redeploy or retract the Solution</span></span>](#retract)  
  
 [<span data-ttu-id="d13fe-117">Acerca de las soluciones de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="d13fe-117">About the PowerPivot Solutions</span></span>](#intro)  
  
##  <a name="prerequisite-verify-the-web-application-uses-classic-mode-authentication"></a><a name="bkmk_classic"></a> <span data-ttu-id="d13fe-118">Requisitos previos: compruebe que la aplicación web usa el Modo clásico de autenticación</span><span class="sxs-lookup"><span data-stu-id="d13fe-118">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>  
 <span data-ttu-id="d13fe-119">PowerPivot para SharePoint solo se admite en las aplicaciones Web que usan el modo clásico de autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="d13fe-119">PowerPivot for SharePoint is only supported for web applications that use Windows-classic mode authentication.</span></span> <span data-ttu-id="d13fe-120">Para comprobar si la aplicación usa el modo clásico, ejecute el siguiente cmdlet de PowerShell desde el **Shell de administración de sharepoint 2010**, reemplazando `http://<top-level site name>` por el nombre de su sitio de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="d13fe-120">To check whether the application uses Classic mode, run the following PowerShell cmdlet from the **SharePoint 2010 Management Shell**, replacing `http://<top-level site name>` with the name of your SharePoint site:</span></span>  
  
```powershell
Get-SPWebApplication http://<top-level site name> | Format-List UseClaimsAuthentication  
```  
  
 <span data-ttu-id="d13fe-121">Se debería devolver el valor **false**.</span><span class="sxs-lookup"><span data-stu-id="d13fe-121">The return value should be **false**.</span></span> <span data-ttu-id="d13fe-122">Si es **true**, no se puede tener acceso a los datos PowerPivot con esta aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="d13fe-122">If it is **true**, you cannot access PowerPivot data with this web application.</span></span>  
  
##  <a name="step-1-deploy-the-farm-solution"></a><a name="bkmk_farm"></a> <span data-ttu-id="d13fe-123">Paso 1: implementar la solución de granja</span><span class="sxs-lookup"><span data-stu-id="d13fe-123">Step 1: Deploy the Farm Solution</span></span>  
 <span data-ttu-id="d13fe-124">En esta sección se muestra cómo implementar soluciones con PowerShell, pero también puede utilizar la Herramienta de configuración de PowerPivot para completar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="d13fe-124">This section shows you how to deploy solutions using PowerShell, but you can also use the PowerPivot Configuration Tool to complete this task.</span></span> <span data-ttu-id="d13fe-125">Para obtener más información, vea [configurar o reparar PowerPivot para SharePoint 2010 &#40;herramienta de configuración de PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="d13fe-125">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="d13fe-126">Esta tarea solo tiene que realizarse una vez, después de instalar PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d13fe-126">This task only needs to be performed once, after you install PowerPivot for SharePoint.</span></span>  
  
1.  <span data-ttu-id="d13fe-127">En un servidor que tenga una instalación de PowerPivot para SharePoint, abra un shell de administración de SharePoint 2010 con la opción **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="d13fe-127">On a server that has an installation of PowerPivot for SharePoint, open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="d13fe-128">Ejecute el siguiente cmdlet para agregar la solución de granja.</span><span class="sxs-lookup"><span data-stu-id="d13fe-128">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="d13fe-129">El cmdlet devuelve el nombre de la solución, su identificador de solución y Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="d13fe-129">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="d13fe-130">En el paso siguiente, implementará la solución.</span><span class="sxs-lookup"><span data-stu-id="d13fe-130">In the next step, you will deploy the solution.</span></span>  
  
3.  <span data-ttu-id="d13fe-131">Ejecute el siguiente cmdlet para implementar la solución de granja:</span><span class="sxs-lookup"><span data-stu-id="d13fe-131">Run the next cmdlet to deploy the farm solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
##  <a name="step-2-deploy-the-powerpivot-web-application-solution-to-central-administration"></a><a name="deployCA"></a><span data-ttu-id="d13fe-132">Paso 2: implementar la solución de aplicación Web de PowerPivot para administración central</span><span class="sxs-lookup"><span data-stu-id="d13fe-132">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>  
 <span data-ttu-id="d13fe-133">Después de implementar la solución de granja, debe implementar la solución de aplicación web para Administración central.</span><span class="sxs-lookup"><span data-stu-id="d13fe-133">After you deploy the farm solution, you must deploy the Web application solution to Central Administration.</span></span> <span data-ttu-id="d13fe-134">Este paso agrega el Panel de administración de PowerPivot a Administración central.</span><span class="sxs-lookup"><span data-stu-id="d13fe-134">This step adds the PowerPivot Management Dashboard to Central Administration.</span></span>  
  
1.  <span data-ttu-id="d13fe-135">Abra un shell de administración de SharePoint 2010 utilizando la opción **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="d13fe-135">Open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="d13fe-136">Ejecute el siguiente cmdlet para crear una referencia a Administración central:</span><span class="sxs-lookup"><span data-stu-id="d13fe-136">Run the following cmdlet to create a reference to Central Administration:</span></span>  
  
    ```powershell
    $centralAdmin = $(Get-SPWebApplication -IncludeCentralAdministration | Where { $_.IsAdministrationWebApplication -eq $TRUE})  
    ```  
  
3.  <span data-ttu-id="d13fe-137">Ejecute el siguiente cmdlet para agregar la solución de granja.</span><span class="sxs-lookup"><span data-stu-id="d13fe-137">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotWebApp.wsp"  
    ```  
  
     <span data-ttu-id="d13fe-138">El cmdlet devuelve el nombre de la solución, su identificador de solución y Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="d13fe-138">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="d13fe-139">En el paso siguiente, implementará la solución.</span><span class="sxs-lookup"><span data-stu-id="d13fe-139">In the next step, you will deploy the solution.</span></span>  
  
4.  <span data-ttu-id="d13fe-140">Ejecute el siguiente cmdlet para instalar la solución de aplicación web en Administración central.</span><span class="sxs-lookup"><span data-stu-id="d13fe-140">Run the next cmdlet to install the web application solution to Central Administration.</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotWebApp.wsp -GACDeployment -Force -WebApplication $centralAdmin  
    ```  
  
 <span data-ttu-id="d13fe-141">Ahora que la solución de aplicación web se implementa en Administración central, puede usar Administración central para completar el resto de pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="d13fe-141">Now that the web application solution is deployed to Central Administration, you can use Central Administration to complete all remaining configuration steps.</span></span>  
  
##  <a name="step-3-deploy-the-powerpivot-web-application-solution-to-other-web-applications"></a><a name="deployUI"></a><span data-ttu-id="d13fe-142">Paso 3: implementar la solución de aplicación Web de PowerPivot en otras aplicaciones Web</span><span class="sxs-lookup"><span data-stu-id="d13fe-142">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>  
 <span data-ttu-id="d13fe-143">En la tarea anterior, implementó Powerpivotwebapp.wsp en Administración central.</span><span class="sxs-lookup"><span data-stu-id="d13fe-143">In the previous task, you deployed Powerpivotwebapp.wsp to Central Administration.</span></span> <span data-ttu-id="d13fe-144">En esta sección, implementa powerpivotwebapp.wsp en cada una de las aplicaciones web existentes que admiten el acceso a datos PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-144">In this section, you deploy the powerpivotwebapp.wsp on each existing web application that supports PowerPivot data access.</span></span> <span data-ttu-id="d13fe-145">Si agrega más aplicaciones web más adelante, asegúrese de repetir este paso para esas aplicaciones web adicionales.</span><span class="sxs-lookup"><span data-stu-id="d13fe-145">If you add more web applications later, be sure to repeat this step for those additional web applications.</span></span>  
  
1.  <span data-ttu-id="d13fe-146">En Administración central, en Configuración del sistema, haga clic en **Administrar soluciones del conjunto de servidores**.</span><span class="sxs-lookup"><span data-stu-id="d13fe-146">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="d13fe-147">Haga clic en **powerpivotwebapp. wsp**.</span><span class="sxs-lookup"><span data-stu-id="d13fe-147">Click **powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="d13fe-148">Haga clic en **Implementar solución**.</span><span class="sxs-lookup"><span data-stu-id="d13fe-148">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="d13fe-149">En **¿cómo implementar en?**, seleccione la aplicación Web de SharePoint para la que desea agregar compatibilidad con las características de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-149">In **Deploy To?**, select the SharePoint web application for which you want to add PowerPivot feature support.</span></span>  
  
5.  <span data-ttu-id="d13fe-150">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="d13fe-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d13fe-151">Repita el mismo proceso con las demás aplicaciones web de SharePoint que también admitirán el acceso a datos PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-151">Repeat for other SharePoint web applications that will also support PowerPivot data access.</span></span>  
  
##  <a name="redeploy-or-retract-the-solution"></a><a name="retract"></a> <span data-ttu-id="d13fe-152">Volver a implementar o retirar la solución</span><span class="sxs-lookup"><span data-stu-id="d13fe-152">Redeploy or retract the Solution</span></span>  
 <span data-ttu-id="d13fe-153">Aunque Administración central de SharePoint proporciona la retirada de la solución, no necesita retirar el archivo powerpivotwebapp.wsp a menos que esté solucionando problemas de una instalación o de la implementación de una revisión.</span><span class="sxs-lookup"><span data-stu-id="d13fe-153">Although SharePoint Central Administration provides solution retraction, you do not need to retract the powerpivotwebapp.wsp file unless you are systematically troubleshooting an installation or patch deployment problem.</span></span>  
  
1.  <span data-ttu-id="d13fe-154">En Administración central de SharePoint 2010, en Configuración del sistema, haga clic en **Administrar las soluciones de la granja**.</span><span class="sxs-lookup"><span data-stu-id="d13fe-154">In SharePoint 2010 Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="d13fe-155">Haga clic en **Powerpivotwebapp.wsp**.</span><span class="sxs-lookup"><span data-stu-id="d13fe-155">Click **Powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="d13fe-156">Haga clic en **Retirar solución**.</span><span class="sxs-lookup"><span data-stu-id="d13fe-156">Click **Retract Solution**.</span></span>  
  
 <span data-ttu-id="d13fe-157">Si encuentra problemas en la implementación del servidor que se reenvían a la solución de granja de servidores, puede volver a implementarla ejecutando la opción **reparar** en la herramienta de configuración de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-157">If you encounter server deployment issues that you trace back to the farm solution, you can redeploy it by running the **Repair** option in the PowerPivot Configuration Tool.</span></span> <span data-ttu-id="d13fe-158">Las operaciones de reparación mediante la herramienta se prefieren porque requieren menos pasos por su parte.</span><span class="sxs-lookup"><span data-stu-id="d13fe-158">Repair operations via the tool is preferred because it requires fewer steps on your part.</span></span> <span data-ttu-id="d13fe-159">Para obtener más información, vea [configurar o reparar PowerPivot para SharePoint 2010 &#40;herramienta de configuración de PowerPivot&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="d13fe-159">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="d13fe-160">Si aun así desea implementar de nuevo todas las soluciones, asegúrese de hacerlo en este orden:</span><span class="sxs-lookup"><span data-stu-id="d13fe-160">If you still want to re-deploy all solutions, be sure to do so in this order:</span></span>  
  
1.  <span data-ttu-id="d13fe-161">Retirar la solución de aplicación web de PowerPivot de todas las aplicaciones web de SharePoint que la utilizan.</span><span class="sxs-lookup"><span data-stu-id="d13fe-161">Retract the PowerPivot Web application solution from all SharePoint web applications that use it.</span></span>  
  
2.  <span data-ttu-id="d13fe-162">Retirar la solución de granja de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-162">Retract the PowerPivot farm solution.</span></span>  
  
3.  <span data-ttu-id="d13fe-163">Volver a implementar la solución de granja de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-163">Redeploy the PowerPivot farm solution.</span></span>  
  
4.  <span data-ttu-id="d13fe-164">Volver a implementar la solución de aplicación web de PowerPivot en todas las aplicaciones web de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d13fe-164">Redeploy the PowerPivot Web application solution to all SharePoint web applications.</span></span>  
  
##  <a name="about-the-powerpivot-solutions"></a><a name="intro"></a><span data-ttu-id="d13fe-165">Acerca de las soluciones de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="d13fe-165">About the PowerPivot Solutions</span></span>  
 <span data-ttu-id="d13fe-166">PowerPivot para SharePoint usa dos paquetes de soluciones para implementar sus páginas de aplicaciones y archivos de programas en la granja y en aplicaciones web individuales.</span><span class="sxs-lookup"><span data-stu-id="d13fe-166">PowerPivot for SharePoint uses two solution packages to deploy its application pages and program files to the farm and to individual web applications.</span></span>  
  
-   <span data-ttu-id="d13fe-167">La solución de granja es global.</span><span class="sxs-lookup"><span data-stu-id="d13fe-167">The farm solution is global.</span></span> <span data-ttu-id="d13fe-168">Se implementa una vez y después se convierte en disponible automáticamente para todos los servidores nuevos de PowerPivot para SharePoint que se agreguen posteriormente a la granja.</span><span class="sxs-lookup"><span data-stu-id="d13fe-168">It is deployed once and then becomes automatically available to any new PowerPivot for SharePoint servers that you add to the farm later.</span></span>  
  
-   <span data-ttu-id="d13fe-169">La solución de aplicación Web es específica de la aplicación y se debe implementar en cada aplicación Web de la granja, incluida la aplicación Web Administración central.</span><span class="sxs-lookup"><span data-stu-id="d13fe-169">The web application solution is application-specific and must be deployed to each web application in the farm, including the Central Administration web application.</span></span>  
  
 <span data-ttu-id="d13fe-170">Cada solución se implementa de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="d13fe-170">Each solution is deployed differently.</span></span>  <span data-ttu-id="d13fe-171">La solución de granja se implementa una vez, tras instalar la primera instancia de PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d13fe-171">The farm solution is deployed once, after the first PowerPivot for SharePoint instance is installed.</span></span> <span data-ttu-id="d13fe-172">Para implementar la solución de granja, use los cmdlets de PowerShell o la Herramienta de configuración de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-172">To deploy the farm solution, you use the PowerPivot Configuration Tool or PowerShell cmdlets.</span></span>  
  
 <span data-ttu-id="d13fe-173">La solución de aplicación Web se implementa inicialmente en Administración central, seguida de las siguientes implementaciones de la solución en cualquier aplicación Web adicional que vaya a admitir solicitudes de los datos PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-173">The web application solution is initially deployed to Central Administration, followed by subsequent solution deployments to any additional web applications that will support requests for PowerPivot data.</span></span> <span data-ttu-id="d13fe-174">Para implementar la solución de aplicación web de Administración central, debe usar el cmdlet de PowerShell o de la Herramienta de configuración de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-174">To deploy the web application solution to Central Administration, you must use the PowerPivot Configuration Tool or PowerShell cmdlet.</span></span> <span data-ttu-id="d13fe-175">Para todas las demás aplicaciones Web, puede implementar la solución de aplicación Web mediante Administración central o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d13fe-175">For all other web applications, you can deploy the web application solution manually using Central Administration or PowerShell.</span></span>  
  
|<span data-ttu-id="d13fe-176">Solución</span><span class="sxs-lookup"><span data-stu-id="d13fe-176">Solution</span></span>|<span data-ttu-id="d13fe-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="d13fe-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d13fe-178">Powerpivotfarm.wsp</span><span class="sxs-lookup"><span data-stu-id="d13fe-178">Powerpivotfarm.wsp</span></span>|<span data-ttu-id="d13fe-179">Agrega los archivos Microsoft.AnalysisServices.SharePoint.Integration.dll al ensamblado global.</span><span class="sxs-lookup"><span data-stu-id="d13fe-179">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="d13fe-180">Agrega Microsoft.AnalysisServices.ChannelTransport.dll al ensamblado global.</span><span class="sxs-lookup"><span data-stu-id="d13fe-180">Adds Microsoft.AnalysisServices.ChannelTransport.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="d13fe-181">Instala las características y los archivos de recursos, y registra los tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="d13fe-181">Installs features and resources files, and registers content types.</span></span><br /><br /> <span data-ttu-id="d13fe-182">Agrega plantillas de biblioteca para las bibliotecas Galería de PowerPivot y Fuentes de datos.</span><span class="sxs-lookup"><span data-stu-id="d13fe-182">Adds library templates for PowerPivot Gallery and Data Feed libraries.</span></span><br /><br /> <span data-ttu-id="d13fe-183">Agrega las páginas de aplicación para la configuración de aplicación de servicio, el panel de administración de PowerPivot, actualización de datos y la Galería de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-183">Adds application pages for service application configuration, PowerPivot Management Dashboard, data refresh, and PowerPivot Gallery.</span></span>|  
|<span data-ttu-id="d13fe-184">powerpivotwebapp.wsp</span><span class="sxs-lookup"><span data-stu-id="d13fe-184">Powerpivotwebapp.wsp</span></span>|<span data-ttu-id="d13fe-185">Agrega los archivos de recursos Microsoft.AnalysisServices.SharePoint.Integration.dll a la carpeta de extensiones de servidor web del servidor front-end web.</span><span class="sxs-lookup"><span data-stu-id="d13fe-185">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll resources files to the web server extensions folder on the Web front-end.</span></span><br /><br /> <span data-ttu-id="d13fe-186">Agrega el Servicio web PowerPivot al servidor front-end web.</span><span class="sxs-lookup"><span data-stu-id="d13fe-186">Adds PowerPivot Web service to the Web-front end.</span></span><br /><br /> <span data-ttu-id="d13fe-187">Agrega la generación de imágenes en miniatura para la Galería de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="d13fe-187">Adds thumbnail image generation for PowerPivot Gallery.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d13fe-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d13fe-188">See Also</span></span>  
 <span data-ttu-id="d13fe-189">[PowerPivot para SharePoint de actualización](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="d13fe-189">[Upgrade PowerPivot for SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="d13fe-190">[Administración y configuración del servidor de PowerPivot en administración central](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="d13fe-190">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 [<span data-ttu-id="d13fe-191">Configuración de PowerPivot mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d13fe-191">PowerPivot Configuration using Windows PowerShell</span></span>](power-pivot-configuration-using-windows-powershell.md)  
