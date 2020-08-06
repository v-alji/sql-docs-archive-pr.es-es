---
title: SQLPrimaryKeys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPrimaryKeys function
ms.assetid: bc61cd5b-d2f4-4f87-abc7-743cf9ea772d
author: rothja
ms.author: jroth
ms.openlocfilehash: 67a932996ccbf52f5ab21fd6aa62381184ebc510
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677055"
---
# <a name="sqlprimarykeys"></a><span data-ttu-id="c1958-102">SQLPrimaryKeys</span><span class="sxs-lookup"><span data-stu-id="c1958-102">SQLPrimaryKeys</span></span>
  <span data-ttu-id="c1958-103">Una tabla puede tener una o varias columnas que pueden actuar como identificadores de fila únicos y las tablas creadas sin una restricción PRIMAry KEY devuelven un conjunto de resultados vacío a SQLPrimaryKeys.</span><span class="sxs-lookup"><span data-stu-id="c1958-103">A table might have a column or columns that can serve as unique row identifiers, and tables created without a PRIMARY KEY constraint return an empty result set to SQLPrimaryKeys.</span></span> <span data-ttu-id="c1958-104">La función ODBC [SQLSpecialColumns](sqlspecialcolumns.md) informa de los candidatos de identificador de fila para las tablas sin claves principales.</span><span class="sxs-lookup"><span data-stu-id="c1958-104">The ODBC function [SQLSpecialColumns](sqlspecialcolumns.md) reports row identifier candidates for tables without primary keys.</span></span>  
  
 <span data-ttu-id="c1958-105">SQLPrimaryKeys devuelve SQL_SUCCESS si existen o no valores para los parámetros *nombrecatálogo*, *SchemaName*o *TableName* .</span><span class="sxs-lookup"><span data-stu-id="c1958-105">SQLPrimaryKeys returns SQL_SUCCESS whether or not values exist for *CatalogName*, *SchemaName*, or *TableName* parameters.</span></span> <span data-ttu-id="c1958-106">SQLFetch devuelve SQL_NO_DATA si se usan valores no válidos en estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="c1958-106">SQLFetch returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="c1958-107">SQLPrimaryKeys se puede ejecutar en un cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="c1958-107">SQLPrimaryKeys can be executed on a static server cursor.</span></span> <span data-ttu-id="c1958-108">Un intento de ejecutar SQLPrimaryKeys en un cursor actualizable (dinámico o de conjunto de claves) devolverá SQL_SUCCESS_WITH_INFO que indica que se ha cambiado el tipo de cursor.</span><span class="sxs-lookup"><span data-stu-id="c1958-108">An attempt to execute SQLPrimaryKeys on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="c1958-109">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client permite notificar información de tablas en servidores vinculados aceptando un nombre de dos partes para el parámetro *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="c1958-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="sqlprimarykeys-and-table-valued-parameters"></a><span data-ttu-id="c1958-110">SQLPrimaryKeys y parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="c1958-110">SQLPrimaryKeys and Table-Valued Parameters</span></span>  
 <span data-ttu-id="c1958-111">Si el atributo de instrucción SQL_SOPT_SS_NAME_SCOPE tiene el valor SQL_SS_NAME_SCOPE_TABLE_TYPE, en lugar de su valor predeterminado de SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys devolverá información sobre las columnas de clave principal de los tipos de tabla.</span><span class="sxs-lookup"><span data-stu-id="c1958-111">If the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys will return information about primary key columns of table types.</span></span> <span data-ttu-id="c1958-112">Para obtener más información sobre SQL_SOPT_SS_NAME_SCOPE, vea [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="c1958-112">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="c1958-113">Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c1958-113">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1958-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1958-114">See Also</span></span>  
 <span data-ttu-id="c1958-115">[SQLPrimaryKeys función)](https://go.microsoft.com/fwlink/?LinkId=59361) </span><span class="sxs-lookup"><span data-stu-id="c1958-115">[SQLPrimaryKeys Function](https://go.microsoft.com/fwlink/?LinkId=59361) </span></span>  
 [<span data-ttu-id="c1958-116">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="c1958-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
