---
title: Método GetReportServerUrls (MSReportServer_Instance de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetReportServerUrls method
ms.assetid: 4865e32c-0114-465a-be8c-be223a7bc09e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f36a5ba10c05276cffabc155e5289d675db8dae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746719"
---
# <a name="getreportserverurls-method-wmi-msreportserver_instance"></a><span data-ttu-id="2913d-102">Método GetReportServerUrls (WMI MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="2913d-102">GetReportServerUrls Method (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="2913d-103">Devuelve una lista de direcciones URL que los usuarios pueden utilizar para tener acceso al servidor de informes y al administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="2913d-103">Returns a list of URLs users can use to access the report server and report manager.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2913d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2913d-104">Syntax</span></span>  
  
```vb  
Public Sub GetReportServerUrls (ByRef ApplicationName() As String, ByRef URLs()_  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetReportServerUrls(out string[] applicationName,   
    out string[] URLs, out int length, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2913d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2913d-105">Parameters</span></span>  
 <span data-ttu-id="2913d-106">*ApplicationName[]*</span><span class="sxs-lookup"><span data-stu-id="2913d-106">*ApplicationName[]*</span></span>  
 <span data-ttu-id="2913d-107">Una matriz que contiene las aplicaciones instaladas.</span><span class="sxs-lookup"><span data-stu-id="2913d-107">An array that contains the applications that are installed.</span></span> <span data-ttu-id="2913d-108">Los valores son `ReportServerWebService` o `ReportManager`.</span><span class="sxs-lookup"><span data-stu-id="2913d-108">Values are either `ReportServerWebService` or `ReportManager`.</span></span>  
  
 <span data-ttu-id="2913d-109">*URLs[]*</span><span class="sxs-lookup"><span data-stu-id="2913d-109">*URLs[]*</span></span>  
 <span data-ttu-id="2913d-110">Una matriz que contiene las direcciones URL correctamente registradas.</span><span class="sxs-lookup"><span data-stu-id="2913d-110">An array that contains the successfully registered Urls.</span></span>  
  
 <span data-ttu-id="2913d-111">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="2913d-111">*Length*</span></span>  
 <span data-ttu-id="2913d-112">Un valor entero que contiene la longitud de las matrices devueltas.</span><span class="sxs-lookup"><span data-stu-id="2913d-112">An integer value that contains the length of the arrays returned.</span></span>  
  
 <span data-ttu-id="2913d-113">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="2913d-113">*HRESULT*</span></span>  
 <span data-ttu-id="2913d-114">Un valor que indica éxito o un código de error.</span><span class="sxs-lookup"><span data-stu-id="2913d-114">A value that indicates success or an error code.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="2913d-115">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="2913d-115">Return Values</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2913d-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2913d-116">Remarks</span></span>  
 <span data-ttu-id="2913d-117">Se llama a los métodos expuestos por objetos de administración de WMI mediante la función InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="2913d-117">Methods exposed by WMI management objects are called through the InvokeMethod function.</span></span> <span data-ttu-id="2913d-118">Para obtener más información, vea "Ejecutar métodos en objetos de administración" en la la documentación de WMI de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2913d-118">For more information, please see "Executing Methods on Management Objects" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework WMI documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2913d-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2913d-119">Requirements</span></span>  
 <span data-ttu-id="2913d-120">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2913d-120">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2913d-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2913d-121">See Also</span></span>  
 [<span data-ttu-id="2913d-122">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="2913d-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
