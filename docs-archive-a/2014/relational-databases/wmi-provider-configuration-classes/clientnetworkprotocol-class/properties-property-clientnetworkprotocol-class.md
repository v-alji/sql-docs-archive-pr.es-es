---
title: Propiedad Properties (clase ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Properties Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Properties property
ms.assetid: 7e0a4e38-4555-4750-8fd3-4425b29e6aa1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 09836db1f510ac77635924c51e5341686627d54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678097"
---
# <a name="properties-property-clientnetworkprotocol-class"></a><span data-ttu-id="d69e3-102">Propiedad Properties (clase ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="d69e3-102">Properties Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="d69e3-103">Obtiene las propiedades asociadas al protocolo de red del cliente actual especificado por [Configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="d69e3-103">Gets the properties associated with the current client network protocol specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d69e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d69e3-104">Syntax</span></span>  
  
```  
  
object  
.Properties [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="d69e3-105">Partes</span><span class="sxs-lookup"><span data-stu-id="d69e3-105">Parts</span></span>  
 <span data-ttu-id="d69e3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d69e3-106">*object*</span></span>  
 <span data-ttu-id="d69e3-107">A [clase ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa el protocolo de red utilizado por el cliente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d69e3-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d69e3-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d69e3-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="d69e3-109">Matriz de objetos de la [clase ClientNetworkProtocolProperty](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) que representan las propiedades admitidas por el protocolo de red del cliente actual al que hace referencia la `OrderValue` propiedad.</span><span class="sxs-lookup"><span data-stu-id="d69e3-109">An array of [ClientNetworkProtocolProperty Class](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) objects that represent the properties supported by the current client network protocol that is referenced by the `OrderValue` property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d69e3-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d69e3-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d69e3-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d69e3-111">See Also</span></span>  
 [<span data-ttu-id="d69e3-112">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="d69e3-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
