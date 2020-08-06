---
title: Procesar resultados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC], about result sets
- SQLRowCount function
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- COMPUTE clause
- result sets [ODBC]
- COMPUTE BY clause
ms.assetid: 61a8db19-6571-47dd-84e8-fcc97cb60b45
author: rothja
ms.author: jroth
ms.openlocfilehash: 72c0d15231b07a23f10a03b0fca270d1d014891c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750869"
---
# <a name="processing-results-odbc"></a><span data-ttu-id="49b5e-102">Procesar los resultados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="49b5e-102">Processing Results (ODBC)</span></span>
  <span data-ttu-id="49b5e-103">Después de que una aplicación envía una instrucción SQL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devuelve los datos resultantes como uno o varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="49b5e-103">After an application submits a SQL statement, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns any resulting data as one or more result sets.</span></span> <span data-ttu-id="49b5e-104">Un conjunto de resultados es un conjunto de filas y columnas que coinciden con los criterios de la consulta.</span><span class="sxs-lookup"><span data-stu-id="49b5e-104">A result set is a set of rows and columns that match the criteria of the query.</span></span> <span data-ttu-id="49b5e-105">Las instrucciones SELECT, las funciones de catálogo y algunos procedimientos almacenados generan un conjunto de resultados que quedan disponibles para las aplicaciones en formato tabular.</span><span class="sxs-lookup"><span data-stu-id="49b5e-105">SELECT statements, catalog functions, and some stored procedures produce a result set made available to an application in tabular form.</span></span> <span data-ttu-id="49b5e-106">Si la instrucción SQL ejecutada es un procedimiento almacenado, un lote que contiene varios comandos o una instrucción SELECT que contiene palabras clave, habrá varios conjuntos de resultados que procesar.</span><span class="sxs-lookup"><span data-stu-id="49b5e-106">If the executed SQL statement is a stored procedure, a batch containing multiple commands, or a SELECT statement containing keywords, there will be multiple result sets to process.</span></span>  
  
 <span data-ttu-id="49b5e-107">Las funciones de catálogo de ODBC también pueden recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="49b5e-107">ODBC catalog functions also can retrieve data.</span></span> <span data-ttu-id="49b5e-108">Por ejemplo, [SQLColumns](../native-client-odbc-api/sqlcolumns.md) recupera datos acerca de las columnas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="49b5e-108">For example, [SQLColumns](../native-client-odbc-api/sqlcolumns.md) retrieves data about columns in the data source.</span></span> <span data-ttu-id="49b5e-109">Estos conjuntos de resultados pueden contener ninguna o más filas.</span><span class="sxs-lookup"><span data-stu-id="49b5e-109">These result sets can contain zero or more rows.</span></span>  
  
 <span data-ttu-id="49b5e-110">Otras instrucciones SQL, como GRANT o REVOKE, no devuelven conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="49b5e-110">Other SQL statements, such as GRANT or REVOKE, do not return result sets.</span></span> <span data-ttu-id="49b5e-111">En estas instrucciones, el código de retorno de **SQLExecute** o **SQLExecDirect** suele ser la única indicación de que la instrucción se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="49b5e-111">For these statements, the return code from **SQLExecute** or **SQLExecDirect** is usually the only indication the statement was successful.</span></span>  
  
 <span data-ttu-id="49b5e-112">Cada instrucción INSERT, UPDATE y DELETE devuelve un conjunto de resultados que contiene solamente el número de filas afectado por la modificación.</span><span class="sxs-lookup"><span data-stu-id="49b5e-112">Each INSERT, UPDATE, and DELETE statement returns a result set containing only the number of rows affected by the modification.</span></span> <span data-ttu-id="49b5e-113">Este recuento está disponible cuando la aplicación llama a [SQLRowCount](../native-client-odbc-api/sqlrowcount.md).</span><span class="sxs-lookup"><span data-stu-id="49b5e-113">This count is made available when application calls [SQLRowCount](../native-client-odbc-api/sqlrowcount.md).</span></span> <span data-ttu-id="49b5e-114">ODBC 3. las aplicaciones *x* deben llamar a **SQLRowCount** para recuperar el conjunto de resultados o [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) para cancelarlo.</span><span class="sxs-lookup"><span data-stu-id="49b5e-114">ODBC 3.*x* applications must either call **SQLRowCount** to retrieve the result set or [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to cancel it.</span></span> <span data-ttu-id="49b5e-115">Cuando una aplicación ejecuta un proceso por lotes o un procedimiento almacenado que contiene varias instrucciones INSERT, UPDATE o DELETE, el conjunto de resultados de cada instrucción de modificación debe procesarse mediante **SQLRowCount** o cancelarse mediante **SQLMoreResults**.</span><span class="sxs-lookup"><span data-stu-id="49b5e-115">When an application executes a batch or stored procedure containing multiple INSERT, UPDATE, or DELETE statements, the result set from each modification statement must be processed using **SQLRowCount** or cancelled using **SQLMoreResults**.</span></span> <span data-ttu-id="49b5e-116">Estos recuentos se pueden cancelar incluyendo una instrucción SET NOCOUNT ON en el lote o procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="49b5e-116">These counts can be cancelled by including a SET NOCOUNT ON statement in the batch or stored procedure.</span></span>  
  
 <span data-ttu-id="49b5e-117">Transact-SQL incluye la instrucción SET NOCOUNT.</span><span class="sxs-lookup"><span data-stu-id="49b5e-117">Transact-SQL includes the SET NOCOUNT statement.</span></span> <span data-ttu-id="49b5e-118">Cuando la opción NOCOUNT está establecida en ON, SQL Server no devuelve los recuentos de las filas afectadas por una instrucción y **SQLRowCount** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="49b5e-118">When the NOCOUNT option is set on, SQL Server does not return the counts of the rows affected by a statement and **SQLRowCount** returns 0.</span></span> <span data-ttu-id="49b5e-119">La [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versión del controlador ODBC de Native Client introduce una opción [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) específica del controlador, SQL_SOPT_SS_NOCOUNT_STATUS, para notificar si la opción NOCOUNT está activada o desactivada.</span><span class="sxs-lookup"><span data-stu-id="49b5e-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver version introduces a driver-specific [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) option, SQL_SOPT_SS_NOCOUNT_STATUS, to report on whether the NOCOUNT option is on or off.</span></span> <span data-ttu-id="49b5e-120">Cada vez que **SQLRowCount** devuelve 0, la aplicación debe probar SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="49b5e-120">Anytime **SQLRowCount** returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="49b5e-121">Si se devuelve SQL_NC_ON, el valor 0 de **SQLRowCount** solo indica que SQL Server no ha devuelto un recuento de filas.</span><span class="sxs-lookup"><span data-stu-id="49b5e-121">If SQL_NC_ON is returned, the value of 0 from **SQLRowCount** only indicates that SQL Server has not returned a row count.</span></span> <span data-ttu-id="49b5e-122">Si se devuelve SQL_NC_OFF, significa que NOCOUNT es OFF y el valor 0 de **SQLRowCount** indica que la instrucción no afectó a ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="49b5e-122">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from **SQLRowCount** indicates that the statement did not affect any rows.</span></span> <span data-ttu-id="49b5e-123">Las aplicaciones no deben mostrar el valor de **SQLRowCount** cuando se SQL_NC_OFF SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="49b5e-123">Applications should not display the value of **SQLRowCount** when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="49b5e-124">Los procedimientos almacenados o lotes de gran tamaño pueden contener varias instrucciones SET NOCOUNT de modo que los programadores no puedan suponer que SQL_SOPT_SS_NOCOUNT_STATUS sigue siendo constante.</span><span class="sxs-lookup"><span data-stu-id="49b5e-124">Large batches or stored procedures may contain multiple SET NOCOUNT statements so programmers cannot assume SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="49b5e-125">La opción se debe probar cada vez que **SQLRowCount** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="49b5e-125">The option should be tested each time **SQLRowCount** returns 0.</span></span>  
  
 <span data-ttu-id="49b5e-126">Otras instrucciones Transact-SQL devuelven los datos en mensajes, en lugar de en conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="49b5e-126">Several other Transact-SQL statements return their data in messages rather than result sets.</span></span> <span data-ttu-id="49b5e-127">Cuando el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client recibe estos mensajes, devuelve SQL_SUCCESS_WITH_INFO para que la aplicación sepa que los mensajes informativos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="49b5e-127">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver receives these messages, it returns SQL_SUCCESS_WITH_INFO to let the application know that informational messages are available.</span></span> <span data-ttu-id="49b5e-128">A continuación, la aplicación puede llamar a **SQLGetDiagRec** para recuperar estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="49b5e-128">The application can then call **SQLGetDiagRec** to retrieve these messages.</span></span> <span data-ttu-id="49b5e-129">Las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] que funcionan de esta manera son:</span><span class="sxs-lookup"><span data-stu-id="49b5e-129">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that work this way are:</span></span>  
  
-   <span data-ttu-id="49b5e-130">DBCC</span><span class="sxs-lookup"><span data-stu-id="49b5e-130">DBCC</span></span>  
  
-   <span data-ttu-id="49b5e-131">SET SHOWPLAN (disponible con versiones anteriores de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="49b5e-131">SET SHOWPLAN (available with earlier versions of SQL Server)</span></span>  
  
-   <span data-ttu-id="49b5e-132">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="49b5e-132">SET STATISTICS</span></span>  
  
-   <span data-ttu-id="49b5e-133">PRINT</span><span class="sxs-lookup"><span data-stu-id="49b5e-133">PRINT</span></span>  
  
-   <span data-ttu-id="49b5e-134">RAISERROR</span><span class="sxs-lookup"><span data-stu-id="49b5e-134">RAISERROR</span></span>  
  
 <span data-ttu-id="49b5e-135">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client devuelve SQL_ERROR en RAISERROR con una gravedad de 11 o superior.</span><span class="sxs-lookup"><span data-stu-id="49b5e-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQL_ERROR on a RAISERROR with a severity of 11 or higher.</span></span> <span data-ttu-id="49b5e-136">Si la gravedad del RAISERROR es 19 o superior, se interrumpe además la conexión.</span><span class="sxs-lookup"><span data-stu-id="49b5e-136">If the severity of the RAISERROR is 19 or higher, the connection is also dropped.</span></span>  
  
 <span data-ttu-id="49b5e-137">Para procesar los conjuntos de resultados de una instrucción SQL, la aplicación:</span><span class="sxs-lookup"><span data-stu-id="49b5e-137">To process the result sets from an SQL statement, the application:</span></span>  
  
-   <span data-ttu-id="49b5e-138">Determina las características del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="49b5e-138">Determines the characteristics of the result set.</span></span>  
  
-   <span data-ttu-id="49b5e-139">Enlaza las columnas a variables de programa.</span><span class="sxs-lookup"><span data-stu-id="49b5e-139">Binds the columns to program variables.</span></span>  
  
-   <span data-ttu-id="49b5e-140">Recupera un valor único, una fila completa de valores o varias filas de valores.</span><span class="sxs-lookup"><span data-stu-id="49b5e-140">Retrieves a single value, an entire row of values, or multiple rows of values.</span></span>  
  
-   <span data-ttu-id="49b5e-141">Comprueba si hay más conjuntos de resultados y, en caso afirmativo, recorre de nuevo el bucle para determinar las características del nuevo conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="49b5e-141">Tests to see if there are more result sets, and if so, loops back to determining the characteristics of the new result set.</span></span>  
  
 <span data-ttu-id="49b5e-142">El proceso de recuperar filas del origen de datos y devolverlas a la aplicación se denomina captura.</span><span class="sxs-lookup"><span data-stu-id="49b5e-142">The process of retrieving rows from the data source and returning them to the application is called fetching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49b5e-143">En esta sección</span><span class="sxs-lookup"><span data-stu-id="49b5e-143">In This Section</span></span>  
  
-   [<span data-ttu-id="49b5e-144">Determinar las características de un conjunto de resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="49b5e-144">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](determining-the-characteristics-of-a-result-set-odbc.md)  
  
-   [<span data-ttu-id="49b5e-145">Asignar almacenamiento</span><span class="sxs-lookup"><span data-stu-id="49b5e-145">Assigning Storage</span></span>](assigning-storage.md)  
  
-   [<span data-ttu-id="49b5e-146">Capturar datos de resultados</span><span class="sxs-lookup"><span data-stu-id="49b5e-146">Fetching Result Data</span></span>](fetching-result-data.md)  
  
-   [<span data-ttu-id="49b5e-147">Asignar tipos de datos &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="49b5e-147">Mapping Data Types &#40;ODBC&#41;</span></span>](mapping-data-types-odbc.md)  
  
-   [<span data-ttu-id="49b5e-148">Uso de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="49b5e-148">Data Type Usage</span></span>](data-type-usage.md)  
  
-   [<span data-ttu-id="49b5e-149">Traducción automática de datos de caracteres</span><span class="sxs-lookup"><span data-stu-id="49b5e-149">Autotranslation of Character Data</span></span>](autotranslation-of-character-data.md)  
  
## <a name="see-also"></a><span data-ttu-id="49b5e-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49b5e-150">See Also</span></span>  
 <span data-ttu-id="49b5e-151">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="49b5e-151">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="49b5e-152">Temas de procedimientos de procesamiento de resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="49b5e-152">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
