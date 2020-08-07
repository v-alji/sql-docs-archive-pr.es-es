---
title: ISSAsynchStatus::Abort (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::Abort (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Abort method
ms.assetid: 2a4bd312-839a-45a8-a299-fc8609be9a2a
author: rothja
ms.author: jroth
ms.openlocfilehash: 0fb352b6541240126dcd4c60521b93d57d6839f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746983"
---
# <a name="issasynchstatusabort-ole-db"></a><span data-ttu-id="e7e1e-102">ISSAsynchStatus::Abort (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="e7e1e-102">ISSAsynchStatus::Abort (OLE DB)</span></span>
  <span data-ttu-id="e7e1e-103">Cancela una operación que se ejecuta de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-103">Cancels an asynchronously executing operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7e1e-104">Syntax</span></span>  
  
```  
  
HRESULT Abort(  
  HCHAPTER hChapter,  
  DBASYNCHOP eOperation);  
```  
  
## <a name="arguments"></a><span data-ttu-id="e7e1e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e7e1e-105">Arguments</span></span>  
 <span data-ttu-id="e7e1e-106">*hChapter*[in]</span><span class="sxs-lookup"><span data-stu-id="e7e1e-106">*hChapter*[in]</span></span>  
 <span data-ttu-id="e7e1e-107">El identificador del segmento para el que se anula la operación.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-107">The handle of the chapter for which to abort the operation.</span></span> <span data-ttu-id="e7e1e-108">Si el objeto al que se llama no es un objeto de conjunto de filas o la operación no se aplica a un segmento, el autor de las llamadas debe establecer *hChapter* en DB_NULL_HCHAPTER.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-108">If the object being called is not a rowset object or the operation does not apply to a chapter, the caller must set *hChapter* to DB_NULL_HCHAPTER.</span></span>  
  
 <span data-ttu-id="e7e1e-109">*eOperation*[in]</span><span class="sxs-lookup"><span data-stu-id="e7e1e-109">*eOperation*[in]</span></span>  
 <span data-ttu-id="e7e1e-110">Operación para anular.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-110">The operation to abort.</span></span> <span data-ttu-id="e7e1e-111">El valor debe ser el siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7e1e-111">This should be the following value:</span></span>  
  
 <span data-ttu-id="e7e1e-112">DBASYNCHOP_OPEN-La solicitud para cancelar se aplica a la apertura o rellenado asincrónico de un conjunto de filas o a la inicialización asincrónica de un objeto de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-112">DBASYNCHOP_OPEN-The request to cancel applies to the asynchronous opening or population of a rowset or to the asynchronous initialization of a data source object.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="e7e1e-113">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="e7e1e-113">Return Code Values</span></span>  
 <span data-ttu-id="e7e1e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7e1e-114">S_OK</span></span>  
 <span data-ttu-id="e7e1e-115">Se procesó la solicitud para cancelar la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-115">The request to cancel the asynchronous operation was processed.</span></span> <span data-ttu-id="e7e1e-116">Esto no garantiza que la operación en sí se haya cancelado.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-116">This does not guarantee that the operation itself was canceled.</span></span> <span data-ttu-id="e7e1e-117">Para determinar si se canceló la operación, el consumidor debería llamar a [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) y realizar una comprobación para DB_E_CANCELED; sin embargo, puede que no se devuelva en la llamada siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-117">To determine whether the operation was canceled, the consumer should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) and check for DB_E_CANCELED; however, it might not be returned in the very next call.</span></span>  
  
 <span data-ttu-id="e7e1e-118">DB_E_CANTCANCEL</span><span class="sxs-lookup"><span data-stu-id="e7e1e-118">DB_E_CANTCANCEL</span></span>  
 <span data-ttu-id="e7e1e-119">La operación asincrónica no puede cancelarse.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-119">The asynchronous operation cannot be canceled.</span></span>  
  
 <span data-ttu-id="e7e1e-120">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="e7e1e-120">DB_E_CANCELED</span></span>  
 <span data-ttu-id="e7e1e-121">La solicitud para anular la operación asincrónica se canceló durante las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-121">The request to abort the asynchronous operation was canceled during notifications.</span></span> <span data-ttu-id="e7e1e-122">La operación todavía se está ejecutando de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-122">The operation is still being executed asynchronously.</span></span>  
  
 <span data-ttu-id="e7e1e-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e7e1e-123">E_FAIL</span></span>  
 <span data-ttu-id="e7e1e-124">Se produjo un error específico del proveedor.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-124">A provider-specific error occurred.</span></span>  
  
 <span data-ttu-id="e7e1e-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e7e1e-125">E_INVALIDARG</span></span>  
 <span data-ttu-id="e7e1e-126">El parámetro *hChapter* no es DB_NULL_HCHAPTER, o *eOperation* no es DBASYNCH_OPEN.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-126">The *hChapter* parameter is not DB_NULL_HCHAPTER or *eOperation* is not DBASYNCH_OPEN.</span></span>  
  
 <span data-ttu-id="e7e1e-127">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="e7e1e-127">E_UNEXPECTED</span></span>  
 <span data-ttu-id="e7e1e-128">Se llamó a**ISSAsynchStatus::Abort** en un objeto de origen de datos en el que no se llamó a **IDBInitialize::Initialize** , o no se ha completado.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-128">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** has not been called, or has not completed.</span></span>  
  
 <span data-ttu-id="e7e1e-129">Se llamó a **ISSAsynchStatus:: ABORT** en un objeto de origen de datos en el que se llamó a **IDBInitialize:: Initialize** pero posteriormente se canceló antes de la inicialización o se agotó el tiempo de espera. Todavía no se ha inicializado el objeto de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-129">**ISSAsynchStatus::Abort** was called on a data source object on which **IDBInitialize::Initialize** was called but subsequently canceled before initialization, or has timed out. The data source object is still uninitialized.</span></span>  
  
 <span data-ttu-id="e7e1e-130">Se llamó a**ISSAsynchStatus::Abo at** en un conjunto de filas en el que previamente se llamó a **ITransaction::Commit** o a **ITransaction::Abo at** was previously called, and the rowset did not survive the commit o a abo at and is in a zombie state.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-130">**ISSAsynchStatus::Abort** was called on a rowset on which **ITransaction::Commit** or **ITransaction::Abort** was previously called, and the rowset did not survive the commit or abort and is in a zombie state.</span></span>  
  
 <span data-ttu-id="e7e1e-131">Se llamó a**ISSAsynchStatus::Abort** en un conjunto de filas que se canceló de forma asincrónica en su fase de inicialización.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-131">**ISSAsynchStatus::Abort** was called on a rowset that was asynchronously canceled in its initialization phase.</span></span> <span data-ttu-id="e7e1e-132">El conjunto de filas se encuentra en estado inerte.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-132">The rowset is in a zombie state.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7e1e-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7e1e-133">Remarks</span></span>  
 <span data-ttu-id="e7e1e-134">Al anular la inicialización de un conjunto de filas u objeto de origen de datos, se podría dejar el conjunto de filas u objeto de origen de datos en un estado zombi, de forma que todos los métodos distintos de los métodos **IUnknown** devuelvan un valor E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-134">Aborting the initialization of a rowset or data source object might leave the rowset or data source object in a zombie state, such that all methods other than **IUnknown** methods return E_UNEXPECTED.</span></span> <span data-ttu-id="e7e1e-135">Si esto sucede, la única acción posible para el consumidor es liberar el conjunto de filas u objeto de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-135">When this happens, the only possible action for the consumer is to release the rowset or data source object.</span></span>  
  
 <span data-ttu-id="e7e1e-136">Llamando a **ISSAsynchStatus::Abort** y pasando un valor para *eOperation* distinto de DBASYNCHOP_OPEN, devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-136">Calling **ISSAsynchStatus::Abort** and passing a value for *eOperation* other than DBASYNCHOP_OPEN returns S_OK.</span></span> <span data-ttu-id="e7e1e-137">Esto no implica que la operación se haya completado o cancelado.</span><span class="sxs-lookup"><span data-stu-id="e7e1e-137">This does not imply that the operation completed or was canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e1e-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7e1e-138">See Also</span></span>  
 [<span data-ttu-id="e7e1e-139">Realizar operaciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="e7e1e-139">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
