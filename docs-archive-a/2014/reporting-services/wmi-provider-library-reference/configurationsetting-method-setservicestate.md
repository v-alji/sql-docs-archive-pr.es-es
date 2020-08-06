---
title: Método SetServiceState (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetServiceState (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceState method
ms.assetid: 9e1ee42d-b388-4929-89c7-8741b956c3be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b4a29b3379fc1d312af42a1f5b1296ee35dcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748564"
---
# <a name="setservicestate-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="8a984-102">Método SetServiceState (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="8a984-102">SetServiceState Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="8a984-103">Activa y desactiva los servicios web y los servicios del Servidor de informes de Windows.</span><span class="sxs-lookup"><span data-stu-id="8a984-103">Turns the Report Server Windows and Web services on and off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a984-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a984-104">Syntax</span></span>  
  
```vb  
Public Sub SetServiceState(ByVal EnableWindowsService As Boolean, _  
    ByVal EnableWebService As Boolean, ByVal EnableReportManager As Boolean, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Boolean EnableWindowsService,  
    Boolean EnableWebService, Boolean EnableReportManager, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a984-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a984-105">Parameters</span></span>  
 <span data-ttu-id="8a984-106">*EnableWindowsService*</span><span class="sxs-lookup"><span data-stu-id="8a984-106">*EnableWindowsService*</span></span>  
 <span data-ttu-id="8a984-107">Valor `Boolean` que indica el estado del servicio Windows.</span><span class="sxs-lookup"><span data-stu-id="8a984-107">A `Boolean` value indicating the state of the Windows service.</span></span> <span data-ttu-id="8a984-108">Un valor de `true` inicia el servicio Windows del servidor de informes; un valor de `false` detiene el servicio Windows.</span><span class="sxs-lookup"><span data-stu-id="8a984-108">A value of `true` starts the Report Server Windows service; a value of `false` stops the Windows service.</span></span>  
  
 <span data-ttu-id="8a984-109">*EnableWebService*</span><span class="sxs-lookup"><span data-stu-id="8a984-109">*EnableWebService*</span></span>  
 <span data-ttu-id="8a984-110">`Boolean`Valor que indica el estado del [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servicio Web.</span><span class="sxs-lookup"><span data-stu-id="8a984-110">A `Boolean` value indicating the state of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web service.</span></span> <span data-ttu-id="8a984-111">Un valor de `true` inicia el servicio web del servidor de informes; un valor de `false` detiene el servicio web.</span><span class="sxs-lookup"><span data-stu-id="8a984-111">A value of `true` starts the Report Server Web service; a value of `false` stops the Web service</span></span>  
  
 <span data-ttu-id="8a984-112">*EnableReportManager*</span><span class="sxs-lookup"><span data-stu-id="8a984-112">*EnableReportManager*</span></span>  
 <span data-ttu-id="8a984-113">Valor `Boolean` que indica el estado deseado del servicio Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="8a984-113">A `Boolean` value indicating the desired state of the Report manager.</span></span>  
  
 <span data-ttu-id="8a984-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="8a984-114">*HRESULT*</span></span>  
 <span data-ttu-id="8a984-115">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="8a984-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a984-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8a984-116">Return Value</span></span>  
 <span data-ttu-id="8a984-117">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="8a984-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="8a984-118">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8a984-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="8a984-119">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="8a984-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a984-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8a984-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a984-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a984-121">Requirements</span></span>  
 <span data-ttu-id="8a984-122">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a984-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a984-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a984-123">See Also</span></span>  
 [<span data-ttu-id="8a984-124">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="8a984-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
