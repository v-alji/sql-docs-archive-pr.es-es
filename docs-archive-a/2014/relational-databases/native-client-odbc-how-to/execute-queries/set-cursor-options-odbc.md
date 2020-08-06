---
title: Establecer opciones de cursor (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], options
ms.assetid: 0e72b48a-fc5a-4656-8cf5-39f57d8c1565
author: rothja
ms.author: jroth
ms.openlocfilehash: 877c2596c87ce50295a15912493661c6dd4e0305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749285"
---
# <a name="set-cursor-options-odbc"></a><span data-ttu-id="796c6-102">Establecer las opciones del cursor (ODBC)</span><span class="sxs-lookup"><span data-stu-id="796c6-102">Set Cursor Options (ODBC)</span></span>
  <span data-ttu-id="796c6-103">Para establecer las opciones de cursor, llame a [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para establecer o [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) para obtener las opciones de la instrucción que controlan el comportamiento del cursor.</span><span class="sxs-lookup"><span data-stu-id="796c6-103">To set cursor options, Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get the statement options that control cursor behavior.</span></span>  
  
|<span data-ttu-id="796c6-104">*Attribute*</span><span class="sxs-lookup"><span data-stu-id="796c6-104">*Attribute*</span></span>|<span data-ttu-id="796c6-105">Especifica</span><span class="sxs-lookup"><span data-stu-id="796c6-105">Specifies</span></span>|  
|-----------------|---------------|  
|<span data-ttu-id="796c6-106">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="796c6-106">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="796c6-107">Tipo de cursor de solo avance, estático, dinámico o controlado por conjunto de claves</span><span class="sxs-lookup"><span data-stu-id="796c6-107">Cursor type of forward-only, static, dynamic, or keyset-driven</span></span>|  
|<span data-ttu-id="796c6-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="796c6-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="796c6-109">Opción de control de simultaneidad de solo lectura, bloqueo, marcas de tiempo de uso optimista o valores de uso optimista</span><span class="sxs-lookup"><span data-stu-id="796c6-109">Concurrency control option of read-only, locking, optimistic using timestamps, or optimistic using values</span></span>|  
|<span data-ttu-id="796c6-110">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="796c6-110">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="796c6-111">Número de filas obtenido en cada captura</span><span class="sxs-lookup"><span data-stu-id="796c6-111">Number of rows retrieved in each fetch</span></span>|  
|<span data-ttu-id="796c6-112">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="796c6-112">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="796c6-113">Cursor que puede mostrar o no las actualizaciones realizadas por otras conexiones en las filas del cursor</span><span class="sxs-lookup"><span data-stu-id="796c6-113">Cursor that does or does not show updates to cursor rows made by other connections</span></span>|  
|<span data-ttu-id="796c6-114">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="796c6-114">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="796c6-115">Cursor que puede desplazarse hacia delante y hacia atrás</span><span class="sxs-lookup"><span data-stu-id="796c6-115">Cursor that can be scrolled forward and backward</span></span>|  
  
 <span data-ttu-id="796c6-116">Los valores predeterminados de estos atributos (solo avance, solo lectura, tamaño del conjunto de filas igual a 1) no usan los cursores del servidor.</span><span class="sxs-lookup"><span data-stu-id="796c6-116">The default values for these attributes (forward-only, read-only, rowset size of 1) do not use server cursors.</span></span> <span data-ttu-id="796c6-117">Para usar los cursores del servidor, al menos uno de estos atributos debe establecerse en un valor distinto del predeterminado y la instrucción en ejecución debe ser una instrucción SELECT única o un procedimiento almacenado que contenga una instrucción SELECT única.</span><span class="sxs-lookup"><span data-stu-id="796c6-117">To use server cursors, at least one of these attributes must be set to a value other than the default, and the statement being executed must be a single SELECT statement or a stored procedure that contains a single SELECT statement.</span></span> <span data-ttu-id="796c6-118">Cuando se utilizan los cursores del servidor, las instrucciones SELECT no pueden utilizar cláusulas que no sean compatibles con los cursores del servidor: COMPUTE, COMPUTE BY, FOR BROWSE e INTO.</span><span class="sxs-lookup"><span data-stu-id="796c6-118">When using server cursors, SELECT statements cannot use clauses not supported by server cursors: COMPUTE, COMPUTE BY, FOR BROWSE, and INTO.</span></span>  
  
 <span data-ttu-id="796c6-119">Puede controlar el tipo de cursor utilizando estableciendo SQL_ATTR_CURSOR_TYPE y SQL_ATTR_CONCURRENCY o estableciendo SQL_ATTR_CURSOR_SENSITIVITY y SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="796c6-119">You can control the type of cursor used either by setting SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="796c6-120">No debe mezclar los dos métodos que se utilizan para especificar el comportamiento del cursor.</span><span class="sxs-lookup"><span data-stu-id="796c6-120">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="796c6-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="796c6-121">Example</span></span>  
 <span data-ttu-id="796c6-122">En el siguiente ejemplo se asigna un identificador de instrucción, se establece un tipo de cursor dinámico con simultaneidad optimista de versiones de fila y, a continuación, se ejecuta una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="796c6-122">The following sample allocates a statement handle, sets a dynamic cursor type with row versioning optimistic concurrency, and then executes a SELECT.</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_TYPE, (SQLPOINTER)SQL_CURSOR_DYNAMIC, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CONCURRENCY, SQLPOINTER)SQL_CONCUR_ROWVER, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, SELECT au_lname FROM authors", SQL_NTS);  
```  
  
## <a name="example"></a><span data-ttu-id="796c6-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="796c6-123">Example</span></span>  
 <span data-ttu-id="796c6-124">En el siguiente ejemplo se asigna un identificador de instrucción, se establece un cursor desplazable de tipo SENSITIVE y, a continuación, se ejecuta una instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="796c6-124">The following sample allocates a statement handle, sets a scrollable, sensitive cursor, and then executes a SELECT</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
  
// Set the cursor options and execute the statement.  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SCROLLABLE, SQLPOINTER)SQL_SCROLLABLE, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SENSITIVITY, SQLPOINTER)SQL_INSENSITIVE, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, select au_lname from authors", SQL_NTS);  
```  
  
## <a name="see-also"></a><span data-ttu-id="796c6-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="796c6-125">See Also</span></span>  
 [<span data-ttu-id="796c6-126">Temas de procedimientos de ejecución de consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="796c6-126">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
