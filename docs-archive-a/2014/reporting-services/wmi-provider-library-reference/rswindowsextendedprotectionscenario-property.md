---
title: Propiedad RSWindowsExtendedProtectionScenario (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ac7ab80-9adf-4f65-abfa-fedf53b082b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84e14d056cc0352b0d1d85bc12c9c873a1b89ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747415"
---
# <a name="rswindowsextendedprotectionscenario-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="3fc77-102">Propiedad RSWindowsExtendedProtectionScenario (MSReportServer_ConfigurationSetting de WMI)</span><span class="sxs-lookup"><span data-stu-id="3fc77-102">RSWindowsExtendedProtectionScenario Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="3fc77-103">Devuelve un valor de cadena que indica el escenario de protección extendida que permite la configuración del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="3fc77-103">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fc77-104">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionScenario As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionScenario;  
```  
  
## <a name="remarks"></a><span data-ttu-id="3fc77-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3fc77-105">Remarks</span></span>  
 <span data-ttu-id="3fc77-106">Devuelve un valor de cadena que indica el escenario de protección extendida que permite la configuración del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="3fc77-106">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span> <span data-ttu-id="3fc77-107">Si el servidor de informes al que se conecta el proveedor de WMI no admite la protección extendida, se devuelve "" (cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="3fc77-107">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span>  
  
 <span data-ttu-id="3fc77-108">En la lista siguiente se muestran los valores válidos:</span><span class="sxs-lookup"><span data-stu-id="3fc77-108">The following list shows valid values:</span></span>  
  
 `"Any | Proxy | Direct"`  
  
## <a name="example-code"></a><span data-ttu-id="3fc77-109">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3fc77-109">Example Code</span></span>  
 [<span data-ttu-id="3fc77-110">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="3fc77-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="3fc77-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3fc77-111">See Also</span></span>  
 <span data-ttu-id="3fc77-112">[Propiedad RSWindowsExtendedProtectionLevel &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="3fc77-112">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="3fc77-113">[Método SetExtendedProtectionSettings &#40;MSReportServer_ConfigurationSetting de WMI&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="3fc77-113">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="3fc77-114">[Protección ampliada para la autenticación con Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="3fc77-114">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="3fc77-115">Archivo de configuración RSReportServer</span><span class="sxs-lookup"><span data-stu-id="3fc77-115">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
