---
title: Método SetSecureConnectionLevel (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetSecureConnectionLevel method
ms.assetid: 0fac7d5e-2670-4657-9439-331e7d93babb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4361f09eb38b3e5650b68ae6f86b7f2266bbf1a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748569"
---
# <a name="setsecureconnectionlevel-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="5948d-102">Método SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="5948d-102">SetSecureConnectionLevel Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="5948d-103">Establece el nivel de conexión segura del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="5948d-103">Sets the secure connection level of the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5948d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5948d-104">Syntax</span></span>  
  
```vb  
Public Sub SetSecureConnectionLevel(Level as Integer, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Int32 Level,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5948d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5948d-105">Parameters</span></span>  
 <span data-ttu-id="5948d-106">*Level*</span><span class="sxs-lookup"><span data-stu-id="5948d-106">*Level*</span></span>  
 <span data-ttu-id="5948d-107">Un valor entero que representa un nivel de conexión segura.</span><span class="sxs-lookup"><span data-stu-id="5948d-107">An integer value representing a secure connection level.</span></span>  
  
 <span data-ttu-id="5948d-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="5948d-108">*HRESULT*</span></span>  
 <span data-ttu-id="5948d-109">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="5948d-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5948d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5948d-110">Return Value</span></span>  
 <span data-ttu-id="5948d-111">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="5948d-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="5948d-112">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5948d-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="5948d-113">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="5948d-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5948d-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5948d-114">Remarks</span></span>  
 <span data-ttu-id="5948d-115">Cuando se realiza una llamada, la propiedad SecureConnectionLevel del servidor de informes se establece en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="5948d-115">When called, the report server SecureConnectionLevel property is set to the value specified.</span></span> <span data-ttu-id="5948d-116">El valor 0 indica que SSL está desactivado.</span><span class="sxs-lookup"><span data-stu-id="5948d-116">A value of 0 indicates that SSL is turned off.</span></span> <span data-ttu-id="5948d-117">Un valor mayor o igual que 1 indica que SSL está activado.</span><span class="sxs-lookup"><span data-stu-id="5948d-117">A value greater than or equal to 1 indicates that SSL is turned on.</span></span>  
  
-   <span data-ttu-id="5948d-118">Cuando se establece el valor, se cambia el elemento SecureConnectionLevel en el archivo de configuración del servidor de informes y el `URLRoot` elemento del archivo de configuración se establece para utilizar "https://" si el *nivel* especificado es mayor o igual que 1, o "http://" si el *nivel* especificado es 0.</span><span class="sxs-lookup"><span data-stu-id="5948d-118">When the value is set, the SecureConnectionLevel element in the report server configuration file is changed, and the `URLRoot` element in the configuration file is set to use "https://" if the specified *Level* is greater than or equal to 1, or "http://" if the specified *Level* is 0.</span></span>  
  
 <span data-ttu-id="5948d-119">En [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], SecureConnectionLevel actúa como un conmutador de activación o desactivación (el valor predeterminado es 0).</span><span class="sxs-lookup"><span data-stu-id="5948d-119">In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], SecureConnectionLevel is made an on/off switch, default value is 0.</span></span> <span data-ttu-id="5948d-120">Para cualquier valor mayor o igual que 1 pasado a la API con el método SetSecureConnectionLevel, SSL se considera activado y la propiedad SecureConnectionLevel de configuración se establece en consecuencia en el archivo rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="5948d-120">For any value greater than or equal to 1 passed through SetSecureConnectionLevel method API, SSL is considered on and the configuration property SecureConnectionLevel is set accordingly in the rsreportserver.config file.</span></span> <span data-ttu-id="5948d-121">Los valores 2 y 3 todavía se permiten por mantener la compatibilidad con las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="5948d-121">Values of 2 and 3 are still allowed for backward compatibility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5948d-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5948d-122">Requirements</span></span>  
 <span data-ttu-id="5948d-123">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5948d-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5948d-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5948d-124">See Also</span></span>  
 [<span data-ttu-id="5948d-125">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="5948d-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
