---
title: Liberar un identificador de instrucción | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- reusing statement handles
- freeing statement handles
- statements [ODBC], statement handles
- SQLFreeStmt function
- ODBC applications, statements
- statement handles [ODBC]
ms.assetid: 96fdff84-0ca7-460a-a240-94ee826ea41c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8d7a1e93d222e2b87058bc878f7eca85313b4108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662866"
---
# <a name="freeing-a-statement-handle"></a><span data-ttu-id="abbde-102">Liberar un identificador de instrucción</span><span class="sxs-lookup"><span data-stu-id="abbde-102">Freeing a Statement Handle</span></span>
  <span data-ttu-id="abbde-103">Es más eficaz volver a utilizar los identificadores de instrucciones que quitarlos y asignar unos nuevos.</span><span class="sxs-lookup"><span data-stu-id="abbde-103">It is more efficient to reuse statement handles than to drop them and allocate new ones.</span></span> <span data-ttu-id="abbde-104">Antes de ejecutar una nueva instrucción SQL en un identificador de instrucciones, las aplicaciones deberían comprobar que la configuración de instrucción actual es correcta.</span><span class="sxs-lookup"><span data-stu-id="abbde-104">Before executing a new SQL statement on a statement handle, applications should verify that the current statement settings are appropriate.</span></span> <span data-ttu-id="abbde-105">Éstos incluyen atributos de instrucción, enlaces de parámetros y enlaces de conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="abbde-105">These include statement attributes, parameter bindings, and result set bindings.</span></span> <span data-ttu-id="abbde-106">Por lo general, los parámetros y conjuntos de resultados de la instrucción SQL anterior deben estar desenlazados mediante una llamada a [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) con las opciones SQL_RESET_PARAMS y SQL_UNBIND y, después, volver a enlazarse a la nueva instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="abbde-106">Generally, parameters and result sets for the old SQL statement must be unbound by calling [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the SQL_RESET_PARAMS and SQL_UNBIND options and then re-bound for the new SQL statement.</span></span>  
  
 <span data-ttu-id="abbde-107">Cuando la aplicación ha terminado de usar la instrucción, llama a [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) para liberar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="abbde-107">When the application has finished using the statement, it calls [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the statement.</span></span> <span data-ttu-id="abbde-108">Tenga en cuenta que **SQLDisconnect** libera automáticamente todas las instrucciones de una conexión.</span><span class="sxs-lookup"><span data-stu-id="abbde-108">Note that **SQLDisconnect** automatically frees all statements on a connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbde-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abbde-109">See Also</span></span>  
 [<span data-ttu-id="abbde-110">Ejecutar consultas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="abbde-110">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
