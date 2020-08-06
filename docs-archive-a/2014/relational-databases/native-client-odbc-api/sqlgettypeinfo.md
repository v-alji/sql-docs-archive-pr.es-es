---
title: SQLGetTypeInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetTypeInfo function
ms.assetid: 13b982c3-ae03-4155-bc0d-e225050703ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b2bca833eeed5e51237347a5ea118d839dd36de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677073"
---
# <a name="sqlgettypeinfo"></a><span data-ttu-id="83410-102">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="83410-102">SQLGetTypeInfo</span></span>
  <span data-ttu-id="83410-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client notifica la columna adicional USERTYPE en el conjunto de resultados de `SQLGetTypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="83410-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports the additional column USERTYPE in the result set of `SQLGetTypeInfo`.</span></span> <span data-ttu-id="83410-104">USERTYPE notifica la definición de tipo de datos de DB-Library y resulta de gran utilidad para los programadores que migran las aplicaciones existentes de DB-Library a ODBC.</span><span class="sxs-lookup"><span data-stu-id="83410-104">USERTYPE reports the DB-Library data type definition and is useful to developers porting existing DB-Library applications to ODBC.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="83410-105">trata la identidad como un atributo, mientras que ODBC la considera como un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="83410-105">treats identity as an attribute, whereas ODBC treats it as a data type.</span></span> <span data-ttu-id="83410-106">Para resolver esta falta de coincidencia, `SQLGetTypeInfo` devuelve los tipos de datos: **intidentity**, **smallintidentity**, **tinyintidentity**, **decimalidentity**y **numericidentity**.</span><span class="sxs-lookup"><span data-stu-id="83410-106">To resolve this mismatch, `SQLGetTypeInfo` returns the data types: **intidentity**, **smallintidentity**, **tinyintidentity**, **decimalidentity**, and **numericidentity**.</span></span> <span data-ttu-id="83410-107">La `SQLGetTypeInfo` columna del conjunto de resultados AUTO_UNIQUE_VALUE notifica el valor true para estos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="83410-107">The `SQLGetTypeInfo` result set column AUTO_UNIQUE_VALUE reports the value TRUE for these data types.</span></span>  
  
 <span data-ttu-id="83410-108">En **VARCHAR**, **nvarchar** y **varbinary**, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client continúa notificando 8000, 4000 y 8000, respectivamente para el valor COLUMN_SIZE, aunque realmente es ilimitado.</span><span class="sxs-lookup"><span data-stu-id="83410-108">For **varchar**, **nvarchar** and **varbinary**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver continues to report 8000, 4000 and 8000 respectively for the COLUMN_SIZE value, even though it is actually unlimited.</span></span> <span data-ttu-id="83410-109">El motivo de ello es garantizar la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="83410-109">This is to ensure backward compatibility.</span></span>  
  
 <span data-ttu-id="83410-110">En el caso del tipo de datos **XML** , el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client informa SQL_SS_LENGTH_UNLIMITED de COLUMN_SIZE para indicar un tamaño ilimitado.</span><span class="sxs-lookup"><span data-stu-id="83410-110">For the **xml** data type, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports SQL_SS_LENGTH_UNLIMITED for COLUMN_SIZE to denote unlimited size.</span></span>  
  
## <a name="sqlgettypeinfo-and-table-valued-parameters"></a><span data-ttu-id="83410-111">SQLGetTypeInfo y parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="83410-111">SQLGetTypeInfo and Table-Valued Parameters</span></span>  
 <span data-ttu-id="83410-112">El tipo de tabla para los parámetros con valores de tabla es realmente un metatipo, es decir, un tipo que se usa para definir otros tipos.</span><span class="sxs-lookup"><span data-stu-id="83410-112">The table type for table-valued parameters is effectively a meta-type-that is, a type used to define other types.</span></span> <span data-ttu-id="83410-113">Por lo tanto, no tiene que exponerse a través de SQLGetTypeInfo.</span><span class="sxs-lookup"><span data-stu-id="83410-113">Therefore, it does not have to be exposed through SQLGetTypeInfo.</span></span> <span data-ttu-id="83410-114">Las aplicaciones deben usar SQLTables, en lugar de SQLGetTypeInfo, para recuperar los metadatos de los tipos de tabla utilizados con parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="83410-114">Applications must use SQLTables, rather than SQLGetTypeInfo, to retrieve metadata for table types used with table-valued parameters.</span></span>  
  
 <span data-ttu-id="83410-115">Para obtener más información sobre la recuperación de metadatos para los parámetros con valores de tabla, vea [atributos de instrucción que afectan a los parámetros con valores de tabla](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="83410-115">For more information, about retrieving metdata for table-valued parameters, see [Statement Attributes that Affect Table-Valued Parameters](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span></span>  
  
 <span data-ttu-id="83410-116">Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="83410-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="83410-117">SQLGetTypeInfo admite las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="83410-117">SQLGetTypeInfo Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="83410-118">Para obtener los valores devueltos para los tipos de fecha y hora, vea [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="83410-118">For the values returned for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="83410-119">Para obtener más información general, consulte [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="83410-119">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-large-clr-udts"></a><span data-ttu-id="83410-120">Compatibilidad de SQLGetTypeInfo para UDT CLR grandes</span><span class="sxs-lookup"><span data-stu-id="83410-120">SQLGetTypeInfo Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="83410-121">`SQLGetTypeInfo` admite tipos CLR definidos por el usuario (UDT) grandes.</span><span class="sxs-lookup"><span data-stu-id="83410-121">`SQLGetTypeInfo` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="83410-122">Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="83410-122">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83410-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83410-123">See Also</span></span>  
 <span data-ttu-id="83410-124">[SQLGetTypeInfo función)](https://go.microsoft.com/fwlink/?LinkId=59356) </span><span class="sxs-lookup"><span data-stu-id="83410-124">[SQLGetTypeInfo Function](https://go.microsoft.com/fwlink/?LinkId=59356) </span></span>  
 [<span data-ttu-id="83410-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="83410-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
