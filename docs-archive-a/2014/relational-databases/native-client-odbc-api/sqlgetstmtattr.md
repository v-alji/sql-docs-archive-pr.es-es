---
title: SQLGetStmtAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetStmtAttr function
ms.assetid: e64f4f94-eb73-4477-9745-080b6cbdc751
author: rothja
ms.author: jroth
ms.openlocfilehash: f1f9b6a0c0668540b566c9b3d7ede781c97a1dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673670"
---
# <a name="sqlgetstmtattr"></a><span data-ttu-id="62508-102">SQLGetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="62508-102">SQLGetStmtAttr</span></span>
  <span data-ttu-id="62508-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client extiende SQLGetStmtAttr para exponer los atributos de instrucción específicos del controlador.</span><span class="sxs-lookup"><span data-stu-id="62508-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver extends SQLGetStmtAttr to expose driver-specific statement attributes.</span></span>  
  
 <span data-ttu-id="62508-104">[SQLSetStmtAttr](sqlsetstmtattr.md) enumera los atributos de instrucción de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="62508-104">[SQLSetStmtAttr](sqlsetstmtattr.md) lists statement attributes that are both read and write.</span></span> <span data-ttu-id="62508-105">En este tema se enumeran los atributos de instrucción de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="62508-105">This topic lists the read only statement attributes.</span></span>  
  
## <a name="sql_sopt_ss_current_command"></a><span data-ttu-id="62508-106">SQL_SOPT_SS_CURRENT_COMMAND</span><span class="sxs-lookup"><span data-stu-id="62508-106">SQL_SOPT_SS_CURRENT_COMMAND</span></span>  
 <span data-ttu-id="62508-107">El atributo SQL_SOPT_SS_CURRENT_COMMAND expone el comando actual de un lote de comandos.</span><span class="sxs-lookup"><span data-stu-id="62508-107">The SQL_SOPT_SS_CURRENT_COMMAND attribute exposes the current command of a command batch.</span></span> <span data-ttu-id="62508-108">El retorno es un entero que especifica la ubicación del comando en el lote.</span><span class="sxs-lookup"><span data-stu-id="62508-108">The return is an integer that specifies the location of the command in the batch.</span></span> <span data-ttu-id="62508-109">El valor de *ValuePtr* es de tipo SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="62508-109">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
## <a name="sql_sopt_ss_nocount_status"></a><span data-ttu-id="62508-110">SQL_SOPT_SS_NOCOUNT_STATUS</span><span class="sxs-lookup"><span data-stu-id="62508-110">SQL_SOPT_SS_NOCOUNT_STATUS</span></span>  
 <span data-ttu-id="62508-111">El atributo SQL_SOPT_SS_NOCOUNT_STATUS indica el valor actual de la opción NOCOUNT, que controla si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] notifica los números de filas afectados por una instrucción cuando se llama a [SQLRowCount](sqlrowcount.md) .</span><span class="sxs-lookup"><span data-stu-id="62508-111">The SQL_SOPT_SS_NOCOUNT_STATUS attribute indicates the current setting of the NOCOUNT option, which controls whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reports the numbers of rows affected by a statement when [SQLRowCount](sqlrowcount.md) is called.</span></span> <span data-ttu-id="62508-112">El valor de *ValuePtr* es de tipo SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="62508-112">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
|<span data-ttu-id="62508-113">Value</span><span class="sxs-lookup"><span data-stu-id="62508-113">Value</span></span>|<span data-ttu-id="62508-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="62508-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="62508-115">SQL_NC_OFF</span><span class="sxs-lookup"><span data-stu-id="62508-115">SQL_NC_OFF</span></span>|<span data-ttu-id="62508-116">NOCOUNT es OFF.</span><span class="sxs-lookup"><span data-stu-id="62508-116">NOCOUNT is OFF.</span></span> <span data-ttu-id="62508-117">SQLRowCount devuelve el número de filas afectadas.</span><span class="sxs-lookup"><span data-stu-id="62508-117">SQLRowCount returns number of rows affected.</span></span>|  
|<span data-ttu-id="62508-118">SQL_NC_ON</span><span class="sxs-lookup"><span data-stu-id="62508-118">SQL_NC_ON</span></span>|<span data-ttu-id="62508-119">NOCOUNT es ON.</span><span class="sxs-lookup"><span data-stu-id="62508-119">NOCOUNT is ON.</span></span> <span data-ttu-id="62508-120">SQLRowCount no devuelve el número de filas afectadas y el valor devuelto es 0.</span><span class="sxs-lookup"><span data-stu-id="62508-120">The number of rows affected is not returned by SQLRowCount and the returned value is 0.</span></span>|  
  
 <span data-ttu-id="62508-121">Si SQLRowCount devuelve 0, la aplicación debe probar SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="62508-121">If SQLRowCount returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="62508-122">Si se devuelve SQL_NC_ON, el valor 0 de SQLRowCount solo indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no ha devuelto un recuento de filas.</span><span class="sxs-lookup"><span data-stu-id="62508-122">If SQL_NC_ON is returned, the value of 0 from SQLRowCount only indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has not returned a row count.</span></span> <span data-ttu-id="62508-123">Si devuelve SQL_NC_OFF, significa que NOCOUNT está desactivado y el valor de 0 en SQLRowCount indica que la instrucción no afectó a ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="62508-123">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from SQLRowCount indicates that the statement did not affect any rows.</span></span>  
  
 <span data-ttu-id="62508-124">Las aplicaciones no deben mostrar el valor de SQLRowCount cuando SQL_SOPT_SS_NOCOUNT_STATUS es SQL_NC_OFF.</span><span class="sxs-lookup"><span data-stu-id="62508-124">Applications should not display the value of SQLRowCount when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="62508-125">Los lotes o los procedimientos almacenados grandes pueden contener varias instrucciones SET NOCOUNT, así que no se puede asumir que SQL_SOPT_SS_NOCOUNT_STATUS permanezca constante.</span><span class="sxs-lookup"><span data-stu-id="62508-125">Large batches or stored procedures can contain multiple SET NOCOUNT statements, so it cannot be assumed that SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="62508-126">Esta opción debe probarse cada vez que SQLRowCount devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="62508-126">This option should be tested each time SQLRowCount returns 0.</span></span>  
  
## <a name="sql_sopt_ss_querynotification_msgtext"></a><span data-ttu-id="62508-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span><span class="sxs-lookup"><span data-stu-id="62508-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span></span>  
 <span data-ttu-id="62508-128">El atributo SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT devuelve el texto del mensaje de la solicitud de notificación de consulta.</span><span class="sxs-lookup"><span data-stu-id="62508-128">The SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT attribute returns the message text for the query notification request.</span></span>  
  
## <a name="sqlgetstmtattr-and-table-valued-parameters"></a><span data-ttu-id="62508-129">SQLGetStmtAttr y los parámetros de valores de tabla</span><span class="sxs-lookup"><span data-stu-id="62508-129">SQLGetStmtAttr and Table-valued Parameters</span></span>  
 <span data-ttu-id="62508-130">Se puede llamar a SQLGetStmtAttr para obtener el valor de SQL_SOPT_SS_PARAM_FOCUS en el descriptor de parámetros de la aplicación (APD) cuando se trabaja con parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="62508-130">SQLGetStmtAttr can be called to get the value of SQL_SOPT_SS_PARAM_FOCUS in the application parameter descriptor (APD) when working with table-valued parameters.</span></span> <span data-ttu-id="62508-131">Para obtener más información sobre SQL_SOPT_SS_PARAM_FOCUS, vea [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="62508-131">For more information on SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="62508-132">Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="62508-132">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62508-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62508-133">See Also</span></span>  
 <span data-ttu-id="62508-134">[SQLSetStmtAttr función)](https://go.microsoft.com/fwlink/?LinkId=59370) </span><span class="sxs-lookup"><span data-stu-id="62508-134">[SQLSetStmtAttr Function](https://go.microsoft.com/fwlink/?LinkId=59370) </span></span>  
 [<span data-ttu-id="62508-135">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="62508-135">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
