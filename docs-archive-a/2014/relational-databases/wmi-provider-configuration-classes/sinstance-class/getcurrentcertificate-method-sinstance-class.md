---
title: Método GetCurrentCertificate (clase SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 9d2b72df-cb21-414a-abef-917f13d4de62
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 47838190e3791e01f8482e3fb064a9dca3a764af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678090"
---
# <a name="getcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="bd2f9-102">Método GetCurrentCertificate (clase SInstance)</span><span class="sxs-lookup"><span data-stu-id="bd2f9-102">GetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="bd2f9-103">Obtiene el certificado de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="bd2f9-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd2f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd2f9-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="bd2f9-105">Partes</span><span class="sxs-lookup"><span data-stu-id="bd2f9-105">Parts</span></span>  
 <span data-ttu-id="bd2f9-106">*object*</span><span class="sxs-lookup"><span data-stu-id="bd2f9-106">*object*</span></span>  
 <span data-ttu-id="bd2f9-107">Objeto de la [clase SInstance](sinstance-class.md) que representa la configuración del servidor en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd2f9-107">An [SInstance Class](sinstance-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="bd2f9-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd2f9-108">Parameters</span></span>  
  
|<span data-ttu-id="bd2f9-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="bd2f9-109">Parameter</span></span>|<span data-ttu-id="bd2f9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd2f9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bd2f9-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="bd2f9-111">*SHA*</span></span>|<span data-ttu-id="bd2f9-112">Valor de objeto de cadena (parámetro de salida) que especifica el certificado de seguridad actual una vez que el método finaliza.</span><span class="sxs-lookup"><span data-stu-id="bd2f9-112">A string object value (output parameter) that specifies the current security certificate after the method completes.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bd2f9-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bd2f9-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="bd2f9-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="bd2f9-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd2f9-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bd2f9-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd2f9-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd2f9-116">See Also</span></span>  
 <span data-ttu-id="bd2f9-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="bd2f9-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
