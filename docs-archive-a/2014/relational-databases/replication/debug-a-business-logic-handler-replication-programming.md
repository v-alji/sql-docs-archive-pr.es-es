---
title: Depurar un controlador de lógica de negocios | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- merge replication business logic handlers [SQL Server replication]
- business logic handlers [SQL Server replication]
- BusinessLogicModule class
ms.assetid: edd0d17a-0e9c-4c28-8395-a7d47e8ce3d6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7b255407783b1e52a376e562ec910f8b123e42c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663406"
---
# <a name="debug-a-business-logic-handler-replication-programming"></a><span data-ttu-id="2acc2-102">Depurar un controlador de lógica de negocios (programación de la replicación)</span><span class="sxs-lookup"><span data-stu-id="2acc2-102">Debug a Business Logic Handler (Replication Programming)</span></span>
  <span data-ttu-id="2acc2-103">Use un controlador de lógica de negocios para invocar la lógica de negocios personalizada cuando se sincroniza una suscripción de mezcla.</span><span class="sxs-lookup"><span data-stu-id="2acc2-103">Use a business logic handler to invoke custom business logic when a merge subscription is synchronized.</span></span> <span data-ttu-id="2acc2-104">Para obtener más información, consulte [Ejecutar lógica de negocios durante la sincronización de mezcla](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="2acc2-104">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
 <span data-ttu-id="2acc2-105">El Reconciliador de replicación de mezcla (replrec.dll) llama al ensamblado de código administrado que contiene la lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="2acc2-105">The Merge Replication Reconciler (replrec.dll) calls the managed code assembly containing the business logic.</span></span> <span data-ttu-id="2acc2-106">En la mayoría de los casos, replrec.dll y la lógica de negocios personalizada se ejecuta en el equipo donde el Agente de mezcla se ejecuta (en el suscriptor para una suscripción de extracción o en el distribuidor para una suscripción de inserción).</span><span class="sxs-lookup"><span data-stu-id="2acc2-106">In most cases, replrec.dll and the custom business logic is executed on the computer where the Merge Agent runs (at the Subscriber for a pull subscription or at the Distributor for a push subscription).</span></span> <span data-ttu-id="2acc2-107">En el caso de la sincronización web o en el caso de un suscriptor de [!INCLUDE[ssEW](../../includes/ssew-md.md)] , el reconciliador y la lógica de negocios personalizada se ejecuta en el servidor web.</span><span class="sxs-lookup"><span data-stu-id="2acc2-107">In the case of Web synchronization, or in the case of a [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscriber, the reconciler and the custom business logic is executed on the Web server.</span></span>  
  
### <a name="to-debug-a-business-logic-handler-on-a-local-computer"></a><span data-ttu-id="2acc2-108">Para depurar un controlador de lógica de negocios en un equipo local</span><span class="sxs-lookup"><span data-stu-id="2acc2-108">To debug a business logic handler on a local computer</span></span>  
  
1.  <span data-ttu-id="2acc2-109">Configure la publicación y la distribución, cree una publicación y cree una suscripción a la publicación.</span><span class="sxs-lookup"><span data-stu-id="2acc2-109">Configure publishing and distribution, create a publication, and create a subscription to the publication.</span></span> <span data-ttu-id="2acc2-110">Para más información, vea [Configuración de la publicación y la distribución](configure-publishing-and-distribution.md) y [Creación de una publicación](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="2acc2-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [Create a Publication](publish/create-a-publication.md).</span></span>  
  
2.  <span data-ttu-id="2acc2-111">Cree y registre un controlador de lógica de negocios</span><span class="sxs-lookup"><span data-stu-id="2acc2-111">Create and register a business logic handler.</span></span> <span data-ttu-id="2acc2-112">Para más información, consulte [Implementar un controlador de lógica de negocios para un artículo de mezcla](implement-a-business-logic-handler-for-a-merge-article.md).</span><span class="sxs-lookup"><span data-stu-id="2acc2-112">For more information, see [Implement a Business Logic Handler for a Merge Article](implement-a-business-logic-handler-for-a-merge-article.md).</span></span>  
  
3.  <span data-ttu-id="2acc2-113">Cree un proyecto de Replication Management Objects (RMO) en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio que mediante programación inicie sincrónicamente el Agente de mezcla.</span><span class="sxs-lookup"><span data-stu-id="2acc2-113">Create a Replication Management Objects (RMO) project in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio that programmatically starts the Merge Agent synchronously.</span></span> <span data-ttu-id="2acc2-114">Para obtener más información, consulte [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="2acc2-114">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
4.  <span data-ttu-id="2acc2-115">Establezca un punto de interrupción en el código del controlador de lógica de negocios, ya sea en el método que se depura o en el constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="2acc2-115">Set a breakpoint in the business logic handler code, either in the method being debugged or in the class constructor.</span></span> <span data-ttu-id="2acc2-116">Para obtener más información acerca de los métodos que se pueden implementar en un controlador de lógica de negocios, vea el tema de métodos <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="2acc2-116">For more information about the methods that can be implemented in a business logic handler, see the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> methods topic.</span></span>  
  
5.  <span data-ttu-id="2acc2-117">Genere el controlador de lógica de negocios en modo de depuración e implemente el archivo de símbolos de ensamblado y depuración (.pdb) en la ubicación registrada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="2acc2-117">Build the business logic handler in debug mode and deploy the assembly and debugging symbol file (.pdb) in the location registered in step 1.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2acc2-118">Para simplificar la depuración, cree una solución de Visual Studio .NET que contenga el proyecto del controlador de lógica de negocios y el proyecto que sincronice la suscripción.</span><span class="sxs-lookup"><span data-stu-id="2acc2-118">To simplify debugging, create a single Visual Studio .NET solution that contains both the business logic handler project and the project that synchronizes the subscription.</span></span> <span data-ttu-id="2acc2-119">En este caso, establezca el proyecto de sincronización como el proyecto de inicio y configure el entorno de la compilación para implementar el ensamblado de lógica de negocios en la ubicación registrada en el paso 1 durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="2acc2-119">In this case, set the synchronization project as the startup project, and configure the build environment to deploy the business logic assembly to the location registered in step 1 during debugging.</span></span>  
  
6.  <span data-ttu-id="2acc2-120">Ejecute los comandos de inserción, actualización o eliminación en la base de datos de suscripciones o de publicación.</span><span class="sxs-lookup"><span data-stu-id="2acc2-120">Execute insert, update, or delete commands against the subscription or publication database.</span></span> <span data-ttu-id="2acc2-121">La ubicación del comando y de la ejecución depende del método que se depura.</span><span class="sxs-lookup"><span data-stu-id="2acc2-121">The command and execution location depends on the method being debugged.</span></span>  
  
7.  <span data-ttu-id="2acc2-122">Inicie el proyecto del paso 3 en modo de depuración para sincronizar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="2acc2-122">Start the project from step 3 in debug mode to synchronize the subscription.</span></span>  
  
8.  <span data-ttu-id="2acc2-123">Suponiendo que no se establezcan otros puntos de interrupción y que se repliquen los comandos adecuados, la ejecución se detiene cuando llega al punto de interrupción en el controlador de lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="2acc2-123">Assuming that no other breakpoints are set and the proper commands are replicated, the execution stops when it reaches the breakpoint in the business logic handler.</span></span>  
  
### <a name="to-debug-a-business-logic-handler-on-a-web-server-using-web-synchronization-or-for-a-sql-server-compact-subscriber"></a><span data-ttu-id="2acc2-124">Para depurar un controlador de lógica de negocios en un servidor web con la sincronización web, o para un suscriptor de SQL Server Compact</span><span class="sxs-lookup"><span data-stu-id="2acc2-124">To debug a business logic handler on a Web server using Web synchronization, or for a SQL Server Compact Subscriber</span></span>  
  
1.  <span data-ttu-id="2acc2-125">Configure la publicación y la distribución, cree una publicación y cree una suscripción de extracción a la publicación.</span><span class="sxs-lookup"><span data-stu-id="2acc2-125">Configure publishing and distribution, create a publication, and create a pull subscription to the publication.</span></span> <span data-ttu-id="2acc2-126">La publicación debe admitir la sincronización web o los suscriptores de [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2acc2-126">The publication must support Web synchronization or [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscribers.</span></span>  
  
2.  <span data-ttu-id="2acc2-127">Cree y registre un controlador de lógica de negocios</span><span class="sxs-lookup"><span data-stu-id="2acc2-127">Create and register a business logic handler.</span></span> <span data-ttu-id="2acc2-128">Para más información, consulte [Implementar un controlador de lógica de negocios para un artículo de mezcla](implement-a-business-logic-handler-for-a-merge-article.md).</span><span class="sxs-lookup"><span data-stu-id="2acc2-128">For more information, see [Implement a Business Logic Handler for a Merge Article](implement-a-business-logic-handler-for-a-merge-article.md).</span></span>  
  
3.  <span data-ttu-id="2acc2-129">Establezca un punto de interrupción en el código del controlador de lógica de negocios, ya sea en el método que se depura o en el constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="2acc2-129">Set a breakpoint in the business logic handler code, either in the method being debugged or in the class constructor.</span></span> <span data-ttu-id="2acc2-130">Para obtener más información acerca de los métodos que se pueden implementar en un controlador de lógica de negocios, vea el tema de métodos <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="2acc2-130">For more information about the methods that can be implemented in a business logic handler, see the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> methods topic.</span></span>  
  
4.  <span data-ttu-id="2acc2-131">Genere el controlador de lógica de negocios en modo de depuración e implemente el archivo de símbolos de ensamblado y depuración (.pdb) en el servidor web, en la ubicación registrada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="2acc2-131">Build the business logic handler in debug mode and deploy the assembly and debugging symbol file (.pdb) at the Web server in the location registered in step 1.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2acc2-132">Si el controlador de lógica de negocios no se genera porque se está usando el ensamblado, escriba el comando `iisreset` en el símbolo del sistema del servidor web para restablecer dicho servidor.</span><span class="sxs-lookup"><span data-stu-id="2acc2-132">If the business logic handler fails to build because the assembly is in use, type the command `iisreset` on the Web server at the command prompt to reset the Web server.</span></span>  
  
5.  <span data-ttu-id="2acc2-133">Sincronice la suscripción con la sincronización web habilitada.</span><span class="sxs-lookup"><span data-stu-id="2acc2-133">Synchronize the subscription with Web synchronization enabled.</span></span> <span data-ttu-id="2acc2-134">Durante la sincronización, el servidor web carga el ensamblado registrado.</span><span class="sxs-lookup"><span data-stu-id="2acc2-134">During synchronization, the Web server loads the registered assembly.</span></span>  
  
6.  <span data-ttu-id="2acc2-135">Con el depurador de Visual Studio .NET, adjúntese a uno de los procesos siguientes del servidor web:</span><span class="sxs-lookup"><span data-stu-id="2acc2-135">Using the Visual Studio .NET debugger, attach to the one of the following processes on the Web server:</span></span>  
  
    -   <span data-ttu-id="2acc2-136">w3wp.exe - Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="2acc2-136">w3wp.exe - Windows Server 2003.</span></span>  
  
    -   <span data-ttu-id="2acc2-137">inetinfo.exe - Windows 2000 y Windows XP.</span><span class="sxs-lookup"><span data-stu-id="2acc2-137">inetinfo.exe - Windows 2000 and Windows XP.</span></span>  
  
7.  <span data-ttu-id="2acc2-138">En la ventana **Salida** , compruebe la depuración generada para comprobar que los símbolos del ensamblado registrado se cargaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="2acc2-138">In the **Output** window, check the debug output to verify that the symbols for the registered assembly loaded properly.</span></span> <span data-ttu-id="2acc2-139">Si no se cargaron los símbolos, asegúrese de que el archivo .pdb correcto se copió en el paso 4, y repita el paso 5.</span><span class="sxs-lookup"><span data-stu-id="2acc2-139">If the symbols were not loaded, ensure that the correct .pdb file was copied in step 4, and repeat step 5.</span></span>  
  
8.  <span data-ttu-id="2acc2-140">Ejecute los comandos de inserción, actualización o eliminación en la base de datos de suscripciones o de publicación.</span><span class="sxs-lookup"><span data-stu-id="2acc2-140">Execute insert, update, or delete commands against the subscription or publication database.</span></span> <span data-ttu-id="2acc2-141">La ubicación del comando y de la ejecución depende del método que se depura.</span><span class="sxs-lookup"><span data-stu-id="2acc2-141">The command and execution location depends on the method being debugged.</span></span>  
  
9. <span data-ttu-id="2acc2-142">Con el depurador de Visual Studio, adjúntese al proceso w3wp.exe.</span><span class="sxs-lookup"><span data-stu-id="2acc2-142">Using the Visual Studio debugger, attach to the w3wp.exe process.</span></span>  
  
10. <span data-ttu-id="2acc2-143">Vuelva a sincronizar la suscripción con la sincronización web.</span><span class="sxs-lookup"><span data-stu-id="2acc2-143">Synchronize the subscription again, using Web synchronization.</span></span>  
  
11. <span data-ttu-id="2acc2-144">Suponiendo que no se establezcan otros puntos de interrupción y que se repliquen los comandos adecuados, la ejecución se detiene cuando llega al punto de interrupción en el controlador de lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="2acc2-144">Assuming that no other breakpoints are set and the proper commands are replicated, the execution stops when it reaches the breakpoint in the business logic handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2acc2-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2acc2-145">See Also</span></span>  
 [<span data-ttu-id="2acc2-146">Implementar un controlador de lógica de negocios para un artículo de mezcla
</span><span class="sxs-lookup"><span data-stu-id="2acc2-146">Implement a Business Logic Handler for a Merge Article</span></span>](implement-a-business-logic-handler-for-a-merge-article.md)  
  
  
