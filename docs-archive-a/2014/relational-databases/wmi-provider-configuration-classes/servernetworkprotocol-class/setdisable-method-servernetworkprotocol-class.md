---
title: Método SetDisable (clase ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 0ebbe0c5-07ad-4a76-a918-e379930adf71
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3176227aba4de1e5aca1be35ec1f071a15caa49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670890"
---
# <a name="setdisable-method-servernetworkprotocol-class"></a><span data-ttu-id="b834f-102">Método SetDisable (clase ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="b834f-102">SetDisable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="b834f-103">Deshabilita el protocolo de red del servidor.</span><span class="sxs-lookup"><span data-stu-id="b834f-103">Disables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b834f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b834f-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="b834f-105">Partes</span><span class="sxs-lookup"><span data-stu-id="b834f-105">Parts</span></span>  
 <span data-ttu-id="b834f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b834f-106">*object*</span></span>  
 <span data-ttu-id="b834f-107">Objeto [ServerNetworkProtocol Class] ServerNetworkProtocol-class.md) que representa el protocolo de red utilizado por la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b834f-107">A [ServerNetworkProtocol Class]servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b834f-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b834f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="b834f-109">Valor unit 32 que es igual a 0 si se modificó el servicio correctamente, igual a 1 si no se admite la solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="b834f-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b834f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b834f-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b834f-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b834f-111">See Also</span></span>  
 <span data-ttu-id="b834f-112">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b834f-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
