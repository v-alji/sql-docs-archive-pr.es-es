---
title: access check cache (opciones de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
- access check cache bucket count
- access check cache quota
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feed895eeb7b11b4c41c51c4c26859a1057d2733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662252"
---
# <a name="access-check-cache-server-configuration-options"></a><span data-ttu-id="8a48b-102">access check cache (opciones de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="8a48b-102">access check cache Server Configuration Options</span></span>
<span data-ttu-id="8a48b-103">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]tiene acceso a los objetos de base de datos, la comprobación del acceso se almacena en memoria caché en una estructura interna denominada **memoria caché de resultados de comprobación de acceso**.</span><span class="sxs-lookup"><span data-stu-id="8a48b-103">When database objects are accessed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the access check is cached in an internal structure called the **access check result cache**.</span></span> 
  
<span data-ttu-id="8a48b-104">La opción **access check cache bucket count** controla el número de cubos de hash que se usan para la caché de resultados de comprobación de acceso.</span><span class="sxs-lookup"><span data-stu-id="8a48b-104">The **access check cache bucket count** option controls the number of hash buckets that are used for the access check result cache.</span></span> 

<span data-ttu-id="8a48b-105">La opción **access check cache quota** controla el número de entradas que se almacenan en la caché de resultados de comprobación de acceso.</span><span class="sxs-lookup"><span data-stu-id="8a48b-105">The **access check cache quota** option controls the number of entries that are stored in the access check result cache.</span></span> <span data-ttu-id="8a48b-106">Cuando se alcanza el número máximo de entradas, las más antiguas se quitan de la caché de resultados de comprobación de acceso.</span><span class="sxs-lookup"><span data-stu-id="8a48b-106">When the maximum number of entries is reached, the oldest entries are removed from the access check result cache.</span></span>
  
<span data-ttu-id="8a48b-107">Los valores predeterminados de 0 indican que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está administrando estas opciones.</span><span class="sxs-lookup"><span data-stu-id="8a48b-107">The default values of 0 indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is managing these options.</span></span> <span data-ttu-id="8a48b-108">De [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] a través de [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] , los valores predeterminados se traducen a las siguientes configuraciones internas:</span><span class="sxs-lookup"><span data-stu-id="8a48b-108">From [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] through [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the default values translate to the following internal configurations:</span></span>
-   <span data-ttu-id="8a48b-109">En el caso de Access check cache bucket Count, el valor 0 establece un valor predeterminado de 256 cubos para la arquitectura x86 y 2.048 depósitos para arquitecturas x64 e IA-64.</span><span class="sxs-lookup"><span data-stu-id="8a48b-109">For access check cache bucket count, the value 0 sets a default value of 256 buckets for x86 architecture, and 2,048 buckets for x64 and IA-64 architectures.</span></span>
-   <span data-ttu-id="8a48b-110">Para la comprobación de acceso de la cuota de caché, el valor 0 establece un valor predeterminado de 1.024 entradas para la arquitectura x86 y de 28.192.048 depósitos para las arquitecturas x64 e IA-64.</span><span class="sxs-lookup"><span data-stu-id="8a48b-110">For access check cache quota, the value 0 sets a default value of 1,024 entries for x86 architecture, and 28,192,048 buckets for x64 and IA-64 architectures.</span></span>

<span data-ttu-id="8a48b-111">En circunstancias excepcionales, el rendimiento se puede mejorar cambiando estas opciones.</span><span class="sxs-lookup"><span data-stu-id="8a48b-111">In rare circumstances, performance can be improved by changing these options.</span></span> <span data-ttu-id="8a48b-112">Por ejemplo, puede que quiera reducir el tamaño de la caché de resultados de la comprobación de acceso si se usa demasiada memoria.</span><span class="sxs-lookup"><span data-stu-id="8a48b-112">For example, you may want to reduce the size of the access check result cache if too much memory is used.</span></span> <span data-ttu-id="8a48b-113">También puede que quiera aumentar el tamaño de la caché de resultados de comprobación de acceso si experimenta un uso intensivo de la CPU cuando se vuelven a calcular los permisos.</span><span class="sxs-lookup"><span data-stu-id="8a48b-113">Or, you may want to increase the size of the access check result cache if you experience high CPU usage when permissions are recalculated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a48b-114">Microsoft solo recomienda cambiar estas opciones cuando lo indiquen los servicios de soporte al cliente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8a48b-114">Microsoft recommends only changing these options when directed by Microsoft Customer Support Services.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a48b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a48b-115">See Also</span></span>  
 <span data-ttu-id="8a48b-116">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8a48b-116">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="8a48b-117">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a48b-117">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
