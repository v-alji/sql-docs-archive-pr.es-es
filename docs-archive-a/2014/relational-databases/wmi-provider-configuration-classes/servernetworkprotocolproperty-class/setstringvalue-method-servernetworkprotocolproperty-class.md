---
title: Método SetStringValue (clase ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: 0911df30-55f7-4fca-a1fb-01d2c91c1467
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8eb4a27d700d801e3ca94362663c6d7feaa7dc86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744589"
---
# <a name="setstringvalue-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="da6e1-102">Método SetStringValue (clase ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="da6e1-102">SetStringValue Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="da6e1-103">Establece el valor de cadena de la propiedad a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="da6e1-103">Sets the string value of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da6e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da6e1-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="da6e1-105">Partes</span><span class="sxs-lookup"><span data-stu-id="da6e1-105">Parts</span></span>  
 <span data-ttu-id="da6e1-106">*object*</span><span class="sxs-lookup"><span data-stu-id="da6e1-106">*object*</span></span>  
 <span data-ttu-id="da6e1-107">Objeto de la [clase ServerNetworkProtocolProperty](servernetworkprotocolproperty-class.md) que representa un atributo del Protocolo de red en la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da6e1-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="da6e1-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da6e1-108">Parameters</span></span>  
  
|<span data-ttu-id="da6e1-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="da6e1-109">Parameter</span></span>|<span data-ttu-id="da6e1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="da6e1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da6e1-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="da6e1-111">*StrValue*</span></span>|<span data-ttu-id="da6e1-112">Valor de cadena que especifica el nuevo valor de la propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="da6e1-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="da6e1-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="da6e1-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="da6e1-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="da6e1-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da6e1-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="da6e1-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da6e1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da6e1-116">See Also</span></span>  
 <span data-ttu-id="da6e1-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="da6e1-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
