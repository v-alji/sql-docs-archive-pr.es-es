---
title: IBCPSession::BCPWriteFmt (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPWriteFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPWriteFmt method
ms.assetid: add50425-2ed6-411a-a391-4ce63c364892
author: rothja
ms.author: jroth
ms.openlocfilehash: ee4dcb5809c0f0fbb6d3f7aba6f4af5f6991e0e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676494"
---
# <a name="ibcpsessionbcpwritefmt-ole-db"></a><span data-ttu-id="23ecf-102">IBCPSession::BCPWriteFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="23ecf-102">IBCPSession::BCPWriteFmt (OLE DB)</span></span>
  <span data-ttu-id="23ecf-103">Escribe la información de formato de cada columna en el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="23ecf-103">Writes format information for each column to the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23ecf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23ecf-104">Syntax</span></span>  
  
```  
  
HRESULT BCPWriteFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="23ecf-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="23ecf-105">Remarks</span></span>  
 <span data-ttu-id="23ecf-106">El archivo de formato especifica el formato de los datos de un archivo de datos creado mediante copia masiva.</span><span class="sxs-lookup"><span data-stu-id="23ecf-106">The format file specifies the data format of a data file created by bulk copy.</span></span> <span data-ttu-id="23ecf-107">Las llamadas a los métodos [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) e [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) definen el formato del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="23ecf-107">Calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods define the format of the data file.</span></span> <span data-ttu-id="23ecf-108">El método **BCPWriteFmt** guarda esta definición en el archivo al que se hace referencia en el argumento pwszFormatFile.</span><span class="sxs-lookup"><span data-stu-id="23ecf-108">The **BCPWriteFmt** method saves this definition in the file referenced by the pwszFormatFile argument.</span></span>  
  
 <span data-ttu-id="23ecf-109">El método **BCPWriteFmt** puede guardar los archivos de formato en formato xml o de texto.</span><span class="sxs-lookup"><span data-stu-id="23ecf-109">The **BCPWriteFmt** method can save the format files in either xml or text format.</span></span> <span data-ttu-id="23ecf-110">Esto se debe indicar mediante la opción de control BCP_OPTION_XML con el método [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="23ecf-110">This must be indicated by using the BCP_OPTION_XML control option with the [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="23ecf-111">Para cargar un archivo de formato guardado, use el método [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="23ecf-111">To load a saved format file, use the [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md) method.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="23ecf-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="23ecf-112">Arguments</span></span>  
 <span data-ttu-id="23ecf-113">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="23ecf-113">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="23ecf-114">La ruta de acceso y nombre del archivo que contiene los valores de formato para el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="23ecf-114">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="23ecf-115">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="23ecf-115">Return Code Values</span></span>  
 <span data-ttu-id="23ecf-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="23ecf-116">S_OK</span></span>  
 <span data-ttu-id="23ecf-117">El método se ha llevado a cabo de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="23ecf-117">The method succeeded.</span></span>  
  
 <span data-ttu-id="23ecf-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23ecf-118">E_FAIL</span></span>  
 <span data-ttu-id="23ecf-119">Se produjo un error específico del proveedor. para obtener información detallada, use la interfaz [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="23ecf-119">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="23ecf-120">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="23ecf-120">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="23ecf-121">Error de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="23ecf-121">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="23ecf-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="23ecf-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="23ecf-123">No se esperaba la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="23ecf-123">The call to the method was unexpected.</span></span> <span data-ttu-id="23ecf-124">Por ejemplo, no se llamó al método [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) antes de llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="23ecf-124">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ecf-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23ecf-125">See Also</span></span>  
 <span data-ttu-id="23ecf-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="23ecf-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="23ecf-127">Realizar operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="23ecf-127">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
