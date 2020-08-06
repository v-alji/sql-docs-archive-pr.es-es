---
title: Objeto SqlTriggerContext | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlTriggerContext object
- triggers [CLR integration]
- context [CLR integration]
ms.assetid: 472a2d0b-64ae-4877-8f11-a5620aa698b7
author: rothja
ms.author: jroth
ms.openlocfilehash: f7eae3d290a70bedee0ed9badf9e6d0503caa2bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751209"
---
# <a name="sqltriggercontext-object"></a><span data-ttu-id="ce156-102">Objeto SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="ce156-102">SqlTriggerContext Object</span></span>
  <span data-ttu-id="ce156-103">La clase `SqlTriggerContext` proporciona información de contexto acerca del desencadenador.</span><span class="sxs-lookup"><span data-stu-id="ce156-103">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="ce156-104">Esto incluye el tipo de acción que ha provocado la activación del desencadenador, las columnas que se modificaron en una operación UPDATE y, en el caso de un desencadenador de lenguaje de definición de datos (DDL), una estructura de XML `EventData` que describe la operación de desencadenamiento.</span><span class="sxs-lookup"><span data-stu-id="ce156-104">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a data definition language (DDL) trigger, an XML `EventData` structure that describes the triggering operation.</span></span> <span data-ttu-id="ce156-105">Para obtener más información y ejemplos de cómo usar la `SqlTriggerContext` clase, vea [desencadenadores CLR](../../database-engine/dev-guide/clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="ce156-105">For more information and examples of how to use the `SqlTriggerContext` class, see [CLR Triggers](../../database-engine/dev-guide/clr-triggers.md).</span></span>  
  
 <span data-ttu-id="ce156-106">Para obtener más información, vea la `Microsoft.SqlServer.Server.SqlTriggerContext` documentación de referencia de la clase en la documentación del SDK de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce156-106">For more information, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the .NET Framework SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce156-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce156-107">See Also</span></span>  
 <span data-ttu-id="ce156-108">[Desencadenadores CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="ce156-108">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="ce156-109">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ce156-109">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
