---
title: Propiedad RSWindowsExtendedProtectionLevel (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 162ffe86-69c3-49d2-b9ed-49d097c05551
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02ff3bad42ae25adf6cfa563944d89bac2c600e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671888"
---
# <a name="rswindowsextendedprotectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="31fc1-102">Propiedad RSWindowsExtendedProtectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="31fc1-102">RSWindowsExtendedProtectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="31fc1-103">Devuelve un valor de cadena que indica el nivel de protección con que se ha configurado el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="31fc1-103">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="31fc1-104">Esta propiedad es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="31fc1-104">This property is read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31fc1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31fc1-105">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionLevel As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionLevel;  
```  
  
## <a name="remarks"></a><span data-ttu-id="31fc1-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="31fc1-106">Remarks</span></span>  
 <span data-ttu-id="31fc1-107">Devuelve un valor de cadena que indica el nivel de protección con que se ha configurado el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="31fc1-107">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="31fc1-108">Si el servidor de informes al que se conecta el proveedor de WMI no admite la protección extendida, se devuelve "" (cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="31fc1-108">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span> <span data-ttu-id="31fc1-109">En la lista siguiente se muestran los valores válidos:</span><span class="sxs-lookup"><span data-stu-id="31fc1-109">The following list shows valid values:</span></span>  
  
 `"Off" | "Allow" | "Require"`  
  
## <a name="example-code"></a><span data-ttu-id="31fc1-110">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="31fc1-110">Example Code</span></span>  
 [<span data-ttu-id="31fc1-111">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="31fc1-111">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="31fc1-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31fc1-112">See Also</span></span>  
 <span data-ttu-id="31fc1-113">[Propiedad RSWindowsExtendedProtectionScenario &#40;MSReportServer_ConfigurationSetting de WMI&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="31fc1-113">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="31fc1-114">[Método SetExtendedProtectionSettings &#40;MSReportServer_ConfigurationSetting de WMI&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="31fc1-114">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="31fc1-115">[Protección ampliada para la autenticación con Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="31fc1-115">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="31fc1-116">Archivo de configuración RSReportServer</span><span class="sxs-lookup"><span data-stu-id="31fc1-116">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
