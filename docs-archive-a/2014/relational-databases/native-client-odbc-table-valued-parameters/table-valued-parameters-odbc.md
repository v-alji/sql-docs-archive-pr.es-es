---
title: Parámetros con valores de tabla (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC)
- ODBC, table-valued parameters
ms.assetid: ef06cd13-18e2-4c65-8ede-c3955d820e54
author: rothja
ms.author: jroth
ms.openlocfilehash: fedfd63f7cbafd68d39aeb62dd29c046df8ab100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662860"
---
# <a name="table-valued-parameters-odbc"></a><span data-ttu-id="ae59c-102">Parámetros con valores de tabla (ODBC)</span><span class="sxs-lookup"><span data-stu-id="ae59c-102">Table-Valued Parameters (ODBC)</span></span>
  <span data-ttu-id="ae59c-103">La compatibilidad con ODBC para parámetros con valores de tabla permite a una aplicación cliente enviar datos parametrizados al servidor más eficazmente, enviando varias filas al servidor con una llamada.</span><span class="sxs-lookup"><span data-stu-id="ae59c-103">ODBC support for table-valued parameters lets a client application send parameterized data to the server more efficiently, by sending multiple rows to the server with one call.</span></span>  
  
 <span data-ttu-id="ae59c-104">Para obtener información sobre los parámetros con valores de tabla en el servidor, vea [usar parámetros con valores de tabla &#40;Motor de base de datos&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="ae59c-104">For information about table-valued parameters on the server, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
 <span data-ttu-id="ae59c-105">En ODBC, hay dos formas de enviar parámetros con valores de tabla al servidor:</span><span class="sxs-lookup"><span data-stu-id="ae59c-105">In ODBC, there are two ways that you can send table-valued parameters to the server:</span></span>  
  
-   <span data-ttu-id="ae59c-106">Todos los datos de parámetros con valores de tabla pueden estar en memoria en el momento en que se llama a SQLExecDirect o SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="ae59c-106">All the table-valued parameter data can be in memory at the time SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="ae59c-107">Estos datos se almacenan en matrices si hay varias filas en el valor de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-107">This data is stored in arrays if there are multiple rows in the table-value.</span></span>  
  
-   <span data-ttu-id="ae59c-108">Una aplicación puede especificar datos en ejecución para un parámetro con valores de tabla cuando se llama a SQLExecDirect o SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="ae59c-108">An application can specify data-at-execution for a table-valued parameter when SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="ae59c-109">En este caso, las filas de datos para el valor de tabla se pueden proporcionar en lotes o de uno en uno para reducir los requerimientos de memoria.</span><span class="sxs-lookup"><span data-stu-id="ae59c-109">In this case, rows of data for the table-value can be provided in batches, or one at a time to reduce memory requirements.</span></span>  
  
 <span data-ttu-id="ae59c-110">La primera opción habilita los procedimientos almacenados para encapsular más lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="ae59c-110">The first option enables stored procedures to encapsulate more business logic.</span></span> <span data-ttu-id="ae59c-111">Por ejemplo, un procedimiento almacenado único podría encapsular una transacción de entrada de pedido entera cuando los elementos del pedido se pasan como un parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-111">For example, a single stored procedure could encapsulate a whole order entry transaction when the order items are passed as a table-valued parameter.</span></span> <span data-ttu-id="ae59c-112">Esta opción es muy eficaz, porque se requiere solo un único ciclo de ida y vuelta al servidor.</span><span class="sxs-lookup"><span data-stu-id="ae59c-112">This option is very efficient, because only a single round trip to the server is required.</span></span> <span data-ttu-id="ae59c-113">Alternativamente, podría utilizar diferentes procedimientos para administrar por separado el encabezado y los elementos del pedido, lo que requeriría más código y un contrato más complejo entre el cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="ae59c-113">Alternatively, you could use different procedures to handle the order header and order items separately, which would require more code and a more complex contract between the client and server.</span></span>  
  
 <span data-ttu-id="ae59c-114">El segundo método proporciona un mecanismo eficaz para las operaciones masivas con cantidades muy grandes de datos.</span><span class="sxs-lookup"><span data-stu-id="ae59c-114">The second method provides an efficient mechanism for bulk operations with very large amounts of data.</span></span> <span data-ttu-id="ae59c-115">Esto habilita a una aplicación para transmitir en secuencias filas de datos al servidor sin tener que almacenar primero todos en memoria.</span><span class="sxs-lookup"><span data-stu-id="ae59c-115">This enables an application to stream rows of data to the server without having to buffer them all in memory first.</span></span>  
  
 <span data-ttu-id="ae59c-116">Puede crear restricciones y claves principales al crear la variable de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-116">You can create constraints and primary keys when you create the table variable.</span></span> <span data-ttu-id="ae59c-117">Las restricciones constituyen un buen medio de asegurarse de que los datos de una tabla cumplan requisitos concretos.</span><span class="sxs-lookup"><span data-stu-id="ae59c-117">Constraints are a good way to ensure that the data in a table meets specific requirements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae59c-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ae59c-118">In This Section</span></span>  
 [<span data-ttu-id="ae59c-119">Usos de parámetros con valores de tabla de ODBC</span><span class="sxs-lookup"><span data-stu-id="ae59c-119">Uses of ODBC Table-Valued Parameters</span></span>](uses-of-odbc-table-valued-parameters.md)  
 <span data-ttu-id="ae59c-120">Describe los escenarios de usuario principales para parámetros con valores de tabla y ODBC.</span><span class="sxs-lookup"><span data-stu-id="ae59c-120">Describes the primary user scenarios for table-valued parameters and ODBC.</span></span>  
  
 [<span data-ttu-id="ae59c-121">Tipo SQL de ODBC para parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="ae59c-121">ODBC SQL Type for Table-Valued Parameters</span></span>](odbc-sql-type-for-table-valued-parameters.md)  
 <span data-ttu-id="ae59c-122">Describe el tipo SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="ae59c-122">Describes the SQL_SS_TABLE type.</span></span> <span data-ttu-id="ae59c-123">Se trata de un nuevo tipo SQL de ODBC que admite parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-123">This is a new ODBC SQL type that supports table-valued parameters.</span></span>  
  
 [<span data-ttu-id="ae59c-124">Campos de descriptor de parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="ae59c-124">Table-Valued Parameter Descriptor Fields</span></span>](table-valued-parameter-descriptor-fields.md)  
 <span data-ttu-id="ae59c-125">Describe campos de descriptor que admiten parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-125">Describes descriptor fields that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="ae59c-126">Campos de descriptor para columnas de parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="ae59c-126">Descriptor Fields for Table-Valued Parameter Constituent Columns</span></span>](descriptor-fields-for-table-valued-parameter-constituent-columns.md)  
 <span data-ttu-id="ae59c-127">Describe campos de descriptor que tienen significado para parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-127">Describes descriptor fields that have meaning for table-valued parameters.</span></span>  
  
 [<span data-ttu-id="ae59c-128">Campos de registros de diagnóstico para parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="ae59c-128">Table-Valued Parameter Diagnostic Record Fields</span></span>](table-valued-parameter-diagnostic-record-fields.md)  
 <span data-ttu-id="ae59c-129">Describe dos campos de diagnóstico agregados a los registros de diagnóstico para admitir los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-129">Describes two diagnostic fields that have been added to diagnostic records to support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="ae59c-130">Atributos de instrucción que afectan a parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="ae59c-130">Statement Attributes that Affect Table-Valued Parameters</span></span>](statement-attributes-that-affect-table-valued-parameters.md)  
 <span data-ttu-id="ae59c-131">Describe un nuevo campo de encabezado de descriptor que habilita la manipulación de columnas de parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-131">Describes a new descriptor header field that enables table-valued parameters columns to be addressed.</span></span>  
  
 [<span data-ttu-id="ae59c-132">Enlace y transferencia de datos de valores de columnas y parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="ae59c-132">Binding and Data Transfer of Table-Valued Parameters and Column Values</span></span>](binding-and-data-transfer-of-table-valued-parameters-and-column-values.md)  
 <span data-ttu-id="ae59c-133">Describe el enlace de parámetros y cómo pasar un parámetro con valores de tabla al servidor.</span><span class="sxs-lookup"><span data-stu-id="ae59c-133">Describes parameter binding and how to pass a table-valued parameter to the server.</span></span>  
  
 [<span data-ttu-id="ae59c-134">Metadatos de parámetros con valores de tabla para instrucciones preparadas</span><span class="sxs-lookup"><span data-stu-id="ae59c-134">Table-Valued Parameter Metadata for Prepared Statements</span></span>](table-valued-parameter-metadata-for-prepared-statements.md)  
 <span data-ttu-id="ae59c-135">Describe cómo una aplicación puede obtener metadatos para una llamada a procedimiento preparada.</span><span class="sxs-lookup"><span data-stu-id="ae59c-135">Describes how an application can obtain metadata for a prepared procedure call.</span></span>  
  
 [<span data-ttu-id="ae59c-136">Metadatos de parámetros con valores de tabla adicionales</span><span class="sxs-lookup"><span data-stu-id="ae59c-136">Additional Table-Valued Parameter Metadata</span></span>](additional-table-valued-parameter-metadata.md)  
 <span data-ttu-id="ae59c-137">Describe cómo usar SQLProcedureColumns, SQLTables y SQLColumns para recuperar los metadatos de un parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-137">Describes how to use SQLProcedureColumns, SQLTables, and SQLColumns to retrieve metadata for a table-valued parameter.</span></span>  
  
 [<span data-ttu-id="ae59c-138">Conversión de datos de parámetros con valores de tabla y otros errores y advertencias</span><span class="sxs-lookup"><span data-stu-id="ae59c-138">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>](table-valued-parameter-data-conversion-and-other-errors-and-warnings.md)  
 <span data-ttu-id="ae59c-139">Describe cómo procesar los errores en valores de columna de parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-139">Describes how to process errors on table-valued parameter column values.</span></span>  
  
 [<span data-ttu-id="ae59c-140">Compatibilidad entre versiones</span><span class="sxs-lookup"><span data-stu-id="ae59c-140">Cross-Version Compatibility</span></span>](cross-version-compatibility.md)  
 <span data-ttu-id="ae59c-141">Describe conflictos que se pueden producir cuando un cliente o un servidor de una versión anterior a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] utiliza parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-141">Describes conflicts that can occur when table-valued parameters are used by a client or server of a version earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 [<span data-ttu-id="ae59c-142">Resumen de la API de parámetros con valores de tabla de ODBC</span><span class="sxs-lookup"><span data-stu-id="ae59c-142">ODBC Table-Valued Parameter API Summary</span></span>](odbc-table-valued-parameter-api-summary.md)  
 <span data-ttu-id="ae59c-143">Muestra la lista de funciones ODBC que admiten parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="ae59c-143">Lists the ODBC functions that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="ae59c-144">Ejemplos de programación de parámetros con valores de tabla ODBC</span><span class="sxs-lookup"><span data-stu-id="ae59c-144">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
 <span data-ttu-id="ae59c-145">Describe cómo realizar tareas comunes.</span><span class="sxs-lookup"><span data-stu-id="ae59c-145">Describes how to perform common tasks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae59c-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae59c-146">See Also</span></span>  
 <span data-ttu-id="ae59c-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="ae59c-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="ae59c-148">Parámetros con valores de tabla &#40;SQL Server Native Client&#41;</span><span class="sxs-lookup"><span data-stu-id="ae59c-148">Table-Valued Parameters &#40;SQL Server Native Client&#41;</span></span>](../native-client/features/table-valued-parameters-sql-server-native-client.md)  
  
  
