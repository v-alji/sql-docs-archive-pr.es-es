---
title: Método SetProtocolsOrder (clase ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetProtocolsOrder Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetProtocolsOrder method
ms.assetid: b86d98b9-aae4-4e74-b4da-1ec984d5c8b4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: aaa1d43c8a2f7f210f61761b28313a93ac6c7a90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677485"
---
# <a name="setprotocolsorder-method-clientnetworkprotocol-class"></a><span data-ttu-id="d32b8-102">Método SetProtocolsOrder (clase ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="d32b8-102">SetProtocolsOrder Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="d32b8-103">Cambia el orden de la lista de protocolos.</span><span class="sxs-lookup"><span data-stu-id="d32b8-103">Changes the order of the protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d32b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d32b8-104">Syntax</span></span>  
  
```  
  
object  
.SetProtocolsOrder(  
ProtocolOrderList  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="d32b8-105">Partes</span><span class="sxs-lookup"><span data-stu-id="d32b8-105">Parts</span></span>  
 <span data-ttu-id="d32b8-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d32b8-106">*object*</span></span>  
 <span data-ttu-id="d32b8-107">A [clase ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa el protocolo de red utilizado por el cliente de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d32b8-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="d32b8-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d32b8-108">Parameters</span></span>  
  
|<span data-ttu-id="d32b8-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d32b8-109">Parameter</span></span>|<span data-ttu-id="d32b8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d32b8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d32b8-111">*ProtocolOrderList*</span><span class="sxs-lookup"><span data-stu-id="d32b8-111">*ProtocolOrderList*</span></span>|<span data-ttu-id="d32b8-112">Matriz de cadenas[] que contiene los protocolos de red del cliente en el nuevo orden.</span><span class="sxs-lookup"><span data-stu-id="d32b8-112">A string[] array that lists the client network protocols in the new order.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d32b8-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d32b8-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="d32b8-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="d32b8-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d32b8-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d32b8-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32b8-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d32b8-116">See Also</span></span>  
 <span data-ttu-id="d32b8-117">[Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="d32b8-117">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="d32b8-118">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="d32b8-118">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
