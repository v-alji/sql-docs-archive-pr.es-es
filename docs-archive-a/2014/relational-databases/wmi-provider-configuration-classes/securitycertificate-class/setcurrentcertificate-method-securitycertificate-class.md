---
title: Método SetCurrentCertificate (clase SecurityCertificate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 04b1a76a-932d-4824-8506-e346afe7554e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4c7065946c858b775e319578eb67c2b7186338f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670896"
---
# <a name="setcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="3a9b2-102">Método SetCurrentCertificate (clase SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="3a9b2-102">SetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="3a9b2-103">Establece el certificado de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a9b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a9b2-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="3a9b2-105">Partes</span><span class="sxs-lookup"><span data-stu-id="3a9b2-105">Parts</span></span>  
 <span data-ttu-id="3a9b2-106">*object*</span><span class="sxs-lookup"><span data-stu-id="3a9b2-106">*object*</span></span>  
 <span data-ttu-id="3a9b2-107">Objeto [SecurityCertificate Class] SecurityCertificate-class.md) que representa un certificado de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-107">A [SecurityCertificate Class]securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3a9b2-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a9b2-108">Parameters</span></span>  
  
|<span data-ttu-id="3a9b2-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="3a9b2-109">Parameter</span></span>|<span data-ttu-id="3a9b2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a9b2-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a9b2-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="3a9b2-111">*SHA*</span></span>|<span data-ttu-id="3a9b2-112">Valor de cadena que especifica la huella digital del algoritmo hash seguro (SHA) del certificado de seguridad necesario.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-112">A string value that specifies the secure hash algorithm (SHA) thumbprint for the required security certificate.</span></span>|  
|<span data-ttu-id="3a9b2-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="3a9b2-113">*SQLInstance*</span></span>|<span data-ttu-id="3a9b2-114">Valor de cadena que especifica la instancia para la que se requiere el certificado.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3a9b2-115">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3a9b2-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="3a9b2-116">Valor unit 32 que es igual a 0 si se modificó el servicio correctamente, igual a 1 si no se admite la solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="3a9b2-116">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a9b2-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3a9b2-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9b2-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a9b2-118">See Also</span></span>  
 <span data-ttu-id="3a9b2-119">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3a9b2-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
