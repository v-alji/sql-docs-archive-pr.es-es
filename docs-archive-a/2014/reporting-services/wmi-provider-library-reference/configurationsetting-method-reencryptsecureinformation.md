---
title: Método ReencryptSecureInformation (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ReencryptSecureInformation method
ms.assetid: 8a487497-c207-45b2-8c92-87c58cc68716
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1a0c657b69d624df8895ae4d5a6d12277b011b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675195"
---
# <a name="reencryptsecureinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="8c6f5-102">Método ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="8c6f5-102">ReencryptSecureInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="8c6f5-103">Genera una nueva clave de cifrado y vuelve a cifrar toda la información segura en el catálogo utilizando esta nueva clave.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-103">Generates a new encryption key and re-encrypts all secure information in the catalog using this new key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c6f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c6f5-104">Syntax</span></span>  
  
```vb  
Public Sub ReencryptSecureInformation(ByRef HRESULT as Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ReencryptSecureInformation (out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c6f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c6f5-105">Parameters</span></span>  
 <span data-ttu-id="8c6f5-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="8c6f5-106">*HRESULT*</span></span>  
 <span data-ttu-id="8c6f5-107">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="8c6f5-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="8c6f5-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="8c6f5-109">[out] Matriz de cadenas que contiene los errores adicionales devueltos por la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c6f5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8c6f5-110">Return Value</span></span>  
 <span data-ttu-id="8c6f5-111">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="8c6f5-112">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="8c6f5-113">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c6f5-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8c6f5-114">Remarks</span></span>  
 <span data-ttu-id="8c6f5-115">El método ReencryptSecureInformation permite que el administrador reemplace la clave de cifrado existente por una nueva clave.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-115">The ReencryptSecureInformation method allows the administrator to replace the existing encryption key with a new key.</span></span>  
  
 <span data-ttu-id="8c6f5-116">Cuando se invoca este método, el servidor de informes genera una nueva clave de cifrado y la utiliza en todo el contenido cifrado para volver a cifrarlo.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-116">When this method is invoked, the report server generates a new encryption key and iterates through all encrypted content to re-encrypt it with the new encryption key.</span></span>  
  
 <span data-ttu-id="8c6f5-117">Las extensiones de entrega pueden almacenar la información segura en sus estructuras de configuración de entrega.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-117">Delivery extensions can store secured information in their delivery settings structures.</span></span> <span data-ttu-id="8c6f5-118">Cuando se llama a ReencryptSecureInformation, el servidor de informes carga cada suscripción y la extensión de entrega correspondiente para volver a cifrar la información almacenada en la configuración asociada.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-118">When ReencryptSecureInformation is called, the report server loads each subscription and the corresponding delivery extension to re-encrypt information stored in the associated settings.</span></span>  
  
 <span data-ttu-id="8c6f5-119">Si este método se ejecuta en un equipo en una implementación escalada, cada equipo en la implementación escalada deberá inicializarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8c6f5-119">If this method is run on a computer in a scale-out deployment, each computer in the scale-out deployment will need to be initialized again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c6f5-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c6f5-120">Requirements</span></span>  
 <span data-ttu-id="8c6f5-121">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c6f5-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6f5-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c6f5-122">See Also</span></span>  
 [<span data-ttu-id="8c6f5-123">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="8c6f5-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
