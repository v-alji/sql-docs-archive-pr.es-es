---
title: Metadatos de parámetros con valores de tabla para instrucciones preparadas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), metadata for prepared statements
ms.assetid: fd2fc705-2e98-4011-9822-c7e6cca4a535
author: rothja
ms.author: jroth
ms.openlocfilehash: ad1394bd5e5bedc69a98308ba67a98434559c146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750842"
---
# <a name="table-valued-parameter-metadata-for-prepared-statements"></a><span data-ttu-id="4d2ef-102">Metadatos de parámetros con valores de tabla para instrucciones preparadas</span><span class="sxs-lookup"><span data-stu-id="4d2ef-102">Table-Valued Parameter Metadata for Prepared Statements</span></span>
  <span data-ttu-id="4d2ef-103">Una aplicación puede obtener metadatos para una llamada a procedimiento preparada a través de SQLNumParams y SQLDescribeParam.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-103">An application can obtain metadata for a prepared procedure call through SQLNumParams and SQLDescribeParam.</span></span> <span data-ttu-id="4d2ef-104">En el caso de los parámetros con valores de tabla, *DataTypePtr* se establece en SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-104">For table-valued parameters, *DataTypePtr* is set to SQL_SS_TABLE.</span></span> <span data-ttu-id="4d2ef-105">Los metadatos adicionales están disponibles a través de SQLGetDescField para SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME y SQL_CA_SS_SCHEMA_NAME.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-105">Additional metadata is available through SQLGetDescField for SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME.</span></span>  
  
 <span data-ttu-id="4d2ef-106">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME y SQL_CA_SS_SCHEMA_NAME se pueden usar con SQLColumns para obtener los metadatos de columna para los tipos de tabla asociados a los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-106">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME can be used with SQLColumns to obtain column metadata for table types associated with table-valued parameters.</span></span> <span data-ttu-id="4d2ef-107">En este caso, SQL_SOPT_SS_NAME_SCOPE debe establecerse en SQL_SS_NAME_SCOPE_TABLE_TYPE antes de que se llame a SQLColumns.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-107">In this case, SQL_SOPT_SS_NAME_SCOPE must be set to SQL_SS_NAME_SCOPE_TABLE_TYPE before SQLColumns is called.</span></span> <span data-ttu-id="4d2ef-108">A continuación, SQL_SOPT_SS_NAME_SCOPE se debe volver a establecer en el valor predeterminado, SQL_SS_NAME_SCOPE_TABLE, cuando la aplicación haya terminado de recuperar los metadatos de columnas de parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-108">SQL_SOPT_SS_NAME_SCOPE should then be set back to the default value, SQL_SS_NAME_SCOPE_TABLE, when the application has finished retrieving table-valued parameter column metadata.</span></span>  
  
 <span data-ttu-id="4d2ef-109">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME y SQL_CA_SS_SCHEMA_NAME se pueden usar también con parámetros de tipos definidos por el usuario de CLR.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-109">SQL_CA_SS_TYPE_NAME , SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME can also be used with CLR user-defined type parameters.</span></span>  
  
 <span data-ttu-id="4d2ef-110">No puede obtener metadatos de parámetros con valores de tabla para instrucciones preparadas que no sean llamadas a procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-110">You cannot obtain table-valued parameter metadata for prepared statements that are not stored procedure calls.</span></span> <span data-ttu-id="4d2ef-111">Si lo intenta, la aplicación devuelve SQL_ERROR con SQLSTATE 42000 y el mensaje "error de sintaxis o infracción de acceso".</span><span class="sxs-lookup"><span data-stu-id="4d2ef-111">If you try to do this, the application returns SQL_ERROR with SQLSTATE 42000 and the message "Syntax error or access violation".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d2ef-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d2ef-112">See Also</span></span>  
 [<span data-ttu-id="4d2ef-113">Parámetros con valores de tabla &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4d2ef-113">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
