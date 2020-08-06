---
title: Método RestoreEncryptionKey (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- RestoreEncryptionKey method
ms.assetid: 37e949f5-15af-4858-848a-f482ee94fcd9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e67478541bab615a6d441ae273ed3385a8654203
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748578"
---
# <a name="restoreencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="2bc4f-102">Método RestoreEncryptionKey (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="2bc4f-102">RestoreEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="2bc4f-103">Vuelve a aplicar la clave de cifrado especificada a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-103">Reapplies the specified encryption key to the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc4f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bc4f-104">Syntax</span></span>  
  
```vb  
Public Sub RestoreEncryptionKey(ByRef KeyFile() As Integer, _  
    ByRef Length As Int32, ByVal Password As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void RestoreEncryptionKey(out Byte[] KeyFile, out Int32 Length,   
            string Password, out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bc4f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bc4f-105">Parameters</span></span>  
 <span data-ttu-id="2bc4f-106">*KeyFile[]*</span><span class="sxs-lookup"><span data-stu-id="2bc4f-106">*KeyFile[]*</span></span>  
 <span data-ttu-id="2bc4f-107">[out] Matriz que contiene la clave de cifrado cifrada.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-107">[out] An array containing the encrypted encryption key.</span></span>  
  
 <span data-ttu-id="2bc4f-108">*Longitud*</span><span class="sxs-lookup"><span data-stu-id="2bc4f-108">*Length*</span></span>  
 <span data-ttu-id="2bc4f-109">[out] Longitud de la matriz devuelta por el método.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-109">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="2bc4f-110">*Contraseña*</span><span class="sxs-lookup"><span data-stu-id="2bc4f-110">*Password*</span></span>  
 <span data-ttu-id="2bc4f-111">Una cadena utilizada para cifrar la clave de cifrado.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-111">A string used to encrypt the encryption key.</span></span>  
  
 <span data-ttu-id="2bc4f-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="2bc4f-112">*HRESULT*</span></span>  
 <span data-ttu-id="2bc4f-113">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="2bc4f-114">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="2bc4f-114">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="2bc4f-115">[out] Matriz de cadenas que contiene los errores adicionales devueltos por la llamada.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-115">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bc4f-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2bc4f-116">Return Value</span></span>  
 <span data-ttu-id="2bc4f-117">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="2bc4f-118">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="2bc4f-119">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bc4f-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2bc4f-120">Remarks</span></span>  
 <span data-ttu-id="2bc4f-121">Si ya existe una entrada para el servidor de informes en la base de datos del servidor de informes, se elimina.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-121">If an entry already exists for the report server in the report server database, it is deleted.</span></span> <span data-ttu-id="2bc4f-122">Después, se crea la entrada con la clave de cifrado especificada y la clave pública del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-122">The new entry is then created using the specified encryption key and the report server's public key.</span></span>  
  
 <span data-ttu-id="2bc4f-123">El método es más efectivo cuando se llama después del método [DeleteEncryptionKey](configurationsetting-method-deleteencryptionkey.md) , que borra la lista de claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="2bc4f-123">The method is most effective when called after the [DeleteEncryptionKey](configurationsetting-method-deleteencryptionkey.md) method, which clears the list of encryption keys.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc4f-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bc4f-124">Requirements</span></span>  
 <span data-ttu-id="2bc4f-125">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bc4f-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc4f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2bc4f-126">See Also</span></span>  
 [<span data-ttu-id="2bc4f-127">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="2bc4f-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
