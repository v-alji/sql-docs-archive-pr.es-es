---
title: Archivos y números de versión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, versions
- components [SMO]
- files [SMO], components
- SMO [SQL Server], versions
- versions [SMO]
ms.assetid: 510907b6-e7a9-41bd-b892-d6d99a5118e1
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1a7286f15af28f97e488b8b40fd745a0d320108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672905"
---
# <a name="files-and-version-numbers"></a><span data-ttu-id="d9766-102">Archivos y números de versión</span><span class="sxs-lookup"><span data-stu-id="d9766-102">Files and Version Numbers</span></span>
  <span data-ttu-id="d9766-103">Todos los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componentes de objetos de administración (SMO) necesarios se instalan como parte de una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cliente o servidor.</span><span class="sxs-lookup"><span data-stu-id="d9766-103">All required [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) components are installed as part of an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client or server.</span></span> <span data-ttu-id="d9766-104">SMO se implementa en varios ensamblados administrados.</span><span class="sxs-lookup"><span data-stu-id="d9766-104">SMO is implemented in several managed assemblies.</span></span> <span data-ttu-id="d9766-105">Puede desarrollar aplicaciones SMO en un cliente o un servidor.</span><span class="sxs-lookup"><span data-stu-id="d9766-105">You can develop SMO applications on either a client or a server.</span></span>  
  
|<span data-ttu-id="d9766-106">Directorio</span><span class="sxs-lookup"><span data-stu-id="d9766-106">Directory</span></span>|<span data-ttu-id="d9766-107">Archivo</span><span class="sxs-lookup"><span data-stu-id="d9766-107">File</span></span>|<span data-ttu-id="d9766-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9766-108">Description</span></span>|  
|---------------|----------|-----------------|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="d9766-109">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="d9766-109">Microsoft.SqlServer.ConnectionInfo.dll</span></span>|<span data-ttu-id="d9766-110">Contiene compatibilidad para conectar a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9766-110">Contains support for connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="d9766-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span><span class="sxs-lookup"><span data-stu-id="d9766-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span></span>|<span data-ttu-id="d9766-112">Contiene compatibilidad para programar [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span><span class="sxs-lookup"><span data-stu-id="d9766-112">Contains support for programming the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span></span> <span data-ttu-id="d9766-113">Solo se requiere en programas que tienen acceso a Service Broker.</span><span class="sxs-lookup"><span data-stu-id="d9766-113">This is required only in programs that access the Service Broker.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="d9766-114">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="d9766-114">Microsoft.SqlServer.Smo.dll</span></span>|<span data-ttu-id="d9766-115">Contiene la mayoría de las clases SMO.</span><span class="sxs-lookup"><span data-stu-id="d9766-115">Contains the most of the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="d9766-116">Microsoft.SqlServer.SmoExtended.dll</span><span class="sxs-lookup"><span data-stu-id="d9766-116">Microsoft.SqlServer.SmoExtended.dll</span></span><br /><br /> <span data-ttu-id="d9766-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="d9766-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span><br /><br /> <span data-ttu-id="d9766-118">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="d9766-118">Microsoft.SqlServer.SqlEnum.dll</span></span>|<span data-ttu-id="d9766-119">Contiene compatibilidad para las clases SMO.</span><span class="sxs-lookup"><span data-stu-id="d9766-119">Contains support for the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="d9766-120">Microsoft.SqlServer.WmiEnum.dll</span><span class="sxs-lookup"><span data-stu-id="d9766-120">Microsoft.SqlServer.WmiEnum.dll</span></span>|<span data-ttu-id="d9766-121">Contiene las clases de proveedor de Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="d9766-121">Contains the Windows Management Instrumentation (WMI) Provider classes.</span></span> <span data-ttu-id="d9766-122">Solo se requiere en los programas que utilizan las clases del proveedor WMI.</span><span class="sxs-lookup"><span data-stu-id="d9766-122">This is required only for programs that use the WMI Provider classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="d9766-123">Microsoft.SqlServer.RegSvrEnum.dll</span><span class="sxs-lookup"><span data-stu-id="d9766-123">Microsoft.SqlServer.RegSvrEnum.dll</span></span>|<span data-ttu-id="d9766-124">Contiene las clases de servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="d9766-124">Contains the Registered Server classes.</span></span> <span data-ttu-id="d9766-125">Solo se requiere en los programas que utilizan las clases de servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="d9766-125">This is required only for programs that use the Registered Server classes.</span></span>|  
  
  
