---
title: Método SetNumericalValue (clase ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: b3b4bce8-9d9e-4ccb-a223-0454281353b0
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f5a4b8d6819dae11abe4cc097f0e423c23d909e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672849"
---
# <a name="setnumericalvalue-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="e5516-102">Método SetNumericalValue (clase ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="e5516-102">SetNumericalValue Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="e5516-103">Establece el valor numérico de la propiedad a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e5516-103">Sets the numeric value of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5516-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5516-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e5516-105">Partes</span><span class="sxs-lookup"><span data-stu-id="e5516-105">Parts</span></span>  
 <span data-ttu-id="e5516-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e5516-106">*object*</span></span>  
 <span data-ttu-id="e5516-107">Objeto [ServerNetworkProtocolProperty Class] ServerNetworkProtocolProperty-class.md) que representa un atributo del Protocolo de red en la instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5516-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e5516-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5516-108">Parameters</span></span>  
  
|<span data-ttu-id="e5516-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e5516-109">Parameter</span></span>|<span data-ttu-id="e5516-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5516-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5516-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="e5516-111">*NumValue*</span></span>|<span data-ttu-id="e5516-112">Valor `uint32` que especifica el nuevo valor de la propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="e5516-112">A `uint32` value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e5516-113">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5516-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e5516-114">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="e5516-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5516-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5516-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5516-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5516-116">See Also</span></span>  
 <span data-ttu-id="e5516-117">[Configurar protocolos y bibliotecas de red de servidores de red](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e5516-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
