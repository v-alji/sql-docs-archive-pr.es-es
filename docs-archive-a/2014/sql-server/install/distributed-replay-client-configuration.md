---
title: Configuración del cliente de Distributed Replay | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccf03e32-6bd9-43c0-b9b6-9fe0d9163339
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 53124029483c25ed7894b279283e1de02c647350
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677400"
---
# <a name="distributed-replay-client-configuration"></a><span data-ttu-id="90520-102">Configuración de Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="90520-102">Distributed Replay Client Configuration</span></span>
  <span data-ttu-id="90520-103">Use la página **Configuración de Distributed Replay Client** del Asistente para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el fin de especificar los usuarios a los que desee conceder permisos administrativos para el servicio Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="90520-103">Use the **Distributed Replay Client Configuration** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the users you want to grant administrative permissions to for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="90520-104">Los usuarios con permisos administrativos tendrán acceso ilimitado al servicio Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="90520-104">Users that have administrative permissions will have unlimited access to the Distributed Replay client service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90520-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="90520-105">Options</span></span>  
 <span data-ttu-id="90520-106">**Nombre del controlador**</span><span class="sxs-lookup"><span data-stu-id="90520-106">**Controller Name**</span></span>  
 <span data-ttu-id="90520-107">Este es un parámetro opcional y el valor predeterminado es \<*blank*> .</span><span class="sxs-lookup"><span data-stu-id="90520-107">This is an optional parameter, and the default value is \<*blank*>.</span></span>  
  
 <span data-ttu-id="90520-108">Escriba el nombre del controlador con el que se comunicará el equipo cliente para el servicio Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="90520-108">Enter the name of the controller that the client computer will communicate with for the Distributed Replay client service.</span></span> <span data-ttu-id="90520-109">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90520-109">Note the following:</span></span>  
  
-   <span data-ttu-id="90520-110">El nombre debe ser un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="90520-110">The name must be a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="90520-111">Por ejemplo, un llamado servidor1 en la jerarquía de productos de Microsoft puede tener un FQDN de servidor1.productos.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="90520-111">For example, a host called server1 in the products hierarchy at Microsoft may have an FQDN of server1.products.microsoft.com.</span></span>  
  
-   <span data-ttu-id="90520-112">Si ya ha configurado un controlador, escriba el nombre del controlador mientras configura cada cliente.</span><span class="sxs-lookup"><span data-stu-id="90520-112">If you have already set up a controller, enter the name of the controller while configuring each client.</span></span>  
  
-   <span data-ttu-id="90520-113">Si aún no ha configurado ningún controlador, puede dejar el nombre del controlador en blanco.</span><span class="sxs-lookup"><span data-stu-id="90520-113">If you have net yet set up a controller, you can leave the controller name blank.</span></span> <span data-ttu-id="90520-114">Sin embargo, debe escribir manualmente el nombre del controlador en el archivo de **configuración de cliente** .</span><span class="sxs-lookup"><span data-stu-id="90520-114">However, you must manually enter the controller name in the **client configuration** file.</span></span>  
  
 <span data-ttu-id="90520-115">**Directorio de trabajo**</span><span class="sxs-lookup"><span data-stu-id="90520-115">**Working Directory**</span></span>  
 <span data-ttu-id="90520-116">Especifique el directorio de trabajo para el servicio Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="90520-116">Specify the working directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="90520-117">El directorio de trabajo predeterminado es \<*drive letter*>:\Archivos de programa\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span><span class="sxs-lookup"><span data-stu-id="90520-117">The default working directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span></span>  
  
 <span data-ttu-id="90520-118">**Directorio de resultados**</span><span class="sxs-lookup"><span data-stu-id="90520-118">**Result Directory**</span></span>  
 <span data-ttu-id="90520-119">Especifique el directorio de resultados para el servicio Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="90520-119">Specify the result directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="90520-120">El directorio de resultados predeterminado es \<*drive letter*>:\Archivos de programa\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span><span class="sxs-lookup"><span data-stu-id="90520-120">The default result directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span></span>  
  
  
