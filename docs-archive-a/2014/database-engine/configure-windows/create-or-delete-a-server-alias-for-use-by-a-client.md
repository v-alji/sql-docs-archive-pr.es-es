---
title: Crear o eliminar un alias de servidor para que lo use un cliente (Administrador de configuración de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- server alias
helpviewer_keywords:
- aliases [SQL Server], deleting
- aliases [SQL Server], creating
ms.assetid: b687e376-ee33-470d-b65a-87246bfefe6f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bead257b40c33e3640b18890a7d109d774131123
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673899"
---
# <a name="create-or-delete-a-server-alias-for-use-by-a-client-sql-server-configuration-manager"></a><span data-ttu-id="93ce9-102">Crear o eliminar un alias de servidor para que lo utilice un cliente (Administrador de configuración de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="93ce9-102">Create or Delete a Server Alias for Use by a Client (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="93ce9-103">En este tema se describe cómo crear o eliminar un alias de servidor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="93ce9-103">This topic describes how to create or delete a server alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="93ce9-104">Un alias es un nombre alternativo que se puede utilizar para establecer una conexión.</span><span class="sxs-lookup"><span data-stu-id="93ce9-104">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="93ce9-105">El alias encapsula los elementos necesarios de una cadena de conexión y los expone con un nombre elegido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="93ce9-105">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="93ce9-106">Los alias se pueden utilizar con cualquier aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="93ce9-106">Aliases can be used with any client application.</span></span> <span data-ttu-id="93ce9-107">Mediante la creación de alias de servidor, el equipo cliente puede conectarse a varios servidores que utilizan distintos protocolos de red sin necesidad de especificar el protocolo y los detalles de conexión de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="93ce9-107">By creating server aliases, your client computer can connect to multiple servers using different network protocols, without having to specify the protocol and connection details for each one.</span></span> <span data-ttu-id="93ce9-108">Además, también puede habilitar varios protocolos de red al mismo tiempo, aunque solo los utilice de vez en cuando.</span><span class="sxs-lookup"><span data-stu-id="93ce9-108">In addition, you can also have different network protocols enabled all the time, even if you only need to use them occasionally.</span></span> <span data-ttu-id="93ce9-109">Si ha configurado el servidor para que escuche en un número de puerto o canalización con nombre que no es el predeterminado, y ha deshabilitado el servicio SQL Server Browser, cree un alias que especifique el nuevo número de puerto o canalización con nombre.</span><span class="sxs-lookup"><span data-stu-id="93ce9-109">If you have configured the server to listen on a non-default port number or named pipe, and you have disabled the SQL Server Browser service, create an alias that specifies the new port number or named pipe.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="93ce9-110">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="93ce9-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-create-an-alias"></a><span data-ttu-id="93ce9-111">Para crear un alias</span><span class="sxs-lookup"><span data-stu-id="93ce9-111">To create an alias</span></span>  
  
1.  <span data-ttu-id="93ce9-112">En el Administrador de configuración de SQL Server, expanda **Configuración de SQL Server Native Client**, haga clic con el botón derecho en **Alias**y, luego, haga clic en **Nuevo alias**.</span><span class="sxs-lookup"><span data-stu-id="93ce9-112">In SQL Server Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Aliases**, and then click **New Alias**.</span></span>  
  
2.  <span data-ttu-id="93ce9-113">En el cuadro **Nombre de alias** , escriba el nombre del alias.</span><span class="sxs-lookup"><span data-stu-id="93ce9-113">In the **Alias Name** box, type the name of the alias.</span></span> <span data-ttu-id="93ce9-114">Las aplicaciones cliente utilizan este nombre cuando se conectan.</span><span class="sxs-lookup"><span data-stu-id="93ce9-114">Client applications use this name when they connect.</span></span>  
  
3.  <span data-ttu-id="93ce9-115">En el cuadro **Servidor** , escriba el nombre o la dirección IP del servidor.</span><span class="sxs-lookup"><span data-stu-id="93ce9-115">In the **Server** box, type the name or IP address of a server.</span></span> <span data-ttu-id="93ce9-116">Para una instancia con nombre, incluya el nombre de la instancia.</span><span class="sxs-lookup"><span data-stu-id="93ce9-116">For a named instance append the instance name.</span></span>  
  
4.  <span data-ttu-id="93ce9-117">En el cuadro **Protocolo** , seleccione el protocolo utilizado para este alias.</span><span class="sxs-lookup"><span data-stu-id="93ce9-117">In the **Protocol** box, select the protocol used for this alias.</span></span> <span data-ttu-id="93ce9-118">Al seleccionar un protocolo, el título del cuadro de diálogo de propiedades opcional cambia a Nº de puerto, Nombre de canalización o Cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="93ce9-118">Selecting a protocol, changes the title of the optional properties box to Port No, Pipe Name, or Connection String.</span></span>  
  
 <span data-ttu-id="93ce9-119">Las cadenas de conexión descritas en la Ayuda del Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueden resultar útiles para que los programadores creen sus propias cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="93ce9-119">The connection strings described in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help can be useful for programmers who create their own connection strings.</span></span> <span data-ttu-id="93ce9-120">Para obtener acceso a esta información, en el cuadro de diálogo **Nuevo alias** , presione F1 o haga clic en **Ayuda**.</span><span class="sxs-lookup"><span data-stu-id="93ce9-120">To access this information, in the **New Alias** dialog box, press F1, or click **Help**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93ce9-121">Si un alias configurado intenta conectarse a una instancia o un servidor incorrectos, deshabilite y vuelva a habilitar el protocolo de red asociado.</span><span class="sxs-lookup"><span data-stu-id="93ce9-121">If a configured alias is connecting to the wrong server or instance, disable and then reenable the associated network protocol.</span></span> <span data-ttu-id="93ce9-122">De este modo, se borrará la información de conexión almacenada en la memoria caché y se podrá establecer una conexión correctamente.</span><span class="sxs-lookup"><span data-stu-id="93ce9-122">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>  
  
#### <a name="to-delete-an-alias"></a><span data-ttu-id="93ce9-123">Para eliminar un alias</span><span class="sxs-lookup"><span data-stu-id="93ce9-123">To delete an alias</span></span>  
  
1.  <span data-ttu-id="93ce9-124">En el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , expanda **Configuración de SQL Server Native Client**y haga clic en **Alias**.</span><span class="sxs-lookup"><span data-stu-id="93ce9-124">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, and then click **Aliases**.</span></span>  
  
2.  <span data-ttu-id="93ce9-125">En el panel de detalles, haga clic con el botón derecho en el alias que quiera eliminar y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="93ce9-125">In the details pane, right-click the alias that you want to delete, and then click **Delete**.</span></span>  
  
  
