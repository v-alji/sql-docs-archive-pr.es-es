---
title: ISSAsynchStatus::WaitForAsynchCompletion (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- WaitForAsynchCompletion method
ms.assetid: 9f65e9e7-eb93-47a1-bc42-acd4649fbd0e
author: rothja
ms.author: jroth
ms.openlocfilehash: f57211d1c62535828704dc971e345b412c284cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671034"
---
# <a name="issasynchstatuswaitforasynchcompletion-ole-db"></a><span data-ttu-id="6d7d5-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="6d7d5-102">ISSAsynchStatus::WaitForAsynchCompletion (OLE DB)</span></span>
  <span data-ttu-id="6d7d5-103">Espera hasta que la operación que se ejecuta de forma asincrónica haya finalizado o hasta que se produzca un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-103">Waits until the asynchronously executing operation is complete or until a time-out occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d7d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d7d5-104">Syntax</span></span>  
  
```  
  
HRESULT WaitForAsynchCompletion(   
  DWORD dwMillisecTimeOut);  
```  
  
## <a name="arguments"></a><span data-ttu-id="6d7d5-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6d7d5-105">Arguments</span></span>  
 <span data-ttu-id="6d7d5-106">*dwMillisecTimeOut*[entrada]</span><span class="sxs-lookup"><span data-stu-id="6d7d5-106">*dwMillisecTimeOut*[in]</span></span>  
 <span data-ttu-id="6d7d5-107">Tiempo de espera en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-107">Time-out in milliseconds.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="6d7d5-108">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="6d7d5-108">Return Code Values</span></span>  
 <span data-ttu-id="6d7d5-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d7d5-109">S_OK</span></span>  
 <span data-ttu-id="6d7d5-110">El método se ha llevado a cabo de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-110">The method succeeded.</span></span>  
  
 <span data-ttu-id="6d7d5-111">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="6d7d5-111">E_UNEXPECTED</span></span>  
 <span data-ttu-id="6d7d5-112">Un conjunto de filas está en un estado no usado porque se ha llamado a **ITransaction::Commit** o a **ITransaction::Abort** o bien el conjunto de filas se ha cancelado durante su fase de inicialización.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-112">A rowset is in an unused state because **ITransaction::Commit** or **ITransaction::Abort** has been called or the rowset was cancelled during its initialization phase.</span></span>  
  
 <span data-ttu-id="6d7d5-113">DB_E_CANCELED</span><span class="sxs-lookup"><span data-stu-id="6d7d5-113">DB_E_CANCELED</span></span>  
 <span data-ttu-id="6d7d5-114">El procesamiento asincrónico se canceló durante el rellenado del conjunto de filas o la inicialización del objeto de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-114">Asynchronous processing was cancelled during rowset population or data source object initialization.</span></span>  
  
 <span data-ttu-id="6d7d5-115">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="6d7d5-115">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="6d7d5-116">La operación todavía no se ha completado aunque se ha alcanzado el tiempo de espera especificado.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-116">The operation has not yet completed even though specified time-out has been reached.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d7d5-117"> Además de los valores de código de retorno enumerados anteriormente, el método **ISSAsynchStatus::WaitForAsynchCompletion** también admite los valores de código de retorno que devuelven los métodos **ICommand::Execute** e **IDBInitialize::Initialize** de OLEDB básicos.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-117">In addition to the return code values listed above, the **ISSAsynchStatus::WaitForAsynchCompletion** method also supports the return code values returned by the core OLEDB **ICommand::Execute** and **IDBInitialize::Initialize** methods.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d7d5-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6d7d5-118">Remarks</span></span>  
 <span data-ttu-id="6d7d5-119">No se devolverá el método **ISSAsynchStatus::WaitForAsynchCompletion** hasta que haya transcurrido el valor de tiempo de espera (en milisegundos) o se haya completado la operación pendiente.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-119">The **ISSAsynchStatus::WaitForAsynchCompletion** method will not return until the time-out value (in milliseconds) has passed or the pending operation is done.</span></span> <span data-ttu-id="6d7d5-120">El objeto **Command** tiene una propiedad **CommandTimeout** que controla el número de segundos que se ejecutará una consulta antes de que se agote el tiempo de espera. La propiedad **CommandTimeout** se omitirá si se utiliza junto con el método **ISSAsynchStatus:: WaitForAsynchCompletion** .</span><span class="sxs-lookup"><span data-stu-id="6d7d5-120">The **Command** object has a **CommandTimeout** property that controls the number of seconds a query will run before timing out. The **CommandTimeout** property will be ignored if used in conjunction with **ISSAsynchStatus::WaitForAsynchCompletion** method.</span></span>  
  
 <span data-ttu-id="6d7d5-121">La propiedad de tiempo de espera se omite en las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-121">The time-out property is ignored for asynchronous operations.</span></span> <span data-ttu-id="6d7d5-122">El parámetro de tiempo de espera de **ISSAsynchStatus::WaitForAsynchCompletion** especifica el tiempo máximo que debe transcurrir antes de que se devuelva el control al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-122">The time-out parameter of **ISSAsynchStatus::WaitForAsynchCompletion** specifies the maximum amount of time that will elapse before control is returned to the caller.</span></span> <span data-ttu-id="6d7d5-123">Si este tiempo de espera expira, se devolverá DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-123">If this time-out expires, DB_S_ASYNCHRONOUS will be returned.</span></span> <span data-ttu-id="6d7d5-124">Los tiempos de espera nunca cancelan las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-124">Time-outs never cancel asynchronous operations.</span></span> <span data-ttu-id="6d7d5-125">Si la aplicación necesita cancelar una operación asincrónica que no se ha completado en un período de tiempo de espera, debe esperar a que finalice el tiempo de espera y, a continuación, cancelar explícitamente la operación si se devuelve DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-125">If the application needs to cancel an asynchronous operation that does not complete within a time-out period, it must wait for the time-out and then explicitly cancel the operation if DB_S_ASYNCHRONOUS is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d7d5-126">Si se usan componentes de servicio OLE DB, se puede devolver S_OK cuando se espera DB_S_ASYNCHRONOUS, por lo que las aplicaciones deben llamar a [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) para comprobar la finalización cuando se devuelven S_OK o DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-126">When the OLE DB Service Components are used, S_OK may be returned when DB_S_ASYNCHRONOUS is expected, so applications should call [ISSAsynchStatus::GetStatus](issasynchstatus-getstatus-ole-db.md) to check for completion when S_OK or DB_S_ASYNCHRONOUS is returned.</span></span>  
  
 <span data-ttu-id="6d7d5-127">Si el valor *dwMillisecTimeOut* se establece en INFINITE, el método **ISSAsynchStatus::WaitForAsynchCompletion** se bloquea hasta que se completa la operación.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-127">If the *dwMillisecTimeOut* value is set to INFINITE, the **ISSAsynchStatus::WaitForAsynchCompletion** method blocks until the operation is done.</span></span> <span data-ttu-id="6d7d5-128">Si el valor *dwMillisecTimeOut* se establece en 0, el método se devolverá inmediatamente con el estado de la operación pendiente.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-128">If the *dwMillisecTimeOut* value is set to 0, then the method will return immediately with the status of the pending operation.</span></span> <span data-ttu-id="6d7d5-129">Si el tiempo de espera expira antes de que se complete la operación, se devolverá DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-129">If the time-out expires before the operation is complete DB_S_ASYNCHRONOUS will be returned.</span></span>  
  
 <span data-ttu-id="6d7d5-130">Si la operación se completa antes de que el tiempo de espera expire, el HRESULT devuelto será el HRESULT devuelto por la operación (el HRESULT que se habría devuelto si la operación se hubiese realizado de forma sincrónica).</span><span class="sxs-lookup"><span data-stu-id="6d7d5-130">If the operation completes before the time-out expires, the returned HRESULT will be the HRESULT returned by the operation (the HRESULT that would have been returned had the operation been performed synchronously).</span></span>  
  
 <span data-ttu-id="6d7d5-131">Además, se ha agregado la propiedad SSPROP_ISSAsynchStatus al conjunto de propiedades DBPROPSET_SQLSERVERROWSET.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-131">In addition, the SSPROP_ISSAsynchStatus property has been added to the DBPROPSET_SQLSERVERROWSET property set.</span></span> <span data-ttu-id="6d7d5-132">Los proveedores que admiten la interfaz [ISSAsynchStatus](issasynchstatus-ole-db.md) deben implementar esta propiedad con un valor de VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="6d7d5-132">Providers that support the [ISSAsynchStatus](issasynchstatus-ole-db.md) interface must implement this property with a value of VARIANT_TRUE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d7d5-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d7d5-133">See Also</span></span>  
 <span data-ttu-id="6d7d5-134">[Realización de operaciones asincrónicas](../native-client/features/performing-asynchronous-operations.md) </span><span class="sxs-lookup"><span data-stu-id="6d7d5-134">[Performing Asynchronous Operations](../native-client/features/performing-asynchronous-operations.md) </span></span>  
 [<span data-ttu-id="6d7d5-135">ISSAsynchStatus &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6d7d5-135">ISSAsynchStatus &#40;OLE DB&#41;</span></span>](issasynchstatus-ole-db.md)  
  
  
