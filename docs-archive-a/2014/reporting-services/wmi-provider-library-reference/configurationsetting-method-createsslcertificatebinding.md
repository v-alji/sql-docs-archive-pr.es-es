---
title: Método CreateSSLCertificateBinding (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- CreateSSLCertificateBinding
ms.assetid: 407d50e4-0a55-43cb-8ddf-2d82714071b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b9a5f9394d655f7b0592ea688a46f3ac2b9c153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671924"
---
# <a name="createsslcertificatebinding-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="37695-102">Método CreateSSLCertificateBinding (MSReportServer_ConfigurationSetting de WMI)</span><span class="sxs-lookup"><span data-stu-id="37695-102">CreateSSLCertificateBinding Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="37695-103">Crea un enlace de certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="37695-103">Creates an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37695-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37695-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void CreateSSLCertificateBinding(string application,   
    string certificateHash, string IPAddress, int Port,   
    int lcid, out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37695-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37695-105">Parameters</span></span>  
 <span data-ttu-id="37695-106">*Aplicación*</span><span class="sxs-lookup"><span data-stu-id="37695-106">*Application*</span></span>  
 <span data-ttu-id="37695-107">Nombre de la aplicación para la que se debe crear el enlace de certificado.</span><span class="sxs-lookup"><span data-stu-id="37695-107">The name of application that the certificate binding should be created for.</span></span>  
  
 <span data-ttu-id="37695-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="37695-108">*CertificateHash*</span></span>  
 <span data-ttu-id="37695-109">Valor hash del certificado.</span><span class="sxs-lookup"><span data-stu-id="37695-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="37695-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="37695-110">*IPAddress*</span></span>  
 <span data-ttu-id="37695-111">Dirección IP para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37695-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="37695-112">*Puerto*</span><span class="sxs-lookup"><span data-stu-id="37695-112">*Port*</span></span>  
 <span data-ttu-id="37695-113">Puerto SSL asociado al enlace.</span><span class="sxs-lookup"><span data-stu-id="37695-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="37695-114">*Lcid*</span><span class="sxs-lookup"><span data-stu-id="37695-114">*Lcid*</span></span>  
 <span data-ttu-id="37695-115">Configuración regional que se utilizará para los mensajes de error devueltos.</span><span class="sxs-lookup"><span data-stu-id="37695-115">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="37695-116">*Error*</span><span class="sxs-lookup"><span data-stu-id="37695-116">*Error*</span></span>  
 <span data-ttu-id="37695-117">[out] Descripción de los errores que se produjeron.</span><span class="sxs-lookup"><span data-stu-id="37695-117">[out] The description of the errors that occurred.</span></span>  
  
 <span data-ttu-id="37695-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="37695-118">*HRESULT*</span></span>  
 <span data-ttu-id="37695-119">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="37695-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37695-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="37695-120">Return Value</span></span>  
 <span data-ttu-id="37695-121">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="37695-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="37695-122">Un valor de 0 indica que la llamada al método se realizó correctamente; un código de error indica que la llamada no se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="37695-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37695-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37695-123">Remarks</span></span>  
 <span data-ttu-id="37695-124">Este método agrega un enlace a rsreportserver.config para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37695-124">This method adds a binding to rsreportserver.config for the application.</span></span> <span data-ttu-id="37695-125">Si no existe todavía un enlace en HTTP.SYS, se crea ahí.</span><span class="sxs-lookup"><span data-stu-id="37695-125">If a binding does not already exist in HTTP.SYS, it is created there.</span></span>  
  
 <span data-ttu-id="37695-126">Antes de crear el enlace, la llamada al método examina las reservas de direcciones URL para la aplicación especificada con el fin de determinar si el enlace de certificado SSL es válido.</span><span class="sxs-lookup"><span data-stu-id="37695-126">Before creating the binding, the method call examines the Url Reservations for the specified application to determine if the SSL Certificate Binding is valid.</span></span>  
  
 <span data-ttu-id="37695-127">Las condiciones siguientes se validan y pueden dar lugar a errores:</span><span class="sxs-lookup"><span data-stu-id="37695-127">The following conditions are validated and can result in errors:</span></span>  
  
1.  <span data-ttu-id="37695-128">El certificado no existe.</span><span class="sxs-lookup"><span data-stu-id="37695-128">Certificate does not exist.</span></span>  
  
2.  <span data-ttu-id="37695-129">La dirección IP especificada no corresponde a una dirección IP de este equipo.</span><span class="sxs-lookup"><span data-stu-id="37695-129">The IPAddress specified does not correspond to an IPAddress of this computer.</span></span>  
  
3.  <span data-ttu-id="37695-130">La dirección IP especificada es una dirección IP para DHCP (cambia periódicamente): en su lugar, use la dirección IP con un carácter comodín (0.0.0.0).</span><span class="sxs-lookup"><span data-stu-id="37695-130">The IPAddress specified is a DHCP IPAddress (changes periodically) - use the Wildcard IP address instead (0.0.0.0).</span></span>  
  
4.  <span data-ttu-id="37695-131">La dirección IP especificada no coincide con la dirección IP de una reserva de dirección URL y no existe una reserva de dirección URL de nombre de host o con un carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="37695-131">IPAddress specified does not match the IP address of a URL reservations AND neither a wildcard or host name URL reservation exist.</span></span>  
  
5.  <span data-ttu-id="37695-132">Existe una reserva de dirección URL que especifica un nombre de host, pero el nombre de host no coincide con el nombre de host del certificado.</span><span class="sxs-lookup"><span data-stu-id="37695-132">A URL reservation that specifies a host name exists, but the host name does not match the certificate host name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37695-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37695-133">Requirements</span></span>  
 <span data-ttu-id="37695-134">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37695-134">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37695-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37695-135">See Also</span></span>  
 [<span data-ttu-id="37695-136">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="37695-136">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
