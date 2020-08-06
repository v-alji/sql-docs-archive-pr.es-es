---
title: Componentes de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Upgrade Advisor, components
- listing components to analyze
- Upgrade Advisor [SQL Server], components
- component analysis [Upgrade Advisor]
- finding components to analyze
- locating components to analyze
- detecting components to analyze
- server names [Upgrade Advisor]
- analyzing system [Upgrade Advisor], component list
- identifying components to analyze
ms.assetid: 539b9525-ce3f-4950-9146-5527a5a297ee
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95fe39ce8e616b238cf7c70763e7cf1819341f16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751678"
---
# <a name="sql-server-components"></a><span data-ttu-id="5cd3d-102">Componentes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5cd3d-102">SQL Server Components</span></span>
  <span data-ttu-id="5cd3d-103">Puede ejecutar el Asistente para análisis del Asesor de actualizaciones en un equipo local o remoto que tenga [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] instalado,, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5cd3d-103">You can run the Upgrade Advisor Analysis Wizard against a local or remote computer that has [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] installed.</span></span> <span data-ttu-id="5cd3d-104">El primer paso en el análisis previo a la actualización es identificar el equipo y los componentes para el análisis.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-104">The first step in the pre-upgrade analysis is to identify the computer and components for analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5cd3d-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="5cd3d-105">Options</span></span>  
 <span data-ttu-id="5cd3d-106">**Nombre del equipo**</span><span class="sxs-lookup"><span data-stu-id="5cd3d-106">**Computer name**</span></span>  
 <span data-ttu-id="5cd3d-107">Especifica el nombre del equipo que se va a analizar.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-107">Specifies the name of the computer to analyze.</span></span> <span data-ttu-id="5cd3d-108">El asesor de actualizaciones rellena el cuadro **nombre del servidor** con el nombre del equipo local.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-108">Upgrade Advisor populates the **Server name** box with the local computer name.</span></span> <span data-ttu-id="5cd3d-109">También puede utilizar "." y "localhost" para conectarse con el equipo local.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-109">You can also use "." and "localhost" to connect to the local computer.</span></span>  
  
 <span data-ttu-id="5cd3d-110">Para analizar un equipo diferente, utilice las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5cd3d-110">To analyze a different computer, use the following guidelines:</span></span>  
  
-   <span data-ttu-id="5cd3d-111">Para examinar instancias no agrupadas, escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-111">To scan nonclustered instances, enter the computer name.</span></span>  
  
-   <span data-ttu-id="5cd3d-112">Para examinar las instancias clúster, escriba el nombre de la instancia en clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cd3d-112">To scan clustered instances, enter the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span>  
  
-   <span data-ttu-id="5cd3d-113">Para examinar los componentes no agrupados que están instalados en un nodo de un clúster, escriba el nombre de equipo del nodo de clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-113">To scan nonclustered components that are installed on a node of a cluster, enter the computer name of the failover cluster node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5cd3d-114">No incluya el nombre de instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cd3d-114">Do not include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name.</span></span>  
  
 <span data-ttu-id="5cd3d-115">En lugar de especificar el nombre de equipo, puede especificar la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-115">Instead of specifying the computer name, you can specify the IP address.</span></span>  
  
 <span data-ttu-id="5cd3d-116">Si está examinando [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], debe especificar el nombre del equipo local.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-116">If scanning [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must specify the name of the local computer.</span></span> <span data-ttu-id="5cd3d-117">El Asesor de actualizaciones solo examina los servidores de informes locales.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-117">Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="5cd3d-118">**Detectar**</span><span class="sxs-lookup"><span data-stu-id="5cd3d-118">**Detect**</span></span>  
 <span data-ttu-id="5cd3d-119">El botón **detectar** accede al equipo especificado y detecta los componentes que se deben analizar:</span><span class="sxs-lookup"><span data-stu-id="5cd3d-119">The **Detect** button accesses the specified computer and detects components to analyze:</span></span>  
  
-   <span data-ttu-id="5cd3d-120">Si se está analizando una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un equipo remoto, deberá habilitar los servicios de Registro remoto en dicho equipo.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-120">If you are analyzing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance on a remote computer, you must enable the remote registry services on the remote computer.</span></span>  
  
-   <span data-ttu-id="5cd3d-121">Se detectará [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si se encuentra una instancia de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] en el Registro del equipo.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is detected if an instance of [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] is found in the computer's registry.</span></span>  
  
-   <span data-ttu-id="5cd3d-122">Se detectará [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] si se encuentra una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en el Registro del equipo.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-122">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is detected if an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is found in the computer's registry.</span></span>  
  
-   <span data-ttu-id="5cd3d-123">Se detectará [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] si se encuentra [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en el registro del equipo.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-123">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is detected if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is found in the computer's registry.</span></span> <span data-ttu-id="5cd3d-124">No obstante, el Asesor de actualizaciones solo examina los servidores de informes locales.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-124">However, Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="5cd3d-125">**Componentes**</span><span class="sxs-lookup"><span data-stu-id="5cd3d-125">**Components**</span></span>  
 <span data-ttu-id="5cd3d-126">Seleccione los componentes que desea analizar.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-126">Select the components to analyze.</span></span> <span data-ttu-id="5cd3d-127">Puede hacer clic en el botón **detectar** para seleccionar todos los componentes instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-127">You can click the **Detect** button to select all the components installed on the computer.</span></span> <span data-ttu-id="5cd3d-128">Aparecerá una marca de verificación junto a aquellos componentes que se han detectado como instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-128">A check mark will appear next to the components that are detected as installed on the computer.</span></span> <span data-ttu-id="5cd3d-129">También puede seleccionar manualmente los componentes a analizar activando o desactivando la casilla que se encuentra al lado de cada componente.</span><span class="sxs-lookup"><span data-stu-id="5cd3d-129">You can also manually select the components to analyze by selecting or clearing the check box next to each component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd3d-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5cd3d-130">See Also</span></span>  
 <span data-ttu-id="5cd3d-131">[Trabajar con el asesor de actualizaciones](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="5cd3d-131">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="5cd3d-132">Referencia de la interfaz de usuario del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="5cd3d-132">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
