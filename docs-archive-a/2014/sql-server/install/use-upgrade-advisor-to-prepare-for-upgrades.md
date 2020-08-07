---
title: Usar el asesor de actualizaciones para preparar las actualizaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server]
- upgrading SQL Server, Upgrade Advisor
- upgrading SQL Server, preparing to upgrade
- SQL Server Upgrade Advisor
- analyzing installations for upgrading [SQL Server]
ms.assetid: d85b0833-ddeb-42e3-9397-97ea60d521b7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e53d895cb19a172d0810ae9d6c2bda3406732da1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746087"
---
# <a name="use-upgrade-advisor-to-prepare-for-upgrades"></a><span data-ttu-id="34f8f-102">Usar el Asesor de actualizaciones para preparar las actualizaciones</span><span class="sxs-lookup"><span data-stu-id="34f8f-102">Use Upgrade Advisor to Prepare for Upgrades</span></span>
  <span data-ttu-id="34f8f-103">El Asesor de actualizaciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ayuda a preparar las actualizaciones de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34f8f-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor helps you prepare for upgrades to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="34f8f-104">Esta herramienta analiza los componentes instalados de las versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y genera un informe que identifica los problemas que han de solucionarse antes o después de la actualización.</span><span class="sxs-lookup"><span data-stu-id="34f8f-104">Upgrade Advisor analyzes installed components from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then generates a report that identifies issues to fix either before or after you upgrade.</span></span>  
  
## <a name="how-upgrade-advisor-works"></a><span data-ttu-id="34f8f-105">Cómo funciona el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="34f8f-105">How Upgrade Advisor Works</span></span>  
 <span data-ttu-id="34f8f-106">Al ejecutar el Asesor de actualizaciones, se mostrará la página de inicio del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="34f8f-106">When you run Upgrade Advisor, the Upgrade Advisor Home page appears.</span></span> <span data-ttu-id="34f8f-107">Desde la página Inicio, podrá ejecutar las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="34f8f-107">From the Home page, you can run the following tools:</span></span>  
  
-   <span data-ttu-id="34f8f-108">Asistente para análisis del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="34f8f-108">Upgrade Advisor Analysis Wizard</span></span>  
  
-   <span data-ttu-id="34f8f-109">Visor de informes del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="34f8f-109">Upgrade Advisor Report Viewer</span></span>  
  
-   <span data-ttu-id="34f8f-110">Ayuda del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="34f8f-110">Upgrade Advisor Help</span></span>  
  
 <span data-ttu-id="34f8f-111">La primera vez que utilice el Asesor de actualizaciones, ejecute el Asistente para análisis del Asesor de actualizaciones para analizar los componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34f8f-111">The first time that you use Upgrade Advisor, run the Upgrade Advisor Analysis Wizard to analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="34f8f-112">Una vez que el asistente haya finalizado el análisis, podrá ver los informes resultantes en el Visor de informes del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="34f8f-112">When the wizard finishes the analysis, view the resulting reports in the Upgrade Advisor Report Viewer.</span></span> <span data-ttu-id="34f8f-113">Los informes incluyen vínculos a información de la Ayuda del Asesor de actualizaciones que le ayudará a solucionar los problemas conocidos o a paliar su efecto.</span><span class="sxs-lookup"><span data-stu-id="34f8f-113">Each report provides links to information in Upgrade Advisor Help that will help you fix or reduce the effect of the known issues.</span></span>  
  
## <a name="upgrade-advisor-analysis"></a><span data-ttu-id="34f8f-114">Análisis del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="34f8f-114">Upgrade Advisor Analysis</span></span>  
 <span data-ttu-id="34f8f-115">El Asesor de actualizaciones analiza los siguientes componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="34f8f-115">Upgrade Advisor analyzes the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
 <span data-ttu-id="34f8f-116">El análisis examina los objetos accesibles, como scripts, procedimientos almacenados, desencadenadores y archivos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="34f8f-116">The analysis examines objects that can be accessed, such as scripts, stored procedures, triggers, and trace files.</span></span> <span data-ttu-id="34f8f-117">El Asesor de actualizaciones no puede analizar aplicaciones de escritorio ni procedimientos almacenados cifrados.</span><span class="sxs-lookup"><span data-stu-id="34f8f-117">Upgrade Advisor cannot analyze desktop applications or encrypted stored procedures.</span></span>  
  
 <span data-ttu-id="34f8f-118">El resultado se presenta como un informe XML.</span><span class="sxs-lookup"><span data-stu-id="34f8f-118">Output is in the form of an XML report.</span></span> <span data-ttu-id="34f8f-119">Podrá ver el informe XML mediante el Visor de informes del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="34f8f-119">View the XML report by using the Upgrade Advisor report viewer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34f8f-120">Los informes pueden contener un elemento "otros problemas de actualización".</span><span class="sxs-lookup"><span data-stu-id="34f8f-120">Reports might contain an "other upgrade issues" item.</span></span> <span data-ttu-id="34f8f-121">Este elemento vincula a una lista de problemas que no detecta el Asesor de actualizaciones, pero que pueden existir en el servidor o en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="34f8f-121">This item links to a list of issues that are not detected by Upgrade Advisor, but might exist on your server or in your applications.</span></span> <span data-ttu-id="34f8f-122">Debe leer la lista de problemas no detectables y determinar si debe realizar cambios en el servidor o en las aplicaciones para solventarlos.</span><span class="sxs-lookup"><span data-stu-id="34f8f-122">You should review the list of undetectable issues and determine whether you must change your server or applications because of the undetectable issues.</span></span>  
  
## <a name="how-to-install-and-run-upgrade-advisor"></a><span data-ttu-id="34f8f-123">Cómo instalar y ejecutar el Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="34f8f-123">How to Install and Run Upgrade Advisor</span></span>  
 <span data-ttu-id="34f8f-124">La ubicación en la que se instala el Asesor de actualizaciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] depende de lo que se vaya a analizar.</span><span class="sxs-lookup"><span data-stu-id="34f8f-124">The location where you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="34f8f-125">El Asesor de actualizaciones admite el análisis remoto de todos los componentes admitidos excepto [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34f8f-125">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="34f8f-126">Si no está analizando instancias de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], puede instalar el Asesor de actualizaciones en cualquier equipo que pueda conectarse a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y que cumpla los requisitos previos del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="34f8f-126">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="34f8f-127">Para obtener información detallada, vea [Actualizaciones de ediciones y versiones admitidas](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="34f8f-127">For more information, see [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span></span> <span data-ttu-id="34f8f-128">Si está examinando instancias de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], debe instalar el Asesor de actualizaciones en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="34f8f-128">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="34f8f-129">El Asesor de actualizaciones está disponible en un Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="34f8f-129">Upgrade Advisor is available in a feature pack.</span></span>  
  
 <span data-ttu-id="34f8f-130">Los requisitos previos para instalar y ejecutar el asesor de actualizaciones son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="34f8f-130">Prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] <span data-ttu-id="34f8f-131">SP2, Windows 7 SP1 y [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="34f8f-131">SP2, Windows 7 SP1, and [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span>  
  
-   <span data-ttu-id="34f8f-132">Windows Installer a partir de la versión 4.5.</span><span class="sxs-lookup"><span data-stu-id="34f8f-132">Windows Installer beginning with version 4.5.</span></span> <span data-ttu-id="34f8f-133">Puede instalar Windows Installer desde el [sitio web de Windows Installer](https://www.microsoft.com/download/details.aspx?id=8483).</span><span class="sxs-lookup"><span data-stu-id="34f8f-133">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="34f8f-134">Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="34f8f-134">Microsoft .NET Framework 4.</span></span> <span data-ttu-id="34f8f-135">.NET Framework 4 está disponible en los [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] medios del producto y en la [Página de descarga de .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=209895).</span><span class="sxs-lookup"><span data-stu-id="34f8f-135">.NET Framework 4 is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [.NET Framework 4 download page](https://go.microsoft.com/fwlink/?LinkId=209895).</span></span>  
  
    -   <span data-ttu-id="34f8f-136">Para instalar .NET Framework 4 desde el disco de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], busque la raíz de la unidad de disco.</span><span class="sxs-lookup"><span data-stu-id="34f8f-136">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="34f8f-137">A continuación, haga doble clic en la carpeta \redist, haga doble clic en la carpeta DotNetFrameworks y ejecute dotNetFx40_Full_x86_x64.exe (para sistemas operativos de 32 bits o para sistemas operativos de 64 bits).</span><span class="sxs-lookup"><span data-stu-id="34f8f-137">Then, double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for 32-bit operating systems or for 64-bit operating systems).</span></span>  
  
 <span data-ttu-id="34f8f-138">Para instalar el Asesor de actualizaciones desde Internet, haga clic en el botón de descarga de la página de descarga.</span><span class="sxs-lookup"><span data-stu-id="34f8f-138">To install Upgrade Advisor from the Web, click the download button on the download page.</span></span> <span data-ttu-id="34f8f-139">Puede ejecutar la instalación inmediatamente o guardar el archivo SQLUA.msi para ejecutarlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="34f8f-139">You can then run installation immediately, or save the SQLUA.msi file to run later.</span></span> <span data-ttu-id="34f8f-140">Si va a realizar la instalación desde el disco del producto, ejecute el archivo SQLUA.msi directamente desde dicho disco.</span><span class="sxs-lookup"><span data-stu-id="34f8f-140">If you are installing from the product disc, run SQLUA.msi directly from the product disk.</span></span>  
  
 <span data-ttu-id="34f8f-141">Después de instalar el asesor de actualizaciones, puede abrirlo desde el menú **Inicio** :</span><span class="sxs-lookup"><span data-stu-id="34f8f-141">After you install Upgrade Advisor, you can open it from the **Start** menu:</span></span>  
  
-   <span data-ttu-id="34f8f-142">Haga clic en **Inicio**, seleccione **todos los programas**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)] y, a continuación, haga clic en \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Asesor de actualizaciones\*\*.</span><span class="sxs-lookup"><span data-stu-id="34f8f-142">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
 <span data-ttu-id="34f8f-143">Para obtener más información, vea la documentación del Asesor de actualizaciones incluida en la descarga del Asesor de actualizaciones y las notas de la versión de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34f8f-143">For more information, see the Upgrade Advisor documentation included in the Upgrade Advisor download and the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Release Notes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f8f-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34f8f-144">See Also</span></span>  
 <span data-ttu-id="34f8f-145">[Trabajar con varias versiones e instancias de SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34f8f-145">[Work with Multiple Versions and Instances of SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md) </span></span>  
 <span data-ttu-id="34f8f-146">[Actualizaciones de ediciones y versiones admitidas](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="34f8f-146">[Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 [<span data-ttu-id="34f8f-147">Compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="34f8f-147">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
