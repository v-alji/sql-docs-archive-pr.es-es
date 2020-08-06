---
title: SQLExecDirect | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLExecDirect function
ms.assetid: e7c2a5b5-83f4-4c72-9aca-7b9fb4748b11
author: rothja
ms.author: jroth
ms.openlocfilehash: 68188506546e7b4a5dd4c05bc9a94cbf34300001
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671987"
---
# <a name="sqlexecdirect"></a>SQLExecDirect
  Si el atributo de instrucción SQL_SOPT_SS_PARAM_FOCUS no es 0, SQLExecDirect devolverá SQL_ERROR y generará un registro de diagnóstico con SQLSTATE = HY024 y el mensaje "valor de atributo no válido SQL_SOPT_SS_PARAM_FOCUS (debe ser cero en tiempo de ejecución)". Para obtener más información acerca de SQL_SOPT_SS_PARAM_FOCUS, vea [SQLSetStmtAttr](sqlsetstmtattr.md).  
  
 Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).  
  
## <a name="see-also"></a>Consulte también  
 [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=80709)   
 [ODBC API Implementation Details](odbc-api-implementation-details.md)  
  
  
