---
title: Método SetEnable (clase ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a287950b-086f-4b6d-a2d8-4d3973bd1b21
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8f77b7a92fe226e349a03ffba03cfe8d67c280e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670888"
---
# <a name="setenable-method-servernetworkprotocol-class"></a><span data-ttu-id="96718-102">Método SetEnable (clase ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="96718-102">SetEnable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="96718-103">Habilita el protocolo de red del servidor.</span><span class="sxs-lookup"><span data-stu-id="96718-103">Enables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96718-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96718-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="96718-105">Partes</span><span class="sxs-lookup"><span data-stu-id="96718-105">Parts</span></span>  
 <span data-ttu-id="96718-106">*object*</span><span class="sxs-lookup"><span data-stu-id="96718-106">*object*</span></span>  
 <span data-ttu-id="96718-107">Objeto de la [clase ServerNetworkProtocol](servernetworkprotocol-class.md) que representa el protocolo de red utilizado por la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96718-107">A [ServerNetworkProtocol Class](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="96718-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="96718-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="96718-109">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="96718-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96718-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="96718-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96718-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96718-111">See Also</span></span>  
 <span data-ttu-id="96718-112">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="96718-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
