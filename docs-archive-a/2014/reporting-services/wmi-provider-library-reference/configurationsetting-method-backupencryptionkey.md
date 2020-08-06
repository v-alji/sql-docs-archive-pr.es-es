---
title: Método BackupEncryptionKey (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- BackupEncryptionKey Method (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- BackupEncryptionKey method
ms.assetid: da1d5dae-2517-448e-96fb-5379c93222ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d625401324e2117ee1e9677d840854fa7b63c6e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748586"
---
# <a name="backupencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="d521a-102">Método BackupEncryptionKey (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="d521a-102">BackupEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="d521a-103">Realiza una copia de seguridad de la clave de cifrado de la instancia del servidor de informes especificada.</span><span class="sxs-lookup"><span data-stu-id="d521a-103">Backs up the encryption key for the specified report server instance.</span></span> <span data-ttu-id="d521a-104">La clave de cifrado se almacena cifrada con una contraseña.</span><span class="sxs-lookup"><span data-stu-id="d521a-104">The encryption key is stored encrypted with a password.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d521a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d521a-105">Syntax</span></span>  
  
```vb  
Public Sub BackupEncryptionKey(Password as String, _  
    ByRef KeyFile() as Integer, ByRef Length as Int32, _  
    ByRef HRESULT as Int32, ByRef ExtendedErrors() as String)  
  
```  
  
```csharp  
public void BackupEncryptionKey(string Password, out Byte[] KeyFile,   
    out Int32 Length, out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d521a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d521a-106">Parameters</span></span>  
 <span data-ttu-id="d521a-107">*Contraseña*</span><span class="sxs-lookup"><span data-stu-id="d521a-107">*Password*</span></span>  
 <span data-ttu-id="d521a-108">Cadena utilizada para cifrar la clave de cifrado antes de devolverse.</span><span class="sxs-lookup"><span data-stu-id="d521a-108">A string used to encrypt the encryption key before it is returned.</span></span>  
  
 <span data-ttu-id="d521a-109">*KeyFile[]*</span><span class="sxs-lookup"><span data-stu-id="d521a-109">*KeyFile[]*</span></span>  
 <span data-ttu-id="d521a-110">[out] Matriz que contiene la clave de cifrado cifrada.</span><span class="sxs-lookup"><span data-stu-id="d521a-110">[out] An array containing the encrypted encryption key.</span></span>  
  
 <span data-ttu-id="d521a-111">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="d521a-111">*Length*</span></span>  
 <span data-ttu-id="d521a-112">[out] Longitud de la matriz devuelta por el método.</span><span class="sxs-lookup"><span data-stu-id="d521a-112">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="d521a-113">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="d521a-113">*HRESULT*</span></span>  
 <span data-ttu-id="d521a-114">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="d521a-114">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="d521a-115">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="d521a-115">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="d521a-116">[out] Matriz de cadenas que contiene los errores adicionales devueltos por la llamada.</span><span class="sxs-lookup"><span data-stu-id="d521a-116">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d521a-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d521a-117">Return Value</span></span>  
 <span data-ttu-id="d521a-118">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="d521a-118">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="d521a-119">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d521a-119">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="d521a-120">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="d521a-120">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d521a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d521a-121">Requirements</span></span>  
 <span data-ttu-id="d521a-122">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d521a-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d521a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d521a-123">See Also</span></span>  
 [<span data-ttu-id="d521a-124">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d521a-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
