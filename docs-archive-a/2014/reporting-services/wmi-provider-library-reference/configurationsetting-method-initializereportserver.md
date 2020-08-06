---
title: Método InitializeReportServer (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- InitializeReportServer (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- InitializeReportServer method
ms.assetid: 0304acc2-1fd7-437b-94d9-1c1073dd3ca4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6a8e44a98320ca2c9add6a1b6eef9362eef7731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671911"
---
# <a name="initializereportserver-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="7e970-102">Método InitializeReportServer (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="7e970-102">InitializeReportServer Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="7e970-103">Inicializa la instancia del servicio de informes especificada.</span><span class="sxs-lookup"><span data-stu-id="7e970-103">Initializes the specified report service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e970-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e970-104">Syntax</span></span>  
  
```vb  
Public Sub InitializeReportServer(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void InitializeReportServer(string InstallationID,   
    out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e970-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e970-105">Parameters</span></span>  
 <span data-ttu-id="7e970-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="7e970-106">*InstallationID*</span></span>  
 <span data-ttu-id="7e970-107">Cadena utilizada para cifrar la clave de cifrado antes de devolverse.</span><span class="sxs-lookup"><span data-stu-id="7e970-107">A string used to encrypt the encryption key before it is returned.</span></span>  
  
 <span data-ttu-id="7e970-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="7e970-108">*HRESULT*</span></span>  
 <span data-ttu-id="7e970-109">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="7e970-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="7e970-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="7e970-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="7e970-111">[out] Matriz de cadenas que contiene los errores adicionales devueltos por la llamada.</span><span class="sxs-lookup"><span data-stu-id="7e970-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e970-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7e970-112">Return Value</span></span>  
 <span data-ttu-id="7e970-113">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="7e970-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="7e970-114">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e970-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="7e970-115">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="7e970-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e970-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7e970-116">Remarks</span></span>  
 <span data-ttu-id="7e970-117">Cuando se llama a este método, la clave de cifrado que tiene acceso a la información segura de la base de datos del servidor de informes se cifra utilizando la clave pública del servidor de informes identificada por *InstallationID*.</span><span class="sxs-lookup"><span data-stu-id="7e970-117">When this method is called, the encryption key that accesses the report server database secure information is encrypted using the public key of the report server identified by *InstallationID*.</span></span>  
  
 <span data-ttu-id="7e970-118">La clave pública del servidor de informes especificado se debe haber escrito previamente en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7e970-118">The specified report server's public key must have previously been written into the report server database.</span></span>  
  
 <span data-ttu-id="7e970-119">Se debe llamar al método *InitializeReportServer* en un servidor de informes que ya tenga acceso a la información segura para que pueda descifrar la clave de cifrado.</span><span class="sxs-lookup"><span data-stu-id="7e970-119">The *InitializeReportServer* method must be called against a report server that already has access to the secure information so that it can decrypt the encryption key.</span></span> <span data-ttu-id="7e970-120">A continuación, la clave de cifrado cifrada resultante se almacena en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7e970-120">The resulting encrypted encryption key is then stored in the report server database.</span></span>  
  
 <span data-ttu-id="7e970-121">Si la propiedad [IsInitialized](configurationsetting-property-isinitialized.md) del servidor de informes se establece en `true` cuando se llama al método InitializeReportServer, el método devuelve SUCCESS sin intentar cifrar la clave de cifrado.</span><span class="sxs-lookup"><span data-stu-id="7e970-121">If the report server's [IsInitialized](configurationsetting-property-isinitialized.md) property is set to `true` when the InitializeReportServer method is called, the method returns success without trying to encrypt the encryption key.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e970-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e970-122">Requirements</span></span>  
 <span data-ttu-id="7e970-123">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e970-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e970-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e970-124">See Also</span></span>  
 [<span data-ttu-id="7e970-125">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="7e970-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
