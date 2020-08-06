---
title: Método SetStringValue (clase ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: 88d67b22-0eea-48c9-ab73-e0b4907953df
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ba2350b798f1d7092a37a28ca35c17d6f4536a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749665"
---
# <a name="setstringvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="17f06-102">Método SetStringValue (clase ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="17f06-102">SetStringValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="17f06-103">Establece el valor de cadena de la propiedad actual a la que hace referencia el valor de la [propiedad PropertyIdx (clase ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="17f06-103">Sets the string value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17f06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17f06-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="17f06-105">Partes</span><span class="sxs-lookup"><span data-stu-id="17f06-105">Parts</span></span>  
 <span data-ttu-id="17f06-106">*object*</span><span class="sxs-lookup"><span data-stu-id="17f06-106">*object*</span></span>  
 <span data-ttu-id="17f06-107">Objeto de la [clase ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) que representa un atributo del Protocolo de red utilizado por el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cliente.</span><span class="sxs-lookup"><span data-stu-id="17f06-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17f06-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17f06-108">Parameters</span></span>  
  
|<span data-ttu-id="17f06-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="17f06-109">Parameter</span></span>|<span data-ttu-id="17f06-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="17f06-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17f06-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="17f06-111">*StrValue*</span></span>|<span data-ttu-id="17f06-112">Valor de cadena que especifica el nuevo valor de la propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="17f06-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="17f06-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="17f06-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="17f06-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="17f06-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17f06-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="17f06-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f06-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17f06-116">See Also</span></span>  
 [<span data-ttu-id="17f06-117">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="17f06-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
