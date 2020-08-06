---
title: Comandos que generan resultados de varios conjuntos de filas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- multiple rowsets
- rowsets [OLE DB], multiple
- SQL Server Native Client OLE DB provider, commands
- SQL Server Native Client OLE DB provider, multiple rowsets
- commands [OLE DB]
- multiple-rowset results
ms.assetid: 4567668d-35fd-4162-b61f-f7536862cdcb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b42a89c0b043e4c72e8b5634cf70e16b435167a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744074"
---
# <a name="commands-generating-multiple-rowset-results"></a><span data-ttu-id="43d48-102">Comandos que generan resultados de varios conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="43d48-102">Commands Generating Multiple-Rowset Results</span></span>
  <span data-ttu-id="43d48-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client puede devolver varios conjuntos de filas a partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instrucciones.</span><span class="sxs-lookup"><span data-stu-id="43d48-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can return multiple rowsets from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements.</span></span> <span data-ttu-id="43d48-104">Las instrucciones [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devuelven resultados de varios conjuntos de filas si se dan las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="43d48-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements return multiple-rowset results under the following conditions:</span></span>  
  
-   <span data-ttu-id="43d48-105">Las instrucciones SQL por lotes se envían como un comando único.</span><span class="sxs-lookup"><span data-stu-id="43d48-105">Batched SQL statements are submitted as a single command.</span></span>  
  
-   <span data-ttu-id="43d48-106">Los procedimientos almacenados implementan un lote de instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="43d48-106">Stored procedures implement a batch of SQL statements.</span></span>  
  
## <a name="batches"></a><span data-ttu-id="43d48-107">Instancias de Batch</span><span class="sxs-lookup"><span data-stu-id="43d48-107">Batches</span></span>  
 <span data-ttu-id="43d48-108">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client reconoce el carácter de punto y coma como un delimitador de lotes para las instrucciones SQL:</span><span class="sxs-lookup"><span data-stu-id="43d48-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes the semicolon character as a batch delimiter for SQL statements:</span></span>  
  
```  
WCHAR*       wSQLString = L"SELECT * FROM Categories; "  
                          L"SELECT * FROM Products";  
```  
  
 <span data-ttu-id="43d48-109">El envío de varias instrucciones SQL en un lote es más eficaz que la ejecución de cada instrucción SQL por separado.</span><span class="sxs-lookup"><span data-stu-id="43d48-109">Sending multiple SQL statements in one batch is more efficient than executing each SQL statement separately.</span></span> <span data-ttu-id="43d48-110">Al enviar un lote, se reducen los viajes de ida y vuelta (round trip) del cliente al servidor en la red.</span><span class="sxs-lookup"><span data-stu-id="43d48-110">Sending one batch reduces the network round trips from the client to the server.</span></span>  
  
## <a name="stored-procedures"></a><span data-ttu-id="43d48-111">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="43d48-111">Stored Procedures</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="43d48-112">devuelve un conjunto de resultados para cada instrucción de un procedimiento almacenado, por lo que la mayoría de los procedimientos almacenados de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devuelven varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="43d48-112">returns a result set for each statement in a stored procedure, so most [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return multiple result sets.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43d48-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="43d48-113">In This Section</span></span>  
  
-   [<span data-ttu-id="43d48-114">Utilizar IMultipleResults para procesar varios conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="43d48-114">Using IMultipleResults to Process Multiple Result Sets</span></span>](using-imultipleresults-to-process-multiple-result-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="43d48-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43d48-115">See Also</span></span>  
 [<span data-ttu-id="43d48-116">Comandos</span><span class="sxs-lookup"><span data-stu-id="43d48-116">Commands</span></span>](commands.md)  
  
  
