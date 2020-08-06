---
title: SQLParamData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLParamData function
ms.assetid: 92349482-ea22-4a6a-8484-e9c6566794fa
author: rothja
ms.author: jroth
ms.openlocfilehash: a4e0e8b31a65f28ce83e0d114231bdedd7a35a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677057"
---
# <a name="sqlparamdata"></a><span data-ttu-id="339e2-102">SQLParamData</span><span class="sxs-lookup"><span data-stu-id="339e2-102">SQLParamData</span></span>
  <span data-ttu-id="339e2-103">Cuando SQLParamData devuelve el *ValuePtrPtr* asociado a un parámetro con valores de tabla, la aplicación debe llamar a SQLPutData con *StrLen_Or_Ind*.</span><span class="sxs-lookup"><span data-stu-id="339e2-103">When SQLParamData returns the *ValuePtrPtr* associated with a table-valued parameter, the application should call SQLPutData with *StrLen_Or_Ind*.</span></span> <span data-ttu-id="339e2-104">Si *StrLen_Or_Ind* tiene un valor mayor que 0, significa que la aplicación está lista para que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client recopile los datos de parámetro para la siguiente fila de parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="339e2-104">If *StrLen_Or_Ind* has a value greater than 0, it means that the application is ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to gather parameter data for the next table-valued parameter row.</span></span> <span data-ttu-id="339e2-105">Si *StrLen_Or_Ind* tiene un valor de 0, significa que no hay más filas de datos para el parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="339e2-105">If *StrLen_Or_Ind* has a value of 0, it means there are no more rows of data for the table-valued parameter.</span></span> <span data-ttu-id="339e2-106">Para obtener más información, vea [enlazar y transferencia de datos de parámetros con valores de tabla y valores de columna](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="339e2-106">For more information, see [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="339e2-107">Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="339e2-107">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="339e2-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="339e2-108">See Also</span></span>  
 <span data-ttu-id="339e2-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span><span class="sxs-lookup"><span data-stu-id="339e2-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span></span>  
 [<span data-ttu-id="339e2-110">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="339e2-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
