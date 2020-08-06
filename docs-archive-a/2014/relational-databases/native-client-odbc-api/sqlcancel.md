---
title: SQLCancel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLCancel function
ms.assetid: d4c965ae-c1ac-4e9d-b4b9-32b561401106
author: rothja
ms.author: jroth
ms.openlocfilehash: dc3d86229501f80b25fb077788d1835a5f4f5c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671989"
---
# <a name="sqlcancel"></a><span data-ttu-id="5aec0-102">SQLCancel</span><span class="sxs-lookup"><span data-stu-id="5aec0-102">SQLCancel</span></span>
  <span data-ttu-id="5aec0-103">En el tema [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) se indica que, en ODBC 2. x, si una aplicación llama a `SQLCancel` cuando no se realiza ningún procesamiento en la instrucción, `SQLCancel` tiene el mismo efecto que `SQLFreeStmt` con la `SQL_CLOSE` opción; este comportamiento solo se define para la integridad y las aplicaciones deben llamar `SQLFreeStmt` `SQLCloseCursor` a o para cerrar los cursores.</span><span class="sxs-lookup"><span data-stu-id="5aec0-103">The [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) topic says that in ODBC 2.x, if an application calls `SQLCancel` when no processing is being done on the statement, `SQLCancel` has the same effect as `SQLFreeStmt` with the `SQL_CLOSE` option; this behavior is defined only for completeness and applications should call `SQLFreeStmt` or `SQLCloseCursor` to close cursors.</span></span> <span data-ttu-id="5aec0-104">Pero aunque la aplicación [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client establezca que la versión de la API de ODBC ha de ser 3.5.x o posterior, la función `SQLCancel` utilizará el comportamiento de ODBC 2.x.</span><span class="sxs-lookup"><span data-stu-id="5aec0-104">But even if your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client application sets the ODBC API version to be 3.5.x or later, the `SQLCancel` function will use the ODBC 2.x behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aec0-105">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5aec0-105">See Also</span></span>  
 <span data-ttu-id="5aec0-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span><span class="sxs-lookup"><span data-stu-id="5aec0-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span></span>  
 [<span data-ttu-id="5aec0-107">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="5aec0-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
