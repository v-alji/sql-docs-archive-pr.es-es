---
title: Método SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetWindowsServiceIdentity method
ms.assetid: 9bbc734c-9e69-48c2-8bec-8abe7c6cc987
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 15d1b7fa5fc6d69a963785cdaf976c80623c47f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748558"
---
# <a name="setwindowsserviceidentity-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="7a871-102">Método SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="7a871-102">SetWindowsServiceIdentity Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="7a871-103">Ejecuta el servicio de Windows de servidor de informes como el usuario de Windows especificado y concede a esta cuenta suficientes permisos de sistema de archivos para permitir que servidor de informes funcione.</span><span class="sxs-lookup"><span data-stu-id="7a871-103">Makes the Report Server Windows service run as a specified Windows user, and grants this account sufficient file system permissions to allow the report server to operate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a871-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a871-104">Syntax</span></span>  
  
```vb  
Public Sub SetWindowsServiceIdentity(UseBuiltInAccount as Boolean, _  
    Account as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetWindowsServiceIdentity(boolean UseBuiltInAccount,   
    string Account, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a871-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7a871-105">Parameters</span></span>  
 <span data-ttu-id="7a871-106">*UseBuiltInAccount*</span><span class="sxs-lookup"><span data-stu-id="7a871-106">*UseBuiltInAccount*</span></span>  
 <span data-ttu-id="7a871-107">Indica si la cuenta especificada es una cuenta de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="7a871-107">Indicates whether the specified account is a built-in Windows account.</span></span>  
  
 <span data-ttu-id="7a871-108">*Cuenta*</span><span class="sxs-lookup"><span data-stu-id="7a871-108">*Account*</span></span>  
 <span data-ttu-id="7a871-109">La cuenta de Windows que se utilizará para ejecutar el servicio de Windows, en formato "DOMAIN\alias."</span><span class="sxs-lookup"><span data-stu-id="7a871-109">The Windows account to use to run the Windows service, in the format "DOMAIN\alias".</span></span>  
  
 <span data-ttu-id="7a871-110">*Contraseña*</span><span class="sxs-lookup"><span data-stu-id="7a871-110">*Password*</span></span>  
 <span data-ttu-id="7a871-111">La contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="7a871-111">The password for the account.</span></span>  
  
 <span data-ttu-id="7a871-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="7a871-112">*HRESULT*</span></span>  
 <span data-ttu-id="7a871-113">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="7a871-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a871-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7a871-114">Return Value</span></span>  
 <span data-ttu-id="7a871-115">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="7a871-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="7a871-116">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7a871-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="7a871-117">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="7a871-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a871-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7a871-118">Remarks</span></span>  
 <span data-ttu-id="7a871-119">Cuando el parámetro *UseBuiltInAccount* se establece en `true` y el servidor de informes se ejecuta en [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] Microsoft o Windows XP, el valor de los parámetros *Name*, *Domain*y *password* se omite y se usa la cuenta de sistema local.</span><span class="sxs-lookup"><span data-stu-id="7a871-119">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] or Windows XP, the value of the *Name*, *Domain*, and *Password* parameters are ignored and the Local system account is used.</span></span>  
  
 <span data-ttu-id="7a871-120">Cuando el parámetro *UseBuiltInAccount* se establece en `true` y el servidor de informes se ejecuta en Windows Server 2003, las propiedades de *dominio* y *contraseña* se omiten y el campo de nombre debe contener "builtin\system" o "," o "Builtin\LocalService".</span><span class="sxs-lookup"><span data-stu-id="7a871-120">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Windows Server 2003, the *Domain* and *Password* properties are ignored, and the name field must contain either "Builtin\NetworkService" or "Builtin\System" or "Builtin\LocalService".</span></span>  
  
 <span data-ttu-id="7a871-121">El método SetWindowsServiceIdentity establece los permisos de archivo en los archivos y carpetas en el directorio de instalación del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7a871-121">The SetWindowsServiceIdentity method sets file permissions on files and folders in the report server installation directory.</span></span>  
  
 <span data-ttu-id="7a871-122">La cuenta especificada en el parámetro *account* requiere `LogonAsService` derechos en Windows.</span><span class="sxs-lookup"><span data-stu-id="7a871-122">The account specified in the *Account* parameter requires `LogonAsService` rights in Windows.</span></span> <span data-ttu-id="7a871-123">El método permite este derecho a la cuenta especificada.</span><span class="sxs-lookup"><span data-stu-id="7a871-123">The method grants this right to the specified account.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a871-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a871-124">Requirements</span></span>  
 <span data-ttu-id="7a871-125">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a871-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a871-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a871-126">See Also</span></span>  
 [<span data-ttu-id="7a871-127">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="7a871-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
