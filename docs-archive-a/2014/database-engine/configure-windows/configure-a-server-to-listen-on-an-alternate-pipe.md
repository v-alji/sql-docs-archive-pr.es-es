---
title: Configurar un servidor para que escuche en una canalización alternativa (Administrador de configuración de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Named Pipes [SQL Server], configuring
- listening [SQL Server], pipes
- pipes [SQL Server], alternate
- alternate pipes [SQL Server]
ms.assetid: 914f7491-e2be-4b0d-b3aa-fe5409cdbafa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 57d70cf4cd1d7474b895aeb8cb144c885e8a0f99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663112"
---
# <a name="configure-a-server-to-listen-on-an-alternate-pipe-sql-server-configuration-manager"></a><span data-ttu-id="0eb83-102">Configurar un servidor para escuchar en una canalización alternativa (Administrador de configuración de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0eb83-102">Configure a Server to Listen on an Alternate Pipe (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="0eb83-103">En este tema se describe cómo configurar un servidor para que escuche en una canalización alternativa en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0eb83-103">This topic describes how to configure a server to listen on an alternate pipe in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="0eb83-104">De forma predeterminada, la instancia predeterminada de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] escucha en la canalización con nombre \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="0eb83-104">By default, the default instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on named pipe \\\\.\pipe\sql\query.</span></span> <span data-ttu-id="0eb83-105">Las instancias con nombre de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y [!INCLUDE[ssEW](../../includes/ssew-md.md)] escuchan en otras canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="0eb83-105">Named instances of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] listen on other pipes.</span></span>  
  
 <span data-ttu-id="0eb83-106">Hay tres formas de conectarse a una canalización con nombre específica con una aplicación cliente:</span><span class="sxs-lookup"><span data-stu-id="0eb83-106">There are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="0eb83-107">Ejecutar el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0eb83-107">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="0eb83-108">Crear un alias en el cliente, especificando la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="0eb83-108">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="0eb83-109">Programar el cliente para conectarse mediante una cadena de conexión personalizada.</span><span class="sxs-lookup"><span data-stu-id="0eb83-109">Program the client to connect using a custom connection string.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0eb83-110">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0eb83-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-the-named-pipe-used-by-the-sql-server-database-engine"></a><span data-ttu-id="0eb83-111">Para configurar la canalización con nombre utilizada por el Motor de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="0eb83-111">To configure the named pipe used by the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="0eb83-112">En el Administrador de configuración de SQL Server, en el panel de consola, expanda **Configuración de red de SQL Server** y después **Protocolos de** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="0eb83-112">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, and then click expand **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="0eb83-113">En el panel de detalles, haga clic con el botón derecho en **Canalizaciones con nombre**y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0eb83-113">In the details pane, right-click **Named Pipes**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0eb83-114">En la pestaña **Protocolo** , en el cuadro **Nombre de canalización** , escriba la canalización en la que desea que escuche [!INCLUDE[ssDE](../../includes/ssde-md.md)] y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0eb83-114">On the **Protocol** tab, in the **Pipe Name** box, type the pipe you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="0eb83-115">En el panel de la consola, haga clic en **Servicios de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0eb83-115">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="0eb83-116">En el panel de detalles, haga clic con el botón derecho en **SQL Server (** \<instance name> **)** y, después, haga clic en **Reiniciar** para detener y reiniciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0eb83-116">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0eb83-117">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está escuchando en una canalización alternativa, hay tres formas de conectarse a una canalización con nombre específica con una aplicación cliente:</span><span class="sxs-lookup"><span data-stu-id="0eb83-117">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening on an alternate pipe, there are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="0eb83-118">Ejecutar el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0eb83-118">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="0eb83-119">Crear un alias en el cliente, especificando la canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="0eb83-119">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="0eb83-120">Programar el cliente para conectarse mediante una cadena de conexión personalizada.</span><span class="sxs-lookup"><span data-stu-id="0eb83-120">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb83-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0eb83-121">See Also</span></span>  
 <span data-ttu-id="0eb83-122">[Crear o eliminar un alias de servidor para que lo utilice un cliente &#40;Administrador de configuración de SQL Server&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span><span class="sxs-lookup"><span data-stu-id="0eb83-122">[Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span></span>  
 [<span data-ttu-id="0eb83-123">Configuración de red del servidor</span><span class="sxs-lookup"><span data-stu-id="0eb83-123">Server Network Configuration</span></span>](server-network-configuration.md)  
  
  
