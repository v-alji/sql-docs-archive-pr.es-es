---
title: Otros problemas de actualización de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- command line setup [Reporting Services]
- Setup commands [Reporting Services]
- multivalued parameters [Reporting Services]
- WMI provider [Reporting Services]
- compile errors [Reporting Services]
- single-valued parameters [Reporting Services]
- data processing extensions [Reporting Services]
- report compilation errors [Reporting Services]
- authentication [Reporting Services]
ms.assetid: 42dd2f06-1de9-449e-ab9d-f4ef25f8b728
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7cba24007534f143e6b8fd4b7cf74357bbfba3a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672463"
---
# <a name="other-reporting-services-upgrade-issues"></a><span data-ttu-id="2e5f0-102">Otros problemas de actualización de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2e5f0-102">Other Reporting Services Upgrade Issues</span></span>
  <span data-ttu-id="2e5f0-103">En este tema se describen problemas conocidos que puede encontrar al actualizar la funcionalidad de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e5f0-103">This topic describes known issues you may experience upgrading [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] functionality.</span></span> <span data-ttu-id="2e5f0-104">**Estos problemas no los detecta el Asesor de actualizaciones.**</span><span class="sxs-lookup"><span data-stu-id="2e5f0-104">**These issues are not detected by Upgrade Advisor.**</span></span> <span data-ttu-id="2e5f0-105">Para obtener más información, consulte las notas de la [versión de SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445)</span><span class="sxs-lookup"><span data-stu-id="2e5f0-105">For additional information, see [SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445)</span></span>  
  
||  
|-|  
|<span data-ttu-id="2e5f0-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; Modo de SharePoint de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e5f0-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
|<span data-ttu-id="2e5f0-107">Incidencia</span><span class="sxs-lookup"><span data-stu-id="2e5f0-107">Issue</span></span>|<span data-ttu-id="2e5f0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e5f0-108">Description</span></span>|<span data-ttu-id="2e5f0-109">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="2e5f0-109">Applies to</span></span>|  
|-----------|-----------------|----------------|  
|<span data-ttu-id="2e5f0-110">Actualización de la granja de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2e5f0-110">SharePoint farm upgrade</span></span>|<span data-ttu-id="2e5f0-111">Actualice el servicio compartido [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] solo después de que todos los demás componentes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] de la granja se hayan actualizado a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e5f0-111">Upgrade the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service only after all other [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] components in the farm have been upgraded to [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span><br /><br /> <span data-ttu-id="2e5f0-112">Para actualizar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] una granja de servidores de SharePoint de varios nodos a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , todas las instancias del [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] complemento para SharePoint en la granja deben actualizarse a la [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] versión antes de actualizar el [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servicio compartido.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-112">To upgrade [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in a multi node SharePoint farm to [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], all instances of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint in the farm must be upgraded to the [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] version before you upgrade the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service.</span></span><br /><br /> <span data-ttu-id="2e5f0-113">La representación de informes generará un error cuando el servicio compartido SharePoint de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se ha actualizado a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] pero otros componentes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] de la granja sigan siendo de la versión [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e5f0-113">Report rendering will fail when the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint shared service has been upgraded to [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] but other [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] components in the farm are still version [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span><br /><br /> <br /><br /> <span data-ttu-id="2e5f0-114">Para obtener más información, vea [Sugerencias, trucos y solución de problemas de SQL Server 2014 Reporting Services](https://go.microsoft.com/fwlink/?LinkID=391254).</span><span class="sxs-lookup"><span data-stu-id="2e5f0-114">For more information, see [SQL Server 2014 Reporting Services Tips, Tricks, and Troubleshooting](https://go.microsoft.com/fwlink/?LinkID=391254).</span></span>|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="2e5f0-115">y [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e5f0-115">and [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]</span></span>|  
|<span data-ttu-id="2e5f0-116">Instalación en paralelo</span><span class="sxs-lookup"><span data-stu-id="2e5f0-116">Side by Side installation</span></span>|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]<span data-ttu-id="2e5f0-117">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]El modo nativo no se puede ejecutar en paralelo con ninguno de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e5f0-117">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native Mode cannot run side by side with either of the following:</span></span><br /><br /> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]<span data-ttu-id="2e5f0-118">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]complemento para SharePoint</span><span class="sxs-lookup"><span data-stu-id="2e5f0-118">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint</span></span><br /><br /> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]<span data-ttu-id="2e5f0-119">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Servicio compartido de SharePoint</span><span class="sxs-lookup"><span data-stu-id="2e5f0-119">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint shared service</span></span><br /><br /> <br /><br /> <span data-ttu-id="2e5f0-120">La instalación en paralelo impide que se [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] inicie el servicio de Windows en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-120">The side by side installation prevents the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native Mode Windows Service from starting.</span></span> <span data-ttu-id="2e5f0-121">Aparecerán mensajes de error similares a los siguientes en el registro de eventos de Windows:</span><span class="sxs-lookup"><span data-stu-id="2e5f0-121">Error messages similar to the following will be seen in the Windows Event log:</span></span><br /><br /> <span data-ttu-id="2e5f0-122">Descripción: La base de datos del servidor de informes tiene una versión no válida.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-122">Description: The report server database is an invalid version.</span></span><br /><br /> <span data-ttu-id="2e5f0-123">Descripción: El servidor de informes [nombre de servidor] no se puede conectar con la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-123">Description: Report Server [server name] cannot connect to the report server database.</span></span>|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="2e5f0-124">en modo nativo</span><span class="sxs-lookup"><span data-stu-id="2e5f0-124">Native mode</span></span>|  
|<span data-ttu-id="2e5f0-125">Error durante la reparación o la actualización</span><span class="sxs-lookup"><span data-stu-id="2e5f0-125">Error during the repair of a failed upgrade</span></span>|<span data-ttu-id="2e5f0-126">**Problema:** Intenta ejecutar una reparación después de que se haya producido un error en una actualización.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-126">**Issue:** You attempt to run a repair after an upgrade has failed.</span></span> <span data-ttu-id="2e5f0-127">La operación de reparación también produce un error y aparecen mensajes parecidos al siguiente en los archivos de registro de instalación:</span><span class="sxs-lookup"><span data-stu-id="2e5f0-127">The repair operation also fails and you see messages similar to the following in the setup log files:</span></span><br /><br /> `(01) 2011-10-27 12:23:15 Slp:` <br /> `(01) 2011-10-27 12:23:15 Slp: Exception type: System.Exception` <br /> `(01) 2011-10-27 12:23:15 Slp:     Message:`  <br /> `(01) 2011-10-27 12:23:15 Slp:         SQLPath element is missing` <br /> `(01) 2011-10-27 12:23:15 Slp:     Data:`  <br /> `(01) 2011-10-27 12:23:15 Slp:       SQL.Setup.FailureCategory = ConfigurationFailure`<br /><br /> <span data-ttu-id="2e5f0-128">Para obtener más información sobre los archivos de registro, vea [ver y leer archivos de registro de instalación de SQL Server](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="2e5f0-128">For more information on the log files, see [View and Read SQL Server Setup Log Files](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md).</span></span><br /><br /> <span data-ttu-id="2e5f0-129">**Solución:** Debe desinstalar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y volver a instalar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e5f0-129">**Solution:** You need to uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and reinstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="2e5f0-130">Ya no es posible llevar a cabo la actualización.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-130">An upgrade is no longer possible.</span></span>|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="2e5f0-131">y [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e5f0-131">and [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]</span></span>|  
|<span data-ttu-id="2e5f0-132">La información de interactividad solo se guarda para la última solicitud.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-132">Interactivity information saved only for the last request.</span></span>|<span data-ttu-id="2e5f0-133">En versiones anteriores de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , las instantáneas guardaban todas las posibles combinaciones de opciones interactivas, como obtener detalles de las opciones y alternar entre ellas.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-133">In earlier versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], snapshots saved all possible combinations of interactive choices, such as drill through information and toggle choices.</span></span> <span data-ttu-id="2e5f0-134">Por ejemplo, podría ver la quinta página de un informe, pero mediante programación cambiar un elemento de la primera página manteniendo el id. correcto para dicho cambio.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-134">For example, you could view page five of a report, but programmatically toggle an item on page one by keeping track of the correct ID for the toggle.</span></span><br /><br /> <span data-ttu-id="2e5f0-135">En [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], solo se genera y se guarda la información de interactividad para la última solicitud de la representación.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-135">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], interactivity information is generated and saved only for the last rendering request.</span></span> <span data-ttu-id="2e5f0-136">No puede ver una página y mediante programación cambiar un elemento de otra página.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-136">You cannot view a page and programmatically toggle an item on another page.</span></span> <span data-ttu-id="2e5f0-137">Solo puede cambiar los elementos de obtención de detalles en la página actual del informe.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-137">You can only toggle drilldown items on the current report page.</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-138">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-138">2005 SP2</span></span>|  
|<span data-ttu-id="2e5f0-139">Los mecanismos de representación y paginación han cambiado.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-139">Rendering and pagination have changed.</span></span>|<span data-ttu-id="2e5f0-140">El modelo de objetos de representación (ROM) ha cambiado en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e5f0-140">The Rendering Object Model (ROM) changed in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="2e5f0-141">Ya no se admiten las versiones anteriores del modelo de objetos de representación.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-141">Earlier versions of the rendering object model are no longer supported.</span></span> <span data-ttu-id="2e5f0-142">Tampoco se admite la posibilidad de obtener acceso al Modelo de objetos de representación desde una extensión de representación multiproceso (y cambiar el contexto en diferentes subprocesos).</span><span class="sxs-lookup"><span data-stu-id="2e5f0-142">Accessing the Rendering Object Model from a multi-threaded rendering extension (and switching context from multiple threads) is not supported.</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-143">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-143">2005 SP2</span></span>|  
|<span data-ttu-id="2e5f0-144">Formato de exportación de archivos CSV rediseñado.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-144">Redesigned CSV export format.</span></span>|<span data-ttu-id="2e5f0-145">En versiones anteriores de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], cuando exportaba un informe a un formato de archivo CSV, se daba formato a los datos de manera que se conservaba la forma de representarlos en la página del informe.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-145">In earlier versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], when you exported a report to a CSV file format, the data was formatted in a way that preserved the way the data appeared on the report page.</span></span> <span data-ttu-id="2e5f0-146">Para las regiones de datos de matriz, esto generaba un formato de datos que no era apto para ser exportado a otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-146">For matrix data regions, this resulted in a data format that was inconvenient to import into other applications.</span></span><br /><br /> <span data-ttu-id="2e5f0-147">En esta versión, al exportar un informe a un archivo CSV, puede elegir entre dos formatos compatibles: modo Predeterminado y modo Compatible.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-147">In this release, when you export a report to a CSV file, you can choose between two supported formats: Default mode and Compliant mode.</span></span> <span data-ttu-id="2e5f0-148">El modo Predeterminado está optimizado para Excel.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-148">Default mode is optimized for Excel.</span></span> <span data-ttu-id="2e5f0-149">El modo compatible está optimizado para aplicaciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-149">Compliant mode is optimized for third-party applications.</span></span><br /><br /> <span data-ttu-id="2e5f0-150">El formato anterior para los archivos CSV ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-150">The earlier format for CSV files is no longer available.</span></span> <span data-ttu-id="2e5f0-151">Sin embargo, para los informes que no utilizan las regiones de datos de matriz, puede utilizar el modo Compatible para obtener un formato de archivo lo más parecido al formato para archivos CSV que se utilizaba anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-151">However, for reports that do not use matrix data regions, you can use Compliant mode to get a file format closest to the earlier CSV file format.</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-152">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-152">2005 SP2</span></span>|  
|<span data-ttu-id="2e5f0-153">Agregados con visibilidad condicional en encabezados y pies de página.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-153">Aggregates with conditional visibility in page headers and footers.</span></span>|<span data-ttu-id="2e5f0-154">En versiones anteriores de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], los sistemas de representación utilizaban diferentes reglas para determinar qué elementos con visibilidad condicional se debían incluir en la página de un informe.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-154">In earlier versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], different renderers used different rules to determine which items with conditional visibility to include on a report page.</span></span> <span data-ttu-id="2e5f0-155">Por ejemplo, no se realizaban cálculos agregados para elementos ocultos en informes impresos, pero sí se calculaban para elementos ocultos en informes que se visualizaban en un explorador o en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office Excel.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-155">For example, aggregate calculations were not performed for hidden items in printed reports, but were calculated for hidden items in reports that you viewed with a browser or in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office Excel.</span></span><br /><br /> <span data-ttu-id="2e5f0-156">En esta versión, todos los sistemas de representación utilizan el mismo conjunto de reglas para determinar qué elementos aparecerán en una página.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-156">In this release, all renderers use the same set of rules to determine which items are on a page.</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-157">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-157">2005 SP2</span></span>|  
|<span data-ttu-id="2e5f0-158">No hay compatibilidad con fórmulas en Excel.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-158">No formula support in Excel.</span></span>|<span data-ttu-id="2e5f0-159">En versiones anteriores de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], existía compatibilidad limitada para convertir expresiones en RDL a fórmulas de Excel.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-159">In earlier versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], there was limited support for translating expressions in RDL to Excel formulas.</span></span> <span data-ttu-id="2e5f0-160">En esta versión, al exportar un informe a Excel, las expresiones RDL no se convertirán en fórmulas de Excel.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-160">In this release, when you export a report to Excel, RDL expressions are not translated to Excel formulas.</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-161">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-161">2005 SP2</span></span>|  
|<span data-ttu-id="2e5f0-162">Elementos superpuestos.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-162">Overlapping items.</span></span>|<span data-ttu-id="2e5f0-163">En versiones anteriores de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], si un informe tenía elementos superpuestos en el área de diseño del informe, si éste se publicaba aparecía una advertencia ("No todos los sistemas de representación admiten elementos del informe superpuestos"), pero los elementos del informe se mantenían en sus posiciones originales sobre el área de diseño.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-163">In earlier versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], if a report had overlapping items on the report design surface, publishing the report produced a warning ("Overlapping report items are not supported in all renderers."), but the report items remained in their original location on the design surface.</span></span> <span data-ttu-id="2e5f0-164">En [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], los elementos del informe se pueden mover para corregir la superposición en caso de que el informe se vaya a visualizar o se vaya a exportar a un sistema de representación que no admita elementos superpuestos.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-164">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], report items may be moved to correct overlapping boundaries when a report is viewed or exported to a renderer that does not support overlapping items.</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-165">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-165">2005 SP2</span></span>|  
|<span data-ttu-id="2e5f0-166">Cambio en el espacio de nombres del modelo de objetos de informe.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-166">Report object model namespace change.</span></span>|<span data-ttu-id="2e5f0-167">En [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , el espacio de nombres del modelo de objetos de informe ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-167">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], the Report Object Model namespace has changed.</span></span> <span data-ttu-id="2e5f0-168">Este espacio de nombres proporciona acceso de solo lectura desde el código personalizado a las colecciones globales, como por ejemplo `Fields`, `Parameters` y `ReportItems`.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-168">This namespace provides read-only access from custom code to global collections like `Fields`, `Parameters`, and `ReportItems`.</span></span> <span data-ttu-id="2e5f0-169">Si el código personalizado existente utiliza explícitamente una referencia completa a un espacio de nombres anterior, este cambio se convierte en un cambio importante.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-169">If existing custom code explicitly uses a fully qualified reference to an earlier namespace, this change is a breaking change.</span></span><br /><br /> <span data-ttu-id="2e5f0-170">Se recomienda no utilizar referencias completas para obtener acceso a las colecciones integradas desde el código.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-170">It is recommended that you do not use fully qualified references to access built-in collections from your code.</span></span> <span data-ttu-id="2e5f0-171">Si no se especifica explícitamente el espacio de nombres, las referencias del código personalizado se resolverán de acuerdo a la versión del modelo de objetos de informe actualmente instalada en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e5f0-171">By not explicitly specifying the namespace, custom code references resolve to the version of the report object model for the currently installed version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-172">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-172">2005 SP2</span></span>|  
|<span data-ttu-id="2e5f0-173">No se admite el proveedor de Instrumental de administración de Windows (WMI) del servidor de informes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 ni de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-173">Report Server Windows Management Instrumentation (WMI) Provider from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 is not supported.</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2e5f0-174">incluye un proveedor de WMI que puede utilizar para configurar, mediante programación, el entorno en el que se ejecutará un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-174">includes a WMI provider that you can use to programmatically configure the environment in which a report server runs.</span></span> <span data-ttu-id="2e5f0-175">La versión [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] incluye una versión totalmente nueva del proveedor WMI que reemplaza por completo a la anterior.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-175">The [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] release of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] includes an all-new version of the WMI provider that completely replaces the previous version.</span></span> <span data-ttu-id="2e5f0-176">Las versiones [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 y 2005 no se admiten en esta versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e5f0-176">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 and 2005 versions are not supported in this release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-177">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-177">2005 SP2</span></span>|  
|<span data-ttu-id="2e5f0-178">Los Nombres principales de servicio (SPN) no se vuelven a crear en un servidor de informes actualizado.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-178">Service Principal Names (SPN) are not recreated on an upgraded report server.</span></span>|<span data-ttu-id="2e5f0-179">Si creó un SPN para el servicio web del servidor de informes, compruebe que la delegación restringida sigue funcionando en el servidor de informes actualizado.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-179">If you created an SPN for the Report Server Web service, verify that constrained delegation still works for the upgraded report server.</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-180">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-180">2005 SP2</span></span>|  
|<span data-ttu-id="2e5f0-181">Los ensamblados personalizados se deben mover manualmente a la nueva carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-181">Custom assemblies must be moved manually to the new installation folder.</span></span>|<span data-ttu-id="2e5f0-182">El asesor de actualizaciones no detecta los ensamblados personalizados y se deben mover manualmente a la nueva carpeta de instalación si se desea seguir utilizando la funcionalidad personalizada en informes.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-182">Custom assemblies are not detected by upgrade advisor, and they must be moved manually to the new installation folder if you want to continue using the custom functionality in reports.</span></span><br /><br /> <span data-ttu-id="2e5f0-183">Si estos ensamblados se instalan en la carpeta de instalación del servidor de informes, necesitan ser movidos a la nueva carpeta de instalación después de completarse la actualización.</span><span class="sxs-lookup"><span data-stu-id="2e5f0-183">If these assemblies are installed in the report server installation folder, they need to be moved to the new installation folder after the upgrade completes.</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e5f0-184">2005 SP2</span><span class="sxs-lookup"><span data-stu-id="2e5f0-184">2005 SP2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e5f0-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e5f0-185">See Also</span></span>  
 [<span data-ttu-id="2e5f0-186">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="2e5f0-186">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  