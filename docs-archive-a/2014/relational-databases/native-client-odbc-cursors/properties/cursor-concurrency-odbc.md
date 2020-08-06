---
title: Simultaneidad de cursores (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- concurrency [ODBC]
- cursors [ODBC], concurrency
- ODBC cursors, concurrency
ms.assetid: 68228ece-cbf1-4f19-bfdc-053884c1af48
author: rothja
ms.author: jroth
ms.openlocfilehash: c47f24152978fedf8f2c3d49ec3b721969712814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675337"
---
# <a name="cursor-concurrency-odbc"></a><span data-ttu-id="b1128-102">Simultaneidad de cursor (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b1128-102">Cursor Concurrency (ODBC)</span></span>
  <span data-ttu-id="b1128-103">Las opciones de simultaneidad establecidas por la aplicación afectan a las operaciones del cursor, como los tipos de cursor.</span><span class="sxs-lookup"><span data-stu-id="b1128-103">Cursor operations, like cursor types, are affected by the concurrency options set by the application.</span></span> <span data-ttu-id="b1128-104">Las opciones de simultaneidad se establecen mediante la opción SQL_ATTR_CONCURRENCY de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="b1128-104">Concurrency options are set using the SQL_ATTR_CONCURRENCY option of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="b1128-105">Los tipos de simultaneidad son:</span><span class="sxs-lookup"><span data-stu-id="b1128-105">The concurrency types are:</span></span>  
  
-   <span data-ttu-id="b1128-106">Solo lectura (SQL_CONCUR_READONLY)</span><span class="sxs-lookup"><span data-stu-id="b1128-106">Read-only (SQL_CONCUR_READONLY)</span></span>  
  
-   <span data-ttu-id="b1128-107">Valores (SQL_CONCUR_VALUES)</span><span class="sxs-lookup"><span data-stu-id="b1128-107">Values (SQL_CONCUR_VALUES)</span></span>  
  
-   <span data-ttu-id="b1128-108">Versión de fila (SQL_CONCUR_ROWVER)</span><span class="sxs-lookup"><span data-stu-id="b1128-108">Row version (SQL_CONCUR_ROWVER)</span></span>  
  
-   <span data-ttu-id="b1128-109">Bloqueo (SQL_CONCUR_LOCK)</span><span class="sxs-lookup"><span data-stu-id="b1128-109">Lock (SQL_CONCUR_LOCK)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1128-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1128-110">See Also</span></span>  
 [<span data-ttu-id="b1128-111">Propiedades de cursor</span><span class="sxs-lookup"><span data-stu-id="b1128-111">Cursor Properties</span></span>](cursor-properties.md)  
  
  
