---
title: Método SetEnable (clase ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a66c756a-1311-4f4a-8088-818f8ed90056
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dfba695506dd04ded82083b85bfbb751913fbcbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676892"
---
# <a name="setenable-method-clientnetworkprotocol-class"></a><span data-ttu-id="13529-102">Método SetEnable (clase ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="13529-102">SetEnable Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="13529-103">Habilita el protocolo de red del cliente especificado por [configurar protocolos de cliente](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="13529-103">Enables the client network protocol that is specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13529-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13529-104">Syntax</span></span>  
  
```  
  
object  
.SetEnableMethod()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="13529-105">Partes</span><span class="sxs-lookup"><span data-stu-id="13529-105">Parts</span></span>  
 <span data-ttu-id="13529-106">*object*</span><span class="sxs-lookup"><span data-stu-id="13529-106">*object*</span></span>  
 <span data-ttu-id="13529-107">A [clase ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa el protocolo de red utilizado por el cliente de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13529-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="13529-108">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="13529-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="13529-109">Valor `uint32` que es 0 si se modificó el servicio correctamente, 1 si no se admite la solicitud y cualquier otro número para indicar un error.</span><span class="sxs-lookup"><span data-stu-id="13529-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13529-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="13529-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13529-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13529-111">See Also</span></span>  
 [<span data-ttu-id="13529-112">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="13529-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
