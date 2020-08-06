---
title: bcp_batch | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_batch
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_batch function
ms.assetid: 0bda489e-86bc-4a7e-80f6-96047e03f281
author: rothja
ms.author: jroth
ms.openlocfilehash: 24cdf6e2934c2b80a55d8fa1fcc572a976b636ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672932"
---
# <a name="bcp_batch"></a><span data-ttu-id="7dc05-102">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="7dc05-102">bcp_batch</span></span>
  <span data-ttu-id="7dc05-103">Confirma todas las filas previamente copiadas de forma masiva desde variables de programa y enviadas a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a través de [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="7dc05-103">Commits all rows previously bulk copied from program variables and sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dc05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dc05-104">Syntax</span></span>  
  
```  
  
DBINT bcp_batch (HDBC  
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="7dc05-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7dc05-105">Arguments</span></span>  
 <span data-ttu-id="7dc05-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="7dc05-106">*hdbc*</span></span>  
 <span data-ttu-id="7dc05-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="7dc05-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7dc05-108">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="7dc05-108">Returns</span></span>  
 <span data-ttu-id="7dc05-109">El número de filas guardado después de la última llamada a **bcp_batch**, o-1 en caso de error.</span><span class="sxs-lookup"><span data-stu-id="7dc05-109">The number of rows saved after the last call to **bcp_batch**, or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dc05-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7dc05-110">Remarks</span></span>  
 <span data-ttu-id="7dc05-111">Los lotes de copia masiva definen las transacciones.</span><span class="sxs-lookup"><span data-stu-id="7dc05-111">Bulk copy batches define transactions.</span></span> <span data-ttu-id="7dc05-112">Cuando una aplicación usa [bcp_bind](bcp-bind.md) y **bcp_sendrow** para copiar filas de forma masiva de variables de programa a las tablas de SQL Server, las filas solo se confirman cuando el programa llama a **bcp_batch** o a [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="7dc05-112">When an application uses [bcp_bind](bcp-bind.md) and **bcp_sendrow** to bulk copy rows from program variables to SQL Server tables, the rows are committed only when the program calls **bcp_batch** or [bcp_done](bcp-done.md).</span></span>  
  
 <span data-ttu-id="7dc05-113">Puede llamar a **bcp_batch** una vez cada *n* filas o cuando se produzcan períodos de inactividad en la entrada de datos (como en una aplicación de telemetría).</span><span class="sxs-lookup"><span data-stu-id="7dc05-113">You can call **bcp_batch** once every *n* rows or when there is a lull in incoming data (as in a telemetry application).</span></span> <span data-ttu-id="7dc05-114">Si una aplicación no llama a **bcp_batch** , las filas copiadas de forma masiva solo se confirmarán cuando se llame a **bcp_done** .</span><span class="sxs-lookup"><span data-stu-id="7dc05-114">If an application does not call **bcp_batch** the bulk copied rows are committed only when **bcp_done** is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc05-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7dc05-115">See Also</span></span>  
 [<span data-ttu-id="7dc05-116">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="7dc05-116">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
