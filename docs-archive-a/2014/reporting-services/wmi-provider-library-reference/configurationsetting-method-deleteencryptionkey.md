---
title: Método DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptionKey method
ms.assetid: ed2f25b6-6a63-468d-9279-a577ca01b096
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e302659615bd620b3b0ed802b83aafc4e9506d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671915"
---
# <a name="deleteencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="6c12c-102">Método DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="6c12c-102">DeleteEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="6c12c-103">Elimina las claves de cifrado de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6c12c-103">Deletes the encryption keys from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c12c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c12c-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptionKeys(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptionKeys(string InstallationID, out Int32 HRESULT,   
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c12c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c12c-105">Parameters</span></span>  
 <span data-ttu-id="6c12c-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="6c12c-106">*InstallationID*</span></span>  
 <span data-ttu-id="6c12c-107">El identificador de instalación de un servidor de informes que está en la tabla de claves de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6c12c-107">The installation ID of a report server that is in the keys table of the report server database.</span></span>  
  
 <span data-ttu-id="6c12c-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6c12c-108">*HRESULT*</span></span>  
 <span data-ttu-id="6c12c-109">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="6c12c-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="6c12c-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="6c12c-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="6c12c-111">[out] Matriz de cadenas que contiene los errores adicionales devueltos por la llamada.</span><span class="sxs-lookup"><span data-stu-id="6c12c-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c12c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6c12c-112">Return Value</span></span>  
 <span data-ttu-id="6c12c-113">Devuelve HRESULT que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="6c12c-113">Returns an HRESULT indicating success or failure of the method call.</span></span> <span data-ttu-id="6c12c-114">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6c12c-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="6c12c-115">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="6c12c-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c12c-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6c12c-116">Remarks</span></span>  
 <span data-ttu-id="6c12c-117">El método *DeleteEncryptionKey* elimina las entradas en la tabla de claves de todos los servidores de informes que tienen acceso a la información segura en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6c12c-117">The *DeleteEncryptionKey* method deletes entries from the keys table for any report servers that have access to the secure information in the report server database.</span></span> <span data-ttu-id="6c12c-118">Si el parámetro *InstallationID* especificado no se corresponde con un identificador de instalación en la base de datos, el método devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="6c12c-118">If the *InstallationID* parameter specified does not correspond to an installation ID in the database, the method returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c12c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c12c-119">Requirements</span></span>  
 <span data-ttu-id="6c12c-120">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c12c-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c12c-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c12c-121">See Also</span></span>  
 [<span data-ttu-id="6c12c-122">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="6c12c-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
