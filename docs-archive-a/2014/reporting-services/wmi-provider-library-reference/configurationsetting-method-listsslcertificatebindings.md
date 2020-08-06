---
title: Método ListSSLCertificateBindings (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListSSLCertificateBindings method
ms.assetid: d12d280c-9b6f-47a8-bcd9-34cde31c8886
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56b19a138dc95b94a20183909dd444c90b158b26
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671896"
---
# <a name="listsslcertificatebindings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="a476d-102">Método ListSSLCertificateBindings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="a476d-102">ListSSLCertificateBindings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="a476d-103">Devuelve una lista de los certificados SSL instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a476d-103">Returns a list of installed SSL certificates on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a476d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a476d-104">Syntax</span></span>  
  
```vb  
Public Sub ListSSLCertificateBindings(ByVal LCID As Int32, ByRef Application() As String, _  
    ByRef CertificateHash() As String, ByRef IPAddresses() As String, ByRef Port() As Int32, _  
    ByRef Errors() As String, ByRef Length As Int32, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void ListSSLCertificateBindings(Int32 Lcid, out string[] Application,   
    out string[] CertificateHash,out string[] IPAddress,   
    out Int32[] Port, out string Errors,   
    out Int32 length, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a476d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a476d-105">Parameters</span></span>  
 <span data-ttu-id="a476d-106">*LCID*</span><span class="sxs-lookup"><span data-stu-id="a476d-106">*LCID*</span></span>  
 <span data-ttu-id="a476d-107">Configuración regional que se utilizará para los mensajes de error que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="a476d-107">The locale to use for the error messages that are returned.</span></span>  
  
 <span data-ttu-id="a476d-108">*Application[]*</span><span class="sxs-lookup"><span data-stu-id="a476d-108">*Application[]*</span></span>  
 <span data-ttu-id="a476d-109">[out] Aplicaciones que tienen enlaces de certificado.</span><span class="sxs-lookup"><span data-stu-id="a476d-109">[out] The applications that have certificate bindings.</span></span>  
  
 <span data-ttu-id="a476d-110">*CertificateHash[]*</span><span class="sxs-lookup"><span data-stu-id="a476d-110">*CertificateHash[]*</span></span>  
 <span data-ttu-id="a476d-111">[out] Valores hash para los certificados.</span><span class="sxs-lookup"><span data-stu-id="a476d-111">[out] The hashes for the certificates.</span></span>  
  
 <span data-ttu-id="a476d-112">*IPAddress[]*</span><span class="sxs-lookup"><span data-stu-id="a476d-112">*IPAddress[]*</span></span>  
 <span data-ttu-id="a476d-113">[out] Dirección IP para las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a476d-113">[out] The IP address for the applications.</span></span>  
  
 <span data-ttu-id="a476d-114">*Port[]*</span><span class="sxs-lookup"><span data-stu-id="a476d-114">*Port[]*</span></span>  
 <span data-ttu-id="a476d-115">[out] Número de puerto almacenado en el enlace en rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="a476d-115">[out] The port number stored in the binding in rsreportserver.config.</span></span>  
  
 <span data-ttu-id="a476d-116">*Errors[]*</span><span class="sxs-lookup"><span data-stu-id="a476d-116">*Errors[]*</span></span>  
 <span data-ttu-id="a476d-117">[out] Descripciones de los errores que se produjeron.</span><span class="sxs-lookup"><span data-stu-id="a476d-117">[out] The descriptions for errors that occurred.</span></span>  
  
 <span data-ttu-id="a476d-118">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="a476d-118">*Length*</span></span>  
 <span data-ttu-id="a476d-119">[out] Longitud de la matriz devuelta por el método.</span><span class="sxs-lookup"><span data-stu-id="a476d-119">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="a476d-120">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="a476d-120">*HRESULT*</span></span>  
 <span data-ttu-id="a476d-121">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="a476d-121">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a476d-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a476d-122">Return Value</span></span>  
 <span data-ttu-id="a476d-123">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="a476d-123">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="a476d-124">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a476d-124">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="a476d-125">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="a476d-125">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a476d-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a476d-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a476d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a476d-127">Requirements</span></span>  
 <span data-ttu-id="a476d-128">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a476d-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a476d-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a476d-129">See Also</span></span>  
 [<span data-ttu-id="a476d-130">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a476d-130">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
