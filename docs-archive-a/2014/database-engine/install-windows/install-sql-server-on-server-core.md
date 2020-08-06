---
title: Instale SQL Server 2014 en Server Core | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 1dd294cc-5b69-4d0c-9005-3e307b75678b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2614c43bb763757db7db46b1c7a966221da96f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744850"
---
# <a name="install-sql-server-2014-on-server-core"></a><span data-ttu-id="73509-102">Instalar SQL Server 2014 en Server Core</span><span class="sxs-lookup"><span data-stu-id="73509-102">Install SQL Server 2014 on Server Core</span></span>
  <span data-ttu-id="73509-103">Puede instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una instalación Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 o de [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-103">You can install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="73509-104">En este tema se proporcionan detalles específicos de la instalación de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en Server Core.</span><span class="sxs-lookup"><span data-stu-id="73509-104">This topic provides setup-specific details for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core.</span></span>  
  
 <span data-ttu-id="73509-105">La opción de instalación Server Core para el sistema operativo [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] proporciona un entorno mínimo para ejecutar determinados roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="73509-105">The Server Core installation option for the [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] operating system provides a minimal environment for running specific server roles.</span></span> <span data-ttu-id="73509-106">Esto ayuda a reducir los requisitos de administración y mantenimiento y la superficie de ataque para esos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="73509-106">This helps to reduce maintenance and management requirements and the attack surface for those server roles.</span></span> <span data-ttu-id="73509-107">Para obtener más información sobre Server Core tal y como se implementa en [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] , vea [Server Core para Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) ( https://go.microsoft.com/fwlink/?LinkId=202439) .</span><span class="sxs-lookup"><span data-stu-id="73509-107">For more information on Server Core as implemented on [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)], see [Server Core for Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) (https://go.microsoft.com/fwlink/?LinkId=202439).</span></span> <span data-ttu-id="73509-108">Para obtener más información sobre Server Core tal y como se implementa en [!INCLUDE[win8srv](../../includes/win8srv-md.md)], vea [Server Core para Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="73509-108">For more information on Server Core as implemented on [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Server Core for Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="73509-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="73509-109">Prerequisites</span></span>  
  
|<span data-ttu-id="73509-110">Requisito</span><span class="sxs-lookup"><span data-stu-id="73509-110">Requirement</span></span>|<span data-ttu-id="73509-111">Cómo instalar</span><span class="sxs-lookup"><span data-stu-id="73509-111">How to install</span></span>|  
|-----------------|--------------------|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="73509-112">2.0 SP2</span><span class="sxs-lookup"><span data-stu-id="73509-112">2.0 SP2</span></span>|<span data-ttu-id="73509-113">Incluido en la instalación Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 y [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-113">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="73509-114">Si no está habilitado, el programa de instalación lo habilita de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="73509-114">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="73509-115">No es posible ejecutar las versiones 2.0, 3.0 y 3.5 en paralelo en un equipo.</span><span class="sxs-lookup"><span data-stu-id="73509-115">It is not possible to run versions 2.0, 3.0, and 3.5 side by side on a computer.</span></span> <span data-ttu-id="73509-116">Cuando instala .NET Framework 3.5 SP1, obtiene los niveles 2.0 y 3.0 automáticamente.</span><span class="sxs-lookup"><span data-stu-id="73509-116">When you install the .NET Framework 3.5 SP1, you get the 2.0 and 3.0 layers automatically.</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="73509-117">3.5 SP1 Full Profile</span><span class="sxs-lookup"><span data-stu-id="73509-117">3.5 SP1 Full Profile</span></span>|<span data-ttu-id="73509-118">Incluido en la instalación Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="73509-118">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span> <span data-ttu-id="73509-119">Si no está habilitado, el programa de instalación lo habilita de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="73509-119">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="73509-120">En un equipo con el sistema operativo de servidor Windows, debe descargar e instalar .NET Framework 3.5 SP1 antes de ejecutar el programa de instalación para instalar componentes dependientes de .NET 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="73509-120">On a computer with Windows server operating system you must download and install .NET Framework 3.5 SP1 before you run Setup, to install components dependent on .NET 3.5 SP1.</span></span><br /><br /> <span data-ttu-id="73509-121">Para obtener más información acerca de las recomendaciones e instrucciones sobre cómo adquirir y habilitar .NET Framework 3,5 en [!INCLUDE[win8srv](../../includes/win8srv-md.md)] , vea [consideraciones sobre la implementación de Microsoft .NET Framework 3,5](https://msdn.microsoft.com/library/windows/hardware/hh975396) ( https://msdn.microsoft.com/library/windows/hardware/hh975396) .</span><span class="sxs-lookup"><span data-stu-id="73509-121">For more information about the recommendations and guidance on how to acquire and enable .NET Framework 3.5 in [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Microsoft .NET Framework 3.5 Deployment Considerations](https://msdn.microsoft.com/library/windows/hardware/hh975396) (https://msdn.microsoft.com/library/windows/hardware/hh975396).</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="73509-122">4 Server Core Profile</span><span class="sxs-lookup"><span data-stu-id="73509-122">4 Server Core Profile</span></span>|<span data-ttu-id="73509-123">Para todas las ediciones de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] excepto [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], el programa de instalación instala [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile como un requisito previo.</span><span class="sxs-lookup"><span data-stu-id="73509-123">For all editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], Setup installs the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile as a prerequisite.</span></span><br /><br /> <span data-ttu-id="73509-124">Para [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)] , descargue [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile desde [Microsoft .NET Framework 4 (instalador independiente) para Server Core](https://www.microsoft.com/download/details.aspx?id=17718) ( https://www.microsoft.com/download/details.aspx?id=17718) y instálelo antes de continuar con la instalación.</span><span class="sxs-lookup"><span data-stu-id="73509-124">For [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)], download the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile from [Microsoft .NET Framework 4 (Standalone Installer) for Server Core](https://www.microsoft.com/download/details.aspx?id=17718) (https://www.microsoft.com/download/details.aspx?id=17718), and install it before you proceed with the setup.</span></span>|  
|<span data-ttu-id="73509-125">Windows Installer 4.5</span><span class="sxs-lookup"><span data-stu-id="73509-125">Windows Installer 4.5</span></span>|<span data-ttu-id="73509-126">Incluido con la instalación Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 y [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-126">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
|<span data-ttu-id="73509-127">Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="73509-127">Windows PowerShell 2.0</span></span>|<span data-ttu-id="73509-128">Incluido con la instalación Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 y [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-128">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
  
##  <a name="supported-features"></a><a name="BK_SupportedFeatures"></a> <span data-ttu-id="73509-129">Características admitidas</span><span class="sxs-lookup"><span data-stu-id="73509-129">Supported Features</span></span>  
 <span data-ttu-id="73509-130">Use la tabla siguiente para encontrar qué características se admiten en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en una instalación Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 y [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-130">Use the following table to find which features are supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|<span data-ttu-id="73509-131">Característica</span><span class="sxs-lookup"><span data-stu-id="73509-131">Feature</span></span>|<span data-ttu-id="73509-132">Compatible</span><span class="sxs-lookup"><span data-stu-id="73509-132">Supported</span></span>|  
|-------------|---------------|  
|[!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="73509-133">Servicios</span><span class="sxs-lookup"><span data-stu-id="73509-133">Services</span></span>|<span data-ttu-id="73509-134">Sí</span><span class="sxs-lookup"><span data-stu-id="73509-134">Yes</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73509-135">Replicación</span><span class="sxs-lookup"><span data-stu-id="73509-135">Replication</span></span>|<span data-ttu-id="73509-136">Sí</span><span class="sxs-lookup"><span data-stu-id="73509-136">Yes</span></span>|  
|<span data-ttu-id="73509-137">Búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="73509-137">Full Text Search</span></span>|<span data-ttu-id="73509-138">Sí</span><span class="sxs-lookup"><span data-stu-id="73509-138">Yes</span></span>|  
|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]|<span data-ttu-id="73509-139">Sí</span><span class="sxs-lookup"><span data-stu-id="73509-139">Yes</span></span>|  
|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|<span data-ttu-id="73509-140">No</span><span class="sxs-lookup"><span data-stu-id="73509-140">No</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73509-141">Data Tools (SSDT)</span><span class="sxs-lookup"><span data-stu-id="73509-141">Data Tools (SSDT)</span></span>|<span data-ttu-id="73509-142">No</span><span class="sxs-lookup"><span data-stu-id="73509-142">No</span></span>|  
|<span data-ttu-id="73509-143">Conectividad con las herramientas de cliente</span><span class="sxs-lookup"><span data-stu-id="73509-143">Client Tools Connectivity</span></span>|<span data-ttu-id="73509-144">Sí</span><span class="sxs-lookup"><span data-stu-id="73509-144">Yes</span></span>|  
|<span data-ttu-id="73509-145">Integration Services Server<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="73509-145">Integration Services Server<sup>[1]</sup></span></span>|<span data-ttu-id="73509-146">Sí</span><span class="sxs-lookup"><span data-stu-id="73509-146">Yes</span></span>|  
|<span data-ttu-id="73509-147">Compatibilidad con las versiones anteriores de las herramientas de cliente</span><span class="sxs-lookup"><span data-stu-id="73509-147">Client Tools Backward Compatibility</span></span>|<span data-ttu-id="73509-148">No</span><span class="sxs-lookup"><span data-stu-id="73509-148">No</span></span>|  
|<span data-ttu-id="73509-149">SDK de las herramientas de cliente</span><span class="sxs-lookup"><span data-stu-id="73509-149">Client Tools SDK</span></span>|<span data-ttu-id="73509-150">No</span><span class="sxs-lookup"><span data-stu-id="73509-150">No</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="73509-151">Libros en pantalla</span><span class="sxs-lookup"><span data-stu-id="73509-151">Books Online</span></span>|<span data-ttu-id="73509-152">No</span><span class="sxs-lookup"><span data-stu-id="73509-152">No</span></span>|  
|<span data-ttu-id="73509-153">Herramientas de administración: básicas</span><span class="sxs-lookup"><span data-stu-id="73509-153">Management Tools - Basic</span></span>|<span data-ttu-id="73509-154">Solo remoto<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="73509-154">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="73509-155">Herramientas de administración - Completa</span><span class="sxs-lookup"><span data-stu-id="73509-155">Management Tools - Complete</span></span>|<span data-ttu-id="73509-156">Solo remoto<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="73509-156">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="73509-157">Distributed Replay Controller</span><span class="sxs-lookup"><span data-stu-id="73509-157">Distributed Replay Controller</span></span>|<span data-ttu-id="73509-158">No</span><span class="sxs-lookup"><span data-stu-id="73509-158">No</span></span>|  
|<span data-ttu-id="73509-159">Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="73509-159">Distributed Replay Client</span></span>|<span data-ttu-id="73509-160">Solo remoto<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="73509-160">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="73509-161">SDK de conectividad de cliente SQL</span><span class="sxs-lookup"><span data-stu-id="73509-161">SQL Client Connectivity SDK</span></span>|<span data-ttu-id="73509-162">Sí</span><span class="sxs-lookup"><span data-stu-id="73509-162">Yes</span></span>|  
|<span data-ttu-id="73509-163">Microsoft Synchronization Framework</span><span class="sxs-lookup"><span data-stu-id="73509-163">Microsoft Sync Framework</span></span>|<span data-ttu-id="73509-164">Sí<sup>[3]</sup></span><span class="sxs-lookup"><span data-stu-id="73509-164">Yes<sup>[3]</sup></span></span>|  
|[!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]|<span data-ttu-id="73509-165">No</span><span class="sxs-lookup"><span data-stu-id="73509-165">No</span></span>|  
|[!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]|<span data-ttu-id="73509-166">No</span><span class="sxs-lookup"><span data-stu-id="73509-166">No</span></span>|  
  
 <span data-ttu-id="73509-167"><sup>[1]</sup> Para obtener más información sobre el nuevo servidor de Integration Services y sus características en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , consulte [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="73509-167"><sup>[1]</sup>For more information about the new Integration Services Server and its features in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="73509-168"><sup>[2]</sup> No se admite la instalación de estas características en Server Core.</span><span class="sxs-lookup"><span data-stu-id="73509-168"><sup>[2]</sup>Installation of these features on Server Core is not supported.</span></span> <span data-ttu-id="73509-169">Estos componentes se pueden instalar en un servidor diferente que no sea [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core y conectarse a los servicios de [!INCLUDE[ssDE](../../includes/ssde-md.md)] instalados en Server Core.</span><span class="sxs-lookup"><span data-stu-id="73509-169">These components can be installed on a different server that is not [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, and connected to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] services installed on Server Core.</span></span>  
  
 <span data-ttu-id="73509-170"><sup>[3]</sup> Microsoft Sync Framework no se incluye en el [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] paquete de instalación.</span><span class="sxs-lookup"><span data-stu-id="73509-170"><sup>[3]</sup>Microsoft Sync Framework is not included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation package.</span></span> <span data-ttu-id="73509-171">Puede descargar la versión adecuada de Sync Framework desde este [centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?LinkId=221788) ( https://go.microsoft.com/fwlink/?LinkId=221788) página e instalarla en un equipo que ejecute la instalación Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73509-171">You can download the appropriate version of Sync Framework from this [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=221788) (https://go.microsoft.com/fwlink/?LinkId=221788) page and install it on a computer that is running Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
## <a name="supported-scenario-matrix"></a><span data-ttu-id="73509-172">Matriz de escenarios admitidos</span><span class="sxs-lookup"><span data-stu-id="73509-172">Supported Scenario Matrix</span></span>  
 <span data-ttu-id="73509-173">En la siguiente tabla se muestra la matriz de escenarios admitidos para instalar [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en una instalación Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 y [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-173">The following table shows the supported scenario matrix for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73509-174">Ediciones de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73509-174">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] editions</span></span>|<span data-ttu-id="73509-175">Todas las [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ediciones de 64 bits<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="73509-175">All [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 64-bit editions<sup>[1]</sup></span></span>|  
|<span data-ttu-id="73509-176">Idioma de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73509-176">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] language</span></span>|<span data-ttu-id="73509-177">Todos los idiomas</span><span class="sxs-lookup"><span data-stu-id="73509-177">All languages</span></span>|  
|<span data-ttu-id="73509-178">Idioma de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el idioma o configuración regional (combinación) del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="73509-178">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] language on OS language/locale (combination)</span></span>|<span data-ttu-id="73509-179">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en inglés en Windows en japonés</span><span class="sxs-lookup"><span data-stu-id="73509-179">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on JPN (Japanese) Windows</span></span><br /><br /> <span data-ttu-id="73509-180">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en inglés en Windows en alemán</span><span class="sxs-lookup"><span data-stu-id="73509-180">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on GER (German) Windows</span></span><br /><br /> <span data-ttu-id="73509-181">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en inglés en Windows en chino</span><span class="sxs-lookup"><span data-stu-id="73509-181">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on CHS (Chinese-China) Windows</span></span><br /><br /> <span data-ttu-id="73509-182">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en inglés en Windows en árabe</span><span class="sxs-lookup"><span data-stu-id="73509-182">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ARA (Arabic (SA)) Windows</span></span><br /><br /> <span data-ttu-id="73509-183">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en inglés en Windows en tailandés</span><span class="sxs-lookup"><span data-stu-id="73509-183">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on THA (Thai) Windows</span></span><br /><br /> <span data-ttu-id="73509-184">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en inglés en Windows en turco</span><span class="sxs-lookup"><span data-stu-id="73509-184">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on TRK (Turkish) Windows</span></span><br /><br /> <span data-ttu-id="73509-185">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en inglés en Windows en portugués de Portugal</span><span class="sxs-lookup"><span data-stu-id="73509-185">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on pt-PT (Portuguese Portugal) Windows</span></span><br /><br /> <span data-ttu-id="73509-186">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en inglés en Windows en inglés</span><span class="sxs-lookup"><span data-stu-id="73509-186">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ENG (English) Windows</span></span>|  
|<span data-ttu-id="73509-187">Edición de Windows</span><span class="sxs-lookup"><span data-stu-id="73509-187">Windows edition</span></span>|[!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="73509-188">de 64 bits x64 Datacenter</span><span class="sxs-lookup"><span data-stu-id="73509-188">64-bit x64 Datacenter</span></span><br /><br /> [!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="73509-189">de 64 bits x64 Standard</span><span class="sxs-lookup"><span data-stu-id="73509-189">64-bit x64 Standard</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="73509-190">S12 de 64 bits x64 Data Center Server Core</span><span class="sxs-lookup"><span data-stu-id="73509-190">SP1 64-bit x64 Data Center Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="73509-191">SP1 64 de bits x64 Enterprise Server Core</span><span class="sxs-lookup"><span data-stu-id="73509-191">SP1 64-bit x64 Enterprise Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="73509-192">SP1 de 64 bits x64 Standard Server Core</span><span class="sxs-lookup"><span data-stu-id="73509-192">SP1 64-bit x64 Standard Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="73509-193">SP1 de 64 bits x64 Web Server Core</span><span class="sxs-lookup"><span data-stu-id="73509-193">SP1 64-bit x64 Web Server Core</span></span>|  
  
 <span data-ttu-id="73509-194"><sup>[1]</sup> No se admite la instalación de la versión de 32 bits de las [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ediciones en Server Core.</span><span class="sxs-lookup"><span data-stu-id="73509-194"><sup>[1]</sup>Installing the 32-bit version of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] editions is not supported on Server Core.</span></span>  
  
## <a name="upgrading"></a><span data-ttu-id="73509-195">Actualizando</span><span class="sxs-lookup"><span data-stu-id="73509-195">Upgrading</span></span>  
 <span data-ttu-id="73509-196">En las instalaciones básicas Server Core, se admite la actualización de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73509-196">On Server Core installations, upgrading from [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is supported.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="73509-197">Instalación</span><span class="sxs-lookup"><span data-stu-id="73509-197">Installation</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="73509-198">no admite la instalación con el asistente de instalación en el sistema operativo Server Core.</span><span class="sxs-lookup"><span data-stu-id="73509-198">does not support setup by using the installation wizard on the Server Core operating system.</span></span> <span data-ttu-id="73509-199">Al realizar la instalación en Server Core, el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite el modo totalmente silencioso mediante el uso del parámetro /Q o el modo silencioso simple mediante el parámetro /QS.</span><span class="sxs-lookup"><span data-stu-id="73509-199">When installing on Server Core, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup supports full quiet mode by using the /Q parameter, or Quiet Simple mode by using the /QS parameter.</span></span> <span data-ttu-id="73509-200">Para obtener más información, vea [Instalar SQL Server 2014 desde el símbolo del sistema](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="73509-200">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="73509-201">no se puede instalar en paralelo con versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un equipo que ejecute [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span><span class="sxs-lookup"><span data-stu-id="73509-201">cannot be installed side-by-side with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span></span>  
  
 <span data-ttu-id="73509-202">Con independencia del método de instalación, es necesario confirmar la aceptación de los términos de la licencia de software como usuario individual o en nombre de una entidad, a menos que el uso del software en su caso se rija por un acuerdo independiente, como un acuerdo de licencia por volumen de [!INCLUDE[msCoName](../../includes/msconame-md.md)] o un acuerdo suscrito con un ISV u OEM.</span><span class="sxs-lookup"><span data-stu-id="73509-202">Regardless of the installation method, you are required to confirm acceptance of the software license terms as an individual or on behalf of an entity, unless your use of the software is governed by a separate agreement such as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing agreement or a third-party agreement with an ISV or OEM.</span></span>  
  
 <span data-ttu-id="73509-203">Los términos de la licencia se muestran para revisarlos y aceptarlos en la interfaz de usuario del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="73509-203">The license terms are displayed for review and acceptance in the Setup user interface.</span></span> <span data-ttu-id="73509-204">Las instalaciones desatendidas (mediante los parámetros /Q o /QS) deben incluir el parámetro /IACCEPTSQLSERVERLICENSETERMS.</span><span class="sxs-lookup"><span data-stu-id="73509-204">Unattended installations (using the /Q or /QS parameters) must include the /IACCEPTSQLSERVERLICENSETERMS parameter.</span></span> <span data-ttu-id="73509-205">Puede revisar separadamente los términos de licencia en [Términos de licencia de software de Microsoft](https://go.microsoft.com/fwlink/?LinkId=148209).</span><span class="sxs-lookup"><span data-stu-id="73509-205">You can review the license terms separately at [Microsoft Software License Terms](https://go.microsoft.com/fwlink/?LinkId=148209).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="73509-206">En función de cómo haya recibido el software (por ejemplo, a través de un contrato de licencias por volumen de [!INCLUDE[msCoName](../../includes/msconame-md.md)] ), su uso del software puede estar sujeto a términos y condiciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="73509-206">Depending on how you received the software (for example, through [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing), your use of the software may be subject to additional terms and conditions.</span></span>  
  
 <span data-ttu-id="73509-207">Para instalar características específicas, use el parámetro /FEATURES y especifique la característica primaria o los valores de las características.</span><span class="sxs-lookup"><span data-stu-id="73509-207">To install specific features, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="73509-208">Para obtener más información sobre los parámetros de las características y su uso, consulte las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="73509-208">For more information about feature parameters and their use, see the following sections.</span></span>  
  
### <a name="feature-parameters"></a><span data-ttu-id="73509-209">Parámetros de características</span><span class="sxs-lookup"><span data-stu-id="73509-209">Feature Parameters</span></span>  
  
|<span data-ttu-id="73509-210">Parámetro de característica</span><span class="sxs-lookup"><span data-stu-id="73509-210">Feature parameter</span></span>|<span data-ttu-id="73509-211">Descripción</span><span class="sxs-lookup"><span data-stu-id="73509-211">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="73509-212">SQLENGINE</span><span class="sxs-lookup"><span data-stu-id="73509-212">SQLENGINE</span></span>|<span data-ttu-id="73509-213">Instala solo el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-213">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="73509-214">REPLICACIÓN</span><span class="sxs-lookup"><span data-stu-id="73509-214">REPLICATION</span></span>|<span data-ttu-id="73509-215">Instala el componente Replicación junto con [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-215">Installs the Replication component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="73509-216">FULLTEXT</span><span class="sxs-lookup"><span data-stu-id="73509-216">FULLTEXT</span></span>|<span data-ttu-id="73509-217">Instala el componente Texto completo junto con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-217">Installs the FullText component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="73509-218">AS</span><span class="sxs-lookup"><span data-stu-id="73509-218">AS</span></span>|<span data-ttu-id="73509-219">Instala todos los componentes de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73509-219">Installs all [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="73509-220">IS</span><span class="sxs-lookup"><span data-stu-id="73509-220">IS</span></span>|<span data-ttu-id="73509-221">Instala todos los componentes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73509-221">Installs all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="73509-222">CONN</span><span class="sxs-lookup"><span data-stu-id="73509-222">CONN</span></span>|<span data-ttu-id="73509-223">Instala los componentes de conectividad.</span><span class="sxs-lookup"><span data-stu-id="73509-223">Installs the connectivity components.</span></span>|  
  
 <span data-ttu-id="73509-224">Vea los siguientes ejemplos de uso de los parámetros de la característica:</span><span class="sxs-lookup"><span data-stu-id="73509-224">See the following examples of the usage of feature parameters:</span></span>  
  
|<span data-ttu-id="73509-225">Parámetro y valores</span><span class="sxs-lookup"><span data-stu-id="73509-225">Parameter and values</span></span>|<span data-ttu-id="73509-226">Descripción</span><span class="sxs-lookup"><span data-stu-id="73509-226">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="73509-227">/FEATURES=SQLEngine</span><span class="sxs-lookup"><span data-stu-id="73509-227">/FEATURES=SQLEngine</span></span>|<span data-ttu-id="73509-228">Instala solo el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-228">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="73509-229">/FEATURES=SQLEngine,FullText</span><span class="sxs-lookup"><span data-stu-id="73509-229">/FEATURES=SQLEngine,FullText</span></span>|<span data-ttu-id="73509-230">Instala [!INCLUDE[ssDE](../../includes/ssde-md.md)] y Texto completo.</span><span class="sxs-lookup"><span data-stu-id="73509-230">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and full-text.</span></span>|  
|<span data-ttu-id="73509-231">/FEATURES=SQLEngine,Conn</span><span class="sxs-lookup"><span data-stu-id="73509-231">/FEATURES=SQLEngine,Conn</span></span>|<span data-ttu-id="73509-232">Instala los componentes de conectividad y [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73509-232">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the connectivity components.</span></span>|  
|<span data-ttu-id="73509-233">/FEATURES=SQLEngine,AS,IS,Conn</span><span class="sxs-lookup"><span data-stu-id="73509-233">/FEATURES=SQLEngine,AS,IS,Conn</span></span>|<span data-ttu-id="73509-234">Instala el [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]y los componentes de conectividad.</span><span class="sxs-lookup"><span data-stu-id="73509-234">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and the connectivity components.</span></span>|  
  
### <a name="installation-options"></a><span data-ttu-id="73509-235">Opción de instalación</span><span class="sxs-lookup"><span data-stu-id="73509-235">Installation Options</span></span>  
 <span data-ttu-id="73509-236">El programa de instalación admite las opciones de instalación siguientes al instalar [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en un sistema operativo Server Core:</span><span class="sxs-lookup"><span data-stu-id="73509-236">The Setup supports the following installation options while installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core operating system:</span></span>  
  
1.  <span data-ttu-id="73509-237">**Instalación desde la línea de comandos**</span><span class="sxs-lookup"><span data-stu-id="73509-237">**Installation from Command Line**</span></span>  
  
     <span data-ttu-id="73509-238">Para instalar características específicas mediante la opción de instalación del símbolo del sistema, use el parámetro /FEATURES y especifique la característica principal o los valores de la característica.</span><span class="sxs-lookup"><span data-stu-id="73509-238">To install specific features using the command prompt installation option, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="73509-239">El siguiente es un ejemplo del uso de los parámetros de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="73509-239">The following is an example of using the parameters from the command line:</span></span>  
  
    ```cmd
    setup.exe /qs /ACTION=Install /FEATURES=SQLEngine,Replication /INSTANCENAME=MSSQLSERVER /SQLSVCACCOUNT="<DomainName\UserName>" /SQLSVCPASSWORD="<StrongPassword>" /SQLSYSADMINACCOUNTS="<DomainName\UserName>" /AGTSVCACCOUNT="NT AUTHORITY\Network Service" /TCPENABLED=1 /IACCEPTSQLSERVERLICENSETERMS  
    ```  
  
2.  <span data-ttu-id="73509-240">**Instalación mediante el archivo de configuración**</span><span class="sxs-lookup"><span data-stu-id="73509-240">**Installation using Configuration File**</span></span>  
  
     <span data-ttu-id="73509-241">El programa de instalación admite el uso del archivo de configuración solamente a través del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="73509-241">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="73509-242">El archivo de configuración es un archivo de texto con la estructura básica de un parámetro (pares nombre-valor) y un comentario descriptivo.</span><span class="sxs-lookup"><span data-stu-id="73509-242">The configuration file is a text file with the basic structure of a parameter (name/value pair) and a descriptive comment.</span></span> <span data-ttu-id="73509-243">El archivo de configuración especificado en el símbolo del sistema debe tener una extensión de nombre de archivo .INI.</span><span class="sxs-lookup"><span data-stu-id="73509-243">The configuration file specified at the command prompt should have an .INI file name extension.</span></span> <span data-ttu-id="73509-244">Vea los ejemplos siguientes de ConfigurationFile.INI:</span><span class="sxs-lookup"><span data-stu-id="73509-244">See the following examples of ConfigurationFile.INI:</span></span>  
  
    -   <span data-ttu-id="73509-245">Instalación de [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73509-245">Installing [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
         <span data-ttu-id="73509-246">En el siguiente ejemplo se muestra cómo instalar una nueva instancia independiente que incluye el [!INCLUDE[ssDE](../../includes/ssde-md.md)] de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="73509-246">The following example shows how to install a new stand-alone instance that includes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine, and Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Accept the License agreement to continue with Installation  
  
        IAcceptSQLServerLicenseTerms="True"
        ```  
  
    -   <span data-ttu-id="73509-247">Instalar los componentes de conectividad</span><span class="sxs-lookup"><span data-stu-id="73509-247">Installing connectivity components</span></span>  
  
         <span data-ttu-id="73509-248">En el siguiente ejemplo se muestra cómo instalar los componentes de conectividad:</span><span class="sxs-lookup"><span data-stu-id="73509-248">The following example shows how to install the connectivity components:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=Conn  
  
        ; Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True
        ```  
  
    -   <span data-ttu-id="73509-249">Instalar todas las características compatibles</span><span class="sxs-lookup"><span data-stu-id="73509-249">Installing all supported features</span></span>  
  
         <span data-ttu-id="73509-250">En el siguiente ejemplo se muestra cómo instalar todas las características admitidas de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en Server Core:</span><span class="sxs-lookup"><span data-stu-id="73509-250">The following example shows how to install all supported features of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE,FullText,Replication,AS,IS,Conn  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine (SQL), or Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; The name of the account that the Analysis Services service runs under.   
  
        ASSVCACCOUNT= "NT Service\MSSQLServerOLAPService"  
  
        ; Specifies the list of administrator accounts that need to be provisioned.   
  
        ASSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Specifies the server mode of the Analysis Services instance. Valid values are MULTIDIMENSIONAL, POWERPIVOT or TABULAR. ASSERVERMODE is case-sensitive. All values must be expressed in upper case.   
  
        ASSERVERMODE="MULTIDIMENSIONAL"  
  
        ; Optional value, which specifies the state of the TCP protocol for the ssNoVersion service. Supported values are: 0 to disable the TCP protocol, and 1 to enable the TCP protocol.  
  
        TCPENABLED=1  
  
        ;Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True"  
        ```  
  
     <span data-ttu-id="73509-251">En los ejemplos siguientes se muestra cómo puede iniciar la instalación mediante un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="73509-251">The following examples show how you can launch the Setup using a configuration file.</span></span>  
  
    -   <span data-ttu-id="73509-252">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="73509-252">Configuration file</span></span>  
  
         <span data-ttu-id="73509-253">A continuación se ofrecen algunos ejemplos de uso del archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="73509-253">Following are some examples of how to use the configuration file:</span></span>  
  
        -   <span data-ttu-id="73509-254">Para especificar el archivo de configuración en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="73509-254">To specify the configuration file at the command prompt:</span></span>  
  
        ```cmd
        setup.exe /QS /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
        -   <span data-ttu-id="73509-255">Para especificar las contraseñas en el símbolo del sistema en lugar de hacerlo en el archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="73509-255">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
        ```cmd
        setup.exe /QS /SQLSVCPASSWORD="************" /ASSVCPASSWORD="************"  /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
    -   <span data-ttu-id="73509-256">DefaultSetup.ini</span><span class="sxs-lookup"><span data-stu-id="73509-256">DefaultSetup.ini</span></span>  
  
         <span data-ttu-id="73509-257">Si tiene el archivo DefaultSetup.ini en las carpetas \x86 y \x64 en el nivel raíz del medio de origen de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , abra el archivo DefaultSetup.ini y agregue el parámetro *Features* al archivo.</span><span class="sxs-lookup"><span data-stu-id="73509-257">If you have the DefaultSetup.ini file in the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media, open the DefaultSetup.ini file, and then add the *Features* parameter to the file.</span></span>  
  
         <span data-ttu-id="73509-258">Si el archivo DefaultSetup.ini no existe, puede crearlo y copiarlo a las carpetas \x86 y \x64 en el nivel raíz de la ubicación de origen de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73509-258">If the DefaultSetup.ini file does not exist, you can create it and copy it to the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media.</span></span>  
  
## <a name="configuring-remote-access-of-ssnoversion-running-on-server-core"></a><span data-ttu-id="73509-259">Configurar el acceso remoto de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en ejecución en Server Core</span><span class="sxs-lookup"><span data-stu-id="73509-259">Configuring Remote Access of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Running on Server Core</span></span>  
 <span data-ttu-id="73509-260">Realice las acciones descritas a continuación para configurar el acceso remoto de una instancia de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] que se está ejecutando en una instalación Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-260">Perform the actions described below to configure remote access of a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance that is running on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
### <a name="enable-remote-connections-on-the-instance-of-ssnoversion"></a><span data-ttu-id="73509-261">Habilitar las conexiones remotas en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73509-261">Enable remote connections on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="73509-262">Para habilitar las conexiones remotas, use SQLCMD.exe localmente y ejecute las instrucciones siguientes en la instancia de Server Core:</span><span class="sxs-lookup"><span data-stu-id="73509-262">To enable remote connections, use SQLCMD.exe locally and execute the following statements against the Server Core instance:</span></span>  
  
-   `EXEC sys.sp_configure N'remote access', N'1'`  
  
     `GO`  
  
-   `RECONFIGURE WITH OVERRIDE`  
  
     `GO`  
  
### <a name="enable-and-start-the-ssnoversion-browser-service"></a><span data-ttu-id="73509-263">Habilitar e iniciar el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span><span class="sxs-lookup"><span data-stu-id="73509-263">Enable and start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service</span></span>  
 <span data-ttu-id="73509-264">De forma predeterminada, el servicio Explorer se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="73509-264">By default, the Browser service is disabled.</span></span>  <span data-ttu-id="73509-265">Si se deshabilita en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecuta en Server Core, ejecute el siguiente comando desde el símbolo del sistema para habilitarlo:</span><span class="sxs-lookup"><span data-stu-id="73509-265">If it is disabled on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on Server Core, run the following command from the command prompt to enable it:</span></span>  
  
 `sc config SQLBROWSER start= auto`  
  
 <span data-ttu-id="73509-266">Una vez habilitado, ejecute el siguiente comando desde el símbolo del sistema para iniciar el servicio:</span><span class="sxs-lookup"><span data-stu-id="73509-266">After it is enabled, run the following command from the command prompt to start the service:</span></span>  
  
 `net start SQLBROWSER`  
  
### <a name="create-exceptions-in-windows-firewall"></a><span data-ttu-id="73509-267">Crear excepciones en Firewall de Windows</span><span class="sxs-lookup"><span data-stu-id="73509-267">Create exceptions in Windows Firewall</span></span>  
 <span data-ttu-id="73509-268">Para crear excepciones para el acceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en Firewall de Windows, siga los pasos especificados en [Configurar Firewall de Windows para permitir el acceso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="73509-268">To create exceptions for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access in Windows Firewall, follow the steps specified in [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
### <a name="enable-tcpip-on-the-instance-of-ssnoversion"></a><span data-ttu-id="73509-269">Habilitar TCP/IP en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73509-269">Enable TCP/IP on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="73509-270">El protocolo TCP/IP puede habilitarse a través de Windows PowerShell para una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en Server Core.</span><span class="sxs-lookup"><span data-stu-id="73509-270">The TCP/IP protocol can be enabled through Windows PowerShell for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on Server Core.</span></span> <span data-ttu-id="73509-271">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="73509-271">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="73509-272">En el equipo que ejecuta [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, inicie el Administrador de tareas.</span><span class="sxs-lookup"><span data-stu-id="73509-272">On the computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, launch Task Manager.</span></span>  
  
2.  <span data-ttu-id="73509-273">En la pestaña **Aplicaciones** , haga clic en **Nueva tarea**.</span><span class="sxs-lookup"><span data-stu-id="73509-273">On the **Applications** tab, click **New Task**.</span></span>  
  
3.  <span data-ttu-id="73509-274">En el cuadro de diálogo **Crear nueva tarea** , escriba **sqlps.exe** en el campo **Abrir** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73509-274">In the **Create New Task** dialog box, type **sqlps.exe** in the **Open** field and then click **OK**.</span></span> <span data-ttu-id="73509-275">Se abrirá la ventana de \*\* [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell\*\* .</span><span class="sxs-lookup"><span data-stu-id="73509-275">This opens the **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window.</span></span>  
  
4.  <span data-ttu-id="73509-276">En la ventana **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell**, ejecute el siguiente script para habilitar el protocolo TCP/IP:</span><span class="sxs-lookup"><span data-stu-id="73509-276">In the **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window, run the following script to enable the TCP/IP protocol:</span></span>  
  
```powershell
$smo = 'Microsoft.SqlServer.Management.Smo.'  
$wmi = New-Object ($smo + 'Wmi.ManagedComputer')  
# Enable the TCP protocol on the default instance.  If the instance is named, replace MSSQLSERVER with the instance name in the following line.  
$uri = "ManagedComputer[@Name='" + (get-item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
$Tcp = $wmi.GetSmoObject($uri)  
$Tcp.IsEnabled = $true  
$Tcp.Alter()  
$Tcp  
```  
  
## <a name="uninstallation"></a><span data-ttu-id="73509-277">Desinstalación</span><span class="sxs-lookup"><span data-stu-id="73509-277">Uninstallation</span></span>  
 <span data-ttu-id="73509-278">Después de iniciar sesión en un equipo que ejecute [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, tiene un entorno de escritorio limitado con un símbolo del sistema del administrador.</span><span class="sxs-lookup"><span data-stu-id="73509-278">After you log on to a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, you have a limited desktop environment with an Administrator command prompt.</span></span> <span data-ttu-id="73509-279">Puede utilizar este símbolo del sistema para iniciar la desinstalación de una instancia de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-279">You can use this command prompt to initiate uninstallation of an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="73509-280">Para desinstalar una instancia de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], inicie la desinstalación desde el símbolo del sistema el modo completamente silencioso utilizando el parámetro /Q o en modo silencioso simple utilizando el parámetro /QS.</span><span class="sxs-lookup"><span data-stu-id="73509-280">To uninstall an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], launch the uninstallation from the command prompt in full quiet mode by using the /Q parameter, or quiet simple mode by using the /QS parameter.</span></span> <span data-ttu-id="73509-281">El parámetro /QS muestra el progreso a través de la interfaz de usuario, pero no acepta ninguna entrada.</span><span class="sxs-lookup"><span data-stu-id="73509-281">The /QS parameter shows progress through the UI, but does not accept any input.</span></span> <span data-ttu-id="73509-282">/Q se ejecuta en modo silencioso sin ninguna interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="73509-282">/Q runs in a quiet mode without any user interface.</span></span>  
  
 <span data-ttu-id="73509-283">Para desinstalar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]existente.</span><span class="sxs-lookup"><span data-stu-id="73509-283">To uninstall an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```cmd
setup.exe /Q /Action=Uninstall /FEATURES=SQLEngine,AS,IS /INSTANCENAME=MSSQLSERVER  
```  
  
 <span data-ttu-id="73509-284">Para quitar una instancia con nombre, especifique el nombre de la instancia en lugar de "MSSQLSERVER" en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="73509-284">To remove a named instance, specify the name of the instance instead of "MSSQLSERVER" in the preceding example.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="73509-285">Si cierra el símbolo del sistema accidentalmente, puede iniciar un nuevo símbolo del sistema siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="73509-285">If you accidentally close the command prompt, you can start a new command prompt by following these steps:</span></span>  
> 
>  1.  <span data-ttu-id="73509-286">Presione Ctrl+Mayús+Esc para mostrar el Administrador de tareas.</span><span class="sxs-lookup"><span data-stu-id="73509-286">Press Ctrl+Shift+Esc to display Task Manager.</span></span>  
> 2.  <span data-ttu-id="73509-287">En la pestaña **Aplicaciones** , haga clic en **Nueva tarea**.</span><span class="sxs-lookup"><span data-stu-id="73509-287">On the **Applications** tab, click **New Task**.</span></span>  
> 3.  <span data-ttu-id="73509-288">En el cuadro de diálogo **Crear nueva tarea** , escriba **cmd** en el campo **Abrir** y haga clic en [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73509-288">In the **Create New Task** dialog box, type **cmd** in the **Open** field and then [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73509-289">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73509-289">See Also</span></span>  
 <span data-ttu-id="73509-290">[Instalación de SQL Server 2014 mediante un archivo de configuración](install-sql-server-using-a-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="73509-290">[Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md) </span></span>  
 <span data-ttu-id="73509-291">[Instalación de SQL Server 2014 desde el símbolo del sistema](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="73509-291">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="73509-292">[Características admitidas por las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="73509-292">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="73509-293">[Guía Introducción de la opción de instalación Server Core](https://go.microsoft.com/fwlink/?LinkId=221422) </span><span class="sxs-lookup"><span data-stu-id="73509-293">[Server Core Installation Option Getting Started Guide](https://go.microsoft.com/fwlink/?LinkId=221422) </span></span>  
 <span data-ttu-id="73509-294">[Configuración de una instalación de Server Core: información general](https://go.microsoft.com/fwlink/?LinkId=221423) </span><span class="sxs-lookup"><span data-stu-id="73509-294">[Configuring a Server Core installation: Overview](https://go.microsoft.com/fwlink/?LinkId=221423) </span></span>  
 <span data-ttu-id="73509-295">[Cmdlets de clúster de conmutación por error en Windows PowerShell enumerados por tarea](https://go.microsoft.com/fwlink/?LinkId=221419) </span><span class="sxs-lookup"><span data-stu-id="73509-295">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://go.microsoft.com/fwlink/?LinkId=221419) </span></span>  
 [<span data-ttu-id="73509-296">Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters (Asignación de comandos cluster.exe a cmdlets de Windows PowerShell para clústeres de conmutación por error)</span><span class="sxs-lookup"><span data-stu-id="73509-296">Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters</span></span>](https://go.microsoft.com/fwlink/?LinkId=221421)  
