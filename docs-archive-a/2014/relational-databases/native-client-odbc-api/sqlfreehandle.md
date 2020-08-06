---
title: SQLFreeHandle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFreeHandle function
ms.assetid: d374e5c8-ed35-43bf-8dd6-c37e38d9b5f1
author: rothja
ms.author: jroth
ms.openlocfilehash: f51f031bec05715e0345507278113f4f16179a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671510"
---
# <a name="sqlfreehandle"></a><span data-ttu-id="e7cf4-102">SQLFreeHandle</span><span class="sxs-lookup"><span data-stu-id="e7cf4-102">SQLFreeHandle</span></span>
  <span data-ttu-id="e7cf4-103">En el modo de confirmación manual, al llamar a **SQLFreeHandle** en un identificador de instrucción con una transacción abierta se produce una operación de reversión de cambios pendientes a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e7cf4-103">In manual-commit mode, calling **SQLFreeHandle** on a statement handle with an open transaction causes a rollback of pending changes to the database.</span></span> <span data-ttu-id="e7cf4-104">Al llamando a **SQLFreeHandle** en un identificador de instrucción siempre se cierra cualquier cursor abierto y se descartan los resultados pendientes, liberando todos los recursos asociados con el identificador de instrucción.</span><span class="sxs-lookup"><span data-stu-id="e7cf4-104">Calling **SQLFreeHandle** on a statement handle always closes any open cursors and discards pending results, freeing all resources associated with the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7cf4-105">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7cf4-105">See Also</span></span>  
 <span data-ttu-id="e7cf4-106">[SQLFreeHandle función)](https://go.microsoft.com/fwlink/?LinkId=59345) </span><span class="sxs-lookup"><span data-stu-id="e7cf4-106">[SQLFreeHandle Function](https://go.microsoft.com/fwlink/?LinkId=59345) </span></span>  
 [<span data-ttu-id="e7cf4-107">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="e7cf4-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
