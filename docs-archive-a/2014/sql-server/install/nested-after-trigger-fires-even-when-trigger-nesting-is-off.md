---
title: El desencadenador AFTER anidado se activa aunque el anidamiento del desencadenador esté desactivado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, nested
- nested triggers option
- triggers [SQL Server], nested
ms.assetid: 94d72960-676e-40d9-81bc-08bffe778110
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f91c04e8d69880b451c1479e2907cd1910e8f9c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751714"
---
# <a name="nested-after-trigger-fires-even-when-trigger-nesting-is-off"></a><span data-ttu-id="e8677-102">El desencadenador AFTER anidado se lanza incluso cuando el anidamiento de desencadenadores está desactivado</span><span class="sxs-lookup"><span data-stu-id="e8677-102">Nested AFTER trigger fires even when trigger nesting is OFF</span></span>
  <span data-ttu-id="e8677-103">El Asesor de actualizaciones ha detectado un desencadenador AFTER anidad dentro de un desencadenador INSTEAD OF que está definido en una o más tablas.</span><span class="sxs-lookup"><span data-stu-id="e8677-103">Upgrade Advisor detected an AFTER trigger nested inside an INSTEAD OF trigger that is defined on one or more tables.</span></span> <span data-ttu-id="e8677-104">Los desencadenadores AFTER anidados pueden activarse incluso cuando la opción de configuración del servidor de `nested triggers` se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="e8677-104">Nested AFTER triggers may fire even when the `nested triggers` server configuration option is set to 0.</span></span>  
  
## <a name="component"></a><span data-ttu-id="e8677-105">Componente</span><span class="sxs-lookup"><span data-stu-id="e8677-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="e8677-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8677-106">Description</span></span>  
 <span data-ttu-id="e8677-107">El primer desencadenador AFTER anidado que esté dentro de un desencadenador INSTEAD OF se activará si la opción de configuración del servidor `nested triggers` está establecida en 0.</span><span class="sxs-lookup"><span data-stu-id="e8677-107">The first AFTER trigger nested inside an INSTEAD OF trigger fires even if the `nested triggers` server configuration option is set to 0.</span></span> <span data-ttu-id="e8677-108">Sin embargo, con esta configuración, no se lanzarán los siguientes desencadenadores AFTER.</span><span class="sxs-lookup"><span data-stu-id="e8677-108">However, under this setting, subsequent AFTER triggers do not fire.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="e8677-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="e8677-109">Corrective Action</span></span>  
 <span data-ttu-id="e8677-110">Revise sus aplicaciones en busca de desencadenadores anidados para determinar si las aplicaciones todavía cumplen con sus reglas de negocios en relación con este comportamiento nuevo, siempre que la opción de configuración del servidor `nested triggers` esté establecida en 0 y, a continuación, realiza las modificaciones apropiadas.</span><span class="sxs-lookup"><span data-stu-id="e8677-110">Review your applications for nested triggers to determine whether the applications still comply with your business rules with regard to this new behavior when the `nested triggers` server configuration option is set to 0, and then make appropriate modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8677-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8677-111">See Also</span></span>  
 <span data-ttu-id="e8677-112">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="e8677-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="e8677-113">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="e8677-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
