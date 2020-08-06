---
title: 'Protocolos de cliente: propiedades de canalizaciones con nombre (pestaña Protocolo) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server], connecting to
- Named Pipes [SQL Server], default pipe
- client protocols [SQL Server]
ms.assetid: 30fbae62-2f2e-4d36-9c6e-3444fff68781
author: stevestein
ms.author: sstein
ms.openlocfilehash: 169b6d98212c724b8d6c43615ae2fa7eba9cfc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744457"
---
# <a name="client-protocols---named-pipes-properties-protocol-tab"></a><span data-ttu-id="16709-102">Protocolos de cliente: Propiedades de Canalizaciones con nombre (pestaña Protocolo)</span><span class="sxs-lookup"><span data-stu-id="16709-102">Client Protocols - Named Pipes Properties (Protocol Tab)</span></span>
  <span data-ttu-id="16709-103">En el Administrador de configuración de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], utilice la pestaña **Protocolo** del cuadro de diálogo **Propiedades de Canalizaciones con nombre** para ver o modificar la descripción de la canalización predeterminada.</span><span class="sxs-lookup"><span data-stu-id="16709-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager use the **Protocol** tab on the **Named Pipes Properties** dialog box to view or modify the description of default pipe.</span></span> <span data-ttu-id="16709-104">Para conectarse a una canalización diferente, escriba el nombre de la canalización en el cuadro **Canalización predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="16709-104">To connect to a different pipe, type the pipe in the **Default Pipe** box.</span></span> <span data-ttu-id="16709-105">Para obtener más información sobre cadenas de conexión, vea [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span><span class="sxs-lookup"><span data-stu-id="16709-105">For more information about connection strings, see [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="16709-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="16709-106">Options</span></span>  
 <span data-ttu-id="16709-107">**Canalización predeterminada**</span><span class="sxs-lookup"><span data-stu-id="16709-107">**Default Pipe**</span></span>  
 <span data-ttu-id="16709-108">Especifica la canalización predeterminada que la biblioteca de red de canalizaciones con nombre utilizará para intentar conectarse a la instancia de destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16709-108">Specifies the default pipe the Named Pipes Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="16709-109">De forma predeterminada, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escucha en: `\\.\pipe\sql\query`</span><span class="sxs-lookup"><span data-stu-id="16709-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query`</span></span>  
  
 <span data-ttu-id="16709-110">Para conectarse a la canalización predeterminada, escriba `sql\query`</span><span class="sxs-lookup"><span data-stu-id="16709-110">To connect to the default pipe, enter `sql\query`</span></span>  
  
 <span data-ttu-id="16709-111">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="16709-111">**Enabled**</span></span>  
 <span data-ttu-id="16709-112">Los valores posibles son **Yes** y **No**.</span><span class="sxs-lookup"><span data-stu-id="16709-112">Possible values are **Yes** and **No**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16709-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16709-113">See Also</span></span>  
 [<span data-ttu-id="16709-114">Elegir un protocolo de red</span><span class="sxs-lookup"><span data-stu-id="16709-114">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
