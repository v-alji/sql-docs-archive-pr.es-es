---
title: Entornos de Integration Services (SSIS) y Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- studio environments [Integration Services]
- tools [Integration Services], Business Intelligence Development Studio
- Business Intelligence Development Studio, Integration Services in
- SQL Server Management Studio [Integration Services]
- SSIS, studio environments
- SQL Server Integration Services, studio environments
- tools [Integration Services], SQL Server Management Studio
ms.assetid: 4eb73e65-d9f3-4ac6-a408-abfa85afc537
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfe0cf7ef482dce3870db8c730c597daf1d539e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673166"
---
# <a name="integration-services-ssis-and-studio-environments"></a><span data-ttu-id="85cda-102">Entornos de Studio e Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="85cda-102">Integration Services (SSIS) and Studio Environments</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="85cda-103">incluye dos estudios para trabajar con [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="85cda-103">includes two studios for working with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="85cda-104">para desarrollar los paquetes [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que una solución empresarial requiere.</span><span class="sxs-lookup"><span data-stu-id="85cda-104">for developing the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that a business solution requires.</span></span> [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="85cda-105">proporciona el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en el que se crean paquetes.</span><span class="sxs-lookup"><span data-stu-id="85cda-105">provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you create packages.</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="85cda-106">para administrar paquetes en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="85cda-106">for managing packages in a production environment.</span></span>  
  
## <a name="sql-server-data-tools"></a><span data-ttu-id="85cda-107">SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="85cda-107">SQL Server Data Tools</span></span>  
 <span data-ttu-id="85cda-108">Al trabajar en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], se pueden realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="85cda-108">Working in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="85cda-109">Ejecutar el Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para crear paquetes básicos que copian datos de un origen en un destino.</span><span class="sxs-lookup"><span data-stu-id="85cda-109">Run the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to create basic packages that copy data from a source to a destination.</span></span>  
  
-   <span data-ttu-id="85cda-110">Crear paquetes que incluyan flujo de control complejo, flujo de datos, lógica controlada por eventos y registro.</span><span class="sxs-lookup"><span data-stu-id="85cda-110">Create packages that include complex control flow, data flow, event-driven logic, and logging.</span></span>  
  
-   <span data-ttu-id="85cda-111">Probar y depurar paquetes mediante las características de solución de problemas y supervisión en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] , y las características de depuración en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85cda-111">Test and debug packages by using the troubleshooting and monitoring features in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, and the debugging features in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="85cda-112">Crear configuraciones que actualizan las propiedades de los paquetes y los objetos de paquete en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="85cda-112">Create configurations that update the properties of packages and package objects at run time.</span></span>  
  
-   <span data-ttu-id="85cda-113">Crear una utilidad de implementación que pueda instalar paquetes y sus dependencias en otros equipos.</span><span class="sxs-lookup"><span data-stu-id="85cda-113">Create a deployment utility that can install packages and their dependencies on other computers.</span></span>  
  
-   <span data-ttu-id="85cda-114">Guardar copias de paquetes en la base de datos msdb de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], el almacén de paquetes de [!INCLUDE[ssIS](../includes/ssis-md.md)] y el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="85cda-114">Save copies of packages to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
 <span data-ttu-id="85cda-115">Para obtener más información sobre [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], consulte [SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686.aspx).</span><span class="sxs-lookup"><span data-stu-id="85cda-115">For more information about [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], see [SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686.aspx).</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="85cda-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="85cda-116">SQL Server Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="85cda-117">proporciona el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que utiliza para administrar los paquetes, supervisar los paquetes en ejecución y determinar el impacto y el linaje de los datos de los objetos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="85cda-117">provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that you use to manage packages, monitor running packages, and determine impact and data lineage for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="85cda-118">Al trabajar en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], se pueden realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="85cda-118">Working in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="85cda-119">Crear carpetas para organizar paquetes de una manera que sirva para su organización.</span><span class="sxs-lookup"><span data-stu-id="85cda-119">Create folders to organize packages in a way that is meaningful to your organization.</span></span>  
  
-   <span data-ttu-id="85cda-120">Ejecutar paquetes que se almacenan en el equipo local mediante la utilidad de ejecución de paquetes.</span><span class="sxs-lookup"><span data-stu-id="85cda-120">Run packages that are stored on the local computer by using the Execute Package utility.</span></span>  
  
-   <span data-ttu-id="85cda-121">Ejecutar la Utilidad de ejecución de paquetes para generar una línea de comandos para usarse al ejecutar a utilidad de símbolo del sistema **dtexec** (dtexec.exe).</span><span class="sxs-lookup"><span data-stu-id="85cda-121">Run the Execute Package utility to generate a command line to use when you run the **dtexec** command prompt utility (dtexec.exe).</span></span>  
  
-   <span data-ttu-id="85cda-122">Importar y exportar paquetes hacia y desde la base de datos msdb de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], el Almacén de paquetes de [!INCLUDE[ssIS](../includes/ssis-md.md)] y el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="85cda-122">Import and export packages to and from the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
