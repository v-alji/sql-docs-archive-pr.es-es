---
title: ISQLServerErrorInfo::GetErrorInfo (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISQLServerErrorInfo::GetErrorInfo (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetErrorInfo method
ms.assetid: 83265c9c-eaf9-41f0-9f73-b0ae0972f0d5
author: rothja
ms.author: jroth
ms.openlocfilehash: c3e325cd99276e04a178b89c19b233289edc09fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746989"
---
# <a name="isqlservererrorinfogeterrorinfo-ole-db"></a><span data-ttu-id="c01a4-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="c01a4-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span></span>
  <span data-ttu-id="c01a4-103">Devuelve un puntero a una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estructura SSERRORINFO del proveedor de OLE DB de Native Client que contiene los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detalles del error.</span><span class="sxs-lookup"><span data-stu-id="c01a4-103">Returns a pointer to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider SSERRORINFO structure containing the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error details.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c01a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c01a4-104">Syntax</span></span>  
  
```  
  
   HRESULT GetErrorInfo(  
SSERRORINFO**ppSSErrorInfo,  
OLECHAR**ppErrorStrings);  
```  
  
## <a name="arguments"></a><span data-ttu-id="c01a4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c01a4-105">Arguments</span></span>  
 <span data-ttu-id="c01a4-106">*ppSSErrorInfo*[out]</span><span class="sxs-lookup"><span data-stu-id="c01a4-106">*ppSSErrorInfo*[out]</span></span>  
 <span data-ttu-id="c01a4-107">Un puntero a una estructura SSERRORINFO.</span><span class="sxs-lookup"><span data-stu-id="c01a4-107">A pointer to a SSERRORINFO structure.</span></span> <span data-ttu-id="c01a4-108">Si el método produce un error o no hay información de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asociada al error, el proveedor no asigna memoria y se asegura de que el argumento *ppSSErrorInfo* dé como resultado un puntero nulo.</span><span class="sxs-lookup"><span data-stu-id="c01a4-108">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with the error, the provider does not allocate any memory, and ensures that the *ppSSErrorInfo* argument is a null pointer on output.</span></span>  
  
 <span data-ttu-id="c01a4-109">*ppErrorStrings*[out]</span><span class="sxs-lookup"><span data-stu-id="c01a4-109">*ppErrorStrings*[out]</span></span>  
 <span data-ttu-id="c01a4-110">Un puntero a una cadena de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="c01a4-110">A pointer to a Unicode character-string pointer.</span></span> <span data-ttu-id="c01a4-111">Si el método produce un error o no hay información de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asociada a un error, el proveedor no asigna memoria y se asegura de que el argumento *ppErrorStrings* dé como resultado un puntero nulo.</span><span class="sxs-lookup"><span data-stu-id="c01a4-111">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with an error, the provider does not allocate any memory, and ensures that the *ppErrorStrings* argument is a null pointer on output.</span></span> <span data-ttu-id="c01a4-112">Cuando se libera el argumento *ppErrorStrings* con el método **IMalloc::Free**, se liberan los tres miembros de cadena de la estructura SSERRORINFO devuelta, ya que la memoria se asigna en un bloque.</span><span class="sxs-lookup"><span data-stu-id="c01a4-112">Freeing the *ppErrorStrings* argument with the **IMalloc::Free** method frees the three individual string members of the returned SSERRORINFO structure, as the memory is allocated in a block.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="c01a4-113">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="c01a4-113">Return Code Values</span></span>  
 <span data-ttu-id="c01a4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c01a4-114">S_OK</span></span>  
 <span data-ttu-id="c01a4-115">El método se ha llevado a cabo de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="c01a4-115">The method succeeded.</span></span>  
  
 <span data-ttu-id="c01a4-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c01a4-116">E_INVALIDARG</span></span>  
 <span data-ttu-id="c01a4-117">El argumento *ppSSErrorInfo* o *ppErrorStrings* era NULL.</span><span class="sxs-lookup"><span data-stu-id="c01a4-117">Either the *ppSSErrorInfo* or the *ppErrorStrings* argument was NULL.</span></span>  
  
 <span data-ttu-id="c01a4-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c01a4-118">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c01a4-119">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no pudo asignar memoria suficiente para completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c01a4-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider could not allocate sufficient memory to complete the request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c01a4-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c01a4-120">Remarks</span></span>  
 <span data-ttu-id="c01a4-121">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client asigna memoria para las cadenas SSERRORINFO y OLECHAR devueltas a través de los punteros pasados por el consumidor.</span><span class="sxs-lookup"><span data-stu-id="c01a4-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider allocates memory for the SSERRORINFO and OLECHAR strings returned through the pointers passed by the consumer.</span></span> <span data-ttu-id="c01a4-122">El consumidor debe desasignar esta memoria mediante el método **IMalloc::Free** cuando ya no requiera tener acceso a los datos de error.</span><span class="sxs-lookup"><span data-stu-id="c01a4-122">The consumer must deallocate this memory by using the **IMalloc::Free** method when it no longer requires access to the error data.</span></span>  
  
 <span data-ttu-id="c01a4-123">La estructura SSERRORINFO se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="c01a4-123">The SSERRORINFO structure is defined as follows:</span></span>  
  
```  
typedef struct tagSSErrorInfo  
   {  
   LPOLESTR pwszMessage;  
   LPOLESTR pwszServer;  
   LPOLESTR pwszProcedure;  
   LONG lNative;  
   BYTE bState;  
   BYTE bClass;  
   WORD wLineNumber;  
   }  
SSERRORINFO;  
```  
  
|<span data-ttu-id="c01a4-124">Miembro</span><span class="sxs-lookup"><span data-stu-id="c01a4-124">Member</span></span>|<span data-ttu-id="c01a4-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c01a4-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c01a4-126">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="c01a4-126">*pwszMessage*</span></span>|<span data-ttu-id="c01a4-127">El mensaje de error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c01a4-127">The error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c01a4-128">El mensaje se devuelve a través del método **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="c01a4-128">The message is returned through the **IErrorInfo::GetDescription** method.</span></span>|  
|<span data-ttu-id="c01a4-129">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="c01a4-129">*pwszServer*</span></span>|<span data-ttu-id="c01a4-130">El nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la que se ha producido el error.</span><span class="sxs-lookup"><span data-stu-id="c01a4-130">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which the error occurred.</span></span>|  
|<span data-ttu-id="c01a4-131">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="c01a4-131">*pwszProcedure*</span></span>|<span data-ttu-id="c01a4-132">El nombre del procedimiento almacenado que genera el error si éste se produjo en un procedimiento almacenado; de lo contrario, una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="c01a4-132">The name of the stored procedure generating the error if the error occurred in a stored procedure; otherwise, an empty string.</span></span>|  
|<span data-ttu-id="c01a4-133">*lNative*</span><span class="sxs-lookup"><span data-stu-id="c01a4-133">*lNative*</span></span>|<span data-ttu-id="c01a4-134">El número de error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c01a4-134">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number.</span></span> <span data-ttu-id="c01a4-135">El número de error es idéntico al devuelto en el parámetro *plNativeError* del método **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="c01a4-135">The error number is identical to that returned in the *plNativeError* parameter of the **ISQLErrorInfo::GetSQLInfo** method.</span></span>|  
|<span data-ttu-id="c01a4-136">*bState*</span><span class="sxs-lookup"><span data-stu-id="c01a4-136">*bState*</span></span>|<span data-ttu-id="c01a4-137">El estado del error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c01a4-137">The state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="c01a4-138">*bClass*</span><span class="sxs-lookup"><span data-stu-id="c01a4-138">*bClass*</span></span>|<span data-ttu-id="c01a4-139">La gravedad del error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c01a4-139">The severity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="c01a4-140">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="c01a4-140">*wLineNumber*</span></span>|<span data-ttu-id="c01a4-141">Cuando sea aplicable, la línea de un procedimiento almacenado de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que generó el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="c01a4-141">When applicable, the line of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure that generated the error message.</span></span> <span data-ttu-id="c01a4-142">Si no hay implicado ningún procedimiento, se utiliza el valor predeterminado 1.</span><span class="sxs-lookup"><span data-stu-id="c01a4-142">If no procedure is involved, the default value is 1.</span></span>|  
  
 <span data-ttu-id="c01a4-143">Los punteros de las direcciones de referencia de la estructura en la cadena devuelta en el argumento *ppErrorStrings*.</span><span class="sxs-lookup"><span data-stu-id="c01a4-143">Pointers in the structure reference addresses in the string returned in the *ppErrorStrings* argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c01a4-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c01a4-144">See Also</span></span>  
 <span data-ttu-id="c01a4-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="c01a4-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span></span>  
 [<span data-ttu-id="c01a4-146">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c01a4-146">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
