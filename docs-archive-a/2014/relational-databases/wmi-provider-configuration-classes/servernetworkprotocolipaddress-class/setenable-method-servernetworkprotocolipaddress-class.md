---
title: Método SetEnable (clase ServerNetworkProtocolIPAddress) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: baa86deb-95dd-416f-b2c7-cec1dfb91ab4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5be9c30acacaedba320fd68363e531b178918271
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674024"
---
# <a name="setenable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="a9b28-102">Método SetEnable (clase ServerNetworkProtocolIPAddress)</span><span class="sxs-lookup"><span data-stu-id="a9b28-102">SetEnable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="a9b28-103">Habilita la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="a9b28-103">Enables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9b28-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9b28-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="a9b28-105">Partes</span><span class="sxs-lookup"><span data-stu-id="a9b28-105">Parts</span></span>  
 <span data-ttu-id="a9b28-106">*object*</span><span class="sxs-lookup"><span data-stu-id="a9b28-106">*object*</span></span>  
 <span data-ttu-id="a9b28-107">A [clase ServerNetworkProtocolIPAdress](servernetworkprotocolipaddress-class.md) que representa una dirección IP del protocolo de red en la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9b28-107">A [ServerNetworkProtocolIPAdress Class](servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a9b28-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9b28-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="a9b28-109">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="a9b28-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9b28-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a9b28-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b28-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9b28-111">See Also</span></span>  
 <span data-ttu-id="a9b28-112">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a9b28-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
