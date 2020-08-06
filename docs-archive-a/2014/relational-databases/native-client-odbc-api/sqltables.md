---
title: SQLTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTables function
ms.assetid: 77b6c15c-9cf7-4019-b3f0-3d27d23ef656
author: rothja
ms.author: jroth
ms.openlocfilehash: bad60aa102a7771935e37ac963e6fa0d3cb2fd57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672944"
---
# <a name="sqltables"></a><span data-ttu-id="45f27-102">SQLTables</span><span class="sxs-lookup"><span data-stu-id="45f27-102">SQLTables</span></span>
  <span data-ttu-id="45f27-103">SQLTables se puede ejecutar en un cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="45f27-103">SQLTables can be executed on a static server cursor.</span></span> <span data-ttu-id="45f27-104">Un intento de ejecutar SQLTables en un cursor actualizable (dinámico o conjunto de claves) devolverá SQL_SUCCESS_WITH_INFO que indica que se ha cambiado el tipo de cursor.</span><span class="sxs-lookup"><span data-stu-id="45f27-104">An attempt to execute SQLTables on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="45f27-105">SQLTables informa de las tablas de todas las bases de datos cuando el parámetro *nombrecatálogo* es SQL_ALL_CATALOGS y el resto de los parámetros contienen valores predeterminados (punteros NULL).</span><span class="sxs-lookup"><span data-stu-id="45f27-105">SQLTables reports tables from all databases when the *CatalogName* parameter is SQL_ALL_CATALOGS and all other parameters contain default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="45f27-106">Para notificar los catálogos, esquemas y tipos de tabla disponibles, SQLTables hace un uso especial de cadenas vacías (punteros de bytes de longitud cero).</span><span class="sxs-lookup"><span data-stu-id="45f27-106">To report available catalogs, schemas, and table types, SQLTables makes special use of empty strings (zero-length byte pointers).</span></span> <span data-ttu-id="45f27-107">Las cadenas vacías no son valores predeterminados (punteros NULL).</span><span class="sxs-lookup"><span data-stu-id="45f27-107">Empty strings are not default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="45f27-108">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client permite notificar información de tablas en servidores vinculados aceptando un nombre de dos partes para el parámetro *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="45f27-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
 <span data-ttu-id="45f27-109">SQLTables devuelve información acerca de las tablas cuyos nombres coinciden con *TableName* y son propiedad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="45f27-109">SQLTables returns information about any tables whose names match *TableName* and are owned by the current user.</span></span>  
  
## <a name="sqltables-and-table-valued-parameters"></a><span data-ttu-id="45f27-110">SQLTables y parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="45f27-110">SQLTables and Table-Valued Parameters</span></span>  
 <span data-ttu-id="45f27-111">Cuando el atributo de instrucción SQL_SOPT_SS_NAME_SCOPE tiene el valor SQL_SS_NAME_SCOPE_TABLE_TYPE, en lugar de su valor predeterminado de SQL_SS_NAME_SCOPE_TABLE, SQLTables devuelve información acerca de los tipos de tabla.</span><span class="sxs-lookup"><span data-stu-id="45f27-111">When the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLTables returns information about table types.</span></span> <span data-ttu-id="45f27-112">El TABLE_TYPE valor devuelto para un tipo de tabla en la columna 4 del conjunto de resultados devuelto por SQLTables es el tipo de tabla.</span><span class="sxs-lookup"><span data-stu-id="45f27-112">The TABLE_TYPE value returned for a table type in column 4 of the result set returned by SQLTables is TABLE TYPE.</span></span> <span data-ttu-id="45f27-113">Para obtener más información sobre SQL_SOPT_SS_NAME_SCOPE, vea [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="45f27-113">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="45f27-114">Las tablas, vistas y sinónimos comparten un espacio de nombres común que es distinto del espacio de nombres que utilizan los tipos de tabla.</span><span class="sxs-lookup"><span data-stu-id="45f27-114">Tables, views, and synonyms share a common namespace that is distinct from the namespace used by table types.</span></span> <span data-ttu-id="45f27-115">Aunque no es posible tener una tabla y una vista con el mismo nombre, sí se puede tener una tabla y un tipo de tabla con el mismo nombre en el mismo catálogo y esquema.</span><span class="sxs-lookup"><span data-stu-id="45f27-115">Although it is not possible to have a table and a view with the same name, it is possible to have a table and a table type with the same in the same catalog and schema.</span></span>  
  
 <span data-ttu-id="45f27-116">Para obtener más información sobre los parámetros con valores de tabla, vea [parámetros con valores de tabla &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="45f27-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45f27-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45f27-117">Example</span></span>  
  
```  
// Get a list of all tables in the current database.  
SQLTables(hstmt, NULL, 0, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of all tables in all databases.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of databases on the current connection's server.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, (SQLCHAR*)"", 0, (SQLCHAR*)"",  
    0, NULL, 0);  
```  
  
## <a name="see-also"></a><span data-ttu-id="45f27-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45f27-118">See Also</span></span>  
 <span data-ttu-id="45f27-119">[SQLTables (función)](https://go.microsoft.com/fwlink/?LinkId=59374) </span><span class="sxs-lookup"><span data-stu-id="45f27-119">[SQLTables Function](https://go.microsoft.com/fwlink/?LinkId=59374) </span></span>  
 [<span data-ttu-id="45f27-120">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="45f27-120">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
