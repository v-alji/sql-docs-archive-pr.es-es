---
title: Propiedad ProtocolOrder (clase ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProtocolOrder Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProtocolOrder property
ms.assetid: aa09b8ab-37db-4406-8973-acf503855fd2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8bccb7109972dea4697e9e289081cbf47d2f9492
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677490"
---
# <a name="protocolorder-property-clientnetworkprotocol-class"></a><span data-ttu-id="25d4c-102">Propiedad ProtocolOrder (clase ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="25d4c-102">ProtocolOrder Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="25d4c-103">Obtiene el número de orden del protocolo de red del cliente al que se hace referencia actualmente especificado por el [método SetOrderValue (clase ClientNetworkProtocol)](clientnetworkprotocol-class.md) .</span><span class="sxs-lookup"><span data-stu-id="25d4c-103">Gets the order number of the currently referenced client network protocol as specified by the [SetOrderValue Method (ClientNetworkProtocol Class)](clientnetworkprotocol-class.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25d4c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25d4c-104">Syntax</span></span>  
  
```  
  
object  
.ProtocolOrder [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="25d4c-105">Partes</span><span class="sxs-lookup"><span data-stu-id="25d4c-105">Parts</span></span>  
 <span data-ttu-id="25d4c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="25d4c-106">*object*</span></span>  
 <span data-ttu-id="25d4c-107">A [clase ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa el protocolo de red utilizado por el cliente de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25d4c-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="25d4c-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="25d4c-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="25d4c-109">Valor `uint32` que especifica el número de orden del protocolo de red del cliente al que se hace referencia actualmente establecido por el método `OrderValue`.</span><span class="sxs-lookup"><span data-stu-id="25d4c-109">A `uint32` value that specifies the order number of the currently referenced client network protocol as set by the `OrderValue` method.</span></span> <span data-ttu-id="25d4c-110">Si el protocolo de red del cliente está deshabilitado, este valor será cero.</span><span class="sxs-lookup"><span data-stu-id="25d4c-110">If the client network protocol is disabled, this value will be zero.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25d4c-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="25d4c-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d4c-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25d4c-112">See Also</span></span>  
 <span data-ttu-id="25d4c-113">[Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="25d4c-113">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="25d4c-114">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="25d4c-114">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
