---
title: Propiedad IpAddresses (clase ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- IpAddresses Property (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- IpAddresses property
ms.assetid: e5d66f7e-9719-436e-b723-12d56f914a05
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b94c4c11327abc1f02bd1e99c414f806f75bc145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661836"
---
# <a name="ipaddresses-property-servernetworkprotocol-class"></a><span data-ttu-id="b9652-102">Propiedad IpAddresses (clase ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="b9652-102">IpAddresses Property (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="b9652-103">Obtiene las direcciones IP asociadas al protocolo de red del servidor.</span><span class="sxs-lookup"><span data-stu-id="b9652-103">Gets the IP addresses associated with the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9652-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9652-104">Syntax</span></span>  
  
```  
  
object  
.IpAddresses [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="b9652-105">Partes</span><span class="sxs-lookup"><span data-stu-id="b9652-105">Parts</span></span>  
 <span data-ttu-id="b9652-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b9652-106">*object*</span></span>  
 <span data-ttu-id="b9652-107">`ServerNetworkProtocol`Objeto que representa el protocolo de red utilizado por la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9652-107">A `ServerNetworkProtocol` object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b9652-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9652-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="b9652-109">Matriz de objetos de la [clase ServerNetworkProtocolIPAdress](../servernetworkprotocolipaddress-class/servernetworkprotocolipaddress-class.md) que representan las direcciones IP admitidas por el protocolo de red del servidor.</span><span class="sxs-lookup"><span data-stu-id="b9652-109">An array of [ServerNetworkProtocolIPAdress Class](../servernetworkprotocolipaddress-class/servernetworkprotocolipaddress-class.md) objects that represent the IP addresses supported by the server network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9652-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b9652-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9652-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9652-111">See Also</span></span>  
 <span data-ttu-id="b9652-112">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b9652-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
