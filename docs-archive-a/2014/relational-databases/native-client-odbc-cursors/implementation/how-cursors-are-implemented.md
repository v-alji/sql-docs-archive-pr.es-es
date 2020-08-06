---
title: Cómo se implementan los cursores | Microsoft Docs
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
- cursors [ODBC], about ODBC cursors
ms.assetid: 2b1d7dd4-08a4-43fc-b3eb-70c183d0941f
author: rothja
ms.author: jroth
ms.openlocfilehash: 18995355b825d9cb1e62b4794429b5e98ef2b472
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671069"
---
# <a name="how-cursors-are-implemented"></a><span data-ttu-id="ce4ae-102">Cómo se implementan los cursores</span><span class="sxs-lookup"><span data-stu-id="ce4ae-102">How Cursors Are Implemented</span></span>
  <span data-ttu-id="ce4ae-103">Las aplicaciones ODBC controlan el comportamiento de un cursor estableciendo uno o más atributos de instrucción antes de ejecutar una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-103">ODBC applications control the behavior of a cursor by setting one or more statement attributes before executing an SQL statement.</span></span> <span data-ttu-id="ce4ae-104">ODBC tiene dos maneras diferentes de especificar las características de un cursor:</span><span class="sxs-lookup"><span data-stu-id="ce4ae-104">ODBC has two different ways to specify the characteristics of a cursor:</span></span>  
  
-   <span data-ttu-id="ce4ae-105">Tipo de cursor</span><span class="sxs-lookup"><span data-stu-id="ce4ae-105">Cursor type</span></span>  
  
     <span data-ttu-id="ce4ae-106">Los tipos de cursor se establecen mediante el atributo SQL_ATTR_CURSOR_TYPE de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="ce4ae-106">Cursor types are set using the SQL_ATTR_CURSOR_TYPE attribute of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="ce4ae-107">Los tipos de cursor de ODBC son de solo avance, estático, controlado por conjunto de claves, mixto y dinámico.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-107">The ODBC cursor types are forward-only, static, keyset-driven, mixed, and dynamic.</span></span> <span data-ttu-id="ce4ae-108">Establecer el tipo de cursor fue el método original para especificar los cursores en ODBC.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-108">Setting the cursor type was the original method of specifying cursors in ODBC.</span></span>  
  
-   <span data-ttu-id="ce4ae-109">Comportamiento de los cursores</span><span class="sxs-lookup"><span data-stu-id="ce4ae-109">Cursor behavior</span></span>  
  
     <span data-ttu-id="ce4ae-110">El comportamiento de los cursores se establece mediante los atributos SQL_ATTR_CURSOR_SCROLLABLE y SQL_ATTR_CURSOR_SENSITIVITY de **SQLSetStmtAttr**.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-110">Cursor behavior is set using the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY attributes of **SQLSetStmtAttr**.</span></span> <span data-ttu-id="ce4ae-111">Estos atributos se modelan en las palabras clave SCROLL y SENSITIVE definidas para la instrucción DECLARE CURSOR en los estándares ISO.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-111">These attributes are modeled on the SCROLL and SENSITIVE keywords defined for the DECLARE CURSOR statement in ISO standards.</span></span> <span data-ttu-id="ce4ae-112">Estas dos opciones ISO se introdujeron en la versión 3.0 de ODBC.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-112">These two ISO options were introduced in ODBC version 3.0.</span></span>  
  
 <span data-ttu-id="ce4ae-113">Las características de un cursor ODBC se deberían especificar con cualquiera de estos dos métodos, siendo preferente el uso de los tipos de cursor de ODBC.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-113">The characteristics of an ODBC cursor should be specified using either one or the other of these two methods, with the preference being to use the ODBC cursor types.</span></span>  
  
 <span data-ttu-id="ce4ae-114">Además de establecer el tipo de un cursor, las aplicaciones ODBC también establecen otras opciones, como el número de filas devueltas en cada captura, opciones de simultaneidad y niveles de aislamiento de transacción.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-114">In addition to setting the type of a cursor, ODBC applications also set other options, such as the number of rows returned on each fetch, concurrency options, and transaction isolation levels.</span></span> <span data-ttu-id="ce4ae-115">Estas opciones se pueden establecer tanto para cursores de estilo ODBC (de solo avance, estático, controlado por conjunto de claves, mixto y dinámico) como para cursores de estilo ISO (desplazamiento y sensibilidad).</span><span class="sxs-lookup"><span data-stu-id="ce4ae-115">These options can be set for either ODBC-style cursors (forward-only, static, keyset-driven, mixed, and dynamic) or ISO style cursors (scrollability and sensitivity).</span></span>  
  
 <span data-ttu-id="ce4ae-116">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client admite varias maneras de implementar físicamente los distintos tipos de cursores.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-116">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports several ways to physically implement the various types of cursors.</span></span> <span data-ttu-id="ce4ae-117">El controlador implementa algunos tipos de cursores mediante un conjunto de resultados predeterminado de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; implementa otros como cursores de servidor o mediante la Biblioteca de cursores ODBC.</span><span class="sxs-lookup"><span data-stu-id="ce4ae-117">The driver implements some types of cursors using a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set; it implements others as server cursors or by using the ODBC Cursor Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce4ae-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ce4ae-118">In This Section</span></span>  
  
-   [<span data-ttu-id="ce4ae-119">Utilizar conjuntos de resultados predeterminados de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ce4ae-119">Using SQL Server Default Result Sets</span></span>](using-sql-server-default-result-sets.md)  
  
-   [<span data-ttu-id="ce4ae-120">Utilizar cursores de servidor</span><span class="sxs-lookup"><span data-stu-id="ce4ae-120">Using Server Cursors</span></span>](using-server-cursors.md)  
  
-   [<span data-ttu-id="ce4ae-121">Biblioteca de cursores ODBC</span><span class="sxs-lookup"><span data-stu-id="ce4ae-121">ODBC Cursor Library</span></span>](odbc-cursor-library.md)  
  
## <a name="see-also"></a><span data-ttu-id="ce4ae-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce4ae-122">See Also</span></span>  
 [<span data-ttu-id="ce4ae-123">Usar cursores &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="ce4ae-123">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  
