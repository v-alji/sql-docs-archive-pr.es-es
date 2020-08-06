---
title: Errores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- OLE/COM errors
- errors [OLE DB]
- OLE DB error handling, about error handling
- OLE DB error handling
ms.assetid: bd0612f4-96ef-4919-b0f9-b5447210fe93
author: rothja
ms.author: jroth
ms.openlocfilehash: 0560a31b60a10e278f621aa53f1c7fa038fe8039
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675842"
---
# <a name="errors"></a><span data-ttu-id="30080-102">Errors</span><span class="sxs-lookup"><span data-stu-id="30080-102">Errors</span></span>
  <span data-ttu-id="30080-103">Los objetos OLE/COM notifican errores a través del código de retorno HRESULT de funciones de miembro de objeto.</span><span class="sxs-lookup"><span data-stu-id="30080-103">OLE/COM objects report errors through the HRESULT return code of object member functions.</span></span> <span data-ttu-id="30080-104">Una estructura OLE/COM HRESULT es una estructura empaquetada de bits.</span><span class="sxs-lookup"><span data-stu-id="30080-104">An OLE/COM HRESULT is a bit-packed structure.</span></span> <span data-ttu-id="30080-105">OLE proporciona macros que eliminan referencias a los miembros de la estructura.</span><span class="sxs-lookup"><span data-stu-id="30080-105">OLE provides macros that dereference structure members.</span></span>  
  
 <span data-ttu-id="30080-106">OLE/COM especifica la interfaz **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="30080-106">OLE/COM specifies the **IErrorInfo** interface.</span></span> <span data-ttu-id="30080-107">La interfaz expone métodos como **GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="30080-107">The interface exposes methods such as **GetDescription**.</span></span> <span data-ttu-id="30080-108">Esto permite a los clientes extraer detalles de error de servidores OLE/COM.</span><span class="sxs-lookup"><span data-stu-id="30080-108">This allows clients to extract error details from OLE/COM servers.</span></span> <span data-ttu-id="30080-109">OLE DB extiende **IErrorInfo** para admitir el retorno de varios paquetes de información de error en una ejecución de función de miembro único.</span><span class="sxs-lookup"><span data-stu-id="30080-109">OLE DB extends **IErrorInfo** to support the return of multiple error information packets on a single-member function execution.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="30080-110">puede devolver varios errores.</span><span class="sxs-lookup"><span data-stu-id="30080-110">can return multiple errors.</span></span> <span data-ttu-id="30080-111">Una aplicación puede recuperar los errores de servidor de uno en uno mediante una llamada a [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) combinada con ISQLErrorInfo e IErrorRecords.</span><span class="sxs-lookup"><span data-stu-id="30080-111">An application can retrieve server errors one at a time by calling [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) combined with ISQLErrorInfo and IErrorRecords.</span></span>  
  
 <span data-ttu-id="30080-112">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client expone las interfaces de los **IErrorInfo**objetos de error de ISQLServerErrorInfo, el objeto personalizado, el personalizado y el proveedor de errores de registro de OLE DB mejorado `ISQLErrorInfo` . [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md)</span><span class="sxs-lookup"><span data-stu-id="30080-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the OLE DB record-enhanced **IErrorInfo**, the custom `ISQLErrorInfo`, and the provider-specific [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) error object interfaces.</span></span>  
  
 <span data-ttu-id="30080-113">Para obtener información sobre cómo realizar un seguimiento de los errores, vea [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805) (Seguimiento de acceso a datos).</span><span class="sxs-lookup"><span data-stu-id="30080-113">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="30080-114">Para información sobre las mejoras en el seguimiento de errores agregadas en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], consulte [Acceso a información de diagnóstico en el registro de eventos extendidos](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="30080-114">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30080-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="30080-115">In This Section</span></span>  
  
-   [<span data-ttu-id="30080-116">Códigos de retorno</span><span class="sxs-lookup"><span data-stu-id="30080-116">Return Codes</span></span>](return-codes.md)  
  
-   [<span data-ttu-id="30080-117">Información en interfaces de error</span><span class="sxs-lookup"><span data-stu-id="30080-117">Information in Error Interfaces</span></span>](information-in-error-interfaces.md)  
  
-   [<span data-ttu-id="30080-118">Detalle del error de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30080-118">SQL Server Error Detail</span></span>](sql-server-error-detail.md)  
  
-   [<span data-ttu-id="30080-119">Recuperar información sobre errores</span><span class="sxs-lookup"><span data-stu-id="30080-119">Retrieving Error Information</span></span>](retrieving-error-information.md)  
  
-   [<span data-ttu-id="30080-120">Resultados del mensaje de SQL Server</span><span class="sxs-lookup"><span data-stu-id="30080-120">SQL Server Message Results</span></span>](sql-server-message-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="30080-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30080-121">See Also</span></span>  
 [<span data-ttu-id="30080-122">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="30080-122">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
