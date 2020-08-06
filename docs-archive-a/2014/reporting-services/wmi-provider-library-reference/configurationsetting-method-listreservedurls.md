---
title: Método ListReservedURLs (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListReservedURLs method
ms.assetid: 32335af1-5eae-4420-a0ef-b1e8a3267166
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7639741adb0c756961c4c6b63a3bffb627c4a89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671902"
---
# <a name="listreservedurls-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="c3bd3-102">Método ListReservedURLs (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="c3bd3-102">ListReservedURLs Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="c3bd3-103">Enumera las direcciones URL reservadas para todas las aplicaciones en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-103">Lists URLs reserved for all applications on the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3bd3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3bd3-104">Syntax</span></span>  
  
```vb  
Public Sub ListReservedUrls(ByRef Application() as String, ByRef UrlString() as String, _  
    ByRef Account() as String, ByRef AccountSID() as String, _  
    ByRef length() as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListReservedUrls(out string[] Application, out string[] UrlString,  
        out string[] Account, out string[] AccountSID,  
        out int[] Length, out int[] HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3bd3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3bd3-105">Parameters</span></span>  
 <span data-ttu-id="c3bd3-106">*Application[]*</span><span class="sxs-lookup"><span data-stu-id="c3bd3-106">*Application[]*</span></span>  
 <span data-ttu-id="c3bd3-107">[out] Aplicaciones que tienen reservas de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-107">[out] The applications that have URL reservations.</span></span>  
  
 <span data-ttu-id="c3bd3-108">*UrlString[]*</span><span class="sxs-lookup"><span data-stu-id="c3bd3-108">*UrlString[]*</span></span>  
 <span data-ttu-id="c3bd3-109">[out] Direcciones URL reservadas.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-109">[out] The URLs that are reserved.</span></span>  
  
 <span data-ttu-id="c3bd3-110">*Account[]*</span><span class="sxs-lookup"><span data-stu-id="c3bd3-110">*Account[]*</span></span>  
 <span data-ttu-id="c3bd3-111">[out] Nombres de cuenta asociados a la cuenta para las reservas de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-111">[out] The account names associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="c3bd3-112">*AccountSID[]*</span><span class="sxs-lookup"><span data-stu-id="c3bd3-112">*AccountSID[]*</span></span>  
 <span data-ttu-id="c3bd3-113">[out] Los SID de cuenta asociados con la cuenta para las reservas URL.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-113">[out] The account SIDs associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="c3bd3-114">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="c3bd3-114">*Length*</span></span>  
 <span data-ttu-id="c3bd3-115">[out] La longitud de las matrices devueltas por el método.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-115">[out] The length of the arrays returned by the method.</span></span>  
  
 <span data-ttu-id="c3bd3-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="c3bd3-116">*HRESULT*</span></span>  
 <span data-ttu-id="c3bd3-117">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3bd3-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c3bd3-118">Return Value</span></span>  
 <span data-ttu-id="c3bd3-119">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="c3bd3-120">Un valor de 0 indica que la llamada al método se realizó correctamente; un código de error indica que la llamada no se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3bd3-120">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3bd3-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c3bd3-121">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3bd3-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3bd3-122">Requirements</span></span>  
 <span data-ttu-id="c3bd3-123">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3bd3-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3bd3-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3bd3-124">See Also</span></span>  
 [<span data-ttu-id="c3bd3-125">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="c3bd3-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
