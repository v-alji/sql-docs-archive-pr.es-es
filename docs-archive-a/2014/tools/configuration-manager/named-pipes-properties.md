---
title: Propiedades de canalizaciones con nombre | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server]
- listening [SQL Server], pipes
- pipes [SQL Server], listening on pipes
- Named Pipes [SQL Server], listening on pipes
ms.assetid: a5fd5b8e-f889-485b-89e3-d4010ec4c6ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80790c1cb8830a0fd132721f375a70d2574421b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672331"
---
# <a name="named-pipes-properties"></a><span data-ttu-id="cbab5-102">Propiedades de Canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="cbab5-102">Named Pipes Properties</span></span>
  <span data-ttu-id="cbab5-103">Utilice la página **Protocolo**del cuadro de diálogo **Named Pipes Properties** (Propiedades de canalizaciones con nombre) para ver o cambiar la canalización con nombre que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escucha, cuando se utiliza el protocolo Canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="cbab5-103">Use the **Protocol**page on the **Named Pipes Properties** dialog box to view or change the named pipe that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens to, when using the Named Pipes protocol.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cbab5-104">para habilitar o deshabilitar el protocolo, o cambiar la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="cbab5-104">must be restarted to enable or disable the protocol, or change the named pipe.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cbab5-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="cbab5-105">Options</span></span>  
 <span data-ttu-id="cbab5-106">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="cbab5-106">**Enabled**</span></span>  
 <span data-ttu-id="cbab5-107">Los valores posibles son **Yes** y **No**.</span><span class="sxs-lookup"><span data-stu-id="cbab5-107">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="cbab5-108">**Nombre de canalización**</span><span class="sxs-lookup"><span data-stu-id="cbab5-108">**Pipe Name**</span></span>  
 <span data-ttu-id="cbab5-109">Especifica la canalización con nombre en la que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escucha.</span><span class="sxs-lookup"><span data-stu-id="cbab5-109">Specifies the named pipe on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens.</span></span> <span data-ttu-id="cbab5-110">De manera predeterminada, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] escucha en: `\\.\pipe\sql\query` para la instancia predeterminada y `\\.\pipe\MSSQL$<instancename>\sql\query` para una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="cbab5-110">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query` for the default instance and `\\.\pipe\MSSQL$<instancename>\sql\query` for a named instance.</span></span> <span data-ttu-id="cbab5-111">Este campo tiene un límite de 2.047 caracteres.</span><span class="sxs-lookup"><span data-stu-id="cbab5-111">This field is limited to 2047 characters.</span></span>  
  
## <a name="creating-an-alternate-named-pipe"></a><span data-ttu-id="cbab5-112">Crear una canalización con nombre alternativa</span><span class="sxs-lookup"><span data-stu-id="cbab5-112">Creating an Alternate Named Pipe</span></span>  
 <span data-ttu-id="cbab5-113">Para cambiar la canalización con nombre, escriba el nuevo nombre de canalización en el cuadro **Nombre de canalización** y, a continuación, detenga y reinicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbab5-113">To change the named pipe, type the new pipe name in the **Pipe Name** box and then stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cbab5-114">Como **sql\query** se conoce ampliamente como la canalización con nombre usada por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el cambio de la canalización puede ayudar a reducir el riesgo de ataques por programas malintencionados.</span><span class="sxs-lookup"><span data-stu-id="cbab5-114">Since **sql\query** is well known as the named pipe used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], changing the pipe can help reduce the risk of attack by malicious programs.</span></span>  
  
### <a name="example"></a><span data-ttu-id="cbab5-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbab5-115">Example</span></span>  
 <span data-ttu-id="cbab5-116">Escriba **\\\\.\pipe\unit\app** para escuchar en la canalización **unit\app** .</span><span class="sxs-lookup"><span data-stu-id="cbab5-116">Type **\\\\.\pipe\unit\app** to listen on the **unit\app** pipe.</span></span>  
  
 <span data-ttu-id="cbab5-117">Escriba **\\\\.\pipe\acct** para escuchar en la canalización **acct** .</span><span class="sxs-lookup"><span data-stu-id="cbab5-117">Type **\\\\.\pipe\acct** to listen on the **acct** pipe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbab5-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbab5-118">See Also</span></span>  
 <span data-ttu-id="cbab5-119">[Habilitar o deshabilitar un protocolo de red de servidor](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="cbab5-119">[Enable or Disable a Server Network Protocol](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 <span data-ttu-id="cbab5-120">[Elegir un protocolo de red](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="cbab5-120">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="cbab5-121">Crear una cadena de conexión válida con canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="cbab5-121">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
