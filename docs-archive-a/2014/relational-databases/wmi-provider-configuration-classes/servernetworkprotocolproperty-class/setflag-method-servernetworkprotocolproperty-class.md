---
title: Método SetFlag (clase ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 95288931-8eb1-4477-ad80-619cf7073e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1a90b4fca194f20cc0a2d70c947577594155f051
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745094"
---
# <a name="setflag-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="752b7-102">Método SetFlag (clase ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="752b7-102">SetFlag Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="752b7-103">Establece la marca de la propiedad a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="752b7-103">Sets the flag of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="752b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="752b7-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="752b7-105">Partes</span><span class="sxs-lookup"><span data-stu-id="752b7-105">Parts</span></span>  
 <span data-ttu-id="752b7-106">*object*</span><span class="sxs-lookup"><span data-stu-id="752b7-106">*object*</span></span>  
 <span data-ttu-id="752b7-107">Objeto [ServerNetworkProtocolProperty Class] ServerNetworkProtocolProperty-class.md) que representa un atributo del Protocolo de red en la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="752b7-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="752b7-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="752b7-108">Parameters</span></span>  
  
|<span data-ttu-id="752b7-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="752b7-109">Parameter</span></span>|<span data-ttu-id="752b7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="752b7-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="752b7-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="752b7-111">*BoolValue*</span></span>|<span data-ttu-id="752b7-112">Valor booleano que especifica el nuevo valor de la marca.</span><span class="sxs-lookup"><span data-stu-id="752b7-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="752b7-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="752b7-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="752b7-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="752b7-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="752b7-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="752b7-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="752b7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="752b7-116">See Also</span></span>  
 <span data-ttu-id="752b7-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="752b7-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
