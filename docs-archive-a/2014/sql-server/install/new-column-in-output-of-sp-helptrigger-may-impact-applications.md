---
title: La nueva columna en la salida de sp_helptrigger puede afectar a las aplicaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sp_helptrigger
ms.assetid: b7c42a8f-f2e0-4fa3-b046-3cf39c854c47
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b1f5e936843ed84a5c6b88e2f3685e7a4272bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676808"
---
# <a name="new-column-in-output-of-sp_helptrigger-may-impact-applications"></a><span data-ttu-id="4ab40-102">La nueva columna de la salida de sp_helptrigger podría afectar a las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4ab40-102">New column in output of sp_helptrigger may impact applications</span></span>
  <span data-ttu-id="4ab40-103">trigger_schemaias la última columna del conjunto de resultados devuelto por el procedimiento almacenado del sistema sp_helptrigger.</span><span class="sxs-lookup"><span data-stu-id="4ab40-103">trigger_schemaias the last column in the result set returned by the sp_helptrigger system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="4ab40-104">Para obtener más información acerca de los desencadenadores definidos en una tabla determinada, consulte la vista de catálogo sys.triggers.</span><span class="sxs-lookup"><span data-stu-id="4ab40-104">To obtain information about triggers defined on a particular table, query the sys.triggers catalog view.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4ab40-105">Componente</span><span class="sxs-lookup"><span data-stu-id="4ab40-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="4ab40-106">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="4ab40-106">Corrective Action</span></span>  
 <span data-ttu-id="4ab40-107">Revise el uso de sp_helptrigger en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4ab40-107">Review the use of sp_helptrigger in applications.</span></span> <span data-ttu-id="4ab40-108">Puede que tenga que modificar las aplicaciones para que se ajusten a la columna adicional.</span><span class="sxs-lookup"><span data-stu-id="4ab40-108">You may need to modify your applications to accommodate the additional column.</span></span> <span data-ttu-id="4ab40-109">O bien, puede utilizar en su lugar la vista de catálogo sys.triggers.</span><span class="sxs-lookup"><span data-stu-id="4ab40-109">Alternatively, you can use the sys.triggers catalog view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab40-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ab40-110">See Also</span></span>  
 <span data-ttu-id="4ab40-111">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="4ab40-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="4ab40-112">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="4ab40-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
