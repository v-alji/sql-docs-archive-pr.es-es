---
title: Validar guías de planes tras una actualización | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], validating after upgrade
ms.assetid: a55ebd88-6f58-454d-b1c4-991b88add522
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18cc0f93ddec46025f659bcb9489bfff3ca846ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746249"
---
# <a name="validate-plan-guides-after-upgrade"></a><span data-ttu-id="33ed1-102">Validar guías de planes tras una actualización</span><span class="sxs-lookup"><span data-stu-id="33ed1-102">Validate Plan Guides After Upgrade</span></span>
  <span data-ttu-id="33ed1-103">Se recomienda volver a evaluar y probar las definiciones de guías de plan al actualizar la aplicación a una nueva versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33ed1-103">We recommend re-evaluating and testing plan guide definitions when you upgrade your application to a new release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="33ed1-104">Los requisitos de optimización del rendimiento y el comportamiento de la coincidencia de las guías de plan pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="33ed1-104">Performance tuning requirements and plan guide matching behavior may change.</span></span> <span data-ttu-id="33ed1-105">Aunque una guía de plan no válida no hará que una consulta provoque un error, el plan se compilada sin utilizar la guía de plan y posiblemente no sea la mejor opción.</span><span class="sxs-lookup"><span data-stu-id="33ed1-105">Although an invalid plan guide will not cause a query to fail, the plan is compiled without using the plan guide and may not be the best choice.</span></span> <span data-ttu-id="33ed1-106">Después de actualizar una base de datos a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], es recomendable que realice las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="33ed1-106">After upgrading a database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="33ed1-107">Valide las guías de plan existentes con la función [sys.fn_validate_plan_guide](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="33ed1-107">Validate existing plan guides by using the [sys.fn_validate_plan_guide](/sql/relational-databases/system-functions/sys-fn-validate-plan-guide-transact-sql) function.</span></span>  
  
-   <span data-ttu-id="33ed1-108">Utilice eventos extendido para supervisar los planes equivocados durante un cierto período de tiempo con el evento [Guía de plan incorrecta](../event-classes/plan-guide-unsuccessful-event-class.md) .</span><span class="sxs-lookup"><span data-stu-id="33ed1-108">Use extended events to monitor for misguided plans for some period of time by using the [Plan Guide Unsuccessful](../event-classes/plan-guide-unsuccessful-event-class.md) event.</span></span>  
  
  
