---
title: Método ListReportServersInDatabase (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ListReportServersInDatabase method
ms.assetid: a4bf5968-c46f-484f-a510-65e2dde65a0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9eaea72c0737124d89c86b55281326073597fb38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671904"
---
# <a name="listreportserversindatabase-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="6c3de-102">Método ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="6c3de-102">ListReportServersInDatabase Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="6c3de-103">Devuelve una lista de las instalaciones del servidor de informes que se encuentran en la base de datos del servidor de informes, sin tener en cuenta si esas instalaciones tienen acceso a la información segura.</span><span class="sxs-lookup"><span data-stu-id="6c3de-103">Returns the list of report server installations that are present in the report server database, regardless of whether they have access to secure information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c3de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c3de-104">Syntax</span></span>  
  
```vb  
Public Sub ListReportServersInDatabase(ByRef MachineNames() As String, _  
    ByRef InstanceNames() As String, ByRef InstallationIDs() As String, _  
    ByRef IsInitialized() As Boolean, ByRef Length As Int32, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] MachineNames,   
    out string[] InstanceNames, out string[] InstallationIDs,   
    out Boolean[] IsInitialized,out Int32 Length, out Int32 HRESULT,    
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c3de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c3de-105">Parameters</span></span>  
 <span data-ttu-id="6c3de-106">*MachineNames[]*</span><span class="sxs-lookup"><span data-stu-id="6c3de-106">*MachineNames[]*</span></span>  
 <span data-ttu-id="6c3de-107">[out] Matriz que contiene los nombres de equipo para las instalaciones del servidor de informes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c3de-107">[out] An array containing the machine names for the report server installations in the database.</span></span>  
  
 <span data-ttu-id="6c3de-108">*InstanceNames[]*</span><span class="sxs-lookup"><span data-stu-id="6c3de-108">*InstanceNames[]*</span></span>  
 <span data-ttu-id="6c3de-109">[out] Matriz que contiene los nombres de instancia de cada una de las instalaciones del servidor de informes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c3de-109">[out] An array containing the instance names of each of the report server installations in the database.</span></span>  
  
 <span data-ttu-id="6c3de-110">*InstallationIDs[]*</span><span class="sxs-lookup"><span data-stu-id="6c3de-110">*InstallationIDs[]*</span></span>  
 <span data-ttu-id="6c3de-111">[out] Una matriz que contiene los Id. de instalación de cada instalación del servidor de informes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c3de-111">[out] An array containing the installation IDs of each report server installation in the database.</span></span>  
  
 <span data-ttu-id="6c3de-112">*IsInitialized[]*</span><span class="sxs-lookup"><span data-stu-id="6c3de-112">*IsInitialized[]*</span></span>  
 <span data-ttu-id="6c3de-113">[out] Una matriz que contiene el estado de inicialización de cada instalación del servidor de informes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6c3de-113">[out] An array containing initialization status for each report server installation in the database.</span></span>  
  
 <span data-ttu-id="6c3de-114">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="6c3de-114">*Length*</span></span>  
 <span data-ttu-id="6c3de-115">[out] La longitud de las matrices devueltas por el método.</span><span class="sxs-lookup"><span data-stu-id="6c3de-115">[out] The length of the arrays returned by the method.</span></span> <span data-ttu-id="6c3de-116">Todas las matrices devueltas tienen la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="6c3de-116">All returned arrays have the same length.</span></span>  
  
 <span data-ttu-id="6c3de-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6c3de-117">*HRESULT*</span></span>  
 <span data-ttu-id="6c3de-118">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="6c3de-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="6c3de-119">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="6c3de-119">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="6c3de-120">[out] Matriz de cadenas que contiene los errores adicionales devueltos por la llamada.</span><span class="sxs-lookup"><span data-stu-id="6c3de-120">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c3de-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6c3de-121">Return Value</span></span>  
 <span data-ttu-id="6c3de-122">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="6c3de-122">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="6c3de-123">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6c3de-123">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="6c3de-124">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="6c3de-124">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c3de-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6c3de-125">Remarks</span></span>  
 <span data-ttu-id="6c3de-126">ListReportServersInDatabase enumera las instalaciones del servidor de informes que se encuentran en la base de datos del servidor de informes, sin tener en cuenta si tienen acceso a información segura, y devuelve un conjunto de matrices que contienen información sobre cada instalación.</span><span class="sxs-lookup"><span data-stu-id="6c3de-126">ListReportServersInDatabase lists the report server installations that are present in the report server database, regardless of whether they have access to secure information, and returns a matched set of arrays containing information about each installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c3de-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c3de-127">Requirements</span></span>  
 <span data-ttu-id="6c3de-128">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c3de-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c3de-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c3de-129">See Also</span></span>  
 [<span data-ttu-id="6c3de-130">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="6c3de-130">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
