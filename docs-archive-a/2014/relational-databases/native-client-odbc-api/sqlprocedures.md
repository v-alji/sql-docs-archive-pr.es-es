---
title: SQLProcedures | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLProcedures function
ms.assetid: ec41f017-f5e0-40ef-913a-65d206068631
author: rothja
ms.author: jroth
ms.openlocfilehash: e37f15841a36eb95c1e9263d137ba2734d622367
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677054"
---
# <a name="sqlprocedures"></a><span data-ttu-id="cbf77-102">SQLProcedures</span><span class="sxs-lookup"><span data-stu-id="cbf77-102">SQLProcedures</span></span>
  <span data-ttu-id="cbf77-103">Todos los procedimientos almacenados de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="cbf77-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return a value.</span></span> <span data-ttu-id="cbf77-104">**SQLProcedures** informa SQL_PT_FUNCTION para la columna del conjunto de resultados PROCEDURE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="cbf77-104">**SQLProcedures** reports SQL_PT_FUNCTION for the result set column PROCEDURE_TYPE.</span></span>  
  
 <span data-ttu-id="cbf77-105">**SQLProcedures** devuelve SQL_SUCCESS si existen o no valores para los parámetros *nombrecatálogo, SchemaName* o *NombreProc* .</span><span class="sxs-lookup"><span data-stu-id="cbf77-105">**SQLProcedures** returns SQL_SUCCESS whether or not values exist for *CatalogName, SchemaName,* or *ProcName* parameters.</span></span> <span data-ttu-id="cbf77-106">**SQLFetch** devuelve SQL_NO_DATA si se usan valores no válidos en estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="cbf77-106">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="cbf77-107">**SQLProcedures** se puede ejecutar en un cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="cbf77-107">**SQLProcedures** can be executed on a static server cursor.</span></span> <span data-ttu-id="cbf77-108">Un intento de ejecutar **SQLProcedures** en un cursor actualizable (dinámico o de conjunto de claves) devolverá SQL_SUCCESS_WITH_INFO, lo que indica que se ha cambiado el tipo de cursor.</span><span class="sxs-lookup"><span data-stu-id="cbf77-108">An attempt to execute **SQLProcedures** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO, indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="cbf77-109">**SQLProcedures** devuelve información sobre los procedimientos cuyos nombres coinciden con *NombreProc* y que el usuario actual puede ejecutar o para los que el usuario actual tiene el permiso View definition.</span><span class="sxs-lookup"><span data-stu-id="cbf77-109">**SQLProcedures** returns information about any procedures whose names match *ProcName* and can be executed by the current user, or for which the current user has been granted VIEW DEFINITION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf77-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbf77-110">See Also</span></span>  
 <span data-ttu-id="cbf77-111">[SQLProcedures función)](https://go.microsoft.com/fwlink/?LinkId=59364) </span><span class="sxs-lookup"><span data-stu-id="cbf77-111">[SQLProcedures Function](https://go.microsoft.com/fwlink/?LinkId=59364) </span></span>  
 [<span data-ttu-id="cbf77-112">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="cbf77-112">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
