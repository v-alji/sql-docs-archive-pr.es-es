---
title: Propiedad PropertyValType (clase ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PropertyValType Property (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PropertyValType property
ms.assetid: fbd42e8e-0642-4a19-b3c8-6ce88345145f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be6c42fbaa36080ec8144d95abb045a3b4328057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749199"
---
# <a name="propertyvaltype-property-servernetworkprotocolproperty-class"></a><span data-ttu-id="9ecb8-102">Propiedad PropertyValType (clase ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="9ecb8-102">PropertyValType Property (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="9ecb8-103">Obtiene el tipo de datos del valor almacenado en la propiedad a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-103">Gets the data type of the value stored in the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ecb8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ecb8-104">Syntax</span></span>  
  
```  
  
object  
.PropertyValType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="9ecb8-105">Partes</span><span class="sxs-lookup"><span data-stu-id="9ecb8-105">Parts</span></span>  
 <span data-ttu-id="9ecb8-106">*object*</span><span class="sxs-lookup"><span data-stu-id="9ecb8-106">*object*</span></span>  
 <span data-ttu-id="9ecb8-107">Objeto de la [clase ServerNetworkProtocolProperty](servernetworkprotocolproperty-class.md) que representa un atributo del Protocolo de red en la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ecb8-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9ecb8-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ecb8-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="9ecb8-109">Valor `uint32` que especifica el tipo de datos del valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-109">A `uint32` value that specifies the data type of the property value.</span></span> <span data-ttu-id="9ecb8-110">Devuelve 0 para un valor de cadena y 1 para un tipo numérico.</span><span class="sxs-lookup"><span data-stu-id="9ecb8-110">It returns 0 for a string value and 1 for a numerical type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ecb8-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9ecb8-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ecb8-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ecb8-112">See Also</span></span>  
 <span data-ttu-id="9ecb8-113">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9ecb8-113">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
