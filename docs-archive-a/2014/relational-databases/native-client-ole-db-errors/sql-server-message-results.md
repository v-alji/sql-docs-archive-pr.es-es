---
title: Resultados de mensajes de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], SQL Server message results
- OLE DB error handling, SQL Server message results
ms.assetid: 6663c6f9-def1-4d9e-845b-2085e5efc401
author: rothja
ms.author: jroth
ms.openlocfilehash: aa63445b81ec89b87523fa29c50817e128d48515
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675832"
---
# <a name="sql-server-message-results"></a><span data-ttu-id="f12a7-102">Resultados de los mensajes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f12a7-102">SQL Server Message Results</span></span>
  <span data-ttu-id="f12a7-103">Las [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucciones siguientes no generan [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjuntos de filas de proveedor de OLE DB de cliente nativo ni un recuento de las filas afectadas cuando se ejecutan:</span><span class="sxs-lookup"><span data-stu-id="f12a7-103">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements do not generate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets or a count of affected rows when executed:</span></span>  
  
-   <span data-ttu-id="f12a7-104">PRINT</span><span class="sxs-lookup"><span data-stu-id="f12a7-104">PRINT</span></span>  
  
-   <span data-ttu-id="f12a7-105">RAISERROR con una gravedad de 10 o inferior</span><span class="sxs-lookup"><span data-stu-id="f12a7-105">RAISERROR with a severity of 10 or lower</span></span>  
  
-   <span data-ttu-id="f12a7-106">DBCC</span><span class="sxs-lookup"><span data-stu-id="f12a7-106">DBCC</span></span>  
  
-   <span data-ttu-id="f12a7-107">SET SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="f12a7-107">SET SHOWPLAN</span></span>  
  
-   <span data-ttu-id="f12a7-108">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="f12a7-108">SET STATISTICS</span></span>  
  
 <span data-ttu-id="f12a7-109">Estas instrucciones devuelven uno o varios mensajes informativos o hacen que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devuelva mensajes informativos en lugar de resultados de conjunto de filas o de recuento.</span><span class="sxs-lookup"><span data-stu-id="f12a7-109">These statements either return one or more informational messages or cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to return informational messages in place of rowset or count results.</span></span> <span data-ttu-id="f12a7-110">Al ejecutarse correctamente, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client devuelve S_OK y los mensajes están disponibles para el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor del proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="f12a7-110">On successful execution, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK, and the messages are available to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer.</span></span>  
  
 <span data-ttu-id="f12a7-111">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client devuelve S_OK y tiene uno o más mensajes informativos disponibles después de la ejecución de muchas [!INCLUDE[tsql](../../includes/tsql-md.md)] instrucciones o la ejecución del consumidor de una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] función miembro de proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="f12a7-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns S_OK and has one or more informational messages available following the execution of many [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or the consumer execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function.</span></span>  
  
 <span data-ttu-id="f12a7-112">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor del proveedor de OLE DB de Native Client que permite la especificación dinámica del texto de la consulta debe comprobar las interfaces de error después de cada ejecución de función miembro independientemente del valor del código de retorno, la presencia o ausencia de una referencia de interfaz **IRowset** o **IMultipleResults** devuelta, o un recuento de filas afectadas.</span><span class="sxs-lookup"><span data-stu-id="f12a7-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer allowing dynamic specification of query text should check error interfaces after every member function execution regardless of the value of the return code, the presence or absence of a returned **IRowset** or **IMultipleResults** interface reference, or a count of affected rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f12a7-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f12a7-113">See Also</span></span>  
 [<span data-ttu-id="f12a7-114">Errores</span><span class="sxs-lookup"><span data-stu-id="f12a7-114">Errors</span></span>](errors.md)  
  
  
