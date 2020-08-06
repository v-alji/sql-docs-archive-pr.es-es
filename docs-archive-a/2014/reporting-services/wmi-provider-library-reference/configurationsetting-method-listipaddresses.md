---
title: Método ListIPAddresses (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListIPAddresses method
ms.assetid: 7e7cf182-fba0-4604-a474-098461e23e9d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 845f7ba7db02a0b860f966184463580733af0faf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671905"
---
# <a name="listipaddresses-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="23364-102">Método ListIPAddresses (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="23364-102">ListIPAddresses Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="23364-103">Enumera las direcciones IP para el equipo del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="23364-103">Lists the IP addresses for the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23364-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23364-104">Syntax</span></span>  
  
```vb  
Public Sub ListIPAddresses (ByRef IPAddress() as String, _  
    ByRef IPVersion()as String, ByRef IsDhcpEnabled () as Boolean, _   
    ByRef Length as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListIPAddresses (out string[] IPAddress,   
    out string[] IPVersion, out bool[] isDhcpEnabled, out int length,   
    out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23364-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23364-105">Parameters</span></span>  
 <span data-ttu-id="23364-106">*IPAddress[]*</span><span class="sxs-lookup"><span data-stu-id="23364-106">*IPAddress[]*</span></span>  
 <span data-ttu-id="23364-107">[fuera] Lista de dirección IP para el equipo.</span><span class="sxs-lookup"><span data-stu-id="23364-107">[out] The list of IP address for the computer.</span></span>  
  
 <span data-ttu-id="23364-108">*IPVersion[]*</span><span class="sxs-lookup"><span data-stu-id="23364-108">*IPVersion[]*</span></span>  
 <span data-ttu-id="23364-109">[out] Versión para las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="23364-109">[out] The version for the IP addresses.</span></span>  
  
 <span data-ttu-id="23364-110">*IsDhcpEnabled[]*</span><span class="sxs-lookup"><span data-stu-id="23364-110">*IsDhcpEnabled[]*</span></span>  
 <span data-ttu-id="23364-111">[out] Indica si las direcciones IP tienen DHCP habilitado.</span><span class="sxs-lookup"><span data-stu-id="23364-111">[out] Indicates whether the IP addresses are DHCP enabled.</span></span>  
  
 <span data-ttu-id="23364-112">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="23364-112">*Length*</span></span>  
 <span data-ttu-id="23364-113">[out] Longitud de la matriz devuelta por el método.</span><span class="sxs-lookup"><span data-stu-id="23364-113">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="23364-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="23364-114">*HRESULT*</span></span>  
 <span data-ttu-id="23364-115">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="23364-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23364-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="23364-116">Return Value</span></span>  
 <span data-ttu-id="23364-117">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="23364-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="23364-118">Un valor de 0 indica que la llamada al método se realizó correctamente; un código de error indica que la llamada no se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="23364-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23364-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="23364-119">Remarks</span></span>  
 <span data-ttu-id="23364-120">Las cadenas de*IPVersion* son V4 y V6.</span><span class="sxs-lookup"><span data-stu-id="23364-120">*IPVersion* strings are V4, V6.</span></span>  
  
 <span data-ttu-id="23364-121">Si *IsDhcpEnabled* es `True` , la *dirección IP* es dinámica.</span><span class="sxs-lookup"><span data-stu-id="23364-121">If *IsDhcpEnabled* is `True`, the *IPAddress* is dynamic.</span></span> <span data-ttu-id="23364-122">No se debe usar para enlaces SSL.</span><span class="sxs-lookup"><span data-stu-id="23364-122">It should not be used for SSL bindings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23364-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23364-123">Requirements</span></span>  
 <span data-ttu-id="23364-124">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23364-124">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23364-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23364-125">See Also</span></span>  
 [<span data-ttu-id="23364-126">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="23364-126">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
