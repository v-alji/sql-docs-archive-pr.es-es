---
title: SQLColumnPrivileges | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLColumnPrivileges function
ms.assetid: c78acd4e-8668-4abc-9bc9-6ad381965863
author: rothja
ms.author: jroth
ms.openlocfilehash: bf46fed47817ed94ea2382f2147df254f2986aec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669674"
---
# <a name="sqlcolumnprivileges"></a><span data-ttu-id="feb14-102">SQLColumnPrivileges</span><span class="sxs-lookup"><span data-stu-id="feb14-102">SQLColumnPrivileges</span></span>
  <span data-ttu-id="feb14-103">**SQLColumnPrivileges** devuelve SQL_SUCCESS si existen o no valores para los parámetros*nombrecatálogo*, *SchemaName*, *TableName*o *columnName* .</span><span class="sxs-lookup"><span data-stu-id="feb14-103">**SQLColumnPrivileges** returns SQL_SUCCESS whether or not values exist for the*CatalogName*, *SchemaName*, *TableName*, or *ColumnName* parameters.</span></span> <span data-ttu-id="feb14-104">**SQLFetch** devuelve SQL_NO_DATA si se usan valores no válidos en estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="feb14-104">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="feb14-105">**SQLColumnPrivileges** se puede ejecutar en un cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="feb14-105">**SQLColumnPrivileges** can be executed on a static server cursor.</span></span> <span data-ttu-id="feb14-106">Un intento de ejecutar **SQLColumnPrivileges** en un cursor actualizable (dinámico o de conjunto de claves) devolverá SQL_SUCCESS_WITH_INFO que indica que se ha cambiado el tipo de cursor.</span><span class="sxs-lookup"><span data-stu-id="feb14-106">An attempt to execute **SQLColumnPrivileges** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="feb14-107">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client permite notificar información de tablas en servidores vinculados aceptando un nombre de dos partes para el parámetro *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="feb14-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb14-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="feb14-108">See Also</span></span>  
 <span data-ttu-id="feb14-109">[SQLColumnPrivileges función)](https://go.microsoft.com/fwlink/?LinkId=59335) </span><span class="sxs-lookup"><span data-stu-id="feb14-109">[SQLColumnPrivileges Function](https://go.microsoft.com/fwlink/?LinkId=59335) </span></span>  
 [<span data-ttu-id="feb14-110">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="feb14-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
