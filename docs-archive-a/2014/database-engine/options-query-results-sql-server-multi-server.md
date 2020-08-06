---
title: Opciones (resultados de la consulta-SQL Server-multiservidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.multiserverresultssettings
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLMultiServerResults
ms.assetid: d6768bd8-9cb5-4606-a726-a33a1df9e1bb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8273ad5edc65dd7351533209e9fa670c49f75f7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748245"
---
# <a name="options-query-results-sql-server-multi-server"></a><span data-ttu-id="0335d-102">Opciones (Resultados de la consulta/SQL Server/Multiservidor)</span><span class="sxs-lookup"><span data-stu-id="0335d-102">Options (Query Results-SQL Server-Multi-Server)</span></span>
  <span data-ttu-id="0335d-103">Cuando esté consultando varios servidores al mismo tiempo, utilice esta página para especificar las opciones para mostrar los conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="0335d-103">When you are querying multiple servers at the same time, use this page to specify the options for displaying result sets.</span></span> <span data-ttu-id="0335d-104">Mezclar resultados combina los conjuntos de resultados de todos los servidores en un conjunto de resultados único.</span><span class="sxs-lookup"><span data-stu-id="0335d-104">Merge results combines the result sets from all servers into a single result set.</span></span> <span data-ttu-id="0335d-105">Cuando se mezclan resultados, el primer servidor en responder establece el esquema para el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="0335d-105">When merging results, the first server to respond sets the schema for the result set.</span></span> <span data-ttu-id="0335d-106">Para mezclar los conjuntos de resultados, la consulta debe devolver el mismo número de columnas con los mismos nombres de columna de cada servidor.</span><span class="sxs-lookup"><span data-stu-id="0335d-106">To merge the result sets, the query must return the same number of columns with the same column names from each server.</span></span> <span data-ttu-id="0335d-107">Cuando se mezclan resultados, se muestra un mensaje para cada servidor que no coincide con el esquema (recuento de columna y nombres de columna) que es devuelto por el primer servidor que devuelve resultados.</span><span class="sxs-lookup"><span data-stu-id="0335d-107">When merging results, a message is displayed for each server that does not match the schema (column count and column names) that is returned by the first server to return results.</span></span>  
  
 <span data-ttu-id="0335d-108">Cuando no se mezclan resultados, el conjunto de resultados de cada servidor se mostrará en su propia cuadrícula con su propio esquema.</span><span class="sxs-lookup"><span data-stu-id="0335d-108">When you do not merge results, the result set from each server will be displayed in its own grid with its own schema.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="0335d-109">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="0335d-109">UI element list</span></span>  
 <span data-ttu-id="0335d-110">**Mezclar resultados**</span><span class="sxs-lookup"><span data-stu-id="0335d-110">**Merge results**</span></span>  
 <span data-ttu-id="0335d-111">Active esta casilla para combinar los conjuntos de resultados de varios servidores en la misma cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0335d-111">Select this check box to combine the result sets from several servers into the same grid.</span></span>  
  
 <span data-ttu-id="0335d-112">**Agregar nombre de servidor a los resultados**</span><span class="sxs-lookup"><span data-stu-id="0335d-112">**Add server name to the results**</span></span>  
 <span data-ttu-id="0335d-113">Active esta casilla para incluir una columna adicional que proporcione el nombre del servidor que generó cada fila.</span><span class="sxs-lookup"><span data-stu-id="0335d-113">Select this check box to include an additional column that provides the name of the server that produced each row.</span></span>  
  
 <span data-ttu-id="0335d-114">**Agregar nombre de inicio de sesión a los resultados**</span><span class="sxs-lookup"><span data-stu-id="0335d-114">**Add login name to the results**</span></span>  
 <span data-ttu-id="0335d-115">Active esta casilla para incluir una columna adicional que proporcione el inicio de sesión que se utilizó para conectarse al servidor que proporcionó cada fila.</span><span class="sxs-lookup"><span data-stu-id="0335d-115">Select this check box to include an additional column that provides the login that was used to connect to the server that provided each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0335d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0335d-116">See Also</span></span>  
 <span data-ttu-id="0335d-117">[Cree un servidor de administración central y un grupo de servidores &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span><span class="sxs-lookup"><span data-stu-id="0335d-117">[Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span></span>  
 [<span data-ttu-id="0335d-118">Ejecutar instrucciones con varios servidores simultáneamente &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0335d-118">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/execute-statements-against-multiple-servers-simultaneously.md)  
  
  
