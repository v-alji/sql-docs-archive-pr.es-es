---
title: Dominios de aplicación y seguridad de la integración CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- application domains [CLR integration]
ms.assetid: 54ee904e-e21a-4ee7-b4ad-a6f6f71bd473
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85d6e66b1d51cc9d7c5829b8e83c510bea750e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670543"
---
# <a name="application-domains-and-clr-integration-security"></a><span data-ttu-id="d5895-102">Dominios de aplicación y seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="d5895-102">Application Domains and CLR Integration Security</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d5895-103">carga ensamblados que pertenecen al mismo propietario en el mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5895-103">loads assemblies belonging to the same owner in the same application domain.</span></span> <span data-ttu-id="d5895-104">En virtud de un conjunto de ensamblados que se ejecutan en el mismo dominio de aplicación, los ensamblados pueden detectarse entre sí en tiempo de ejecución mediante las interfaces de programación de aplicaciones de reflexión de .NET Framework u otros recursos y pueden realizar llamadas en ellos en modo de enlace en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d5895-104">By virtue of a set of assemblies running in the same application domain, assemblies are able to discover each other at execution time using the.NET Framework reflection application programming interfaces or other means, and can call into them in late-bound fashion.</span></span> <span data-ttu-id="d5895-105">Dado que tales llamadas se producen en ensamblados que pertenecen al mismo propietario, en ellas no se compruebe ningún permiso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5895-105">Because such calls are occurring against assemblies belonging to the same owner, there are no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions checked for these calls.</span></span> <span data-ttu-id="d5895-106">El esquema de ubicación de los ensamblados en los dominios de aplicación se ha diseñado principalmente para lograr los objetivos de escalabilidad, seguridad y aislamiento y es posible que cambie en futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="d5895-106">The placement scheme of assemblies in application domains is designed primarily to achieve scalability, security, and isolation goals, and can potentially change in future releases.</span></span> <span data-ttu-id="d5895-107">Por lo tanto, no debe depender de la localización de ensamblados en el mismo dominio de aplicación a través de los mecanismos de enlace en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d5895-107">Hence, you should not rely on finding assemblies in the same application domain through late-bound mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5895-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5895-108">See Also</span></span>  
 [<span data-ttu-id="d5895-109">Seguridad de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="d5895-109">CLR Integration Security</span></span>](../../relational-databases/clr-integration/security/clr-integration-security.md)  
  
  
