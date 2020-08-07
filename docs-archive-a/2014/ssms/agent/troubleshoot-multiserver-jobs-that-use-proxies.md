---
title: Solucionar problemas de trabajos multiservidor que usan servidores proxy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], multiserver jobs
- jobs [SQL Server Agent], multiserver jobs using proxies
ms.assetid: fc579bd3-010c-4f72-8b5c-d0cc18a1f280
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19de975ef5e1f22c93cec72a5014a01da5b03dd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745611"
---
# <a name="troubleshoot-multiserver-jobs-that-use-proxies"></a><span data-ttu-id="6d3a6-102">Solucionar problemas de trabajos multiservidor que usan servidores proxy</span><span class="sxs-lookup"><span data-stu-id="6d3a6-102">Troubleshoot Multiserver Jobs That Use Proxies</span></span>
  <span data-ttu-id="6d3a6-103">Los trabajos distribuidos que tienen pasos asociados a un proxy se ejecutan en el contexto de la cuenta de proxy del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="6d3a6-103">Distributed jobs whose steps are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="6d3a6-104">Si se producen errores en los pasos de trabajo que utilizan cuentas de proxy cuando se descargan desde el servidor maestro, busque en la columna **error_message** de la tabla **sysdownloadlist** de la base de datos **msdb** los siguientes mensajes de error:</span><span class="sxs-lookup"><span data-stu-id="6d3a6-104">If job steps that use proxy accounts fail when downloaded from the master server, check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="6d3a6-105">"Este trabajo requiere una cuenta de proxy, pero la coincidencia de proxy se ha deshabilitado en el servidor de destino."</span><span class="sxs-lookup"><span data-stu-id="6d3a6-105">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="6d3a6-106">Para resolver este error, establezca el valor de **\ HKEY_LOCAL_MACHINE \SOFTWARE\MICROSOFT\MICROSOFT SQL Server\Mssql.** _ \<n_> **\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** la subclave del registro en **1 (true)**.</span><span class="sxs-lookup"><span data-stu-id="6d3a6-106">To resolve this error, set the **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL.**_\<n_>**\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** registry subkey to **1 (true)**.</span></span> <span data-ttu-id="6d3a6-107">De forma predeterminada, esta subclave se establece en **0** ( `false` ).</span><span class="sxs-lookup"><span data-stu-id="6d3a6-107">By default, this subkey is set to **0** (`false`).</span></span> <span data-ttu-id="6d3a6-108">El valor de **MSSQL.**\<*n*></span><span class="sxs-lookup"><span data-stu-id="6d3a6-108">The value of **MSSQL.**\<*n*></span></span> <span data-ttu-id="6d3a6-109">es el nombre de la instancia; por ejemplo, **MSSQL. 1** o **MSSQL. 3**.</span><span class="sxs-lookup"><span data-stu-id="6d3a6-109">is the instance name; for example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
-   <span data-ttu-id="6d3a6-110">"No se encontró el proxy".</span><span class="sxs-lookup"><span data-stu-id="6d3a6-110">"Proxy not found."</span></span>  
  
     <span data-ttu-id="6d3a6-111">Para resolver este error, asegúrese de que existe una cuenta de proxy en el servidor de destino con el mismo nombre que la cuenta de proxy del servidor maestro en la que se ejecuta el paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6d3a6-111">To resolve this error, make sure a proxy account exists on the target server with the same name as the master server proxy account under which the job step runs.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6d3a6-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d3a6-112">See Also</span></span>  
 [<span data-ttu-id="6d3a6-113">Crear un entorno multiservidor</span><span class="sxs-lookup"><span data-stu-id="6d3a6-113">Create a Multiserver Environment</span></span>](create-a-multiserver-environment.md)  
  
  
