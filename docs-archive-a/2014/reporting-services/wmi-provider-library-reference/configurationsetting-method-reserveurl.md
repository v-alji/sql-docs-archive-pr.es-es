---
title: Método ReserveURL (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ReservedURL method
ms.assetid: b9008a62-3edd-4f8a-99f2-7598c2133899
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95a58938ada19b4e49f094e3d8d01b241f1a4286
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748579"
---
# <a name="reserveurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="9013d-102">Método ReserveURL (MSReportServer_ConfigurationSetting de WMI)</span><span class="sxs-lookup"><span data-stu-id="9013d-102">ReserveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="9013d-103">Agrega una reserva URL para una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="9013d-103">Adds a URL reservation for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9013d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9013d-104">Syntax</span></span>  
  
```vb  
Public Sub ReserveURL(Application as String, _  
    UrlString as String, Lcid as Int32, _   
    ByRef [Error] as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ReserveURL(string Application, string UrlString, int Lcid,   
    out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9013d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9013d-105">Parameters</span></span>  
 <span data-ttu-id="9013d-106">*Aplicación*</span><span class="sxs-lookup"><span data-stu-id="9013d-106">*Application*</span></span>  
 <span data-ttu-id="9013d-107">Nombre de la aplicación para la que se va a reservar la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="9013d-107">The name of application to reserve the URL for.</span></span>  
  
 <span data-ttu-id="9013d-108">*URLString*</span><span class="sxs-lookup"><span data-stu-id="9013d-108">*URLString*</span></span>  
 <span data-ttu-id="9013d-109">Dirección URL para la reserva.</span><span class="sxs-lookup"><span data-stu-id="9013d-109">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="9013d-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="9013d-110">*lcid*</span></span>  
 <span data-ttu-id="9013d-111">Configuración regional que se utilizará para los mensajes de error devueltos.</span><span class="sxs-lookup"><span data-stu-id="9013d-111">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="9013d-112">*Error*</span><span class="sxs-lookup"><span data-stu-id="9013d-112">*Error*</span></span>  
 <span data-ttu-id="9013d-113">[out] Descripción del error que se produjo.</span><span class="sxs-lookup"><span data-stu-id="9013d-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="9013d-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="9013d-114">*HRESULT*</span></span>  
 <span data-ttu-id="9013d-115">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="9013d-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9013d-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9013d-116">Return Value</span></span>  
 <span data-ttu-id="9013d-117">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="9013d-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="9013d-118">Un valor de 0 indica que la llamada al método se realizó correctamente; un código de error indica que la llamada no se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9013d-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9013d-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9013d-119">Remarks</span></span>  
 <span data-ttu-id="9013d-120">*UrlString* no incluye el nombre del directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="9013d-120">*UrlString* does not include the virtual directory name.</span></span> <span data-ttu-id="9013d-121">El método [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) se proporciona para ese fin.</span><span class="sxs-lookup"><span data-stu-id="9013d-121">The [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="9013d-122">Las reservas de dirección URL se crean para la cuenta de servicio de Windows actual.</span><span class="sxs-lookup"><span data-stu-id="9013d-122">URL reservations are created for the current windows service account.</span></span> <span data-ttu-id="9013d-123">El cambio de la cuenta de servicio de Windows requiere la actualización manual de todas las reservas de dirección URL.</span><span class="sxs-lookup"><span data-stu-id="9013d-123">Changing the windows service account requires updating all the URL reservations manually.</span></span>  
  
 <span data-ttu-id="9013d-124">Este método produce el reciclaje con reinicio de dominios de aplicación de todos los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9013d-124">This method causes all application domains to hard recycle.</span></span> <span data-ttu-id="9013d-125">Los dominios de aplicación se reinician una vez completada esta operación.</span><span class="sxs-lookup"><span data-stu-id="9013d-125">Application domains are restarted after this operation is complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9013d-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9013d-126">Requirements</span></span>  
 <span data-ttu-id="9013d-127">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9013d-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9013d-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9013d-128">See Also</span></span>  
 [<span data-ttu-id="9013d-129">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="9013d-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
