---
title: Método RemoveSSLCertificateBindings (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveSSLCertificateBindings method
ms.assetid: b8b484c9-04c4-4ae9-980e-67bbe5aa8481
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d42d17d9c92f2e100a7800e607536ff6c7eab891
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747925"
---
# <a name="removesslcertificatebindings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="dfa29-102">Método RemoveSSLCertificateBindings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="dfa29-102">RemoveSSLCertificateBindings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="dfa29-103">Quita un enlace de certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="dfa29-103">Removes an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfa29-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfa29-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveSSLCertificateBindings(string Application,  
    string CertificateHash, string IPAddress, Int32 Port, Int32 Lcid,  
    out string Error, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfa29-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dfa29-105">Parameters</span></span>  
 <span data-ttu-id="dfa29-106">*Aplicación*</span><span class="sxs-lookup"><span data-stu-id="dfa29-106">*Application*</span></span>  
 <span data-ttu-id="dfa29-107">El nombre de la aplicación para la que se debería quitar el enlace de certificado.</span><span class="sxs-lookup"><span data-stu-id="dfa29-107">The name of application for which the certificate binding should be removed.</span></span>  
  
 <span data-ttu-id="dfa29-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="dfa29-108">*CertificateHash*</span></span>  
 <span data-ttu-id="dfa29-109">Valor hash del certificado.</span><span class="sxs-lookup"><span data-stu-id="dfa29-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="dfa29-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="dfa29-110">*IPAddress*</span></span>  
 <span data-ttu-id="dfa29-111">Dirección IP para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dfa29-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="dfa29-112">*Puerto*</span><span class="sxs-lookup"><span data-stu-id="dfa29-112">*Port*</span></span>  
 <span data-ttu-id="dfa29-113">Puerto SSL asociado al enlace.</span><span class="sxs-lookup"><span data-stu-id="dfa29-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="dfa29-114">*lcid*</span><span class="sxs-lookup"><span data-stu-id="dfa29-114">*lcid*</span></span>  
 <span data-ttu-id="dfa29-115">Configuración regional que se utilizará para los mensajes de error que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="dfa29-115">The locale to use for the error messages that are returned.</span></span>  
  
 <span data-ttu-id="dfa29-116">*Error*</span><span class="sxs-lookup"><span data-stu-id="dfa29-116">*Error*</span></span>  
 <span data-ttu-id="dfa29-117">[out] Descripción del error que se produjo.</span><span class="sxs-lookup"><span data-stu-id="dfa29-117">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="dfa29-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="dfa29-118">*HRESULT*</span></span>  
 <span data-ttu-id="dfa29-119">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="dfa29-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfa29-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dfa29-120">Return Value</span></span>  
 <span data-ttu-id="dfa29-121">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="dfa29-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="dfa29-122">Un valor de 0 indica que la llamada al método se realizó correctamente; un código de error indica que la llamada no se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="dfa29-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfa29-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dfa29-123">Remarks</span></span>  
 <span data-ttu-id="dfa29-124">Este método quita el enlace específico del archivo rsreportserver.config y opcionalmente HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="dfa29-124">This method removes the specific binding from the rsreportserver.config file and optionally HTTP.SYS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfa29-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfa29-125">Requirements</span></span>  
 <span data-ttu-id="dfa29-126">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfa29-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa29-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dfa29-127">See Also</span></span>  
 [<span data-ttu-id="dfa29-128">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="dfa29-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
