---
title: IBCPSession::BCPColumns (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPColumns (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPColumns method
ms.assetid: c338abe8-9e30-4853-a7c6-b1a6c00095e1
author: rothja
ms.author: jroth
ms.openlocfilehash: c842b2a815074c0db7e6ab21e0a85eac68a986a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749270"
---
# <a name="ibcpsessionbcpcolumns-ole-db"></a><span data-ttu-id="bec47-102">IBCPSession::BCPColumns (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="bec47-102">IBCPSession::BCPColumns (OLE DB)</span></span>
  <span data-ttu-id="bec47-103">Establece el número de campos que van a enlazarse a las columnas en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bec47-103">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec47-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bec47-104">Syntax</span></span>  
  
```  
  
HRESULT BCPColumns(   
DBCOUNTITEMnColumns);  
```  
  
## <a name="remarks"></a><span data-ttu-id="bec47-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bec47-105">Remarks</span></span>  
 <span data-ttu-id="bec47-106">Llama a [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) internamente para establecer los valores predeterminados de los datos de campo.</span><span class="sxs-lookup"><span data-stu-id="bec47-106">Internally it calls [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) to set the default values for field data.</span></span> <span data-ttu-id="bec47-107">Estos valores predeterminados se obtienen de la información de columna de SQL Server que el proveedor recupera internamente cuando el nombre de tabla se especifica a través de [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="bec47-107">These default values are obtained from the SQL Server column information that the provider internally retrieves when the table name is specified through [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bec47-108"> Se puede llamar a este método solamente después de que se haya llamado a **a BCPInit** con un nombre de archivo válido.</span><span class="sxs-lookup"><span data-stu-id="bec47-108">This method can be called only after **BCPInit** has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="bec47-109">Solo debe llamar a este método si piensa utilizar un formato de archivo de usuario que difiere del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bec47-109">You should call this method only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="bec47-110">Para obtener más información sobre una descripción del formato predeterminado del archivo de usuario, vea el método **BCPInit** .</span><span class="sxs-lookup"><span data-stu-id="bec47-110">For more information about a description of the default user-file format, see the **BCPInit** method.</span></span>  
  
 <span data-ttu-id="bec47-111">Después de llamar al método **BCPColumns** , debe llamar al método **BCPColFmt** para cada columna en el archivo de usuario para definir completamente un formato de archivo personalizado.</span><span class="sxs-lookup"><span data-stu-id="bec47-111">After calling the **BCPColumns** method, you must call the **BCPColFmt** method for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="bec47-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bec47-112">Arguments</span></span>  
 <span data-ttu-id="bec47-113">*nColumns*[in]</span><span class="sxs-lookup"><span data-stu-id="bec47-113">*nColumns*[in]</span></span>  
 <span data-ttu-id="bec47-114">El número total de campos en el archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="bec47-114">The total number of fields in the user file.</span></span> <span data-ttu-id="bec47-115">Aun cuando está preparando para realizar copias masiva de datos del archivo de usuario a una tabla SQL Server y no piensa copiar todos los campos en el archivo de usuario, todavía debe establecer el argumento *nColumns* en el número total de campos de archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="bec47-115">Even if you are preparing to bulk copy data from the user file to a SQL Server table and do not intend to copy all fields in the user file, you must still set the *nColumns* argument to the total number of user-file fields.</span></span> <span data-ttu-id="bec47-116">Los campos omitidos se pueden especificar a continuación a través de **BCPColFmt**.</span><span class="sxs-lookup"><span data-stu-id="bec47-116">The skipped fields can then be specified through **BCPColFmt**.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="bec47-117">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="bec47-117">Return Code Values</span></span>  
 <span data-ttu-id="bec47-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="bec47-118">S_OK</span></span>  
 <span data-ttu-id="bec47-119">El método se ha llevado a cabo de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="bec47-119">The method succeeded.</span></span>  
  
 <span data-ttu-id="bec47-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bec47-120">E_FAIL</span></span>  
 <span data-ttu-id="bec47-121">Se produjo un error específico del proveedor. para obtener información detallada, use la interfaz [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="bec47-121">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="bec47-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="bec47-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="bec47-123">No se esperaba la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="bec47-123">The call to the method was unexpected.</span></span> <span data-ttu-id="bec47-124">Por ejemplo, no se llamó al método **BCPInit** antes de llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="bec47-124">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="bec47-125">También se produce cuando se llama a este método más de una vez para una operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="bec47-125">Also occurs when this method is called more than once for a bulk copy operation.</span></span>  
  
 <span data-ttu-id="bec47-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bec47-126">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="bec47-127">Error de memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="bec47-127">Out-of-memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec47-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bec47-128">See Also</span></span>  
 <span data-ttu-id="bec47-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="bec47-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="bec47-130">Realizar operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="bec47-130">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
