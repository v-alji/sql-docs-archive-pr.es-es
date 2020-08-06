---
title: Método ListInstalledSharePointVersions (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListInstalledSharePointVersions method
ms.assetid: 8f0a5e9f-23f1-41e5-9a90-dfec19ef1df7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ceee23876461cf31cbd265ea39ae015ddcbc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671907"
---
# <a name="listinstalledsharepointversions-method-wmi"></a><span data-ttu-id="e3550-102">Método ListInstalledSharePointVersions (WMI)</span><span class="sxs-lookup"><span data-stu-id="e3550-102">ListInstalledSharePointVersions Method (WMI)</span></span>
  <span data-ttu-id="e3550-103">Devuelve un conjunto de tokens que representan las versiones de Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] que se instalan en el mismo equipo que el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e3550-103">Returns a set of tokens that represent the versions of Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] that are installed on the same computer as the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3550-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3550-104">Syntax</span></span>  
  
```vb  
Public Sub ListInstalledSharePointVersions(ByRef VersionTokens() _  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] VersionTokens,   
    out Int32 Length, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3550-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3550-105">Parameters</span></span>  
 <span data-ttu-id="e3550-106">*VersionTokens[]*</span><span class="sxs-lookup"><span data-stu-id="e3550-106">*VersionTokens[]*</span></span>  
 <span data-ttu-id="e3550-107">[out] Una matriz que contiene los tokens que representan la versión de un producto o tecnología de SharePoint que es compatible con el servidor de informes instalado.</span><span class="sxs-lookup"><span data-stu-id="e3550-107">[out] An array that contains the tokens that represent the version of a SharePoint product or technology that is compatible with the installed report server.</span></span>  
  
 <span data-ttu-id="e3550-108">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="e3550-108">*Length*</span></span>  
 <span data-ttu-id="e3550-109">[out] La longitud de la matriz de tokens de versión.</span><span class="sxs-lookup"><span data-stu-id="e3550-109">[out] The length of the version tokens array.</span></span>  
  
 <span data-ttu-id="e3550-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="e3550-110">*HRESULT*</span></span>  
 <span data-ttu-id="e3550-111">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="e3550-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3550-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e3550-112">Return Value</span></span>  
 <span data-ttu-id="e3550-113">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="e3550-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="e3550-114">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e3550-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="e3550-115">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="e3550-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3550-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e3550-116">Remarks</span></span>  
 <span data-ttu-id="e3550-117">Cada token que se devuelve representa una versión de [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] o [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] que es compatible con el servidor de informes instalado actualmente.</span><span class="sxs-lookup"><span data-stu-id="e3550-117">Each token that is returned represents a version of [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] or [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] that is compatible with the currently installed report server.</span></span> <span data-ttu-id="e3550-118">Si una versión determinada de SharePoint es compatible con versiones anteriores de SharePoint, se devuelven los tokens para cada versión de SharePoint compatible.</span><span class="sxs-lookup"><span data-stu-id="e3550-118">If a particular version of SharePoint is compatible with previous SharePoint versions, tokens for each compatible SharePoint version are returned.</span></span>  
  
 <span data-ttu-id="e3550-119">La tabla siguiente muestra los tokens de SharePoint que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="e3550-119">The following is a table of the SharePoint tokens that are returned.</span></span>  
  
|<span data-ttu-id="e3550-120">**Tokens de versión**</span><span class="sxs-lookup"><span data-stu-id="e3550-120">**Version Tokens**</span></span>|<span data-ttu-id="e3550-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e3550-121">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="e3550-122">WSS_V2_Compatible</span><span class="sxs-lookup"><span data-stu-id="e3550-122">WSS_V2_Compatible</span></span>|<span data-ttu-id="e3550-123">Se instala una instalación de [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] que es compatible con [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span><span class="sxs-lookup"><span data-stu-id="e3550-123">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span></span>|  
|<span data-ttu-id="e3550-124">WSS_V3_Compatible</span><span class="sxs-lookup"><span data-stu-id="e3550-124">WSS_V3_Compatible</span></span>|<span data-ttu-id="e3550-125">Se instala una instalación de [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] que es compatible con [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span><span class="sxs-lookup"><span data-stu-id="e3550-125">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span></span>|  
|<span data-ttu-id="e3550-126">WSS_V4_Compatible</span><span class="sxs-lookup"><span data-stu-id="e3550-126">WSS_V4_Compatible</span></span>|<span data-ttu-id="e3550-127">Se instala una instalación de [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] o [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] que es compatible con Office 14.</span><span class="sxs-lookup"><span data-stu-id="e3550-127">A [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with Office 14.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3550-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3550-128">Requirements</span></span>  
 <span data-ttu-id="e3550-129">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3550-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3550-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3550-130">See Also</span></span>  
 [<span data-ttu-id="e3550-131">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e3550-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
