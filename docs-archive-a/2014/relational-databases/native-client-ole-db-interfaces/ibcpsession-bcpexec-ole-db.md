---
title: IBCPSession::BCPExec (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPExec (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPExec method
ms.assetid: 0f4ebb63-cf03-4e53-846e-6c3021cde007
author: rothja
ms.author: jroth
ms.openlocfilehash: 1452888e046b6223c64a6cdf6fe09b074b815702
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744678"
---
# <a name="ibcpsessionbcpexec-ole-db"></a><span data-ttu-id="cd692-102">IBCPSession::BCPExec (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="cd692-102">IBCPSession::BCPExec (OLE DB)</span></span>
  <span data-ttu-id="cd692-103">Realiza la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="cd692-103">Performs the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd692-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd692-104">Syntax</span></span>  
  
```  
  
HRESULT BCPExec(   
DBROWCOUNT *pRowsCopied);  
```  
  
## <a name="remarks"></a><span data-ttu-id="cd692-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cd692-105">Remarks</span></span>  
 <span data-ttu-id="cd692-106">El método **BCPExec** copia los datos de un archivo de usuario en una tabla de base de datos o viceversa, en función del valor del parámetro *eDirection* usado con el método [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="cd692-106">The **BCPExec** method copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter used with the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="cd692-107">Antes de llamar a **BCPExec**, llame al método **BCPInit** con un nombre de archivo de usuario válido.</span><span class="sxs-lookup"><span data-stu-id="cd692-107">Before calling **BCPExec**, call the **BCPInit** method with a valid user file name.</span></span> <span data-ttu-id="cd692-108">Si no lo hace, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="cd692-108">Failure to do so results in an error.</span></span> <span data-ttu-id="cd692-109">La única excepción es que una consulta vaya a utilizarse para una operación de salida de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="cd692-109">The only exception is if a query is to be used for a bulk copy out operation.</span></span> <span data-ttu-id="cd692-110">En ese caso, especifique NULL para el nombre de tabla en el método **BCPInit** y, a continuación, especifique la consulta mediante la opción BCP_OPTION_HINTS.</span><span class="sxs-lookup"><span data-stu-id="cd692-110">In that case specify NULL for the table name in the **BCPInit** method and then specify the query using the BCP_OPTION_HINTS option.</span></span>  
  
 <span data-ttu-id="cd692-111">El método **BCPExec** es el único método de copia masiva que es probable que quede pendiente durante un período de tiempo indeterminado.</span><span class="sxs-lookup"><span data-stu-id="cd692-111">The **BCPExec** method is the only bulk copy method that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="cd692-112">Por lo tanto, es el único método de copia masiva que admite el modo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="cd692-112">It is therefore the only bulk copy method that supports asynchronous mode.</span></span> <span data-ttu-id="cd692-113">Para usar el modo asincrónico, establezca la propiedad de sesión específica del proveedor SSPROP_ASYNCH_BULKCOPY en VARIANT_TRUE antes de llamar al método **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="cd692-113">To use asynchronous mode, set the provider specific session property SSPROP_ASYNCH_BULKCOPY to VARIANT_TRUE before calling the **BCPExec** method.</span></span> <span data-ttu-id="cd692-114">Esta propiedad se encuentra disponible en el conjunto de propiedades DBPROPSET_SQLSERVERSESSION.</span><span class="sxs-lookup"><span data-stu-id="cd692-114">This property is available in the DBPROPSET_SQLSERVERSESSION property set.</span></span> <span data-ttu-id="cd692-115">Para comprobar si se ha completado, llame al método **BCPExec** con los mismos parámetros.</span><span class="sxs-lookup"><span data-stu-id="cd692-115">To test for completion, call the **BCPExec** method with the same parameters.</span></span> <span data-ttu-id="cd692-116">Si la copia masiva aún no se ha completado, el método **BCPExec** devuelve DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="cd692-116">If the bulk copy has not yet completed, the **BCPExec** method returns DB_S_ASYNCHRONOUS.</span></span> <span data-ttu-id="cd692-117">También devuelve en el argumento *pRowsCopied* un recuento de estado del número de filas que se han enviado al servidor o que se han recibido del servidor.</span><span class="sxs-lookup"><span data-stu-id="cd692-117">It also returns in the *pRowsCopied* argument a status count of the number of rows that have been sent to or received from the server.</span></span> <span data-ttu-id="cd692-118">Las filas enviadas al servidor no se confirman hasta que se alcanza el final de un lote.</span><span class="sxs-lookup"><span data-stu-id="cd692-118">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="cd692-119">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cd692-119">Arguments</span></span>  
 <span data-ttu-id="cd692-120">*pRowsCopied*[out]</span><span class="sxs-lookup"><span data-stu-id="cd692-120">*pRowsCopied*[out]</span></span>  
 <span data-ttu-id="cd692-121">Puntero a un valor de tipo DWORD.</span><span class="sxs-lookup"><span data-stu-id="cd692-121">A pointer to a DWORD.</span></span> <span data-ttu-id="cd692-122">El método **BCPExec** rellena el valor DWORD con el número de filas que se han copiado correctamente.</span><span class="sxs-lookup"><span data-stu-id="cd692-122">The **BCPExec** method fills the DWORD with the number of rows successfully copied.</span></span> <span data-ttu-id="cd692-123">Si el argumento *pRowsCopied* está establecido en NULL, el método **BCPExec** lo omite.</span><span class="sxs-lookup"><span data-stu-id="cd692-123">If the *pRowsCopied* argument is set to NULL, it is ignored by the **BCPExec** method.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="cd692-124">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="cd692-124">Return Code Values</span></span>  
 <span data-ttu-id="cd692-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd692-125">S_OK</span></span>  
 <span data-ttu-id="cd692-126">El método se ha llevado a cabo de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="cd692-126">The method succeeded.</span></span>  
  
 <span data-ttu-id="cd692-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd692-127">E_FAIL</span></span>  
 <span data-ttu-id="cd692-128">Se produjo un error específico del proveedor. para obtener información detallada, use la interfaz [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="cd692-128">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="cd692-129">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="cd692-129">E_UNEXPECTED</span></span>  
 <span data-ttu-id="cd692-130">No se esperaba la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="cd692-130">The call to the method was unexpected.</span></span> <span data-ttu-id="cd692-131">Por ejemplo, no se llamó al método **BCPInit** antes de llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="cd692-131">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="cd692-132">También se produce si la operación se anuló mediante el uso de la opción BCP_OPTION_ABORT y después se llamó al método **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="cd692-132">Also occurs if the operation has been aborted through using the BCP_OPTION_ABORT option, and the **BCPExec** method was called afterwards.</span></span>  
  
 <span data-ttu-id="cd692-133">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="cd692-133">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="cd692-134">Error de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="cd692-134">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="cd692-135">DB_S_ENDOFROWSET</span><span class="sxs-lookup"><span data-stu-id="cd692-135">DB_S_ENDOFROWSET</span></span>  
 <span data-ttu-id="cd692-136">La operación de copia masiva finalizó y se completó toda la operación de transferencia de datos.</span><span class="sxs-lookup"><span data-stu-id="cd692-136">The bulk copy operation finished, and all the data transfer was completed.</span></span>  
  
 <span data-ttu-id="cd692-137">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="cd692-137">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="cd692-138">Se copió el lote actual de filas.</span><span class="sxs-lookup"><span data-stu-id="cd692-138">The current batch of rows has been copied.</span></span> <span data-ttu-id="cd692-139">Vuelva a llamar al método **BCPExec** para transferir el siguiente lote.</span><span class="sxs-lookup"><span data-stu-id="cd692-139">Call the **BCPExec** method again to transfer the next batch.</span></span>  
  
 <span data-ttu-id="cd692-140">DB_S_ERRORSOCCURRED</span><span class="sxs-lookup"><span data-stu-id="cd692-140">DB_S_ERRORSOCCURRED</span></span>  
 <span data-ttu-id="cd692-141">Se produjeron errores durante la operación de copia masiva y algunas filas no pudieron copiarse.</span><span class="sxs-lookup"><span data-stu-id="cd692-141">Errors occurred during the bulk copy operation, and some rows might not have been copied.</span></span> <span data-ttu-id="cd692-142">El número de errores sigue siendo menor al número máximo de errores permitidos.</span><span class="sxs-lookup"><span data-stu-id="cd692-142">The number of errors is still less than the maximum errors allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd692-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd692-143">See Also</span></span>  
 <span data-ttu-id="cd692-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="cd692-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="cd692-145">Realizar operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="cd692-145">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
