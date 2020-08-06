---
title: Método SetOrderValue (clase ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetOrderValue method
ms.assetid: 15f693fd-37f6-41d9-9dab-d2c93db19895
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6839e85b6131c54e233d980c84a8727eeda2202a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677489"
---
# <a name="setordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="d22ae-102">Método SetOrderValue (clase ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="d22ae-102">SetOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="d22ae-103">Selecciona el protocolo con el valor de orden especificado en la lista de protocolos del cliente.</span><span class="sxs-lookup"><span data-stu-id="d22ae-103">Selects the protocol with the specified order value from the client protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d22ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d22ae-104">Syntax</span></span>  
  
```  
  
object  
.SetOrderValue(  
OrderValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="d22ae-105">Partes</span><span class="sxs-lookup"><span data-stu-id="d22ae-105">Parts</span></span>  
 <span data-ttu-id="d22ae-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d22ae-106">*object*</span></span>  
 <span data-ttu-id="d22ae-107">A [clase ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa el protocolo de red utilizado por el cliente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d22ae-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="d22ae-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d22ae-108">Parameters</span></span>  
  
|<span data-ttu-id="d22ae-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d22ae-109">Parameter</span></span>|<span data-ttu-id="d22ae-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d22ae-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d22ae-111">*OrderValue*</span><span class="sxs-lookup"><span data-stu-id="d22ae-111">*OrderValue*</span></span>|<span data-ttu-id="d22ae-112">Valor u`int32` que establece el valor de orden.</span><span class="sxs-lookup"><span data-stu-id="d22ae-112">A u`int32` value that sets the order value.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d22ae-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d22ae-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="d22ae-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="d22ae-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d22ae-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d22ae-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d22ae-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d22ae-116">See Also</span></span>  
 [<span data-ttu-id="d22ae-117">Propiedades de los protocolos de cliente (pestaña Ordenar)</span><span class="sxs-lookup"><span data-stu-id="d22ae-117">Client Protocols Properties (Order Tab)</span></span>](https://technet.microsoft.com/library/ms187884.aspx)  
  
  
