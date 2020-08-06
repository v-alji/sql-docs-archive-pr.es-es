---
title: Detalla de errores de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], error details
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error details
- ISQLServerErrorInfo interface
ms.assetid: 51500ee3-3d78-47ec-b90f-ebfc55642e06
author: rothja
ms.author: jroth
ms.openlocfilehash: 4c03cf62dd274f9bcca213d33fb8969b26c9d980
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675833"
---
# <a name="sql-server-error-detail"></a><span data-ttu-id="e5005-102">Detalles de errores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5005-102">SQL Server Error Detail</span></span>
  <span data-ttu-id="e5005-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client define la interfaz de error específica del proveedor [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="e5005-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the provider-specific error interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span> <span data-ttu-id="e5005-104">La interfaz devuelve más detalles acerca de un error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y resulta útil cuando se produce un error en la ejecución del comando o en operaciones de conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="e5005-104">The interface returns more detail about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error and is valuable when command execution or rowset operations fail.</span></span>  
  
 <span data-ttu-id="e5005-105">Hay dos maneras de obtener acceso a la interfaz **ISQLServerErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="e5005-105">There are two ways to obtain access to **ISQLServerErrorInfo** interface.</span></span>  
  
 <span data-ttu-id="e5005-106">El consumidor puede llamar a **IErrorRecords::GetCustomerErrorObject** para obtener un puntero **ISQLServerErrorInfo**, tal como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5005-106">The consumer may call **IErrorRecords::GetCustomerErrorObject** to obtain an **ISQLServerErrorInfo** pointer, as shown in the following code sample.</span></span> <span data-ttu-id="e5005-107">(No hay ninguna necesidad de obtener **ISQLErrorInfo**). **ISQLErrorInfo** e **ISQLServerErrorInfo** son objetos de error de OLE DB personalizados; **ISQLServerErrorInfo** es la interfaz que se usa para obtener información de errores de servidor, incluidos detalles como el nombre del procedimiento y los números de línea.</span><span class="sxs-lookup"><span data-stu-id="e5005-107">(There is no need to obtain **ISQLErrorInfo.**) Both **ISQLErrorInfo** and **ISQLServerErrorInfo** are custom OLE DB error objects, with **ISQLServerErrorInfo** being the interface to use to obtain information of server errors, including such details as procedure name and line numbers.</span></span>  
  
```  
// Get the SQL Server custom error object.  
if(FAILED(hr=pIErrorRecords->GetCustomErrorObject(  
   nRec, IID_ISQLServerErrorInfo,  
   (IUnknown**)&pISQLServerErrorErrorInfo)))  
```  
  
 <span data-ttu-id="e5005-108">Otra manera de obtener un puntero **ISQLServerErrorInfo** consiste en llamar al método **QueryInterface** en un puntero **ISQLErrorInfo** ya obtenido.</span><span class="sxs-lookup"><span data-stu-id="e5005-108">Another way to get an **ISQLServerErrorInfo** pointer is to call the **QueryInterface** method on an already-obtained **ISQLErrorInfo** pointer.</span></span> <span data-ttu-id="e5005-109">Tenga en cuenta que, como **ISQLServerErrorInfo** contiene un superconjunto de la información disponible en **ISQLErrorInfo**, conviene pasar directamente a **ISQLServerErrorInfo** a través de **GetCustomerErrorObject**.</span><span class="sxs-lookup"><span data-stu-id="e5005-109">Note that because **ISQLServerErrorInfo** contains a superset of the information available from **ISQLErrorInfo**, it makes sense to go directly to **ISQLServerErrorInfo** through **GetCustomerErrorObject**.</span></span>  
  
 <span data-ttu-id="e5005-110">La interfaz **ISQLServerErrorInfo** expone una función miembro, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="e5005-110">The **ISQLServerErrorInfo** interface exposes one member function, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span></span> <span data-ttu-id="e5005-111">La función devuelve un puntero a una estructura SSERRORINFO y un puntero a un búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="e5005-111">The function returns a pointer to an SSERRORINFO structure and a pointer to a string buffer.</span></span> <span data-ttu-id="e5005-112">Ambos punteros hacen referencia a la memoria que el consumidor debe desasignar mediante el método **IMalloc::Free**.</span><span class="sxs-lookup"><span data-stu-id="e5005-112">Both pointers reference memory the consumer must deallocate by using the **IMalloc::Free** method.</span></span>  
  
 <span data-ttu-id="e5005-113">El consumidor interpreta los miembros de la estructura SSERRORINFO de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="e5005-113">SSERRORINFO structure members are interpreted by the consumer as follows.</span></span>  
  
|<span data-ttu-id="e5005-114">Miembro</span><span class="sxs-lookup"><span data-stu-id="e5005-114">Member</span></span>|<span data-ttu-id="e5005-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5005-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e5005-116">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="e5005-116">*pwszMessage*</span></span>|<span data-ttu-id="e5005-117">Mensaje de error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5005-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span> <span data-ttu-id="e5005-118">Idéntico a la cadena que se devuelve en **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="e5005-118">Identical to the string returned in **IErrorInfo::GetDescription**.</span></span>|  
|<span data-ttu-id="e5005-119">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="e5005-119">*pwszServer*</span></span>|<span data-ttu-id="e5005-120">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la sesión.</span><span class="sxs-lookup"><span data-stu-id="e5005-120">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the session.</span></span>|  
|<span data-ttu-id="e5005-121">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="e5005-121">*pwszProcedure*</span></span>|<span data-ttu-id="e5005-122">Si procede, nombre del procedimiento donde se ha producido el error.</span><span class="sxs-lookup"><span data-stu-id="e5005-122">If appropriate, the name of the procedure in which the error originated.</span></span> <span data-ttu-id="e5005-123">De lo contrario, una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="e5005-123">An empty string otherwise.</span></span>|  
|<span data-ttu-id="e5005-124">*lNative*</span><span class="sxs-lookup"><span data-stu-id="e5005-124">*lNative*</span></span>|<span data-ttu-id="e5005-125">Número del error nativo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5005-125">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native error number.</span></span> <span data-ttu-id="e5005-126">Idéntico al valor que se devuelve en el parámetro *plNativeError* de **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="e5005-126">Identical to the value returned in the *plNativeError* parameter of **ISQLErrorInfo::GetSQLInfo**.</span></span>|  
|<span data-ttu-id="e5005-127">*bState*</span><span class="sxs-lookup"><span data-stu-id="e5005-127">*bState*</span></span>|<span data-ttu-id="e5005-128">Estado de un mensaje de error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5005-128">State of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="e5005-129">*bClass*</span><span class="sxs-lookup"><span data-stu-id="e5005-129">*bClass*</span></span>|<span data-ttu-id="e5005-130">Gravedad de un mensaje de error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5005-130">Severity of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="e5005-131">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="e5005-131">*wLineNumber*</span></span>|<span data-ttu-id="e5005-132">Si procede, número de línea del procedimiento almacenado donde se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="e5005-132">When applicable, the line number of a stored procedure on which the error occurred.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5005-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5005-133">See Also</span></span>  
 <span data-ttu-id="e5005-134">[Posibles](errors.md) </span><span class="sxs-lookup"><span data-stu-id="e5005-134">[Errors](errors.md) </span></span>  
 [<span data-ttu-id="e5005-135">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5005-135">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
