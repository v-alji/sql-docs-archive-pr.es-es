---
title: SQLPutData | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPutData function
ms.assetid: d39aaa5b-7fbc-4315-a7f2-5a7787e04f25
author: rothja
ms.author: jroth
ms.openlocfilehash: 31da9c21f9e4323a492a25629a979c66a4f7d365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677053"
---
# <a name="sqlputdata"></a><span data-ttu-id="cace2-102">SQLPutData</span><span class="sxs-lookup"><span data-stu-id="cace2-102">SQLPutData</span></span>
  <span data-ttu-id="cace2-103">Se aplican las siguientes restricciones al usar SQLPutData para enviar más de 65.535 bytes de datos (para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la versión 4.21 a) o 400 KB de datos (para SQL Server versión 6,0 y posteriores) para una columna SQL_LONGVARCHAR ( `text` ), SQL_WLONGVARCHAR ( `ntext` ) o SQL_LONGVARBINARY ( `image` ):</span><span class="sxs-lookup"><span data-stu-id="cace2-103">The following restrictions apply when using SQLPutData to send more than 65,535 bytes of data (for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 4.21a) or 400 KB of data (for SQL Server version 6.0 and later) for a SQL_LONGVARCHAR (`text`), SQL_WLONGVARCHAR (`ntext`) or SQL_LONGVARBINARY (`image`) column:</span></span>  
  
-   <span data-ttu-id="cace2-104">El parámetro al que se hace referencia puede ser el *insert_value* en una instrucción INSERT.</span><span class="sxs-lookup"><span data-stu-id="cace2-104">The referenced parameter can be the *insert_value* in an INSERT statement.</span></span>  
  
-   <span data-ttu-id="cace2-105">El parámetro al que se hace referencia puede ser una *expresión* de la cláusula SET de una instrucción UPDATE.</span><span class="sxs-lookup"><span data-stu-id="cace2-105">The referenced parameter can be an *expression* in the SET clause of an UPDATE statement.</span></span>  
  
 <span data-ttu-id="cace2-106">Al cancelar una secuencia de llamadas a SQLPutData que proporcionan datos en bloques a un servidor que ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se produce una actualización parcial del valor de la columna cuando se usa la versión 6,5 o anterior.</span><span class="sxs-lookup"><span data-stu-id="cace2-106">Canceling a sequence of SQLPutData calls that provide data in blocks to a server running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] causes a partial update of the column's value when using version 6.5 or earlier.</span></span> <span data-ttu-id="cace2-107">La `text` `ntext` columna, o `image` a la que se hizo referencia cuando se llamó a SQLCancel se establece en un valor de marcador de posición intermedio.</span><span class="sxs-lookup"><span data-stu-id="cace2-107">The `text`, `ntext`, or `image` column that was referenced when SQLCancel was called is set to an intermediate placeholder value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cace2-108">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client no permite la conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versión 6.5 y anteriores.</span><span class="sxs-lookup"><span data-stu-id="cace2-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 6.5 and earlier.</span></span>  
  
## <a name="diagnostics"></a><span data-ttu-id="cace2-109">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="cace2-109">Diagnostics</span></span>  
 <span data-ttu-id="cace2-110">Hay un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQLSTATE específico del cliente nativo para SQLPutData:</span><span class="sxs-lookup"><span data-stu-id="cace2-110">There is one [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client specific SQLSTATE for SQLPutData:</span></span>  
  
|<span data-ttu-id="cace2-111">SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="cace2-111">SQLSTATE</span></span>|<span data-ttu-id="cace2-112">Error</span><span class="sxs-lookup"><span data-stu-id="cace2-112">Error</span></span>|<span data-ttu-id="cace2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cace2-113">Description</span></span>|  
|--------------|-----------|-----------------|  
|<span data-ttu-id="cace2-114">22026</span><span class="sxs-lookup"><span data-stu-id="cace2-114">22026</span></span>|<span data-ttu-id="cace2-115">Datos de cadena, desigualdad de longitud</span><span class="sxs-lookup"><span data-stu-id="cace2-115">String data, length mismatch</span></span>|<span data-ttu-id="cace2-116">Si una aplicación ha especificado la longitud de los datos en bytes que se van a enviar, por ejemplo, con SQL_LEN_DATA_AT_EXEC (*n*), donde *n* es mayor que 0, el número total de bytes proporcionado por la aplicación a través de SQLPutData debe coincidir con la longitud especificada.</span><span class="sxs-lookup"><span data-stu-id="cace2-116">If the length of data in bytes to be sent has been specified by an application, for example, with SQL_LEN_DATA_AT_EXEC(*n*) where *n* is greater than 0, the total number of bytes given by the application via SQLPutData must match the specified length.</span></span>|  
  
## <a name="sqlputdata-and-table-valued-parameters"></a><span data-ttu-id="cace2-117">SQLPutData y parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="cace2-117">SQLPutData and Table-Valued Parameters</span></span>  
 <span data-ttu-id="cace2-118">Una aplicación utiliza SQLPutData cuando se usa el enlace de filas variable con parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="cace2-118">SQLPutData is used by an application when using variable row binding with table-valued parameters.</span></span> <span data-ttu-id="cace2-119">El parámetro *StrLen_Or_Ind* indica que está listo para que el controlador recopile datos de la siguiente fila o filas de datos de parámetros con valores de tabla, o que no haya más filas disponibles:</span><span class="sxs-lookup"><span data-stu-id="cace2-119">The *StrLen_Or_Ind* parameter indicates that it is ready for the driver to collect data for the next row or rows of table-valued parameter data, or that no more rows are available:</span></span>  
  
-   <span data-ttu-id="cace2-120">Un valor mayor que 0 indica que el conjunto siguiente de valores de fila está disponible.</span><span class="sxs-lookup"><span data-stu-id="cace2-120">A value greater than 0 indicates that the next set of row values is available.</span></span>  
  
-   <span data-ttu-id="cace2-121">Un valor de 0 indica que no hay ninguna fila más para enviar.</span><span class="sxs-lookup"><span data-stu-id="cace2-121">A value of 0 indicates that there are no more rows to be sent.</span></span>  
  
-   <span data-ttu-id="cace2-122">Cualquier valor menor que 0 es un error tiene como resultado un registro de diagnóstico que se registra con con SQLState HY090 y el mensaje "Longitud de búfer o cadena no válida".</span><span class="sxs-lookup"><span data-stu-id="cace2-122">Any value less than 0 is an error and results in a diagnostic record being logged with SQLState HY090 and the messaage "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="cace2-123">Se omite el parámetro *DataPtr* , pero debe establecerse en un valor distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="cace2-123">The *DataPtr* parameter is ignored, but must be set to a non-NULL value.</span></span> <span data-ttu-id="cace2-124">Para obtener más información, vea la sección sobre el enlace de filas variable TVP en [Binding y transferencia de datos de parámetros con valores de tabla y valores de columna](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="cace2-124">For more information, see the section on Variable TVP row binding in [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="cace2-125">Si *StrLen_Or_Ind* tiene un valor distinto de SQL_DEFAULT_PARAM o un número entre 0 y el SQL_PARAMSET_SIZE (es decir, el parámetro *columnas* de SQLBindParameter), se trata de un error.</span><span class="sxs-lookup"><span data-stu-id="cace2-125">If *StrLen_Or_Ind* has any value other than SQL_DEFAULT_PARAM or a number between 0 and the SQL_PARAMSET_SIZE (that is, the *ColumnSize* parameter of SQLBindParameter), it is an error.</span></span> <span data-ttu-id="cace2-126">Este error hace que SQLPutData devuelva SQL_ERROR: SQLSTATE=HY090, "Longitud de búfer o cadena no válida".</span><span class="sxs-lookup"><span data-stu-id="cace2-126">This error causes SQLPutData to return SQL_ERROR: SQLSTATE=HY090, "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="cace2-127">Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="cace2-127">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="cace2-128">Compatibilidad de SQLPutData con las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="cace2-128">SQLPutData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="cace2-129">Los valores de parámetro de los tipos de fecha y hora se convierten como se describe en [conversiones de C a SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="cace2-129">Parameter values of date/time types are converted as described in [Conversions from C to SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span></span>  
  
 <span data-ttu-id="cace2-130">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="cace2-130">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-large-clr-udts"></a><span data-ttu-id="cace2-131">Compatibilidad de SQLPutData con los UDT CLR grandes</span><span class="sxs-lookup"><span data-stu-id="cace2-131">SQLPutData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="cace2-132">`SQLPutData` admite tipos CLR definidos por el usuario (UDT) grandes.</span><span class="sxs-lookup"><span data-stu-id="cace2-132">`SQLPutData` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="cace2-133">Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="cace2-133">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cace2-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cace2-134">See Also</span></span>  
 <span data-ttu-id="cace2-135">[SQLPutData función)](https://go.microsoft.com/fwlink/?LinkId=59365) </span><span class="sxs-lookup"><span data-stu-id="cace2-135">[SQLPutData Function](https://go.microsoft.com/fwlink/?LinkId=59365) </span></span>  
 [<span data-ttu-id="cace2-136">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="cace2-136">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
