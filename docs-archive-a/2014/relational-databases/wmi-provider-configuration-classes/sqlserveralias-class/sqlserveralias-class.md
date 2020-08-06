---
title: Clase SqlServerAlias | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SqlServerAlias Class
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServerAlias class
ms.assetid: 475662b9-6985-45bf-b1e9-b0f26ef50443
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 46994409cc6a5119c9144eb7a3a4b9a8a9a22c44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677464"
---
# <a name="sqlserveralias-class"></a><span data-ttu-id="e6777-102">Clase SqlServerAlias</span><span class="sxs-lookup"><span data-stu-id="e6777-102">SqlServerAlias Class</span></span>
  <span data-ttu-id="e6777-103">La [clase SqlServerAlias](sqlserveralias-class.md) representa un alias de conexión del servidor.</span><span class="sxs-lookup"><span data-stu-id="e6777-103">The [SqlServerAlias Class](sqlserveralias-class.md) class represents a server connection alias.</span></span>  
  
 <span data-ttu-id="e6777-104">Se requiere un alias de conexión del servidor cuando se dan las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6777-104">A server connection alias is required when both the following occur:</span></span>  
  
-   <span data-ttu-id="e6777-105">El cliente se está conectando a una instancia de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a través de un transporte de red que no es el transporte de red predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e6777-105">The client is connecting to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] over a network transport that is not the default network transport.</span></span>  
  
-   <span data-ttu-id="e6777-106">La instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a la que se conecta el cliente está a la escucha en una canalización con nombre alternativa.</span><span class="sxs-lookup"><span data-stu-id="e6777-106">The instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the client is connected listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="e6777-107">**Nota:** La [clase SqlServerAlias](sqlserveralias-class.md) hereda el `Put` método de la clase Provider.</span><span class="sxs-lookup"><span data-stu-id="e6777-107">**Note:** The [SqlServerAlias Class](sqlserveralias-class.md) inherits the `Put` method from the Provider class.</span></span> <span data-ttu-id="e6777-108">Sin embargo, no devuelve ningún resultado indicado por el método `Provider::Put`.</span><span class="sxs-lookup"><span data-stu-id="e6777-108">However, it does not return any results as indicated by the `Provider::Put` method.</span></span> <span data-ttu-id="e6777-109">Para obtener más información, vea la documentación de WMI.</span><span class="sxs-lookup"><span data-stu-id="e6777-109">For more information, see the WMI documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6777-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6777-110">See Also</span></span>  
 [<span data-ttu-id="e6777-111">Configurar protocolos de cliente</span><span class="sxs-lookup"><span data-stu-id="e6777-111">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
