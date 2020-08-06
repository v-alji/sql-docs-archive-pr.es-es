---
title: SQLFetchScroll | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFetchScroll function
ms.assetid: 524a3985-a08d-4445-99e0-bb551a666615
author: rothja
ms.author: jroth
ms.openlocfilehash: eecf9714a97577ff490b642cee5b9c380333e40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671072"
---
# <a name="sqlfetchscroll"></a><span data-ttu-id="465fa-102">SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="465fa-102">SQLFetchScroll</span></span>
  <span data-ttu-id="465fa-103">**SQLFetchScroll** devuelve un conjunto de filas de datos a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="465fa-103">**SQLFetchScroll** returns one row set of data to the application.</span></span> <span data-ttu-id="465fa-104">El tamaño del conjunto de filas se establece mediante [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="465fa-104">The size of the row set is set using [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span> <span data-ttu-id="465fa-105">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client admite todas las instrucciones de captura definidas (por ejemplo, SQL_FETCH_RELATIVE), con las limitaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="465fa-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports all defined fetch instructions (for example, SQL_FETCH_RELATIVE) with the following limitations:</span></span>  
  
-   <span data-ttu-id="465fa-106">Si se define un cursor de solo avance para la instrucción, se requiere SQL_FETCH_NEXT y los intentos de capturar de cualquier otro modo producirán un retorno incorrecto.</span><span class="sxs-lookup"><span data-stu-id="465fa-106">If a forward-only cursor is defined for the statement, SQL_FETCH_NEXT is required and attempts to fetch in any other fashion will result in an error return.</span></span>  
  
-   <span data-ttu-id="465fa-107">SQL_FETCH_BOOKMARK solamente se admite en cursores estáticos y controlados por conjunto de claves.</span><span class="sxs-lookup"><span data-stu-id="465fa-107">SQL_FETCH_BOOKMARK is supported for static and keyset-driven cursors only.</span></span>  
  
## <a name="sqlfetchscroll-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="465fa-108">SQLFetchScroll admite las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="465fa-108">SQLFetchScroll Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="465fa-109">Los valores de las columnas de resultados de los tipos de fecha y hora se convierten como se describe en [conversiones de SQL a C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="465fa-109">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="465fa-110">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="465fa-110">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlfetchscroll-support-for-large-clr-udts"></a><span data-ttu-id="465fa-111">SQLFetchScroll admite UDT CLR grandes</span><span class="sxs-lookup"><span data-stu-id="465fa-111">SQLFetchScroll Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="465fa-112">**SQLFetchScroll** admite los tipos definidos por el usuario (UDT) CLR grandes.</span><span class="sxs-lookup"><span data-stu-id="465fa-112">**SQLFetchScroll** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="465fa-113">Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="465fa-113">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="465fa-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="465fa-114">See Also</span></span>  
 <span data-ttu-id="465fa-115">[Función SQLFetchScroll](https://go.microsoft.com/fwlink/?LinkId=59343) </span><span class="sxs-lookup"><span data-stu-id="465fa-115">[SQLFetchScroll Function](https://go.microsoft.com/fwlink/?LinkId=59343) </span></span>  
 [<span data-ttu-id="465fa-116">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="465fa-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
