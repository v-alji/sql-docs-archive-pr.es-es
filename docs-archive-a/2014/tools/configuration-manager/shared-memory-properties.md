---
title: Propiedades de memoria compartida | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- shared memory [SQL Server]
ms.assetid: dc1704da-eacd-4d26-b529-c996f958ca4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6275215afdb6de3aa134dbffe74aa22b9e7b6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676760"
---
# <a name="shared-memory-properties"></a><span data-ttu-id="2f8c7-102">Propiedades de Memoria compartida</span><span class="sxs-lookup"><span data-stu-id="2f8c7-102">Shared Memory Properties</span></span>
  <span data-ttu-id="2f8c7-103">Utilice la página **Protocolo**del cuadro de diálogo **Propiedades de Memoria compartida** para habilitar o deshabilitar el protocolo de memoria compartida.</span><span class="sxs-lookup"><span data-stu-id="2f8c7-103">Use the **Protocol**page on the **Shared Memory Properties** dialog box to enable or disable the shared memory protocol.</span></span> <span data-ttu-id="2f8c7-104">El protocolo de memoria compartida es el más sencillo de utilizar y no tiene ningún valor configurable.</span><span class="sxs-lookup"><span data-stu-id="2f8c7-104">Shared memory is the simplest protocol to use and has no configurable settings.</span></span> <span data-ttu-id="2f8c7-105">Dado que los clientes que utilizan el protocolo de memoria compartida solo se pueden conectar a una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecute en el mismo equipo, no es útil para la mayoría de las actividades de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f8c7-105">Because clients using the shared memory protocol can only connect to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance running on the same computer, it is not useful for most database activity.</span></span> <span data-ttu-id="2f8c7-106">Utilice el protocolo de memoria compartida para la solución de problemas cuando sospeche que los demás protocolos no están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="2f8c7-106">Use the shared memory protocol for troubleshooting when you suspect the other protocols are configured incorrectly.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2f8c7-107">.</span><span class="sxs-lookup"><span data-stu-id="2f8c7-107">must be restarted to enable or disable the protocol.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2f8c7-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="2f8c7-108">Options</span></span>  
 <span data-ttu-id="2f8c7-109">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="2f8c7-109">**Enabled**</span></span>  
 <span data-ttu-id="2f8c7-110">Los valores posibles son **Yes** y **No**.</span><span class="sxs-lookup"><span data-stu-id="2f8c7-110">Possible values are **Yes** and **No**.</span></span> <span data-ttu-id="2f8c7-111">El protocolo de memoria compartida está habilitado de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2f8c7-111">The shared memory protocol is enabled by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8c7-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f8c7-112">See Also</span></span>  
 <span data-ttu-id="2f8c7-113">[Elegir un protocolo de red](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="2f8c7-113">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="2f8c7-114">Crear una cadena de conexión válida con el protocolo de memoria compartida</span><span class="sxs-lookup"><span data-stu-id="2f8c7-114">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
  
