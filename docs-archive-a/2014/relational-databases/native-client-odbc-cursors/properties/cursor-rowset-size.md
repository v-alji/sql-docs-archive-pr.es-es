---
title: Tamaño del conjunto de filas cursor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], rowset size
- ODBC cursors, rowset size
- rowsets [ODBC]
ms.assetid: 2febe2ae-fdc1-490e-a79f-c516bc8e7c3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 83c4e55025e6e3724f354f022760b7ba1e2f10e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675329"
---
# <a name="cursor-rowset-size"></a><span data-ttu-id="57a90-102">Tamaño del conjunto de filas del cursor</span><span class="sxs-lookup"><span data-stu-id="57a90-102">Cursor Rowset Size</span></span>
  <span data-ttu-id="57a90-103">Los cursores ODBC no están limitados a capturar una fila cada vez.</span><span class="sxs-lookup"><span data-stu-id="57a90-103">ODBC cursors are not limited to fetching one row at a time.</span></span> <span data-ttu-id="57a90-104">Pueden recuperar varias filas en cada llamada a **SQLFetch** o [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="57a90-104">They can retrieve multiple rows in each call to **SQLFetch** or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="57a90-105">Cuando se trabaja con una base de datos cliente/servidor, como [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de Microsoft, resulta más eficaz capturar varias filas a la vez.</span><span class="sxs-lookup"><span data-stu-id="57a90-105">When you are working with a client/server database such as Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it is more efficient to fetch several rows at a time.</span></span> <span data-ttu-id="57a90-106">El número de filas devueltas en una captura se denomina tamaño del conjunto de filas y se especifica mediante el SQL_ATTR_ROW_ARRAY_SIZE de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="57a90-106">The number of rows returned on a fetch is called the rowset size and is specified by using the SQL_ATTR_ROW_ARRAY_SIZE of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
```  
SQLUINTEGER uwRowsize;  
SQLSetStmtAttr(m_hstmt, SQL_ATTR_ROW_ARRAY_SIZE, (SQLPOINTER)uwRowsetSize, SQL_IS_UINTEGER);  
```  
  
 <span data-ttu-id="57a90-107">Los cursores con un tamaño del conjunto de filas mayor que 1 reciben el nombre de cursores de bloque.</span><span class="sxs-lookup"><span data-stu-id="57a90-107">Cursors with a rowset size greater than 1 are called block cursors.</span></span>  
  
 <span data-ttu-id="57a90-108">Hay dos opciones para enlazar las columnas de conjunto de resultados para los cursores de bloque:</span><span class="sxs-lookup"><span data-stu-id="57a90-108">There are two options for binding result set columns for block cursors:</span></span>  
  
-   <span data-ttu-id="57a90-109">Enlace de modo de columna</span><span class="sxs-lookup"><span data-stu-id="57a90-109">Column-wise binding</span></span>  
  
     <span data-ttu-id="57a90-110">Cada columna se enlaza a una matriz de variables.</span><span class="sxs-lookup"><span data-stu-id="57a90-110">Each column is bound to an array of variables.</span></span> <span data-ttu-id="57a90-111">Cada matriz tiene el mismo número de elementos que el tamaño del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="57a90-111">Each array has the same number of elements as the rowset size.</span></span>  
  
-   <span data-ttu-id="57a90-112">Enlace de modo de fila</span><span class="sxs-lookup"><span data-stu-id="57a90-112">Row-wise binding</span></span>  
  
     <span data-ttu-id="57a90-113">Una matriz se genera mediante estructuras que contienen los datos e indicadores para todas las columnas de una fila.</span><span class="sxs-lookup"><span data-stu-id="57a90-113">An array is built using structures that hold the data and indicators for all the columns in a row.</span></span> <span data-ttu-id="57a90-114">La matriz tiene el mismo número de estructuras que el tamaño del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="57a90-114">The array has the same number of structures as the rowset size.</span></span>  
  
 <span data-ttu-id="57a90-115">Cuando se usa un enlace de modo de columna o de modo de fila, cada llamada a **SQLFetch** o **SQLFetchScroll** rellena las matrices enlazadas con los datos del conjunto de filas recuperado.</span><span class="sxs-lookup"><span data-stu-id="57a90-115">When either column-wise or row-wise binding is used, each call to **SQLFetch** or **SQLFetchScroll** fills the bound arrays with data from the rowset retrieved.</span></span>  
  
 <span data-ttu-id="57a90-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) también se puede usar para recuperar datos de columna de un cursor de bloque.</span><span class="sxs-lookup"><span data-stu-id="57a90-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) can also be used to retrieve column data from a block cursor.</span></span> <span data-ttu-id="57a90-117">Dado que **SQLGetData** funciona una fila cada vez, se debe llamar a **SQLSetPos** para establecer una fila específica del conjunto de filas como la fila actual antes de llamar a **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="57a90-117">Because **SQLGetData** works one row at a time, **SQLSetPos** must be called to set a specific row in the rowset as the current row before calling **SQLGetData**.</span></span>  
  
 <span data-ttu-id="57a90-118">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client ofrece una optimización mediante conjuntos de filas para recuperar rápidamente un conjunto de resultados completo.</span><span class="sxs-lookup"><span data-stu-id="57a90-118">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers an optimization using rowsets to retrieve a whole result set quickly.</span></span> <span data-ttu-id="57a90-119">Para usar esta optimización, establezca los atributos de cursor en sus valores predeterminados (solo avance, solo lectura, tamaño del conjunto de filas = 1) en el momento en que se llama a **SQLExecDirect** o **SQLExecute** .</span><span class="sxs-lookup"><span data-stu-id="57a90-119">To use this optimization, set the cursor attributes to their defaults (forward-only, read-only, rowset size = 1) at the time **SQLExecDirect** or **SQLExecute** is called.</span></span> <span data-ttu-id="57a90-120">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client configura un conjunto de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="57a90-120">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver sets up a default result set.</span></span> <span data-ttu-id="57a90-121">Esto es más eficaz que los cursores de servidor al transferir los resultados al cliente sin desplazarse.</span><span class="sxs-lookup"><span data-stu-id="57a90-121">This is more efficient than server cursors when transferring results to the client without scrolling.</span></span> <span data-ttu-id="57a90-122">Después de ejecutar la instrucción, aumente el tamaño del conjunto de filas y use el enlace de modo de columna o de modo de fila.</span><span class="sxs-lookup"><span data-stu-id="57a90-122">After the statement has been executed, increase the rowset size and use either column-wise or row-wise binding.</span></span> <span data-ttu-id="57a90-123">Esto permite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usar un conjunto de resultados predeterminado para enviar filas de resultados de forma eficaz al cliente, mientras que el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client extrae continuamente filas de los búferes de red en el cliente.</span><span class="sxs-lookup"><span data-stu-id="57a90-123">This lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] use a default result set to send result rows efficiently to the client, while the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver continuously pulls rows from the network buffers on the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a90-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57a90-124">See Also</span></span>  
 [<span data-ttu-id="57a90-125">Propiedades de cursor</span><span class="sxs-lookup"><span data-stu-id="57a90-125">Cursor Properties</span></span>](cursor-properties.md)  
  
  
