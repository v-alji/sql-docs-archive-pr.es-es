---
title: Tipo SQL de ODBC para parámetros con valores de tabla | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL_SS_TABLE
ms.assetid: 6725bfb9-5f10-4115-be09-fd9c9f5779ea
author: rothja
ms.author: jroth
ms.openlocfilehash: c8ed46bf117c9158ae5b60c10ebd89e3d348f77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675851"
---
# <a name="odbc-sql-type-for-table-valued-parameters"></a><span data-ttu-id="cc63a-102">Tipo SQL de ODBC para parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="cc63a-102">ODBC SQL Type for Table-Valued Parameters</span></span>
  <span data-ttu-id="cc63a-103">Un nuevo tipo de SQL de ODBC, SQL_SS_TABLE, proporciona compatibilidad con parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="cc63a-103">Support for table-valued parameters is provided by a new ODBC SQL type, SQL_SS_TABLE.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc63a-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cc63a-104">Remarks</span></span>  
 <span data-ttu-id="cc63a-105">SQL_SS_TABLE no se puede convertir en ningún otro tipo de datos ODBC o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc63a-105">SQL_SS_TABLE cannot be converted to any other ODBC or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="cc63a-106">Si se usa SQL_SS_TABLE como un tipo de datos de C en el parámetro *ValueType* de SQLBindParameter, o se intenta establecer SQL_DESC_TYPE en un registro de descriptor de parámetros de la aplicación (APD) en SQL_SS_TABLE, se devuelve SQL_ERROR y se genera un registro de diagnóstico con SQLSTATE = HY003, "tipo de búfer de aplicación no válido".</span><span class="sxs-lookup"><span data-stu-id="cc63a-106">If SQL_SS_TABLE is used as a C data type in the *ValueType* parameter of SQLBindParameter, or an attempt is made to set SQL_DESC_TYPE in an application parameter descriptor (APD) record to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="cc63a-107">Si SQL_DESC_TYPE está establecido en SQL_SS_TABLE en un registro IPD y el registro del descriptor de parámetros de la aplicación correspondiente no es SQL_C_DEFAULT, se devuelve SQL_ERROR y se genera un registro de diagnóstico con SQLSTATE=HY003, "Tipo de búfer de aplicación no válido".</span><span class="sxs-lookup"><span data-stu-id="cc63a-107">If SQL_DESC_TYPE is set to SQL_SS_TABLE in an IPD record and the corresponding application parameter descriptor record is not SQL_C_DEFAULT, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span> <span data-ttu-id="cc63a-108">Esto puede ocurrir con el *ParameterType* de SQLSetDescField, SQLSetDescRec o SQLBindParameter.</span><span class="sxs-lookup"><span data-stu-id="cc63a-108">This can occur with the *ParameterType* of a SQLSetDescField, SQLSetDescRec or SQLBindParameter.</span></span>  
  
 <span data-ttu-id="cc63a-109">Si el parámetro *TargetType* es SQL_SS_TABLE al llamar a SQLGetData, se devuelve SQL_ERROR y se genera un registro de diagnóstico con SQLSTATE = HY003, "tipo de búfer de aplicación no válido".</span><span class="sxs-lookup"><span data-stu-id="cc63a-109">If the *TargetType* parameter is SQL_SS_TABLE when calling SQLGetData, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="cc63a-110">Una columna de parámetro con valores de tabla no se puede enlazar como tipo SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="cc63a-110">A table-valued parameter column cannot be bound as type SQL_SS_TABLE.</span></span> <span data-ttu-id="cc63a-111">Si `SQLBindParameter` se llama a con *ParameterType* establecido en SQL_SS_TABLE, se devuelve SQL_ERROR y se genera un registro de diagnóstico con SQLSTATE = HY004, "tipo de datos SQL no válido".</span><span class="sxs-lookup"><span data-stu-id="cc63a-111">If `SQLBindParameter` is called with *ParameterType* set to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY004, "Invalid SQL data type".</span></span> <span data-ttu-id="cc63a-112">Esto también puede ocurrir con SQLSetDescField y SQLSetDescRec.</span><span class="sxs-lookup"><span data-stu-id="cc63a-112">This can also occur with SQLSetDescField and SQLSetDescRec.</span></span>  
  
 <span data-ttu-id="cc63a-113">Los valores de las columnas de parámetros con valores de tabla tienen las mismas opciones de conversión de datos que las columnas de parámetros y resultado.</span><span class="sxs-lookup"><span data-stu-id="cc63a-113">Table-valued parameter column values have the same data conversion options as parameters and result columns.</span></span>  
  
 <span data-ttu-id="cc63a-114">Un parámetro con valores de tabla puede ser solamente un parámetro de entrada en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o posterior.</span><span class="sxs-lookup"><span data-stu-id="cc63a-114">A table-valued parameter can only be an input parameter in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="cc63a-115">Si se realiza un intento de establecer SQL_DESC_PARAMETER_TYPE en un valor distinto de SQL_PARAM_INPUT a través de SQLBindParameter o SQLSetDescField, se devuelve SQL_ERROR y se agrega un registro de diagnóstico a la instrucción con SQLSTATE = HY105 y el mensaje "tipo de parámetro no válido".</span><span class="sxs-lookup"><span data-stu-id="cc63a-115">If an attempt is made to set SQL_DESC_PARAMETER_TYPE to a value other than SQL_PARAM_INPUT via SQLBindParameter or SQLSetDescField, SQL_ERROR is returned and a diagnostic record is added to the statement with SQLSTATE=HY105 and the message "Invalid parameter type".</span></span>  
  
 <span data-ttu-id="cc63a-116">Las columnas de parámetros con valores de tabla no pueden utilizar SQL_DEFAULT_PARAM en *StrLen_or_IndPtr*, porque los valores predeterminados por fila no se admiten con los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="cc63a-116">Table-valued parameter columns cannot use SQL_DEFAULT_PARAM in *StrLen_or_IndPtr*, because per-row default values are not supported with table-valued parameters.</span></span> <span data-ttu-id="cc63a-117">En su lugar, una aplicación puede establecer el atributo de columna SQL_CA_SS_COL_HAS_DEFAULT_VALUE en 1.</span><span class="sxs-lookup"><span data-stu-id="cc63a-117">Instead, an application can set the column attribute SQL_CA_SS_COL_HAS_DEFAULT_VALUE to 1.</span></span> <span data-ttu-id="cc63a-118">Esto significa que la columna tendrá los valores predeterminados para todas las filas.</span><span class="sxs-lookup"><span data-stu-id="cc63a-118">This means that the column will have default values for all rows.</span></span> <span data-ttu-id="cc63a-119">Si *StrLen_or_IndPtr* se establece en SQL_DEFAULT_PARAM, SQLExecute o SQLExecDirect devolverán SQL_ERROR y se agregará un registro de diagnóstico a la instrucción con SQLSTATE = HY090 y el mensaje "longitud de búfer o cadena no válida".</span><span class="sxs-lookup"><span data-stu-id="cc63a-119">If *StrLen_or_IndPtr* is set to SQL_DEFAULT_PARAM, SQLExecute or SQLExecDirect will return SQL_ERROR, and a diagnostic record will be added to the statement with SQLSTATE=HY090 and the message "Invalid string or buffer length".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc63a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc63a-120">See Also</span></span>  
 [<span data-ttu-id="cc63a-121">Parámetros con valores de tabla &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="cc63a-121">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
