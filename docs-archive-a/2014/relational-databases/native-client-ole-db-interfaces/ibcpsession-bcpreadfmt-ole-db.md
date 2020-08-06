---
title: IBCPSession::BCPReadFmt (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPReadFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPReadFmt method
ms.assetid: e2a12050-94e4-48a3-8a48-b780d646f116
author: rothja
ms.author: jroth
ms.openlocfilehash: ca811dceb8ab6771e3bdd6689a8e11eca6a0e3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749265"
---
# <a name="ibcpsessionbcpreadfmt-ole-db"></a><span data-ttu-id="153c0-102">IBCPSession::BCPReadFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="153c0-102">IBCPSession::BCPReadFmt (OLE DB)</span></span>
  <span data-ttu-id="153c0-103">Lee la información de formato de cada columna en el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="153c0-103">Reads format information for each column from the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="153c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="153c0-104">Syntax</span></span>  
  
```  
  
HRESULT BCPReadFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="153c0-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="153c0-105">Remarks</span></span>  
 <span data-ttu-id="153c0-106">El método **BCPReadFmt** se utiliza para leer datos de un archivo de formato que especifica el formato de datos en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="153c0-106">The **BCPReadFmt** method is used for reading data from a format file that specifies the format of data in the data file.</span></span> <span data-ttu-id="153c0-107">Este método es capaz de detectar la versión correcta del archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="153c0-107">This method is capable of detecting the correct version of the format file.</span></span> <span data-ttu-id="153c0-108">Puede detectar automáticamente si el archivo de formato está en xml o en el formato de texto de estilo anterior y se comporta en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="153c0-108">It can automatically detect whether the format file is in xml or old style text format and behaves accordingly.</span></span> <span data-ttu-id="153c0-109">Las versiones del archivo de formato admitidas por el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client BCP son la 6.0 o más reciente.</span><span class="sxs-lookup"><span data-stu-id="153c0-109">The format file versions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider BCP are version 6.0 or newer.</span></span>  
  
 <span data-ttu-id="153c0-110">Después de que el método **BCPReadFmt** lee los valores de formato, realiza las llamadas adecuadas a los métodos [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) e [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="153c0-110">After the **BCPReadFmt** method reads the format values, it makes the appropriate calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods.</span></span> <span data-ttu-id="153c0-111">No es necesario que analice un archivo de formato y realice estas llamadas.</span><span class="sxs-lookup"><span data-stu-id="153c0-111">There is no need for the user to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="153c0-112">Para guardar un archivo de formato, llame al método [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="153c0-112">To save a format file, call the [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md) method.</span></span> <span data-ttu-id="153c0-113">Las llamadas al método **BCPReadFmt** pueden hacer referencia a formatos guardados.</span><span class="sxs-lookup"><span data-stu-id="153c0-113">Calls to the **BCPReadFmt** method can reference saved formats.</span></span> <span data-ttu-id="153c0-114">Como alternativa, la utilidad de copia masiva (**bcp**) puede guardar formatos de datos definidos por el usuario en archivos a los que puede hacer referencia el método **BCPReadFmt** .</span><span class="sxs-lookup"><span data-stu-id="153c0-114">Alternatively, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by the **BCPReadFmt** method.</span></span>  
  
 <span data-ttu-id="153c0-115">El `BCP_OPTION_DELAYREADFMT` valor del parámetro *EOption* de [IBCPSession:: BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifica el comportamiento de IBCPSession:: BCPReadFmt.</span><span class="sxs-lookup"><span data-stu-id="153c0-115">The `BCP_OPTION_DELAYREADFMT` value of the *eOption* parameter of [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifies the behavior of IBCPSession::BCPReadFmt.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="153c0-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="153c0-116">Arguments</span></span>  
 <span data-ttu-id="153c0-117">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="153c0-117">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="153c0-118">La ruta de acceso y nombre del archivo que contiene los valores de formato para el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="153c0-118">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="153c0-119">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="153c0-119">Return Code Values</span></span>  
 <span data-ttu-id="153c0-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="153c0-120">S_OK</span></span>  
 <span data-ttu-id="153c0-121">El método se ha llevado a cabo de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="153c0-121">The method succeeded.</span></span>  
  
 <span data-ttu-id="153c0-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="153c0-122">E_FAIL</span></span>  
 <span data-ttu-id="153c0-123">Se produjo un error específico del proveedor; para obtener información detallada, use la interfaz [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="153c0-123">A provider-specific error occurred, for detailed information use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="153c0-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="153c0-124">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="153c0-125">Error de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="153c0-125">Out of memory error.</span></span>  
  
 <span data-ttu-id="153c0-126">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="153c0-126">E_UNEXPECTED</span></span>  
 <span data-ttu-id="153c0-127">No se esperaba la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="153c0-127">The call to the method was unexpected.</span></span> <span data-ttu-id="153c0-128">Por ejemplo, no se llamó al método [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) antes de llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="153c0-128">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="153c0-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="153c0-129">See Also</span></span>  
 <span data-ttu-id="153c0-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="153c0-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="153c0-131">Realizar operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="153c0-131">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
