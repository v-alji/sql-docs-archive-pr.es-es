---
title: Método SetExtendedProtectionSettings (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d8e7232-42f4-41b6-98eb-c856f6c85d8c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ee937747b74bcf8d53012721b4be5bfca04185df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748572"
---
# <a name="setextendedprotectionsettings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="94e2a-102">Método SetExtendedProtectionSettings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="94e2a-102">SetExtendedProtectionSettings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="94e2a-103">El método SetExtendedProtectionSettings se utiliza para establecer las propiedades RSWindowsExtendedProtectionScenario y RSWindowsExtendedProtectionLevel en el archivo de configuración RSReportServer.config de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94e2a-103">The SetExtendedProtectionSettings method is used to set the RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration file RSReportServer.config.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e2a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94e2a-104">Syntax</span></span>  
  
```vb  
Public Sub SetExtendedProtectionSettings( _  
        ByVal ExtendedProtectionLevel As String, _  
        ByVal ExtendedProtectionScenario As String, _  
        ByRef Warnings() As String, _  
        ByRef Length As Int32, _  
        ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetExtendedProtectionSettings(  
            string ExtendedProtectionLevel,  
            string ExtendedProtectionScenario,  
            out string[] Warnings,  
            out Int32 Length,  
            out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94e2a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94e2a-105">Parameters</span></span>  
 <span data-ttu-id="94e2a-106">*ExtendedProtectionLevel*</span><span class="sxs-lookup"><span data-stu-id="94e2a-106">*ExtendedProtectionLevel*</span></span>  
 <span data-ttu-id="94e2a-107">Establece el RSWindowsExtendedProtectionLevel en el archivo RSRreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="94e2a-107">Sets the RSWindowsExtendedProtectionLevel in the RSRreportserver.config file.</span></span> <span data-ttu-id="94e2a-108">El valor es obligatorio y no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="94e2a-108">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="94e2a-109">En la lista siguiente se muestran los valores válidos:</span><span class="sxs-lookup"><span data-stu-id="94e2a-109">The following list shows valid values:</span></span>  
  
 `"Off | Allow | Require"`  
  
 <span data-ttu-id="94e2a-110">*ExtendedProtectionScenario*</span><span class="sxs-lookup"><span data-stu-id="94e2a-110">*ExtendedProtectionScenario*</span></span>  
 <span data-ttu-id="94e2a-111">Establece el RSWindowsExtendedProtectionScenario en el archivo RSReportserver.config.</span><span class="sxs-lookup"><span data-stu-id="94e2a-111">Sets the RSWindowsExtendedProtectionScenario in the RSReportserver.config file.</span></span> <span data-ttu-id="94e2a-112">El valor es obligatorio y no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="94e2a-112">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="94e2a-113">En la lista siguiente se muestran los valores válidos:</span><span class="sxs-lookup"><span data-stu-id="94e2a-113">The following list shows valid values:</span></span>  
  
 `"Any" | "Proxy" | "Direct"`  
  
## <a name="remarks"></a><span data-ttu-id="94e2a-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="94e2a-114">Remarks</span></span>  
 <span data-ttu-id="94e2a-115">Las propiedades RSWindowsExtendedProtectionLevel y RSWindowsExtendedProtectionScenario se aplican cuando AuthenticationTypes del archivo RSReportServer.config incluye RSWindowNTLM, RSWindowsNegotiate o RSWindowsKerberos.</span><span class="sxs-lookup"><span data-stu-id="94e2a-115">The RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties apply when the AuthenticationTypes in the RSReportServer.config file include RSWindowNTLM, RSWindowsNegotiate, or RSWindowsKerberos.</span></span> <span data-ttu-id="94e2a-116">El establecimiento de estas propiedades afecta a cómo los usuarios y el software cliente se autentican con un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="94e2a-116">Setting these properties affects how users and client software authenticate with a report server.</span></span> <span data-ttu-id="94e2a-117">Se recomienda leer la documentación sobre protección extendida antes de establecer ExtendedProtectionLevel en `Allow` o `Require`.</span><span class="sxs-lookup"><span data-stu-id="94e2a-117">It is recommended that you read the documentation for extended protection before setting ExtendedProtectionLevel to either `Allow` or `Require`.</span></span>  
  
 <span data-ttu-id="94e2a-118">Para establecer ExtendedProtectionLevel, el usuario debe ser miembro del grupo de administradores integrado (BUILTIN\Administrators) en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="94e2a-118">To set the ExtendedProtectionLevel, the user must be a member of the BUILTIN\Administrators group on the report server.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94e2a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94e2a-119">Requirements</span></span>  
 <span data-ttu-id="94e2a-120">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94e2a-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e2a-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="94e2a-121">See Also</span></span>  
 <span data-ttu-id="94e2a-122">[Propiedad RSWindowsExtendedProtectionScenario &#40;MSReportServer_ConfigurationSetting de WMI&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="94e2a-122">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="94e2a-123">[Propiedad RSWindowsExtendedProtectionLevel &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="94e2a-123">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="94e2a-124">[Protección ampliada para la autenticación con Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="94e2a-124">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="94e2a-125">Archivo de configuración RSReportServer</span><span class="sxs-lookup"><span data-stu-id="94e2a-125">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
