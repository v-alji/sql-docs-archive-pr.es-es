---
title: Propiedades de SQL Server Browser (pestaña Avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ba79137a-cb72-4bf3-a650-e11d02cfce10
author: stevestein
ms.author: sstein
ms.openlocfilehash: 480cd93c3feca44dd455a1a9ce2fd12994ca6100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676284"
---
# <a name="sql-server-browser-properties-advanced-tab"></a><span data-ttu-id="9315b-102">Propiedades de SQL Server Browser (pestaña Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="9315b-102">SQL Server Browser Properties (Advanced Tab)</span></span>
  <span data-ttu-id="9315b-103">El programa Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ejecuta como un servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9315b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> <span data-ttu-id="9315b-104">El Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escucha las solicitudes entrantes de recursos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y proporciona información sobre las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9315b-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9315b-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="9315b-105">Options</span></span>  
 <span data-ttu-id="9315b-106">**Agrupado**</span><span class="sxs-lookup"><span data-stu-id="9315b-106">**Clustered**</span></span>  
 <span data-ttu-id="9315b-107">Indica si este servicio está instalado como un recurso de un servidor en clúster.</span><span class="sxs-lookup"><span data-stu-id="9315b-107">Indicates if this service is installed as a resource of a clustered server.</span></span>  
  
 <span data-ttu-id="9315b-108">**Informes de comentarios de clientes**</span><span class="sxs-lookup"><span data-stu-id="9315b-108">**Customer Feedback Reporting**</span></span>  
 <span data-ttu-id="9315b-109">Indica si se ha habilitado la supervisión de la calidad del servicio en este servicio.</span><span class="sxs-lookup"><span data-stu-id="9315b-109">Indicates whether Service Quality Monitoring has been enabled on this service.</span></span> <span data-ttu-id="9315b-110">Para obtener más información acerca de los informes de comentarios de clientes, busque el tema sobre la configuración de informes de errores y uso en los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="9315b-110">For more information on Customer Feedback Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="9315b-111">**Volcar directorio**</span><span class="sxs-lookup"><span data-stu-id="9315b-111">**Dump Directory**</span></span>  
 <span data-ttu-id="9315b-112">Ubicación de los volcados de memoria si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="9315b-112">The location where memory dumps are placed in case of an error.</span></span>  
  
 <span data-ttu-id="9315b-113">**Informes de errores**</span><span class="sxs-lookup"><span data-stu-id="9315b-113">**Error Reporting**</span></span>  
 <span data-ttu-id="9315b-114">Cuando se establece en **Sí**, el programa Dr. Watson envía información a [!INCLUDE[msCoName](../../includes/msconame-md.md)] o a su servidor de errores si se produce un error grave.</span><span class="sxs-lookup"><span data-stu-id="9315b-114">When set to **Yes**, the Dr. Watson program forwards information to either [!INCLUDE[msCoName](../../includes/msconame-md.md)] or your error server if a serious failure occurs.</span></span> <span data-ttu-id="9315b-115">Para obtener más información acerca de Informes de errores, busque el tema sobre la configuración de informes de errores y uso en los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="9315b-115">For more information on Error Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="9315b-116">**Id. de instancia**</span><span class="sxs-lookup"><span data-stu-id="9315b-116">**Instance ID**</span></span>  
 <span data-ttu-id="9315b-117">Indica la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que ha usado esta instancia del Agente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9315b-117">Indicates the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that used this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance.</span></span> <span data-ttu-id="9315b-118">La instancia predeterminada es **MSSQL10_50.MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="9315b-118">The default instance is **MSSQL10_50.MSSQLSERVER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9315b-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9315b-119">See Also</span></span>  
 [<span data-ttu-id="9315b-120">Servicio SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="9315b-120">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
