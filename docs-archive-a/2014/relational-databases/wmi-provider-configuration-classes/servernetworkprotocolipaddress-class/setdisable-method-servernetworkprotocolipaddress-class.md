---
title: Método SetDisable (clase ServerNetworkProtocolIPAddress) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 7a7cc8cc-9fb8-4bf5-b483-2150d633ee10
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 9fbe928de1144c3065ddabb07bfd48606fdcea51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744593"
---
# <a name="setdisable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="599f7-102">Método SetDisable (clase ServerNetworkProtocolIPAddress)</span><span class="sxs-lookup"><span data-stu-id="599f7-102">SetDisable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="599f7-103">Deshabilita la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="599f7-103">Disables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="599f7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="599f7-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="599f7-105">Partes</span><span class="sxs-lookup"><span data-stu-id="599f7-105">Parts</span></span>  
 <span data-ttu-id="599f7-106">*object*</span><span class="sxs-lookup"><span data-stu-id="599f7-106">*object*</span></span>  
 <span data-ttu-id="599f7-107">Objeto [ServerNetworkProtocolIPAdress Class] servernetworkprotocolipaddress-class.md) que representa una dirección IP para el protocolo de red en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="599f7-107">A [ServerNetworkProtocolIPAdress Class]servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="599f7-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="599f7-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="599f7-109">Valor unit 32 que es igual a 0 si se modificó el servicio correctamente, igual a 1 si no se admite la solicitud e igual a cualquier otro número para indicar que hubo un error.</span><span class="sxs-lookup"><span data-stu-id="599f7-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="599f7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="599f7-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="599f7-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="599f7-111">See Also</span></span>  
 <span data-ttu-id="599f7-112">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="599f7-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
