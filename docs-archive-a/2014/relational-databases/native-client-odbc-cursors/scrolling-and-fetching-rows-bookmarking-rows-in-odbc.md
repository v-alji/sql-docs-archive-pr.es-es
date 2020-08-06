---
title: Marcar filas en ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- ODBC cursors, scrolling rows
- bookmarks [ODBC]
ms.assetid: 9cfcd243-c9d4-4c2a-abc4-399dbabe5f6b
author: rothja
ms.author: jroth
ms.openlocfilehash: def05f478c16dcbcdc91771925a11b0b91da2e9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749304"
---
# <a name="bookmarking-rows-in-odbc"></a><span data-ttu-id="7fc9b-102">Marcar filas en ODBC</span><span class="sxs-lookup"><span data-stu-id="7fc9b-102">Bookmarking Rows in ODBC</span></span>
  <span data-ttu-id="7fc9b-103">Un marcador es un valor utilizado para identificar una fila de datos.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-103">A bookmark is a value used to identify a row of data.</span></span> <span data-ttu-id="7fc9b-104">El significado del valor de marcador solamente lo conocen el controlador u origen de datos.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-104">The meaning of the bookmark value is known only to the driver or data source.</span></span> <span data-ttu-id="7fc9b-105">Por ejemplo, podría ser tan simple como un número de fila o tan complejo como una dirección de disco.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-105">For example, it might be as simple as a row number or as complex as a disk address.</span></span> <span data-ttu-id="7fc9b-106">En ODBC, la aplicación solicita un marcador para una fila determinada, lo almacena y lo pasa de vuelta al cursor para volver a la fila.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-106">In ODBC, the application requests a bookmark for a particular row, stores it, and passes it back to the cursor to return to the row.</span></span>  
  
 <span data-ttu-id="7fc9b-107">Al capturar filas con [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), una aplicación puede usar un marcador como base para seleccionar la fila inicial.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-107">When fetching rows with [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), an application can use a bookmark as a basis for selecting the starting row.</span></span> <span data-ttu-id="7fc9b-108">Ésta es una forma de dirección absoluta porque no depende de la posición actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-108">This is a form of absolute addressing because it does not depend on the current cursor position.</span></span> <span data-ttu-id="7fc9b-109">Para desplazarse a una fila marcada, la aplicación llama a **SQLFetchScroll** con un *FetchOrientation* de SQL_FETCH_BOOKMARK.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-109">To scroll to a bookmarked row, the application calls **SQLFetchScroll** with a *FetchOrientation* of SQL_FETCH_BOOKMARK.</span></span> <span data-ttu-id="7fc9b-110">Esta operación utiliza el marcador al que señala el atributo de opción SQL_ATTR_FETCH_BOOKMARK_PTR.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-110">This operation uses the bookmark pointed to by the SQL_ATTR_FETCH_BOOKMARK_PTR option attribute.</span></span> <span data-ttu-id="7fc9b-111">Devuelve el conjunto de filas que comienza con la fila identificada por este marcador.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-111">It returns the rowset starting with the row identified by that bookmark.</span></span> <span data-ttu-id="7fc9b-112">Una aplicación puede especificar un desplazamiento para esta operación en el argumento *FetchOffset* de la llamada a **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-112">An application can specify an offset for this operation in the *FetchOffset* argument of the call to **SQLFetchScroll**.</span></span> <span data-ttu-id="7fc9b-113">Cuando se especifica un desplazamiento, la primera fila del conjunto de filas devuelto se determina sumando el número del argumento FetchOffset al número de la fila que identifica el marcador.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-113">When an offset is specified, the first row of the returned rowset is determined by adding the number in the FetchOffset argument to the number of the row identified by the bookmark.</span></span> <span data-ttu-id="7fc9b-114">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client solamente admite marcadores en los cursores estáticos y controlados por conjunto de claves.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver only supports bookmarks on static and keyset cursors.</span></span> <span data-ttu-id="7fc9b-115">Si se solicita un cursor dinámico cuando los marcadores están activados, se abre un cursor controlado por conjunto de claves.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-115">If a dynamic cursor is requested when bookmarks are set on, a keyset cursor is opened instead.</span></span>  
  
 <span data-ttu-id="7fc9b-116">Los marcadores también se pueden usar con la función **SQLBulkOperations** para realizar operaciones en un conjunto de filas a partir del marcador.</span><span class="sxs-lookup"><span data-stu-id="7fc9b-116">Bookmarks can also be used with the **SQLBulkOperations** function to perform operations on a set of rows starting at the bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc9b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7fc9b-117">See Also</span></span>  
 [<span data-ttu-id="7fc9b-118">Desplazamiento y captura de filas</span><span class="sxs-lookup"><span data-stu-id="7fc9b-118">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
  
