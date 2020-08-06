---
title: Registrar un servidor conectado
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.f1
helpviewer_keywords:
- Registered Servers [SQL Server], register connected servers
- connected server registrations [SQL Server]
ms.assetid: 77deb5f5-0f80-484f-8b8b-29afa67ec18f
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 1d337d2da7d305165307745fb02526e37b53bbd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671309"
---
# <a name="register-a-connected-server-sql-server-management-studio"></a><span data-ttu-id="17168-102">Registrar un servidor conectado (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="17168-102">Register a Connected Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="17168-103">En este tema se describe cómo registrar servidores en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17168-103">This topic describes how to register servers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="17168-104">Mediante el registro del servidor, puede guardar la información de conexión correspondiente a los servidores a los que accede con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="17168-104">By registering the server, you can save the connection information for servers that you access frequently.</span></span> <span data-ttu-id="17168-105">Un servidor puede registrarse antes de conectarlo o cuando se conecta desde el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="17168-105">A server can be registered before connecting, or at the time of connection from Object Explorer.</span></span>  
  
 <span data-ttu-id="17168-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="17168-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="17168-107">**Para registrar un servidor, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="17168-107">**To register a server, using:**</span></span>  
  
     [<span data-ttu-id="17168-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17168-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="17168-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17168-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-register-a-connected-server"></a><span data-ttu-id="17168-110">Para registrar un servidor conectado</span><span class="sxs-lookup"><span data-stu-id="17168-110">To register a connected server</span></span>  
  
1.  <span data-ttu-id="17168-111">En el Explorador de objetos, haga clic con el botón derecho en un servidor al que ya esté conectado y haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="17168-111">In Object Explorer, right-click a server to which you already are connected, and then click **Register**.</span></span>  
  
     <span data-ttu-id="17168-112">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="17168-112">**Server name**</span></span>  
     <span data-ttu-id="17168-113">Escriba el nombre que desea utilizar para el servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="17168-113">Enter the name you want to use for the registered server.</span></span> <span data-ttu-id="17168-114">El registro de un servidor local o remoto con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] permite almacenar la información de conexión del servidor para futuras conexiones.</span><span class="sxs-lookup"><span data-stu-id="17168-114">Registering a local or remote server using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] lets you store the server connection information for future connections.</span></span> <span data-ttu-id="17168-115">Este campo muestra de manera predeterminada el nombre de servidor especificado en la conexión.</span><span class="sxs-lookup"><span data-stu-id="17168-115">This field defaults to the server name entered when you were connecting to the server.</span></span> <span data-ttu-id="17168-116">Puede conservar este nombre o indicar otro nombre de uso sencillo.</span><span class="sxs-lookup"><span data-stu-id="17168-116">You can retain this server name or enter another easy-to-use name for the server.</span></span>  
  
     <span data-ttu-id="17168-117">**Descripción del servidor**</span><span class="sxs-lookup"><span data-stu-id="17168-117">**Server description**</span></span>  
     <span data-ttu-id="17168-118">Escriba una descripción opcional del servidor.</span><span class="sxs-lookup"><span data-stu-id="17168-118">Enter an optional description of the server.</span></span> <span data-ttu-id="17168-119">El número máximo de caracteres permitido es 250.</span><span class="sxs-lookup"><span data-stu-id="17168-119">The maximum number of characters allowed is 250.</span></span>  
  
     <span data-ttu-id="17168-120">**Seleccionar un grupo de servidores**</span><span class="sxs-lookup"><span data-stu-id="17168-120">**Select a server group**</span></span>  
     <span data-ttu-id="17168-121">Seleccione el grupo de servidores donde desea guardar el registro del servidor.</span><span class="sxs-lookup"><span data-stu-id="17168-121">Select the server group where you want to save the server registration.</span></span>  
  
     <span data-ttu-id="17168-122">**Nuevo grupo**</span><span class="sxs-lookup"><span data-stu-id="17168-122">**New Group**</span></span>  
     <span data-ttu-id="17168-123">Haga clic en este botón para abrir el cuadro de diálogo **Nuevo grupo** , donde puede crear un grupo de servidores para el servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="17168-123">Click to launch the **New Group** dialog box, where you can create a new server group for the registered server.</span></span>  
  
     <span data-ttu-id="17168-124">**Guardar**</span><span class="sxs-lookup"><span data-stu-id="17168-124">**Save**</span></span>  
     <span data-ttu-id="17168-125">Haga clic para guardar la información insertada y crear un servidor registrado.</span><span class="sxs-lookup"><span data-stu-id="17168-125">Click to save the information you have entered and create a registered server.</span></span>  
  
  
