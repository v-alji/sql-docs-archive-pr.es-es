---
title: Método GetDatabaseVersionDisplayName (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetDatabaseVersionDisplayName method
ms.assetid: e1286424-7043-4f12-a7ad-1cf69e81baa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b39ce39a4f26964c148631c903869b0234e2b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671908"
---
# <a name="getdatabaseversiondisplayname-method-wmi"></a><span data-ttu-id="8167c-102">Método GetDatabaseVersionDisplayName (WMI)</span><span class="sxs-lookup"><span data-stu-id="8167c-102">GetDatabaseVersionDisplayName Method (WMI)</span></span>
  <span data-ttu-id="8167c-103">Obtiene el nombre para mostrar para una cadena de versión de base de datos del servidor de informes determinada.</span><span class="sxs-lookup"><span data-stu-id="8167c-103">Gets the display name for a given report server database version string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8167c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8167c-104">Syntax</span></span>  
  
```vb  
Public Sub GetDatabaseVersionDisplayName(Version As String, DisplayName As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetDatabaseVersionDisplayName(string Version, string DisplayName, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8167c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8167c-105">Parameters</span></span>  
 <span data-ttu-id="8167c-106">*Versión*</span><span class="sxs-lookup"><span data-stu-id="8167c-106">*Version*</span></span>  
 <span data-ttu-id="8167c-107">Una cadena que contiene la cadena de la versión de una base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="8167c-107">A string that contains the version string for a report server database.</span></span>  
  
 <span data-ttu-id="8167c-108">*DisplayName*</span><span class="sxs-lookup"><span data-stu-id="8167c-108">*DisplayName*</span></span>  
 <span data-ttu-id="8167c-109">[out] Una cadena que contiene el nombre para mostrar que corresponde a la versión proporcionada.</span><span class="sxs-lookup"><span data-stu-id="8167c-109">[out] A string that contains the display name that corresponds to the version supplied.</span></span>  
  
 <span data-ttu-id="8167c-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="8167c-110">*HRESULT*</span></span>  
 <span data-ttu-id="8167c-111">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="8167c-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8167c-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8167c-112">Remarks</span></span>  
 <span data-ttu-id="8167c-113">En la tabla siguiente se muestra la asignación de la versión de la base de datos para la cadena de nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="8167c-113">The following table shows the mapping from database version to display string.</span></span>  
  
|<span data-ttu-id="8167c-114">**Versión**</span><span class="sxs-lookup"><span data-stu-id="8167c-114">**Release**</span></span>|`Version`|<span data-ttu-id="8167c-115">**Nombre para mostrar**</span><span class="sxs-lookup"><span data-stu-id="8167c-115">**Display Name**</span></span>|  
|-----------------|-----------------|----------------------|  
|<span data-ttu-id="8167c-116">RS 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="8167c-116">RS 2005 SP2</span></span>|<span data-ttu-id="8167c-117">@DBVersion = "C.0.8.54"</span><span class="sxs-lookup"><span data-stu-id="8167c-117">@DBVersion = 'C.0.8.54'</span></span>|<span data-ttu-id="8167c-118">SQL Server 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="8167c-118">SQL Server 2005 SP2</span></span>|  
|<span data-ttu-id="8167c-119">RS 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="8167c-119">RS 2005 SP1</span></span>|<span data-ttu-id="8167c-120">@DBVersion = "C.0.8.43"</span><span class="sxs-lookup"><span data-stu-id="8167c-120">@DBVersion = 'C.0.8.43'</span></span>|<span data-ttu-id="8167c-121">SQL Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="8167c-121">SQL Server 2005 SP1</span></span>|  
|<span data-ttu-id="8167c-122">RS 2005 RTM</span><span class="sxs-lookup"><span data-stu-id="8167c-122">RS 2005 RTM</span></span>|<span data-ttu-id="8167c-123">@DBVersion = "C.0.8.40"</span><span class="sxs-lookup"><span data-stu-id="8167c-123">@DBVersion = 'C.0.8.40'</span></span>|<span data-ttu-id="8167c-124">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="8167c-124">SQL Server 2005</span></span>|  
|<span data-ttu-id="8167c-125">RS 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="8167c-125">RS 2000 SP2</span></span>|<span data-ttu-id="8167c-126">@DBVersion = "C.0.6.54"</span><span class="sxs-lookup"><span data-stu-id="8167c-126">@DBVersion = 'C.0.6.54'</span></span>|<span data-ttu-id="8167c-127">SQL Server 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="8167c-127">SQL Server 2000 SP2</span></span>|  
|<span data-ttu-id="8167c-128">RS 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="8167c-128">RS 2000 SP1</span></span>|<span data-ttu-id="8167c-129">@DBVersion = "C.0.6.51"</span><span class="sxs-lookup"><span data-stu-id="8167c-129">@DBVersion = 'C.0.6.51'</span></span>|<span data-ttu-id="8167c-130">SQL Server 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="8167c-130">SQL Server 2000 SP1</span></span>|  
|<span data-ttu-id="8167c-131">RS 2000 RTM</span><span class="sxs-lookup"><span data-stu-id="8167c-131">RS 2000 RTM</span></span>|<span data-ttu-id="8167c-132">@DBVersion = "C.0.6.43"</span><span class="sxs-lookup"><span data-stu-id="8167c-132">@DBVersion = 'C.0.6.43'</span></span>|<span data-ttu-id="8167c-133">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="8167c-133">SQL Server 2000</span></span>|  
|<span data-ttu-id="8167c-134">Revisión</span><span class="sxs-lookup"><span data-stu-id="8167c-134">Hotfix</span></span>||<span data-ttu-id="8167c-135">Versión aplicable más cercana</span><span class="sxs-lookup"><span data-stu-id="8167c-135">Closest applicable version</span></span>|  
  
 <span data-ttu-id="8167c-136">Para una *versión* anterior a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 se devuelve un valor de HRESULT de ACT_E_BAD_VERSION.</span><span class="sxs-lookup"><span data-stu-id="8167c-136">For a *Version* prior to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 an HRESULT of ACT_E_BAD_VERSION is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8167c-137">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8167c-137">Return Value</span></span>  
 <span data-ttu-id="8167c-138">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="8167c-138">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="8167c-139">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8167c-139">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="8167c-140">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="8167c-140">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8167c-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8167c-141">Requirements</span></span>  
 <span data-ttu-id="8167c-142">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8167c-142">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8167c-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8167c-143">See Also</span></span>  
 [<span data-ttu-id="8167c-144">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="8167c-144">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
