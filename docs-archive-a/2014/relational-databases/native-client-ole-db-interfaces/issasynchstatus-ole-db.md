---
title: ISSAsynchStatus (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSAsynchStatus interface
ms.assetid: c643f09f-9ccc-4d8b-9243-3cde86c2bd46
author: rothja
ms.author: jroth
ms.openlocfilehash: 4489f9d1ad576d49d885842f6969f9b61065791c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671035"
---
# <a name="issasynchstatus-ole-db"></a><span data-ttu-id="81367-102">ISSAsynchStatus (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="81367-102">ISSAsynchStatus (OLE DB)</span></span>
  <span data-ttu-id="81367-103">**ISSAsynchStatus** expone la compatibilidad para operaciones asincrónicas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81367-103">**ISSAsynchStatus** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asynchronous operations.</span></span> <span data-ttu-id="81367-104">Ésta es una interfaz opcional que se hereda de la interfaz de OLE DB **IDBAsynchStatus**principal.</span><span class="sxs-lookup"><span data-stu-id="81367-104">This is an optional interface that inherits from the core OLE DB interface **IDBAsynchStatus**.</span></span> <span data-ttu-id="81367-105">Además de los métodos **Abort** y **GetStatus** heredados de **IDBAsynchStatus**, **ISSAsynchStatus** proporciona un nuevo método que se usa para esperar hasta que una operación asincrónica se ha completado o se agota el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="81367-105">In addition to the **Abort** and **GetStatus** methods inherited from **IDBAsynchStatus**, **ISSAsynchStatus** provides one new method that is used to wait until an asynchronous operation has completed or a time-out occurs.</span></span>  
  
|<span data-ttu-id="81367-106">Método</span><span class="sxs-lookup"><span data-stu-id="81367-106">Method</span></span>|<span data-ttu-id="81367-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="81367-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81367-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="81367-108">ISSAsynchStatus::Abort &#40;OLE DB&#41;</span></span>](issasynchstatus-abort-ole-db.md)|<span data-ttu-id="81367-109">Cancela una operación que se ejecuta de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="81367-109">Cancels an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="81367-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="81367-110">ISSAsynchStatus::GetStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-getstatus-ole-db.md)|<span data-ttu-id="81367-111">Devuelve el estado de una operación de ejecución asincrónica.</span><span class="sxs-lookup"><span data-stu-id="81367-111">Returns the status of an asynchronously executing operation.</span></span>|  
|[<span data-ttu-id="81367-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="81367-112">ISSAsynchStatus::WaitForAsynchCompletion &#40;OLE DB&#41;</span></span>](issasynchstatus-waitforasynchcompletion-ole-db.md)|<span data-ttu-id="81367-113">Espera hasta que la operación que se ejecuta de forma asincrónica se haya completado o hasta que se produzca un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="81367-113">Waits until the asynchronously executing operation is complete or a time-out occurs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81367-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="81367-114">Remarks</span></span>  
 <span data-ttu-id="81367-115">La implementación de **ISSAsynchStatus** del método **ISSAsynchStatus::GetStatus** es la misma que el método **IDBAsynchStatus::GetStatus** salvo si se anula la inicialización de un objeto de origen de datos, se devuelve E_UNEXPECTED en lugar de DB_E_CANCELED (aunque **ISSAsynchStatus::WaitForAsynchCompletion** devuelve DB_E_CANCELED).</span><span class="sxs-lookup"><span data-stu-id="81367-115">The **ISSAsynchStatus** implementation of the **ISSAsynchStatus::GetStatus** method is the same as the **IDBAsynchStatus::GetStatus** method except that if the initialization of a data source object is aborted, E_UNEXPECTED is returned rather than DB_E_CANCELED (although **ISSAsynchStatus::WaitForAsynchCompletion** returns DB_E_CANCELED).</span></span> <span data-ttu-id="81367-116">Esto se debe a que el objeto de origen de datos no se queda en el estado habitual que sigue a una operación de anulación, de manera que se puedan intentar otras operaciones de inicialización.</span><span class="sxs-lookup"><span data-stu-id="81367-116">This is because the data source object is not left in the usual state following an abort operation, so that further initialization operations may be attempted.</span></span>  
  
 <span data-ttu-id="81367-117">Los métodos siguientes admiten el uso de ejecución asincrónica en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="81367-117">The following methods support the use of asynchronous execution in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="81367-118">**ICommand::Execute**</span><span class="sxs-lookup"><span data-stu-id="81367-118">**ICommand::Execute**</span></span>  
  
-   <span data-ttu-id="81367-119">**IOpenRowset::OpenRowset**</span><span class="sxs-lookup"><span data-stu-id="81367-119">**IOpenRowset::OpenRowset**</span></span>  
  
-   <span data-ttu-id="81367-120">**IMultipleResults::GetResult**</span><span class="sxs-lookup"><span data-stu-id="81367-120">**IMultipleResults::GetResult**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81367-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81367-121">See Also</span></span>  
 <span data-ttu-id="81367-122">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="81367-122">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 [<span data-ttu-id="81367-123">Realizar operaciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="81367-123">Performing Asynchronous Operations</span></span>](../native-client/features/performing-asynchronous-operations.md)  
  
  
