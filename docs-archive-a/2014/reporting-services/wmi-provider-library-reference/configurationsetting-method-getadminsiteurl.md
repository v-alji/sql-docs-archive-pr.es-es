---
title: Método GetAdminSiteUrl (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetAdminSiteUrl method
ms.assetid: fbc5bf3c-120c-4aec-a4f2-f5391bd415f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cae1a6f7e363ddce8c47c00eb5ef25fc832e59c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671909"
---
# <a name="getadminsiteurl-method-wmi"></a><span data-ttu-id="4d261-102">Método GetAdminSiteUrl (WMI)</span><span class="sxs-lookup"><span data-stu-id="4d261-102">GetAdminSiteUrl Method (WMI)</span></span>
  <span data-ttu-id="4d261-103">Obtiene la dirección URL absoluta para sitio web de administración central para la granja Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] con la que el servidor de informes está integrada.</span><span class="sxs-lookup"><span data-stu-id="4d261-103">Gets the absolute URL for the Central Administration Web site for the Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] farm that the report server is integrated with.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d261-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d261-104">Syntax</span></span>  
  
```vb  
Public Sub GetAdminSiteUrl(ByRef AdminSiteUrl as String, _  
ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GetAdminSiteUrl(out string AdminSiteUrl, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d261-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d261-105">Parameters</span></span>  
 <span data-ttu-id="4d261-106">*AdminSiteUrl*</span><span class="sxs-lookup"><span data-stu-id="4d261-106">*AdminSiteUrl*</span></span>  
 <span data-ttu-id="4d261-107">[out] Una cadena que contiene la dirección URL absoluta para el sitio web de administración central para la granja de SharePoint con la que el servidor de informes está integrada.</span><span class="sxs-lookup"><span data-stu-id="4d261-107">[out] A string that contains the absolute URL for the Central Administration Web site for the SharePoint farm that the report server is integrated with.</span></span>  
  
 <span data-ttu-id="4d261-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="4d261-108">*HRESULT*</span></span>  
 <span data-ttu-id="4d261-109">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="4d261-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d261-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d261-110">Return Value</span></span>  
 <span data-ttu-id="4d261-111">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="4d261-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="4d261-112">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d261-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="4d261-113">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="4d261-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d261-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d261-114">Requirements</span></span>  
 <span data-ttu-id="4d261-115">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d261-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d261-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d261-116">See Also</span></span>  
 [<span data-ttu-id="4d261-117">Métodos MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4d261-117">MSReportServer_ConfigurationSetting Methods</span></span>](msreportserver-configurationsetting-methods.md)  
  
  
