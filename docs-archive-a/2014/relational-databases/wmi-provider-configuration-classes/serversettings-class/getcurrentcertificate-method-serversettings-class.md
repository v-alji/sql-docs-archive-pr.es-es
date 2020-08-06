---
title: Método GetCurrentCertificate (clase ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 450e33c6-91d4-420f-ab7c-1905111f5658
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b36a5fe7cd39da0f336d05fc4c450170fa21199d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744587"
---
# <a name="getcurrentcertificate-method-serversettings-class"></a><span data-ttu-id="5a8fe-102">Método GetCurrentCertificate (clase ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="5a8fe-102">GetCurrentCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="5a8fe-103">Obtiene el certificado de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a8fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a8fe-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="5a8fe-105">Partes</span><span class="sxs-lookup"><span data-stu-id="5a8fe-105">Parts</span></span>  
 <span data-ttu-id="5a8fe-106">*object*</span><span class="sxs-lookup"><span data-stu-id="5a8fe-106">*object*</span></span>  
 <span data-ttu-id="5a8fe-107">Objeto `ServerSettings` que representa la configuración del servidor en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a8fe-107">A `ServerSettings` object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="5a8fe-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a8fe-108">Parameters</span></span>  
  
|<span data-ttu-id="5a8fe-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="5a8fe-109">Parameter</span></span>|<span data-ttu-id="5a8fe-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a8fe-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a8fe-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="5a8fe-111">*SHA*</span></span>|<span data-ttu-id="5a8fe-112">Valor de objeto de cadena (parámetro de salida) que especifica el certificado de seguridad actual una vez que el método finaliza.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-112">A string object value (output parameter) that specifies the current security certificate after the method completes.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5a8fe-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5a8fe-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="5a8fe-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="5a8fe-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a8fe-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a8fe-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a8fe-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a8fe-116">See Also</span></span>  
 <span data-ttu-id="5a8fe-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="5a8fe-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
