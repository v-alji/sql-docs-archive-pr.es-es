---
title: Usar cursores (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC]
- ODBC cursors
ms.assetid: 51322f92-0d76-44c9-9c33-9223676cf1d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 61afedab4f4a1e309a08d9c2421ca7889811da8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749292"
---
# <a name="using-cursors-odbc"></a><span data-ttu-id="3fd68-102">Usar cursores (ODBC)</span><span class="sxs-lookup"><span data-stu-id="3fd68-102">Using Cursors (ODBC)</span></span>
  <span data-ttu-id="3fd68-103">ODBC admite un modelo de cursor que permite:</span><span class="sxs-lookup"><span data-stu-id="3fd68-103">ODBC supports a cursor model that allows:</span></span>  
  
-   <span data-ttu-id="3fd68-104">Varios tipos de cursores.</span><span class="sxs-lookup"><span data-stu-id="3fd68-104">Several types of cursors.</span></span>  
  
-   <span data-ttu-id="3fd68-105">Desplazamiento y colocación en un cursor.</span><span class="sxs-lookup"><span data-stu-id="3fd68-105">Scrolling and positioning within a cursor.</span></span>  
  
-   <span data-ttu-id="3fd68-106">Varias opciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="3fd68-106">Several concurrency options.</span></span>  
  
-   <span data-ttu-id="3fd68-107">Actualizaciones posicionadas.</span><span class="sxs-lookup"><span data-stu-id="3fd68-107">Positioned updates.</span></span>  
  
 <span data-ttu-id="3fd68-108">Las aplicaciones ODBC raramente declaran y abren cursores o utilizan cualquier instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] relacionada con cursores.</span><span class="sxs-lookup"><span data-stu-id="3fd68-108">ODBC applications rarely declare and open cursors or use any cursor-related [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="3fd68-109">ODBC abre automáticamente un cursor para cada conjunto de resultados que devuelve una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="3fd68-109">ODBC automatically opens a cursor for every result set returned from an SQL statement.</span></span> <span data-ttu-id="3fd68-110">Las características de los cursores se controlan mediante atributos de instrucción establecidos con [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) antes de que se ejecute la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="3fd68-110">The characteristics of the cursors are controlled by statement attributes set with [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) before the SQL statement is executed.</span></span> <span data-ttu-id="3fd68-111">Las funciones de la API de ODBC para procesar conjuntos de resultados admiten toda la funcionalidad del cursor, entre la que se incluye la captura, el desplazamiento y las actualizaciones posicionadas.</span><span class="sxs-lookup"><span data-stu-id="3fd68-111">The ODBC API functions for processing result sets support the full range of cursor functionality, including fetching, scrolling, and positioned updates.</span></span>  
  
 <span data-ttu-id="3fd68-112">A continuación se ofrece una comparación de cómo los scripts de [!INCLUDE[tsql](../../includes/tsql-md.md)] y las aplicaciones ODBC trabajan con cursores.</span><span class="sxs-lookup"><span data-stu-id="3fd68-112">This is a comparison of how [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and ODBC applications work with cursors.</span></span>  
  
|<span data-ttu-id="3fd68-113">Acción</span><span class="sxs-lookup"><span data-stu-id="3fd68-113">Action</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)]|<span data-ttu-id="3fd68-114">ODBC</span><span class="sxs-lookup"><span data-stu-id="3fd68-114">ODBC</span></span>|  
|------------|------------------------|----------|  
|<span data-ttu-id="3fd68-115">Definir el comportamiento del cursor</span><span class="sxs-lookup"><span data-stu-id="3fd68-115">Define cursor behavior</span></span>|<span data-ttu-id="3fd68-116">Se especifica a través de parámetros DECLARE CURSOR</span><span class="sxs-lookup"><span data-stu-id="3fd68-116">Specify through DECLARE CURSOR parameters</span></span>|<span data-ttu-id="3fd68-117">Establecer atributos de cursor mediante [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span><span class="sxs-lookup"><span data-stu-id="3fd68-117">Set cursor attributes by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span></span>|  
|<span data-ttu-id="3fd68-118">Abrir un cursor</span><span class="sxs-lookup"><span data-stu-id="3fd68-118">Open a cursor</span></span>|<span data-ttu-id="3fd68-119">DECLARE CURSOR OPEN *cursor_name*</span><span class="sxs-lookup"><span data-stu-id="3fd68-119">DECLARE CURSOR OPEN *cursor_name*</span></span>|<span data-ttu-id="3fd68-120">**SQLExecDirect** o **SQLExecute**</span><span class="sxs-lookup"><span data-stu-id="3fd68-120">**SQLExecDirect** or **SQLExecute**</span></span>|  
|<span data-ttu-id="3fd68-121">Capturar filas</span><span class="sxs-lookup"><span data-stu-id="3fd68-121">Fetch rows</span></span>|<span data-ttu-id="3fd68-122">FETCH</span><span class="sxs-lookup"><span data-stu-id="3fd68-122">FETCH</span></span>|<span data-ttu-id="3fd68-123">**SQLFetch** o [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span><span class="sxs-lookup"><span data-stu-id="3fd68-123">**SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span></span>|  
|<span data-ttu-id="3fd68-124">Actualización posicionada</span><span class="sxs-lookup"><span data-stu-id="3fd68-124">Positioned update</span></span>|<span data-ttu-id="3fd68-125">Cláusula WHERE CURRENT OF en UPDATE o DELETE</span><span class="sxs-lookup"><span data-stu-id="3fd68-125">WHERE CURRENT OF clause on UPDATE or DELETE</span></span>|<span data-ttu-id="3fd68-126">**SQLSetPos**</span><span class="sxs-lookup"><span data-stu-id="3fd68-126">**SQLSetPos**</span></span>|  
|<span data-ttu-id="3fd68-127">Cerrar un cursor</span><span class="sxs-lookup"><span data-stu-id="3fd68-127">Close a cursor</span></span>|<span data-ttu-id="3fd68-128">CERRAR *cursor_name* desasignar</span><span class="sxs-lookup"><span data-stu-id="3fd68-128">CLOSE *cursor_name* DEALLOCATE</span></span>|[<span data-ttu-id="3fd68-129">SQLCloseCursor</span><span class="sxs-lookup"><span data-stu-id="3fd68-129">SQLCloseCursor</span></span>](../native-client-odbc-api/sqlclosecursor.md)|  
  
 <span data-ttu-id="3fd68-130">Los cursores de servidor implementados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admiten la funcionalidad del modelo de cursores de ODBC.</span><span class="sxs-lookup"><span data-stu-id="3fd68-130">The server cursors implemented in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support the functionality of the ODBC cursor model.</span></span> <span data-ttu-id="3fd68-131">El controlador [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client utiliza cursores de servidor para admitir la funcionalidad de cursor de la API de ODBC.</span><span class="sxs-lookup"><span data-stu-id="3fd68-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client driver uses server cursors to support the cursor functionality of the ODBC API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3fd68-132">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3fd68-132">In This Section</span></span>  
  
-   [<span data-ttu-id="3fd68-133">Cómo se implementan los cursores</span><span class="sxs-lookup"><span data-stu-id="3fd68-133">How Cursors Are Implemented</span></span>](implementation/how-cursors-are-implemented.md)  
  
-   [<span data-ttu-id="3fd68-134">Tipos de cursor</span><span class="sxs-lookup"><span data-stu-id="3fd68-134">Cursor Types</span></span>](cursor-types.md)  
  
-   [<span data-ttu-id="3fd68-135">Comportamientos de los cursores</span><span class="sxs-lookup"><span data-stu-id="3fd68-135">Cursor Behaviors</span></span>](cursor-behaviors.md)  
  
-   [<span data-ttu-id="3fd68-136">Propiedades de cursor</span><span class="sxs-lookup"><span data-stu-id="3fd68-136">Cursor Properties</span></span>](properties/cursor-properties.md)  
  
-   [<span data-ttu-id="3fd68-137">Detalles de la programación de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3fd68-137">Cursor Programming Details &#40;ODBC&#41;</span></span>](programming/cursor-programming-details-odbc.md)  
  
-   [<span data-ttu-id="3fd68-138">Desplazamiento y captura de filas</span><span class="sxs-lookup"><span data-stu-id="3fd68-138">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
-   [<span data-ttu-id="3fd68-139">Actualizaciones posicionadas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3fd68-139">Positioned Updates &#40;ODBC&#41;</span></span>](positioned-updates-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="3fd68-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3fd68-140">See Also</span></span>  
 <span data-ttu-id="3fd68-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="3fd68-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="3fd68-142">[CERRAR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/close-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3fd68-142">[CLOSE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/close-transact-sql) </span></span>  
 <span data-ttu-id="3fd68-143">[Cursores](../../relational-databases/cursors.md) </span><span class="sxs-lookup"><span data-stu-id="3fd68-143">[Cursors](../../relational-databases/cursors.md) </span></span>  
 <span data-ttu-id="3fd68-144">[Desasignar &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/deallocate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3fd68-144">[DEALLOCATE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/deallocate-transact-sql) </span></span>  
 <span data-ttu-id="3fd68-145">[DECLARE CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3fd68-145">[DECLARE CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span></span>  
 <span data-ttu-id="3fd68-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3fd68-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span></span>  
 [<span data-ttu-id="3fd68-147">OPEN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3fd68-147">OPEN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/open-transact-sql)  
  
  
