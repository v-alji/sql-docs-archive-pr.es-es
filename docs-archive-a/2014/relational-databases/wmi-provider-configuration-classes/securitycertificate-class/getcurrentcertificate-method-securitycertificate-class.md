---
title: Método GetCurrentCertificate (clase SecurityCertificate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 987a2671-1801-45c4-93e6-29f883c58720
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ab96b2e2a8fabf9e9ccce647e54be1983fe40ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744596"
---
# <a name="getcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="2e584-102">Método GetCurrentCertificate (clase SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="2e584-102">GetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="2e584-103">Obtiene el certificado de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="2e584-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e584-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e584-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="2e584-105">Partes</span><span class="sxs-lookup"><span data-stu-id="2e584-105">Parts</span></span>  
 <span data-ttu-id="2e584-106">*object*</span><span class="sxs-lookup"><span data-stu-id="2e584-106">*object*</span></span>  
 <span data-ttu-id="2e584-107">Objeto de la [clase SecurityCertificate](securitycertificate-class.md) que representa un certificado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2e584-107">A [SecurityCertificate Class](securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2e584-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e584-108">Parameters</span></span>  
  
|<span data-ttu-id="2e584-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="2e584-109">Parameter</span></span>|<span data-ttu-id="2e584-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e584-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e584-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="2e584-111">*SHA*</span></span>|<span data-ttu-id="2e584-112">Valor de objeto de cadena (parámetro de salida) que especifica la huella digital de SHA del certificado de seguridad actual una vez que el método finaliza.</span><span class="sxs-lookup"><span data-stu-id="2e584-112">A string value (output parameter) that specifies the current security certificate SHA thumbprint after the method completes.</span></span>|  
|<span data-ttu-id="2e584-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="2e584-113">*SQLInstance*</span></span>|<span data-ttu-id="2e584-114">Valor de cadena que especifica la instancia para la que se requiere el certificado.</span><span class="sxs-lookup"><span data-stu-id="2e584-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2e584-115">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2e584-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="2e584-116">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="2e584-116">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e584-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2e584-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e584-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e584-118">See Also</span></span>  
 <span data-ttu-id="2e584-119">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2e584-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
