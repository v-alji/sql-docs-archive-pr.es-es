---
title: Servicio Servidor de informes de Windows (MSSQLServer) 107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- MSSQLServer 107 error
ms.assetid: 52b5704b-27f9-400a-a821-d8fa0786afe4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8651f98b47b698fbe3cfb6a152b9220a84ed7256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671928"
---
# <a name="report-server-windows-service-mssqlserver-107"></a><span data-ttu-id="af187-102">Servicio Servidor de informes de Windows (MSSQLServer) 107</span><span class="sxs-lookup"><span data-stu-id="af187-102">Report Server Windows Service (MSSQLServer) 107</span></span>
    
## <a name="details"></a><span data-ttu-id="af187-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="af187-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af187-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="af187-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="af187-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="af187-105">Event ID</span></span>|<span data-ttu-id="af187-106">107</span><span class="sxs-lookup"><span data-stu-id="af187-106">107</span></span>|  
|<span data-ttu-id="af187-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="af187-107">Event Source</span></span>|<span data-ttu-id="af187-108">Servicio Servidor de informes de Windows</span><span class="sxs-lookup"><span data-stu-id="af187-108">Report Server Windows Service</span></span>|  
|<span data-ttu-id="af187-109">Componente</span><span class="sxs-lookup"><span data-stu-id="af187-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="af187-110">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="af187-110">Message Text</span></span>|<span data-ttu-id="af187-111">El servicio Servidor de informes de Windows (MSSQLSERVER) no se puede conectar a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af187-111">Report Server Windows Service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="af187-112">Explicación</span><span class="sxs-lookup"><span data-stu-id="af187-112">Explanation</span></span>  
 <span data-ttu-id="af187-113">El servicio del Servidor de informes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no puede establecer conexión con la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af187-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service cannot connect to the report server database.</span></span> <span data-ttu-id="af187-114">Este error se produce durante una reiniciación del servicio si no se puede establecer una conexión con la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af187-114">This error occurs during a service restart if a connection to the report server database cannot be established.</span></span> <span data-ttu-id="af187-115">Entre las condiciones en que se produce este error se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="af187-115">Conditions under which this error occurs include the following:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="af187-116">[!INCLUDE[ssDE](../../includes/ssde-md.md)] no se está ejecutando cuando se inicia el servicio del Servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af187-116">[!INCLUDE[ssDE](../../includes/ssde-md.md)] service is not running when the Report Server service starts.</span></span>  
  
-   <span data-ttu-id="af187-117">La conexión con el servicio de [!INCLUDE[ssDE](../../includes/ssde-md.md)] sufre un error porque no están habilitadas las conexiones remotas o el protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="af187-117">The connection to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service fails because remote connections or the TCP/IP protocol is not enabled.</span></span>  
  
-   <span data-ttu-id="af187-118">La base de datos del servidor de informes no está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="af187-118">The report server database is not configured correctly.</span></span>  
  
-   <span data-ttu-id="af187-119">La cuenta del servicio no está configurada correctamente o dicha cuenta ya no tiene permisos para la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af187-119">The service account is not configured correctly, or the account no longer has permissions on the report server database.</span></span> <span data-ttu-id="af187-120">Esto puede producirse si no se utiliza la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para configurar la cuenta o la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af187-120">This can occur if you do not use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set up the account or the report server database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="af187-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="af187-121">User Action</span></span>  
 <span data-ttu-id="af187-122">Inicie el servicio de [!INCLUDE[ssDE](../../includes/ssde-md.md)] si no se está ejecutando y compruebe que las conexiones remotas están habilitadas para el protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="af187-122">Start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service if it is not running and check that remote connections are enabled for TCP/IP protocol.</span></span>  
  
 <span data-ttu-id="af187-123">Use la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para configurar la cuenta del servicio y la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="af187-123">Use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to configure the report server database and service account.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="af187-124">Solo para uso interno</span><span class="sxs-lookup"><span data-stu-id="af187-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af187-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af187-125">See Also</span></span>  
 <span data-ttu-id="af187-126">[Configurar la cuenta de servicio del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="af187-126">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="af187-127">[Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="af187-127">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 [<span data-ttu-id="af187-128">Inicio y detención del servicio del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="af187-128">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
