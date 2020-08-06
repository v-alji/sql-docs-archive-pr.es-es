---
title: Método SetStrValue (clase ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 4ff80124-6e2e-4d96-a692-57c17b53c55e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f3c23eebdbe948e1b77c47ef56a04691fa391938
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749661"
---
# <a name="setstrvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="5654c-102">Método SetStrValue (clase ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="5654c-102">SetStrValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="5654c-103">Establece el valor de cadena de la propiedad actual a la que hace referencia el valor de la [propiedad PropertyIdx (clase ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="5654c-103">Sets the string value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5654c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5654c-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="5654c-105">Partes</span><span class="sxs-lookup"><span data-stu-id="5654c-105">Parts</span></span>  
 <span data-ttu-id="5654c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="5654c-106">*object*</span></span>  
 <span data-ttu-id="5654c-107">Objeto de la [clase ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) que representa un atributo del protocolo de red utilizado por el cliente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5654c-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="5654c-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5654c-108">Parameters</span></span>  
  
|<span data-ttu-id="5654c-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="5654c-109">Parameter</span></span>|<span data-ttu-id="5654c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5654c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5654c-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="5654c-111">*StrValue*</span></span>|<span data-ttu-id="5654c-112">Valor de cadena que especifica el nuevo valor de la propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="5654c-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5654c-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5654c-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="5654c-114">Valor unit 32 que es igual a 0 si se modificó el servicio correctamente, igual a 1 si no se admite la solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="5654c-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5654c-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5654c-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5654c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5654c-116">See Also</span></span>  
 [<span data-ttu-id="5654c-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="5654c-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
