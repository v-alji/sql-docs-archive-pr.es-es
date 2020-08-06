---
title: Información en interfaces de error | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
author: rothja
ms.author: jroth
ms.openlocfilehash: e9859ccbd804ba15685d84b98cbe74d4b096d98c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675838"
---
# <a name="information-in-error-interfaces"></a><span data-ttu-id="923bd-102">Información en interfaces de error</span><span class="sxs-lookup"><span data-stu-id="923bd-102">Information in Error Interfaces</span></span>
  <span data-ttu-id="923bd-103">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client notifica información de error y de estado en las interfaces de error definidas por el OLE DB **IErrorInfo**, **IErrorRecords**y **ISQLErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="923bd-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reports some error and status information in the OLE DB-defined error interfaces **IErrorInfo**, **IErrorRecords**, and **ISQLErrorInfo**.</span></span>  
  
 <span data-ttu-id="923bd-104">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite las funciones miembro de **IErrorInfo** como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="923bd-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IErrorInfo** member functions as follows.</span></span>  
  
|<span data-ttu-id="923bd-105">Función de miembro</span><span class="sxs-lookup"><span data-stu-id="923bd-105">Member function</span></span>|<span data-ttu-id="923bd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="923bd-106">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="923bd-107">**GetDescription**</span><span class="sxs-lookup"><span data-stu-id="923bd-107">**GetDescription**</span></span>|<span data-ttu-id="923bd-108">Cadena de mensaje de error descriptiva.</span><span class="sxs-lookup"><span data-stu-id="923bd-108">Descriptive error message string.</span></span>|  
|<span data-ttu-id="923bd-109">**GetGUID**</span><span class="sxs-lookup"><span data-stu-id="923bd-109">**GetGUID**</span></span>|<span data-ttu-id="923bd-110">GUID de la interfaz que definió el error.</span><span class="sxs-lookup"><span data-stu-id="923bd-110">GUID of the interface that defined the error.</span></span>|  
|<span data-ttu-id="923bd-111">**GetHelpContext**</span><span class="sxs-lookup"><span data-stu-id="923bd-111">**GetHelpContext**</span></span>|<span data-ttu-id="923bd-112">No compatible.</span><span class="sxs-lookup"><span data-stu-id="923bd-112">Not supported.</span></span> <span data-ttu-id="923bd-113">Siempre devuelve cero.</span><span class="sxs-lookup"><span data-stu-id="923bd-113">Always returns zero.</span></span>|  
|<span data-ttu-id="923bd-114">**GetHelpFile**</span><span class="sxs-lookup"><span data-stu-id="923bd-114">**GetHelpFile**</span></span>|<span data-ttu-id="923bd-115">No compatible.</span><span class="sxs-lookup"><span data-stu-id="923bd-115">Not supported.</span></span> <span data-ttu-id="923bd-116">Siempre devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="923bd-116">Always returns NULL.</span></span>|  
|<span data-ttu-id="923bd-117">**GetSource**</span><span class="sxs-lookup"><span data-stu-id="923bd-117">**GetSource**</span></span>|<span data-ttu-id="923bd-118">Cadena "Microsoft SQL Server Native Client".</span><span class="sxs-lookup"><span data-stu-id="923bd-118">String "Microsoft SQL Server Native Client".</span></span>|  
  
 <span data-ttu-id="923bd-119">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client es compatible con las funciones miembro de **IErrorRecords** disponibles para el consumidor como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="923bd-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports consumer-available **IErrorRecords** member functions as follows.</span></span>  
  
|<span data-ttu-id="923bd-120">Función de miembro</span><span class="sxs-lookup"><span data-stu-id="923bd-120">Member function</span></span>|<span data-ttu-id="923bd-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="923bd-121">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="923bd-122">**GetBasicErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="923bd-122">**GetBasicErrorInfo**</span></span>|<span data-ttu-id="923bd-123">Llena una estructura ERRORINFO con información básica acerca de un error.</span><span class="sxs-lookup"><span data-stu-id="923bd-123">Fills an ERRORINFO structure with basic information about an error.</span></span> <span data-ttu-id="923bd-124">Una estructura ERRORINFO contiene miembros que identifican el valor devuelto HRESULT del error así como el proveedor y la interfaz a los que se aplica el error.</span><span class="sxs-lookup"><span data-stu-id="923bd-124">An ERRORINFO structure contains members that identify the HRESULT return value for the error, and the provider and interface to which the error applies.</span></span>|  
|<span data-ttu-id="923bd-125">**GetCustomErrorObject**</span><span class="sxs-lookup"><span data-stu-id="923bd-125">**GetCustomErrorObject**</span></span>|<span data-ttu-id="923bd-126">Devuelve una referencia en las interfaces **ISQLErrorInfo** e [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="923bd-126">Returns a reference on interfaces **ISQLErrorInfo,** and [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span>|  
|<span data-ttu-id="923bd-127">**GetErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="923bd-127">**GetErrorInfo**</span></span>|<span data-ttu-id="923bd-128">Devuelve una referencia en una interfaz **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="923bd-128">Returns a reference on an **IErrorInfo** interface.</span></span>|  
|<span data-ttu-id="923bd-129">**GetErrorParameters**</span><span class="sxs-lookup"><span data-stu-id="923bd-129">**GetErrorParameters**</span></span>|<span data-ttu-id="923bd-130">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client no devuelve parámetros al consumidor a través de **GetErrorParameters**.</span><span class="sxs-lookup"><span data-stu-id="923bd-130">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not return parameters to the consumer through **GetErrorParameters**.</span></span>|  
|<span data-ttu-id="923bd-131">**GetRecordCount**</span><span class="sxs-lookup"><span data-stu-id="923bd-131">**GetRecordCount**</span></span>|<span data-ttu-id="923bd-132">Recuento de registros de error disponibles.</span><span class="sxs-lookup"><span data-stu-id="923bd-132">Count of error records available.</span></span>|  
  
 <span data-ttu-id="923bd-133">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client admite los parámetros **ISQLErrorInfo:: GetSQLInfo** como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="923bd-133">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ISQLErrorInfo::GetSQLInfo** parameters as follows.</span></span>  
  
|<span data-ttu-id="923bd-134">Parámetro</span><span class="sxs-lookup"><span data-stu-id="923bd-134">Parameter</span></span>|<span data-ttu-id="923bd-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="923bd-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="923bd-136">*pbstrSQLState*</span><span class="sxs-lookup"><span data-stu-id="923bd-136">*pbstrSQLState*</span></span>|<span data-ttu-id="923bd-137">Devuelve un valor SQLSTATE para el error.</span><span class="sxs-lookup"><span data-stu-id="923bd-137">Returns a SQLSTATE value for the error.</span></span> <span data-ttu-id="923bd-138">Los valores SQLSTATE se definen en las especificaciones SQL 92, ODBC e ISO SQL y API.</span><span class="sxs-lookup"><span data-stu-id="923bd-138">SQLSTATE values are defined in the SQL-92, ODBC and ISO SQL, and API specifications.</span></span> <span data-ttu-id="923bd-139">Ni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ni el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client definen los valores SQLSTATE específicos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="923bd-139">Neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defined implementation-specific SQLSTATE values.</span></span>|  
|<span data-ttu-id="923bd-140">*plNativeError*</span><span class="sxs-lookup"><span data-stu-id="923bd-140">*plNativeError*</span></span>|<span data-ttu-id="923bd-141">Devuelve el número de error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procedente de **master.dbo.sysmessages** cuando está disponible.</span><span class="sxs-lookup"><span data-stu-id="923bd-141">Returns the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number from **master.dbo.sysmessages** when available.</span></span> <span data-ttu-id="923bd-142">Los errores nativos están disponibles después de un intento correcto de inicializar un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] origen de datos del proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="923bd-142">Native errors are available after a successful attempt to initialize a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source.</span></span> <span data-ttu-id="923bd-143">Antes del intento, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client siempre devuelve cero.</span><span class="sxs-lookup"><span data-stu-id="923bd-143">Prior to the attempt, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider always returns zero.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="923bd-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="923bd-144">See Also</span></span>  
 [<span data-ttu-id="923bd-145">Errores</span><span class="sxs-lookup"><span data-stu-id="923bd-145">Errors</span></span>](errors.md)  
  
  
