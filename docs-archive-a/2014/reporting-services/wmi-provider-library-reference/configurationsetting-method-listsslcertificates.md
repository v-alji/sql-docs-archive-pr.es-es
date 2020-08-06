---
title: Método ListSSLCertificates (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListSSLCertificates method
ms.assetid: 88cd0936-b202-4ab8-90f2-d9c3f66d37f4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a5ced8371817adc44bbbc89400dc83e0dfccef0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671893"
---
# <a name="listsslcertificates-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="d07ea-102">Método ListSSLCertificates (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="d07ea-102">ListSSLCertificates Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="d07ea-103">Devuelve una lista de certificados en el equipo del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d07ea-103">Returns a list of certificates on the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d07ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d07ea-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding (ByRef CertificateHash() as String, _  
    ByRef CertName() as String, ByRef HostName() as String, ByRef Length as Int32, _   
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListSSLCertificates(out string[] CertificateHash,   
    out string[] CertName, out string[] Hostname, out Int32 length,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d07ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d07ea-105">Parameters</span></span>  
 <span data-ttu-id="d07ea-106">*CertificateHash[]*</span><span class="sxs-lookup"><span data-stu-id="d07ea-106">*CertificateHash[]*</span></span>  
 <span data-ttu-id="d07ea-107">[out] Valores hash del certificado.</span><span class="sxs-lookup"><span data-stu-id="d07ea-107">[out] The certificate hashes.</span></span>  
  
 <span data-ttu-id="d07ea-108">*CertName[]*</span><span class="sxs-lookup"><span data-stu-id="d07ea-108">*CertName[]*</span></span>  
 <span data-ttu-id="d07ea-109">[out] Nombres del certificado.</span><span class="sxs-lookup"><span data-stu-id="d07ea-109">[out] Names of the certificate.</span></span>  
  
 <span data-ttu-id="d07ea-110">*HostName[]*</span><span class="sxs-lookup"><span data-stu-id="d07ea-110">*HostName[]*</span></span>  
 <span data-ttu-id="d07ea-111">[out] Nombres de host para los certificados.</span><span class="sxs-lookup"><span data-stu-id="d07ea-111">[out] The host names for the certificates.</span></span>  
  
 <span data-ttu-id="d07ea-112">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="d07ea-112">*Length*</span></span>  
 <span data-ttu-id="d07ea-113">[out] Representa la longitud de las matrices *CertificateHash*, *CertName* y *HostName* .</span><span class="sxs-lookup"><span data-stu-id="d07ea-113">[out] Represents the length of the *CertificateHash*, *CertName* and *HostName* arrays.</span></span>  
  
 <span data-ttu-id="d07ea-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="d07ea-114">*HRESULT*</span></span>  
 <span data-ttu-id="d07ea-115">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="d07ea-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d07ea-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d07ea-116">Return Value</span></span>  
 <span data-ttu-id="d07ea-117">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="d07ea-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="d07ea-118">Un valor de 0 indica que la llamada al método se realizó correctamente; un código de error indica que la llamada no se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d07ea-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d07ea-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d07ea-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d07ea-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d07ea-120">Requirements</span></span>  
 <span data-ttu-id="d07ea-121">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d07ea-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d07ea-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d07ea-122">See Also</span></span>  
 [<span data-ttu-id="d07ea-123">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d07ea-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
