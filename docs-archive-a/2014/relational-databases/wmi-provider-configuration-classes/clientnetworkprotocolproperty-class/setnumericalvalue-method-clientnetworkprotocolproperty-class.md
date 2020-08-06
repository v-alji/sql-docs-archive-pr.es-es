---
title: Método SetNumericalValue (clase ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: d4d6df52-9e68-4003-9e28-ece6716ba7f1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ba963bb14e46aaa3f098ae74cd7aca92019256e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671952"
---
# <a name="setnumericalvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="6fe84-102">Método SetNumericalValue (clase ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="6fe84-102">SetNumericalValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="6fe84-103">Establece el valor numérico de la propiedad actual a la que hace referencia el valor de la [propiedad PropertyIdx (clase ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="6fe84-103">Sets the numeric value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fe84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fe84-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="6fe84-105">Partes</span><span class="sxs-lookup"><span data-stu-id="6fe84-105">Parts</span></span>  
 <span data-ttu-id="6fe84-106">*object*</span><span class="sxs-lookup"><span data-stu-id="6fe84-106">*object*</span></span>  
 <span data-ttu-id="6fe84-107">Objeto de la [clase ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) que representa un atributo del Protocolo de red utilizado por el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cliente.</span><span class="sxs-lookup"><span data-stu-id="6fe84-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="6fe84-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6fe84-108">Parameters</span></span>  
  
|<span data-ttu-id="6fe84-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6fe84-109">Parameter</span></span>|<span data-ttu-id="6fe84-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="6fe84-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6fe84-111">*value*</span><span class="sxs-lookup"><span data-stu-id="6fe84-111">*value*</span></span>|<span data-ttu-id="6fe84-112">Valor de `uint32` que especifica el valor numérico de la propiedad a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="6fe84-112">A `uint32` value that specifies the numeric value of the referenced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6fe84-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6fe84-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="6fe84-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="6fe84-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fe84-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6fe84-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe84-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6fe84-116">See Also</span></span>  
 [<span data-ttu-id="6fe84-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="6fe84-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  