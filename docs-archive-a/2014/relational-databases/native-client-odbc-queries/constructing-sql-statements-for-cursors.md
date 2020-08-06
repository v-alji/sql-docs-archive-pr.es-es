---
title: Crear instrucciones SQL para cursores | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], statement construction
- ODBC applications, cursors
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
- statements [ODBC], cursors
ms.assetid: 134003fd-9c93-4f5c-a988-045990933b80
author: rothja
ms.author: jroth
ms.openlocfilehash: b0fe0831b97c13c5d20067386f4e9d8c97ee19ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662883"
---
# <a name="constructing-sql-statements-for-cursors"></a><span data-ttu-id="5c79b-102">Crear instrucciones SQL para cursores</span><span class="sxs-lookup"><span data-stu-id="5c79b-102">Constructing SQL Statements for Cursors</span></span>
  <span data-ttu-id="5c79b-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client utiliza cursores de servidor para implementar la funcionalidad de cursor definida en la especificación ODBC.</span><span class="sxs-lookup"><span data-stu-id="5c79b-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses server cursors to implement the cursor functionality defined in the ODBC specification.</span></span> <span data-ttu-id="5c79b-104">Una aplicación ODBC controla el comportamiento del cursor mediante el uso de [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) para establecer distintos atributos de instrucción.</span><span class="sxs-lookup"><span data-stu-id="5c79b-104">An ODBC application controls the cursor behavior by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) to set different statement attributes.</span></span> <span data-ttu-id="5c79b-105">Éstos son los atributos y sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5c79b-105">These are the attributes and their defaults.</span></span>  
  
|<span data-ttu-id="5c79b-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="5c79b-106">Attribute</span></span>|<span data-ttu-id="5c79b-107">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="5c79b-107">Default</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="5c79b-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="5c79b-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="5c79b-109">SQL_CONCUR_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="5c79b-109">SQL_CONCUR_READ_ONLY</span></span>|  
|<span data-ttu-id="5c79b-110">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="5c79b-110">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="5c79b-111">SQL_CURSOR_FORWARD_ONLY</span><span class="sxs-lookup"><span data-stu-id="5c79b-111">SQL_CURSOR_FORWARD_ONLY</span></span>|  
|<span data-ttu-id="5c79b-112">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="5c79b-112">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="5c79b-113">SQL_NONSCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="5c79b-113">SQL_NONSCROLLABLE</span></span>|  
|<span data-ttu-id="5c79b-114">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="5c79b-114">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="5c79b-115">SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="5c79b-115">SQL_UNSPECIFIED</span></span>|  
|<span data-ttu-id="5c79b-116">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="5c79b-116">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="5c79b-117">1</span><span class="sxs-lookup"><span data-stu-id="5c79b-117">1</span></span>|  
  
 <span data-ttu-id="5c79b-118">Cuando estas opciones se establecen en sus valores predeterminados en el momento en que se ejecuta una instrucción SQL, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client no utiliza un cursor de servidor para implementar el conjunto de resultados; en su lugar, utiliza un conjunto de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5c79b-118">When these options are set to their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not use a server cursor to implement the result set; instead, it uses a default result set.</span></span> <span data-ttu-id="5c79b-119">Si alguna de estas opciones se cambia con respecto a sus valores predeterminados en el momento en que se ejecuta una instrucción SQL, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client intenta usar un cursor de servidor para implementar el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5c79b-119">If any of these options are changed from their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver attempts to use a server cursor to implement the result set.</span></span>  
  
 <span data-ttu-id="5c79b-120">Los conjuntos de resultados predeterminados admiten todas las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c79b-120">Default result sets support all of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="5c79b-121">No hay ninguna restricción con respecto a los tipos de instrucciones SQL que pueden ejecutarse cuando se utiliza un conjunto de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5c79b-121">There are no restrictions on the types of SQL statements that can be executed when using a default result set.</span></span>  
  
 <span data-ttu-id="5c79b-122">Los cursores de servidor no admiten todas las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c79b-122">Server cursors do not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="5c79b-123">Los cursores de servidor no admiten cualquier instrucción SQL que genere varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="5c79b-123">Server cursors do not support any SQL statement that generates multiple result sets.</span></span>  
  
 <span data-ttu-id="5c79b-124">Los cursores de servidor no admiten los siguientes tipos de instrucciones:</span><span class="sxs-lookup"><span data-stu-id="5c79b-124">The following types of statements are not supported by server cursors:</span></span>  
  
-   <span data-ttu-id="5c79b-125">Instancias de Batch</span><span class="sxs-lookup"><span data-stu-id="5c79b-125">Batches</span></span>  
  
     <span data-ttu-id="5c79b-126">Instrucciones SQL generadas a partir de dos o más instrucciones SQL SELECT individuales como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5c79b-126">SQL statements built from two or more individual SQL SELECT statements, for example:</span></span>  
  
    ```  
    SELECT * FROM Authors; SELECT * FROM Titles  
    ```  
  
-   <span data-ttu-id="5c79b-127">Procedimientos almacenados con varias instrucciones SELECT</span><span class="sxs-lookup"><span data-stu-id="5c79b-127">Stored procedures with multiple SELECT statements</span></span>  
  
     <span data-ttu-id="5c79b-128">Instrucciones SQL que ejecutan un procedimiento almacenado que contiene más de una instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="5c79b-128">SQL statements that execute a stored procedure containing more than one SELECT statement.</span></span> <span data-ttu-id="5c79b-129">Entre estas instrucciones se incluyen las instrucciones SELECT que rellenan parámetros o variables.</span><span class="sxs-lookup"><span data-stu-id="5c79b-129">This includes SELECT statements that fill parameters or variables.</span></span>  
  
-   <span data-ttu-id="5c79b-130">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5c79b-130">Keywords</span></span>  
  
     <span data-ttu-id="5c79b-131">Instrucciones SQL que contienen las palabras clave FOR BROWSE o INTO.</span><span class="sxs-lookup"><span data-stu-id="5c79b-131">SQL statements containing the keywords FOR BROWSE, or INTO.</span></span>  
  
 <span data-ttu-id="5c79b-132">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], si se ejecuta una instrucción SQL que se ajusta a alguna de estas condiciones con un cursor de servidor, el cursor de servidor se convierte de forma implícita en un conjunto de resultados predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5c79b-132">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if an SQL statement that matches any of these conditions is executed with a server cursor, the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="5c79b-133">Después de que **SQLExecDirect** o **SQLExecute** devuelva SQL_SUCCESS_WITH_INFO, los atributos de cursor se devolverán a su configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5c79b-133">After **SQLExecDirect** or **SQLExecute** returns SQL_SUCCESS_WITH_INFO, the cursor attributes will be set back to their default settings.</span></span>  
  
 <span data-ttu-id="5c79b-134">Las instrucciones SQL que no se ajustan a las categorías anteriores pueden ejecutarse con cualquier valor de atributo de instrucción; funcionan igual de bien con un conjunto de resultados predeterminado que con un cursor de servidor.</span><span class="sxs-lookup"><span data-stu-id="5c79b-134">SQL statements that do not fit the categories above can be executed with any statement attribute settings; they work equally well with either a default result set or a server cursor.</span></span>  
  
## <a name="errors"></a><span data-ttu-id="5c79b-135">Errors</span><span class="sxs-lookup"><span data-stu-id="5c79b-135">Errors</span></span>  
 <span data-ttu-id="5c79b-136">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 y versiones posteriores, un intento de ejecución de una instrucción que da lugar a varios conjuntos de resultados genera SQL_SUCCESS_WITH INFO y el mensaje siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c79b-136">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 and later, an attempt to execute a statement that produces multiple result sets generates SQL_SUCCESS_WITH INFO and the following message:</span></span>  
  
```  
SqlState: 01S02"  
pfNative: 0  
szErrorMsgString: "[Microsoft][SQL Server Native Client][SQL Server]  
               Cursor type changed."  
```  
  
 <span data-ttu-id="5c79b-137">Las aplicaciones ODBC que reciben este mensaje pueden llamar a [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) para determinar la configuración actual del cursor.</span><span class="sxs-lookup"><span data-stu-id="5c79b-137">ODBC applications receiving this message can call [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) to determine the current cursor settings.</span></span>  
  
 <span data-ttu-id="5c79b-138">Un intento de ejecutar un procedimiento con varias instrucciones SELECT cuando se utilizan los cursores de servidor genera el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c79b-138">An attempt to execute a procedure with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16937  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               A server cursor is not allowed on a stored procedure  
               with more than one SELECT statement in it. Use a  
               default result set or client cursor.  
```  
  
 <span data-ttu-id="5c79b-139">Un intento de ejecutar un lote con varias instrucciones SELECT cuando se utilizan los cursores de servidor genera el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c79b-139">An attempt to execute a batch with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16938  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               sp_cursoropen. The statement parameter can only  
               be a single SELECT statement or a single stored   
               procedure.  
```  
  
 <span data-ttu-id="5c79b-140">Las aplicaciones ODBC que reciben estos errores deben restablecer todos los atributos de instrucción de cursor a sus valores predeterminados antes de intentar ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="5c79b-140">ODBC applications receiving these errors must reset all the cursor statement attributes to their defaults before attempting to execute the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c79b-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c79b-141">See Also</span></span>  
 [<span data-ttu-id="5c79b-142">Ejecutar consultas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="5c79b-142">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
