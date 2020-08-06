---
title: Propiedad IsSharePointIntegrated (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: c548fed8-5e04-4faf-8b10-b37c86178056
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a1f3f38c23546ddf4dfb52c2a3af7c122af10cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675194"
---
# <a name="issharepointintegrated-property-wmi"></a><span data-ttu-id="65225-102">Propiedad IsSharePointIntegrated (WMI)</span><span class="sxs-lookup"><span data-stu-id="65225-102">IsSharePointIntegrated Property (WMI)</span></span>
  <span data-ttu-id="65225-103">Especifica si el servidor de informes está en modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="65225-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="65225-104">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], esta propiedad siempre devuelve `False`, porque en modo de SharePoint las instancias de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] son servicios compartidos de SharePoint y los proveedores WMI no las controlan.</span><span class="sxs-lookup"><span data-stu-id="65225-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65225-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65225-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="65225-106">Valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="65225-106">Property Values</span></span>  
 <span data-ttu-id="65225-107">Un objeto `Boolean` que indica si el servidor de informes está en modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="65225-107">A `Boolean` object that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="65225-108">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="65225-108">Example Code</span></span>  
 [<span data-ttu-id="65225-109">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="65225-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="65225-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65225-110">Requirements</span></span>  
 <span data-ttu-id="65225-111">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65225-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65225-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65225-112">See Also</span></span>  
 [<span data-ttu-id="65225-113">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="65225-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
