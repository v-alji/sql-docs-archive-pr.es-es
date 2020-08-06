---
title: Propiedad IsSharePointIntegrated (MSReportServer_Instance de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: e21d00ad-5d9a-4290-8d74-7eeeda39e1ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0c92ebe586d37053b47f90ca98c31b3068a7b91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671889"
---
# <a name="issharepointintegrated-property-wmi-msreportserver_instance"></a><span data-ttu-id="b5965-102">Propiedad IsSharePointIntegrated (WMI MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="b5965-102">IsSharePointIntegrated Property (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="b5965-103">Especifica si el servidor de informes está en modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b5965-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="b5965-104">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], esta propiedad siempre devuelve `False`, porque en modo de SharePoint las instancias de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] son servicios compartidos de SharePoint y los proveedores WMI no las controlan.</span><span class="sxs-lookup"><span data-stu-id="b5965-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5965-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5965-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="b5965-106">Valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="b5965-106">Property Values</span></span>  
 <span data-ttu-id="b5965-107">Un valor `Boolean` que indica si el servidor de informes está en modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b5965-107">A `Boolean` value that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5965-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5965-108">Requirements</span></span>  
 <span data-ttu-id="b5965-109">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5965-109">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5965-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5965-110">See Also</span></span>  
 <span data-ttu-id="b5965-111">[Miembros de MSReportServer_Instance](msreportserver-instance-members.md) </span><span class="sxs-lookup"><span data-stu-id="b5965-111">[MSReportServer_Instance Members](msreportserver-instance-members.md) </span></span>  
 [<span data-ttu-id="b5965-112">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="b5965-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
  
