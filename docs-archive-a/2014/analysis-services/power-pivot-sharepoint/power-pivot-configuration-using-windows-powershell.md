---
title: Configuración de PowerPivot mediante Windows PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4d83e53e-04f1-417d-9039-d9e81ae0483d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 83b42da3e676a291bb021c02ee52e9a810207397
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676194"
---
# <a name="powerpivot-configuration-using-windows-powershell"></a><span data-ttu-id="ebc68-102">Configuración de PowerPivot mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebc68-102">PowerPivot Configuration using Windows PowerShell</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="ebc68-103">incluye cmdlets de Windows PowerShell que puede usar para configurar una instalación de [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebc68-103">includes Windows PowerShell cmdlets that you can use to configure an installation of [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span></span> <span data-ttu-id="ebc68-104">Para configurar totalmente una instalación con PowerShell es necesario usar cmdlets de SharePoint y de PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ebc68-104">To fully configure an installation with PowerShell requires the use of both SharePoint cmdlets and PowerPivot for SharePoint cmdlets.</span></span> <span data-ttu-id="ebc68-105">Gran parte de la configuración se puede completar mediante una de las herramientas de [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ebc68-105">A majority of configuration can be completed using one of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] tools.</span></span> <span data-ttu-id="ebc68-106">Para obtener más información sobre las herramientas, vea [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ebc68-106">For more information on the tools, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ebc68-107">En el caso de una granja de servidores de SharePoint 2010, debe instalarse SharePoint 2010 SP1 antes de configurar PowerPivot para SharePoint o una granja de SharePoint que use un servidor de bases de datos de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ebc68-107">For a SharePoint 2010 farm, SharePoint 2010 SP1 must be installed before you can configure either PowerPivot for SharePoint, or a SharePoint farm that uses a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] database server.</span></span> <span data-ttu-id="ebc68-108">Si no ha instalado todavía el Service Pack, instálelo antes de empezar a configurar el servidor.</span><span class="sxs-lookup"><span data-stu-id="ebc68-108">If you have not yet installed the service pack, install it before you begin configuring the server.</span></span>  
  
## <a name="benefits-of-configuring-powerpivot-for-sharepoint-using-powershell"></a><span data-ttu-id="ebc68-109">Ventajas de configurar PowerPivot para SharePoint utilizando PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebc68-109">Benefits of Configuring PowerPivot for SharePoint Using PowerShell</span></span>  
 <span data-ttu-id="ebc68-110">Puede crear archivos de script de Windows PowerShell (.ps1) para automatizar las tareas de configuración.</span><span class="sxs-lookup"><span data-stu-id="ebc68-110">You can build Windows PowerShell script (.ps1) files to automate configuration tasks.</span></span> <span data-ttu-id="ebc68-111">Se recomienda este enfoque si se requieren pasos de instalación y configuración con script que se puedan ejecutar en cualquier servidor.</span><span class="sxs-lookup"><span data-stu-id="ebc68-111">This approach is recommended if you require scripted installation and configuration steps that you can run on any server.</span></span> <span data-ttu-id="ebc68-112">Puede que se necesite un script como parte de un plan de recuperación ante desastres para volver a generar un servidor en caso de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="ebc68-112">You might require such a script as part of a disaster recovery plan for rebuilding a server in the event of a hardware failure.</span></span>  
  
## <a name="view-a-list-of-the-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="ebc68-113">Ver una lista de los cmdlets de PowerPivot de un servidor</span><span class="sxs-lookup"><span data-stu-id="ebc68-113">View a list of the PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="ebc68-114">Para ver el contenido y ejemplos de los [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cmdlets, consulte [referencia de PowerShell para PowerPivot para SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span><span class="sxs-lookup"><span data-stu-id="ebc68-114">To see content and examples of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cmdlets, see [PowerShell Reference for PowerPivot for SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span></span>  
  
 <span data-ttu-id="ebc68-115">Para usar PowerShell con el fin de ver una lista de los cmdlets de PowerPivot:</span><span class="sxs-lookup"><span data-stu-id="ebc68-115">To use PowerShell to view a list of the PowerPivot cmdlets:</span></span>  
  
1.  <span data-ttu-id="ebc68-116">Abra el Shell de administración de SharePoint usando la opción **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="ebc68-116">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="ebc68-117">Escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebc68-117">Enter the following command:</span></span>  
  
    ```powershell
    Get-Help *powerpivot*  
    ```  
  
     <span data-ttu-id="ebc68-118">Debe ver una lista de cmdlets que incluyen PowerPivot en el nombre del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ebc68-118">You should see a list of cmdlets that include PowerPivot in the cmdlet name.</span></span> <span data-ttu-id="ebc68-119">Por ejemplo: `Get-PowerPivotServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="ebc68-119">For example `Get-PowerPivotServiceApplication`.</span></span> <span data-ttu-id="ebc68-120">El número de cmdlets disponibles depende de la versión de Analysis Services que está usando.</span><span class="sxs-lookup"><span data-stu-id="ebc68-120">The number of cmdlets available depends on the version of Analysis Services you are using.</span></span>  
  
    -   <span data-ttu-id="ebc68-121">10 cmdlets con el servidor de SQL Server 2012 SP1 Analysis Services configurado en modo de SharePoint, y SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="ebc68-121">10 cmdlets with SQL Server 2012 SP1 Analysis Services server configured in SharePoint mode, and SharePoint 2013.</span></span> <span data-ttu-id="ebc68-122">La versión de 2012 SP1 emplea una nueva arquitectura que permite que Analysis Server se ejecute fuera de la granja de servidores de SharePoint y necesita menos cmdlets de Windows PowerShell de administración.</span><span class="sxs-lookup"><span data-stu-id="ebc68-122">The 2012 SP1 version utilizes a new architecture that allows the Analysis Server to run outside the SharePoint farm and requires fewer management Windows PowerShell cmdlets.</span></span>  
  
    -   <span data-ttu-id="ebc68-123">17 cmdlets con el servidor de SQL Server 2012 Analysis Services configurado en modo de SharePoint, y SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="ebc68-123">17 cmdlets with SQL Server 2012 Analysis Services server configured in SharePoint mode, and SharePoint 2010.</span></span>  
  
     <span data-ttu-id="ebc68-124">Si no se devuelve ningún comando en la lista o aparece un mensaje de error similar a " `get-help could not find *powerpivot* in a help file in this session.` ", vea la sección siguiente de este tema para obtener instrucciones sobre cómo habilitar los cmdlets de PowerPivot en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ebc68-124">If no commands are returned in the list or you see an error message similar to "`get-help could not find *powerpivot* in a help file in this session.`", see the next section in this topic for instructions on how to enable the PowerPivot cmdlets on the server.</span></span>  
  
     <span data-ttu-id="ebc68-125">Todos los cmdlets tienen ayuda en pantalla.</span><span class="sxs-lookup"><span data-stu-id="ebc68-125">All cmdlets have online help.</span></span> <span data-ttu-id="ebc68-126">En el ejemplo siguiente se muestra cómo ver la ayuda en pantalla del cmdlet `New-PowerPivotServiceApplication`:</span><span class="sxs-lookup"><span data-stu-id="ebc68-126">The following example shows how to view the online help for the `New-PowerPivotServiceApplication` cmdlet:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Full  
    ```  
  
     <span data-ttu-id="ebc68-127">También puede ver solo los ejemplos utilizando la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ebc68-127">Alternatively, to view just the examples, use the following syntax:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Example  
    ```  
  
## <a name="enable-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="ebc68-128">Habilitar los cmdlets de PowerPivot en un servidor</span><span class="sxs-lookup"><span data-stu-id="ebc68-128">Enable PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="ebc68-129">Los cmdlets de PowerPivot están disponibles después de instalar PowerPivot para SharePoint e implementar la solución de granja.</span><span class="sxs-lookup"><span data-stu-id="ebc68-129">PowerPivot cmdlets are available after you install PowerPivot for SharePoint and deploy the farm solution.</span></span> <span data-ttu-id="ebc68-130">Las soluciones se implementan al ejecutar la herramienta de configuración de PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="ebc68-130">The solutions are deployed when you ran the PowerPivot Configuration tool.</span></span> <span data-ttu-id="ebc68-131">Siga estos pasos para habilitar el uso de cmdlets:</span><span class="sxs-lookup"><span data-stu-id="ebc68-131">Follow these steps to enable the use of cmdlets:</span></span>  
  
1.  <span data-ttu-id="ebc68-132">Abra el Shell de administración de SharePoint usando la opción **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="ebc68-132">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="ebc68-133">Ejecute el primer cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ebc68-133">Run the first cmdlet:</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="ebc68-134">El cmdlet devuelve el nombre de la solución, su identificador de solución y Deployed=False.</span><span class="sxs-lookup"><span data-stu-id="ebc68-134">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="ebc68-135">En el paso siguiente, implemente la solución.</span><span class="sxs-lookup"><span data-stu-id="ebc68-135">In the next step, you deploy the solution.</span></span>  
  
3.  <span data-ttu-id="ebc68-136">Ejecute el segundo cmdlet para implementar la solución:</span><span class="sxs-lookup"><span data-stu-id="ebc68-136">Run the second cmdlet to deploy the solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
4.  <span data-ttu-id="ebc68-137">Cierre la ventana.</span><span class="sxs-lookup"><span data-stu-id="ebc68-137">Close the window.</span></span> <span data-ttu-id="ebc68-138">Vuelva a abrirla utilizando de nuevo la opción **Ejecutar como administrador** .</span><span class="sxs-lookup"><span data-stu-id="ebc68-138">Reopen it, again using the **Run as Administrator** option.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="ebc68-139">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="ebc68-139">Related Content</span></span>  
 [<span data-ttu-id="ebc68-140">Administración y configuración del servidor PowerPivot en Administración central</span><span class="sxs-lookup"><span data-stu-id="ebc68-140">PowerPivot Server Administration and Configuration in Central Administration</span></span>](power-pivot-server-administration-and-configuration-in-central-administration.md)  
  
 [<span data-ttu-id="ebc68-141">Herramientas de configuración de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="ebc68-141">PowerPivot Configuration Tools</span></span>](power-pivot-configuration-tools.md)  
  
 [<span data-ttu-id="ebc68-142">Referencia de PowerShell para PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="ebc68-142">PowerShell Reference for PowerPivot for SharePoint</span></span>](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint)  
