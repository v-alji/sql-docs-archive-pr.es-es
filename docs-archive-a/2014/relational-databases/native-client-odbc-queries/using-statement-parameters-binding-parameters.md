---
title: Parámetros de enlace | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- statements [ODBC], parameters
- binding parameters [SQL Server Native Client]
- parameter markers [ODBC]
- unbound parameter markers
- SQLBindParameter function
- ODBC applications, parameters
- bound parameter markers [SQL Server Native Client]
ms.assetid: d6c69739-8f89-475f-a60a-b2f6c06576e2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3402a7efce43d0ce94a20c93504ac1dcb2c7b48f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662864"
---
# <a name="binding-parameters"></a><span data-ttu-id="bd955-102">Enlazar parámetros</span><span class="sxs-lookup"><span data-stu-id="bd955-102">Binding Parameters</span></span>
  <span data-ttu-id="bd955-103">Cada marcador de parámetros de una instrucción SQL debe estar asociado o enlazado a una variable de la aplicación antes de que se pueda ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="bd955-103">Each parameter marker in an SQL statement must be associated, or bound, to a variable in the application before the statement can be executed.</span></span> <span data-ttu-id="bd955-104">Esto se realiza mediante una llamada a la función [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) .</span><span class="sxs-lookup"><span data-stu-id="bd955-104">This is done by calling the [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) function.</span></span> <span data-ttu-id="bd955-105">**SQLBindParameter** describe la variable de programa (dirección, tipo de datos de C, etc.) al controlador.</span><span class="sxs-lookup"><span data-stu-id="bd955-105">**SQLBindParameter** describes the program variable (address, C data type, and so on) to the driver.</span></span> <span data-ttu-id="bd955-106">También identifica el marcador de parámetros indicando su valor ordinal y, a continuación, describe las características del objeto SQL que representa (tipo de datos SQL, precisión, etc.).</span><span class="sxs-lookup"><span data-stu-id="bd955-106">It also identifies the parameter marker by indicating its ordinal value and then describes the characteristics of the SQL object it represents (SQL data type, precision, and so on).</span></span>

 <span data-ttu-id="bd955-107">Los marcadores de parámetros se pueden enlazar o reenlazar en cualquier momento antes de que se ejecute una instrucción.</span><span class="sxs-lookup"><span data-stu-id="bd955-107">Parameter markers can be bound or rebound at any time before a statement is executed.</span></span> <span data-ttu-id="bd955-108">Un enlace de parámetro continúa activo hasta que se produce uno de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="bd955-108">A parameter binding remains in effect until one of the following occurs:</span></span>

-   <span data-ttu-id="bd955-109">Una llamada a [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) con el parámetro *Option* establecido en SQL_RESET_PARAMS libera todos los parámetros enlazados al identificador de instrucción.</span><span class="sxs-lookup"><span data-stu-id="bd955-109">A call to [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the *Option* parameter set to SQL_RESET_PARAMS frees all parameters bound to the statement handle.</span></span>

-   <span data-ttu-id="bd955-110">Una llamada a **SQLBindParameter** con *ParameterNumber* establecido en el ordinal de un marcador de parámetro enlazado libera automáticamente el enlace anterior.</span><span class="sxs-lookup"><span data-stu-id="bd955-110">A call to **SQLBindParameter** with *ParameterNumber* set to the ordinal of a bound parameter marker automatically releases the previous binding.</span></span>

 <span data-ttu-id="bd955-111">Una aplicación también puede enlazar parámetros a matrices de variables de programa para procesar una instrucción SQL por lotes.</span><span class="sxs-lookup"><span data-stu-id="bd955-111">An application can also bind parameters to arrays of program variables to process an SQL statement in batches.</span></span> <span data-ttu-id="bd955-112">Existen dos tipos de enlaces de matriz:</span><span class="sxs-lookup"><span data-stu-id="bd955-112">There are two types of array binding:</span></span>

-   <span data-ttu-id="bd955-113">El enlace de modo de columna se hace cuando cada parámetro individual se enlaza a su propia matriz de variables.</span><span class="sxs-lookup"><span data-stu-id="bd955-113">Column-wise binding is done when each individual parameter is bound to its own array of variables.</span></span>

     <span data-ttu-id="bd955-114">El enlace de modo de columna se especifica llamando a [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) con el *atributo* establecido en SQL_ATTR_PARAM_BIND_TYPE y *ValuePtr* establecido en SQL_PARAM_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="bd955-114">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to SQL_PARAM_BIND_BY_COLUMN.</span></span>

-   <span data-ttu-id="bd955-115">El enlace de modo de fila se hace cuando todos los parámetros de la instrucción SQL se enlazan como una unidad a una matriz de estructuras que contienen variables individuales para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="bd955-115">Row-wise binding is done when all of the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>

     <span data-ttu-id="bd955-116">El enlace de modo de fila se especifica mediante una llamada a **SQLSetStmtAttr** con el *atributo* establecido en SQL_ATTR_PARAM_BIND_TYPE y *ValuePtr* establecido en el tamaño de la estructura que contiene las variables de programa.</span><span class="sxs-lookup"><span data-stu-id="bd955-116">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to the size of the structure holding the program variables.</span></span>

 <span data-ttu-id="bd955-117">Cuando el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client envía parámetros de cadena binaria o de caracteres al servidor, rellena los valores con la longitud especificada en el parámetro **SQLBindParameter** *columnas* .</span><span class="sxs-lookup"><span data-stu-id="bd955-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver sends character or binary string parameters to the server, it pads the values to the length specified in **SQLBindParameter** *ColumnSize* parameter.</span></span> <span data-ttu-id="bd955-118">Si una aplicación ODBC 2. x especifica 0 para *columnas*, el controlador rellena el valor del parámetro con la precisión del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="bd955-118">If an ODBC 2.x application specifies 0 for *ColumnSize*, the driver pads the parameter value to the precision of the data type.</span></span> <span data-ttu-id="bd955-119">La precisión es 8000 cuando se conecta con los servidores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], 255 cuando se conecta con versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd955-119">The precision is 8000 when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers, 255 when connected to earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bd955-120">*Columnas* en bytes para las columnas Variant.</span><span class="sxs-lookup"><span data-stu-id="bd955-120">*ColumnSize* is in bytes for variant columns.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bd955-121">permite definir nombres para parámetros de procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="bd955-121">supports defining names for stored procedure parameters.</span></span> <span data-ttu-id="bd955-122">ODBC 3.5 también introdujo la compatibilidad con el uso de parámetros con nombre para llamar a procedimientos almacenados de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd955-122">ODBC 3.5 also introduced support for named parameters used when calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="bd955-123">Esta compatibilidad se puede utilizar para:</span><span class="sxs-lookup"><span data-stu-id="bd955-123">This support can be used to:</span></span>

-   <span data-ttu-id="bd955-124">Llamar a un procedimiento almacenado y proporcionar valores para un subconjunto de parámetros definido para el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="bd955-124">Call a stored procedure and provide values for a subset of the parameters defined for the stored procedure.</span></span>

-   <span data-ttu-id="bd955-125">Especifique los parámetros en la aplicación en un orden diferente que el orden especificado cuando se creó el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="bd955-125">Specify the parameters in a different order in the application than the order specified when the stored procedure was created.</span></span>

 <span data-ttu-id="bd955-126">Los parámetros con nombre solo se admiten cuando se usa la [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` instrucción o la secuencia de escape ODBC Call para ejecutar un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="bd955-126">Named parameters are only supported when using the [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` statement or the ODBC CALL escape sequence to execute a stored procedure.</span></span>

 <span data-ttu-id="bd955-127">Si `SQL_DESC_NAME` está establecido para un parámetro de procedimiento almacenado, todos los parámetros de procedimiento almacenado de la consulta también deben establecer `SQL_DESC_NAME`.</span><span class="sxs-lookup"><span data-stu-id="bd955-127">If `SQL_DESC_NAME` is set for a stored procedure parameter, all stored procedure parameters in the query should also set `SQL_DESC_NAME`.</span></span>  <span data-ttu-id="bd955-128">Si se usan literales en llamadas a procedimientos almacenados, donde los parámetros tienen `SQL_DESC_NAME` establecido, los literales deben usar el formato *' nombre* = *valor*', donde *nombre* es el nombre del parámetro del procedimiento almacenado (por ejemplo, @p1 ).</span><span class="sxs-lookup"><span data-stu-id="bd955-128">If literals are used in stored procedure calls, where parameters have `SQL_DESC_NAME` set, the literals should use the format *'name*=*value*', where *name* is the stored procedure parameter name (for example, @p1).</span></span> <span data-ttu-id="bd955-129">Para obtener más información, vea [enlazar parámetros por nombre (parámetros con nombre)](https://go.microsoft.com/fwlink/?LinkId=167215).</span><span class="sxs-lookup"><span data-stu-id="bd955-129">For more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkId=167215).</span></span>

## <a name="see-also"></a><span data-ttu-id="bd955-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd955-130">See Also</span></span>
 [<span data-ttu-id="bd955-131">Usar parámetros de instrucciones</span><span class="sxs-lookup"><span data-stu-id="bd955-131">Using Statement Parameters</span></span>](using-statement-parameters.md)


