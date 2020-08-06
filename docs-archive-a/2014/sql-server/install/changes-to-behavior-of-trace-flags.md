---
title: Cambios en el comportamiento de las marcas de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- trace flags [SQL Server], behavior changes
ms.assetid: d739df96-2659-4383-8e10-194657632526
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11d71e8401f6b870aaeb3f64f4145b509e3a3fe0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672509"
---
# <a name="changes-to-behavior-of-trace-flags"></a><span data-ttu-id="18266-102">Cambios en el comportamiento de marcas de seguimiento</span><span class="sxs-lookup"><span data-stu-id="18266-102">Changes to behavior of trace flags</span></span>
  <span data-ttu-id="18266-103">Las marcas de seguimiento globales establecidos por una sesión surten efecto en otras sesiones de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="18266-103">Global trace flags set by a session take effect in other sessions immediately.</span></span> <span data-ttu-id="18266-104">Algunas marcas de seguimiento de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] no existen en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18266-104">Some trace flags from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] do not exist in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="18266-105">Componente</span><span class="sxs-lookup"><span data-stu-id="18266-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="18266-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="18266-106">Description</span></span>  
 <span data-ttu-id="18266-107">Le recomendamos deshabilitar todas las marcas de seguimiento antes de actualizar.</span><span class="sxs-lookup"><span data-stu-id="18266-107">We recommend that you disable all trace flags before you upgrade.</span></span> <span data-ttu-id="18266-108">Las marcas de seguimiento que modifican la disponibilidad de la base de datos o los modos de recuperación podrían impedir que se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] actualice correctamente la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18266-108">Trace flags that modify the database availability or recovery modes might prevent the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] from successfully upgrading your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="18266-109">Puede habilitar las marcas de seguimiento después de comprobar que sean necesarias y que siguen siendo válidas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18266-109">You can enable the trace flags after you verify that the trace flags are required and are still valid in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="18266-110">Si necesita volver a habilitar las marcas de seguimiento, debería realizar pruebas adicionales en su instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18266-110">If you must re-enable trace flags, you should perform additional tests on your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="18266-111">admite marcas de seguimiento globales y de nivel de sesión.</span><span class="sxs-lookup"><span data-stu-id="18266-111">supports global and session level trace flags.</span></span> <span data-ttu-id="18266-112">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], es posible especificar las marcas de seguimiento como locales o globales utilizando un argumento adicional (-1) en el comando DBCC TRACEON.</span><span class="sxs-lookup"><span data-stu-id="18266-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], trace flags can be specified as either local or global by using an additional argument (-1) in the DBCC TRACEON command.</span></span> <span data-ttu-id="18266-113">Si no se especifica este argumento, el valor predeterminado será local.</span><span class="sxs-lookup"><span data-stu-id="18266-113">If this argument is not specified, the default value is local.</span></span>  
  
 <span data-ttu-id="18266-114">Además, en [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] , una marca de seguimiento establecida en la sesión a no surte efecto automáticamente en una sesión B ya existente. En su lugar, esta marca de seguimiento surte efecto solo después de la primera vez que se establece una marca de seguimiento en la sesión B. Este comportamiento no es determinista en [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] y es determinista en [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores, donde las marcas de seguimiento globales establecidas en la sesión A se establecen inmediatamente en otras sesiones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="18266-114">Also, in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], a trace flag set in session A does not automatically take effect in an already existing session B. Instead, this trace flag takes effect only after the first time any trace flag is set in session B. This behavior is nondeterministic in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] and is deterministic in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, where global trace flags set in session A are set immediately in other concurrent sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18266-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18266-115">See Also</span></span>  
 <span data-ttu-id="18266-116">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="18266-116">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="18266-117">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="18266-117">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
