---
title: ISSAbort::Abort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAbort::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: a5bca169-694b-4895-84ac-e8fba491e479
author: rothja
ms.author: jroth
ms.openlocfilehash: 3daad53087c876af8dc46bccc9c4bf7952976067
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746985"
---
# <a name="issabortabort-ole-db"></a><span data-ttu-id="22b0b-102">ISSAbort::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="22b0b-102">ISSAbort::Abort (OLE DB)</span></span>
  <span data-ttu-id="22b0b-103">Cancela el conjunto de filas actual y los comandos en lotes asociados al comando actual.</span><span class="sxs-lookup"><span data-stu-id="22b0b-103">Cancels the current rowset plus any batched commands associated with the current command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22b0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22b0b-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="22b0b-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="22b0b-105">Remarks</span></span>  
 <span data-ttu-id="22b0b-106">Si el comando que se anula se encuentra en un procedimiento almacenado, terminará la ejecución del procedimiento almacenado (y cualquier procedimiento que haya llamado a este procedimiento) así como del lote de comandos que contiene la llamada al procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="22b0b-106">If the command being aborted is in a stored procedure, execution of the stored procedure (and any procedures which had called that procedure) will be terminated as well as the command batch which contains the stored procedure call.</span></span> <span data-ttu-id="22b0b-107">Si el servidor está en proceso de transferir un conjunto de resultados al cliente, se detendrá.</span><span class="sxs-lookup"><span data-stu-id="22b0b-107">If the server is in the process of transferring a result set to the client, this will be stopped.</span></span> <span data-ttu-id="22b0b-108">Si el cliente no desea consumir un conjunto de resultados, la llamada a **ISSAbort::Abort** antes de liberar el conjunto de filas acelerará la liberación del conjunto de filas, pero si hay una transacción abierta y XACT_ABORT está establecido en ON, la transacción se revertirá al llamar a **ISSAbort::Abort** .</span><span class="sxs-lookup"><span data-stu-id="22b0b-108">If the client does not want to consume a result set, calling **ISSAbort::Abort** before releasing the rowset will speed up the rowset release, but if there is an open transaction and XACT_ABORT is ON, the transaction will be rolled back when **ISSAbort::Abort** is called</span></span>  
  
 <span data-ttu-id="22b0b-109">Después de que **ISSAbort::Abort** devuelva S_OK, la interfaz **IMultipleResults** asociada inicia un estado inutilizable y devuelve DB_E_CANCELED a todas las llamadas a método (excepto en los métodos que define la interfaz **IUNKNOWN** ) hasta que se libera.</span><span class="sxs-lookup"><span data-stu-id="22b0b-109">After **ISSAbort::Abort** returns S_OK, the associated **IMultipleResults** interface enters a unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface) until it is released.</span></span> <span data-ttu-id="22b0b-110">Si se ha obtenido una interfaz **IRowset** de **IMultipleResults** antes de una llamada a **Anular**, también inicia un estado inutilizable y devuelve DB_E_CANCELED a todas las llamadas a método (excepto en los métodos que define la interfaz **IUNKNOWN** e **IRowset::ReleaseRows**) hasta que se libera después de una llamada correcta a **ISSAbort::Abort**.</span><span class="sxs-lookup"><span data-stu-id="22b0b-110">If an **IRowset** had been obtained from **IMultipleResults** prior to a call to **Abort**, it also enters an unusable state and returns DB_E_CANCELED to all method calls (except for methods defined by the **IUnknown** interface and **IRowset::ReleaseRows**) until it is released after a successful call to **ISSAbort::Abort**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22b0b-111">A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], si el estado de servidor XACT_ABORT está establecido en ON, la ejecución de **ISSAbort::Abort** finalizará y revertirá cualquier transacción implícita o explícita actual al conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22b0b-111">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if the server XACT_ABORT state is ON, executing **ISSAbort::Abort** will terminate and roll back any current implicit or explicit transaction when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="22b0b-112">Las versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no anularán la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="22b0b-112">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not abort the current transaction.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="22b0b-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="22b0b-113">Arguments</span></span>  
 <span data-ttu-id="22b0b-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22b0b-114">None.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="22b0b-115">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="22b0b-115">Return Code Values</span></span>  
 <span data-ttu-id="22b0b-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="22b0b-116">S_OK</span></span>  
 <span data-ttu-id="22b0b-117">El método **ISSAbort::Abort** devuelve S_OK si el lote se ha cancelado y DB_E_CANTCANCEL de lo contrario.</span><span class="sxs-lookup"><span data-stu-id="22b0b-117">The **ISSAbort::Abort** method returns S_OK if the batch was canceled and DB_E_CANTCANCEL otherwise.</span></span> <span data-ttu-id="22b0b-118">Si el lote ya se había cancelado, se devuelve DB_E_CANCELED.</span><span class="sxs-lookup"><span data-stu-id="22b0b-118">If the batch has already been canceled, DB_E_CANCELED is returned.</span></span>  
  
 <span data-ttu-id="22b0b-119">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="22b0b-119">DB_E_CANCELED</span></span>  
 <span data-ttu-id="22b0b-120">El lote ya se ha cancelado.</span><span class="sxs-lookup"><span data-stu-id="22b0b-120">The batch has already been canceled.</span></span>  
  
 <span data-ttu-id="22b0b-121">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="22b0b-121">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="22b0b-122">El lote no se ha cancelado.</span><span class="sxs-lookup"><span data-stu-id="22b0b-122">The batch was not canceled.</span></span>  
  
 <span data-ttu-id="22b0b-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22b0b-123">E_FAIL</span></span>  
 <span data-ttu-id="22b0b-124">Se produjo un error específico del proveedor. para obtener información detallada, use la interfaz [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="22b0b-124">A provider specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="22b0b-125">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="22b0b-125">E_UNEXPECTED</span></span>  
 <span data-ttu-id="22b0b-126">No se esperaba la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="22b0b-126">The call to the method was unexpected.</span></span> <span data-ttu-id="22b0b-127">Por ejemplo, el objeto está en un estado zombi porque ya se ha llamado a **ISSAbort::Abort** .</span><span class="sxs-lookup"><span data-stu-id="22b0b-127">For example, the object is in a zombie state because **ISSAbort::Abort** has already been called.</span></span>  
  
 <span data-ttu-id="22b0b-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="22b0b-128">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="22b0b-129">Error de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="22b0b-129">Out of memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b0b-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22b0b-130">See Also</span></span>  
 [<span data-ttu-id="22b0b-131">ISSAbort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="22b0b-131">ISSAbort &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/issabort-ole-db.md)  
  
  
