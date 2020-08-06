---
title: Método GetNextOrderValue (clase ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetNextOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetNextOrderValue method
ms.assetid: d741dc5c-c225-43d9-a730-7ad664ac525f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bdc3eecd9e151d7da32a5fd65a90552c0743b3d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678099"
---
# <a name="getnextordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="be9a2-102">Método GetNextOrderValue (clase ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="be9a2-102">GetNextOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="be9a2-103">Selecciona el protocolo que se encuentra en la posición siguiente en la lista de protocolos.</span><span class="sxs-lookup"><span data-stu-id="be9a2-103">Selects the protocol that is in the next position in the list of protocols.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be9a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be9a2-104">Syntax</span></span>  
  
```  
  
object  
.GetNextOrderValue()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="be9a2-105">Partes</span><span class="sxs-lookup"><span data-stu-id="be9a2-105">Parts</span></span>  
 <span data-ttu-id="be9a2-106">*object*</span><span class="sxs-lookup"><span data-stu-id="be9a2-106">*object*</span></span>  
 <span data-ttu-id="be9a2-107">A [clase ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa el protocolo de red utilizado por el cliente de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="be9a2-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="be9a2-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="be9a2-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="be9a2-109">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="be9a2-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be9a2-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="be9a2-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be9a2-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be9a2-111">See Also</span></span>  
 <span data-ttu-id="be9a2-112">[Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="be9a2-112">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="be9a2-113">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="be9a2-113">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
