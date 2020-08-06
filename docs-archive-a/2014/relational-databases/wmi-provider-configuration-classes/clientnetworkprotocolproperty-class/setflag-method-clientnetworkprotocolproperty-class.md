---
title: Método SetFlag (clase ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 0407520f-2f84-4f68-b2b7-429697286c1b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1c83a1d647b62f0e5c5acf0659d54bf787bf0c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748709"
---
# <a name="setflag-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="9b850-102">Método SetFlag (clase ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="9b850-102">SetFlag Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="9b850-103">Establece la marca de la propiedad actual a la que hace referencia el valor de la [propiedad PropertyIdx (clase ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="9b850-103">Sets the flag of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b850-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b850-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
) [=]  
```  
  
## <a name="parts"></a><span data-ttu-id="9b850-105">Partes</span><span class="sxs-lookup"><span data-stu-id="9b850-105">Parts</span></span>  
 <span data-ttu-id="9b850-106">*object*</span><span class="sxs-lookup"><span data-stu-id="9b850-106">*object*</span></span>  
 <span data-ttu-id="9b850-107">Objeto de la [clase ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) que representa un atributo del Protocolo de red utilizado por el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cliente.</span><span class="sxs-lookup"><span data-stu-id="9b850-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="9b850-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b850-108">Parameters</span></span>  
  
|<span data-ttu-id="9b850-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9b850-109">Parameter</span></span>|<span data-ttu-id="9b850-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b850-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b850-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="9b850-111">*BoolValue*</span></span>|<span data-ttu-id="9b850-112">Valor booleano que especifica el nuevo valor de la marca.</span><span class="sxs-lookup"><span data-stu-id="9b850-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9b850-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9b850-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="9b850-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="9b850-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b850-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9b850-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b850-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b850-116">See Also</span></span>  
 [<span data-ttu-id="9b850-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="9b850-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
