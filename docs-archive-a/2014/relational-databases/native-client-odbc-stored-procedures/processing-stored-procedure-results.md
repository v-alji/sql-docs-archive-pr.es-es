---
title: Procesando resultados de procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], results
ms.assetid: 788ef2a4-17de-4526-960b-46bf29aafc9f
author: rothja
ms.author: jroth
ms.openlocfilehash: 5f37a6d8beff88748fa944293bd67f449d29eff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750854"
---
# <a name="processing-stored-procedure-results"></a><span data-ttu-id="d3d28-102">Procesar resultados de procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="d3d28-102">Processing Stored Procedure Results</span></span>
  <span data-ttu-id="d3d28-103">Los procedimientos almacenados de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tienen cuatro mecanismos que se utilizan para devolver datos:</span><span class="sxs-lookup"><span data-stu-id="d3d28-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures have four mechanisms used to return data:</span></span>  
  
-   <span data-ttu-id="d3d28-104">Cada instrucción SELECT del procedimiento genera un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="d3d28-104">Each SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="d3d28-105">El procedimiento puede devolver datos mediante parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="d3d28-105">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="d3d28-106">Un parámetro de salida del cursor puede devolver un cursor de servidor [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3d28-106">A cursor output parameter can pass back a [!INCLUDE[tsql](../../includes/tsql-md.md)] server cursor.</span></span>  
  
-   <span data-ttu-id="d3d28-107">El procedimiento puede tener un código de retorno de tipo entero.</span><span class="sxs-lookup"><span data-stu-id="d3d28-107">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="d3d28-108">Las aplicaciones deben ser capaces de administrar todos estos resultados de los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="d3d28-108">Applications must be able to handle all these outputs from stored procedures.</span></span> <span data-ttu-id="d3d28-109">La instrucción CALL o EXECUTE debería incluir los marcadores de parámetros para el código de retorno y los parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="d3d28-109">The CALL or EXECUTE statement should include parameter markers for the return code and output parameters.</span></span> <span data-ttu-id="d3d28-110">Utilice [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) para enlazarlos todos como parámetros de salida y el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client transferirá los valores de salida a las variables enlazadas.</span><span class="sxs-lookup"><span data-stu-id="d3d28-110">Use [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) to bind them all as output parameters and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will transfer the output values to the bound variables.</span></span> <span data-ttu-id="d3d28-111">Los parámetros de salida y los códigos de retorno son los últimos elementos devueltos por el cliente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; no se devuelven a la aplicación hasta que [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) devuelve SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="d3d28-111">Output parameters and return codes are the last items returned to the client by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they are not returned to the application until [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="d3d28-112">ODBC no permite enlazar parámetros de cursor [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3d28-112">ODBC does not support binding [!INCLUDE[tsql](../../includes/tsql-md.md)] cursor parameters.</span></span> <span data-ttu-id="d3d28-113">Puesto que todos los parámetros de salida se deben enlazar antes de ejecutar un procedimiento, las aplicaciones ODBC no pueden llamar a ningún procedimiento almacenado [!INCLUDE[tsql](../../includes/tsql-md.md)] que contenga un parámetro de cursor de salida.</span><span class="sxs-lookup"><span data-stu-id="d3d28-113">Because all output parameters must be bound before executing a procedure, any [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure that contains an output cursor parameter cannot be called by ODBC applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d28-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3d28-114">See Also</span></span>  
 [<span data-ttu-id="d3d28-115">Ejecutar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="d3d28-115">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
