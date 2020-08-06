---
title: Configurar un paquete para usar transacciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], configuring packages to use
ms.assetid: 8bf14957-27b4-456b-81d9-e1a0e0ca94b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f469c2439deb2d16ac9046a1628e82c34e39b31d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744818"
---
# <a name="configure-a-package-to-use-transactions"></a><span data-ttu-id="0b9dd-102">Configurar un paquete para el uso de transacciones</span><span class="sxs-lookup"><span data-stu-id="0b9dd-102">Configure a Package to Use Transactions</span></span>
  <span data-ttu-id="0b9dd-103">Cuando configura un paquete para utilizar transacciones, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="0b9dd-103">When you configure a package to use transactions, you have two options:</span></span>  
  
-   <span data-ttu-id="0b9dd-104">Tener una transacción única para el paquete.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-104">Have a single transaction for the package.</span></span> <span data-ttu-id="0b9dd-105">En este caso, es el propio paquete el que *inicia* esta transacción, mientras que las tareas y contenedores individuales del paquete participan en esta transacción única.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-105">In this case, it is the package itself that *initiates* this transaction, whereas individual tasks and containers in the package participate in this single transaction.</span></span>  
  
-   <span data-ttu-id="0b9dd-106">Tener varias transacciones en el paquete.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-106">Have multiple transactions in the package.</span></span> <span data-ttu-id="0b9dd-107">En este caso, el paquete admite transacciones, pero las tareas y contenedores individuales del paquete inician realmente las transacciones.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-107">In this case, the package supports transactions, but individual tasks and containers in the package actually initiate the transactions.</span></span>  
  
 <span data-ttu-id="0b9dd-108">El procedimiento siguiente describe cómo configurar ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-108">The following procedures describe how to configure both options.</span></span>  
  
## <a name="configuring-a-single-transaction"></a><span data-ttu-id="0b9dd-109">Configurar una transacción única</span><span class="sxs-lookup"><span data-stu-id="0b9dd-109">Configuring a Single Transaction</span></span>  
 <span data-ttu-id="0b9dd-110">En esta opción, el propio paquete inicia una transacción única.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-110">In this option, the package itself initiates a single transaction.</span></span> <span data-ttu-id="0b9dd-111">Configure el paquete para iniciar esta transacción estableciendo la propiedad TransactionOption del paquete en `Required` .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-111">You configure the package to initiate this transaction by setting the TransactionOption property of the package to `Required`.</span></span>  
  
 <span data-ttu-id="0b9dd-112">A continuación, dé de alta tareas y contenedores específicos en esta transacción única.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-112">Next, you enlist specific tasks and containers in this single transaction.</span></span> <span data-ttu-id="0b9dd-113">Para dar de alta una tarea o un contenedor en una transacción, establezca la propiedad TransactionOption de esa tarea o contenedor en `Supported` .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-113">To enlist a task or container in a transaction, you set the TransactionOption property of that task or container to `Supported`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-a-single-transaction"></a><span data-ttu-id="0b9dd-114">Para configurar un paquete para usar una transacción única</span><span class="sxs-lookup"><span data-stu-id="0b9dd-114">To configure a package to use a single transaction</span></span>  
  
1.  <span data-ttu-id="0b9dd-115">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea configurar para usar una transacción.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use a transaction.</span></span>  
  
2.  <span data-ttu-id="0b9dd-116">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0b9dd-117">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-117">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="0b9dd-118">Haga clic con el botón derecho en cualquier parte del fondo de la superficie de diseño de flujo de control y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-118">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="0b9dd-119">En la ventana **propiedades** , establezca la propiedad TransactionOption en `Required` .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-119">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
6.  <span data-ttu-id="0b9dd-120">En la superficie de diseño de la pestaña **Flujo de control** , haga clic con el botón derecho en la tarea o contenedor que quiere inscribir en la transacción y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-120">On the design surface of the **ControlFlow** tab, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="0b9dd-121">En la ventana **propiedades** , establezca la propiedad TransactionOption en `Supported` .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-121">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b9dd-122">Para dar de alta una conexión en una transacción, inscriba las tareas que usan la conexión en la transacción.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-122">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="0b9dd-123">Para más información, vea [Conexiones de Integration Services &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="0b9dd-123">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
8.  <span data-ttu-id="0b9dd-124">Repita los pasos 6 y 7 para cada tarea y contenedor que desee inscribir en la transacción.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-124">Repeat steps 6 and 7 for each task and container that you want to enroll in the transaction.</span></span>  
  
## <a name="configuring-multiple-transactions"></a><span data-ttu-id="0b9dd-125">Configurar varias transacciones</span><span class="sxs-lookup"><span data-stu-id="0b9dd-125">Configuring Multiple Transactions</span></span>  
 <span data-ttu-id="0b9dd-126">En esta opción, el propio paquete admite las transacciones pero no inicia una transacción.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-126">In this option, the package itself supports transactions but does not start a transaction.</span></span> <span data-ttu-id="0b9dd-127">Configure el paquete para admitir transacciones estableciendo la propiedad TransactionOption del paquete en `Supported` .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-127">You configure the package to support transactions by setting the TransactionOption property of the package to `Supported`.</span></span>  
  
 <span data-ttu-id="0b9dd-128">A continuación, configure las tareas y contenedores deseados dentro del paquete para iniciar transacciones o participar en ellas.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-128">Next, you configure the desired tasks and containers inside the package to initiate or participate in transactions.</span></span> <span data-ttu-id="0b9dd-129">Para configurar una tarea o un contenedor para iniciar una transacción, establezca la propiedad TransactionOption de esa tarea o contenedor en `Required` .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-129">To configure a task or container to initiate a transaction, you set the TransactionOption property of that task or container to `Required`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-multiple-transactions"></a><span data-ttu-id="0b9dd-130">Para configurar un paquete de modo que use varias transacciones</span><span class="sxs-lookup"><span data-stu-id="0b9dd-130">To configure a package to use multiple transactions</span></span>  
  
1.  <span data-ttu-id="0b9dd-131">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea configurar para usar transacciones.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-131">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use transaction.s</span></span>  
  
2.  <span data-ttu-id="0b9dd-132">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-132">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0b9dd-133">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-133">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="0b9dd-134">Haga clic con el botón derecho en cualquier parte del fondo de la superficie de diseño de flujo de control y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-134">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="0b9dd-135">En la ventana **propiedades** , establezca la propiedad TransactionOption en `Supported` .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-135">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b9dd-136">El paquete ejecuta transacciones pero las transacciones las inician tareas o contenedores del paquete.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-136">The package supports transactions, but the transactions are started by task or containers in the package.</span></span>  
  
6.  <span data-ttu-id="0b9dd-137">En la superficie de diseño de la pestaña **Flujo de control** , haga clic con el botón derecho en la tarea o contenedor del paquete para el que quiere iniciar una transacción y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-137">On the design surface of the **ControlFlow** tab, right-click the task or the container in the package for which you want to start a transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="0b9dd-138">En la ventana **propiedades** , establezca la propiedad TransactionOption en `Required` .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-138">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
8.  <span data-ttu-id="0b9dd-139">Si contenedor inicia una transacción, haga clic con el botón derecho en la tarea o el contenedor que quiere inscribir en la transacción y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-139">If a transaction is started by a container, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
9. <span data-ttu-id="0b9dd-140">En la ventana **propiedades** , establezca la propiedad TransactionOption en `Supported` .</span><span class="sxs-lookup"><span data-stu-id="0b9dd-140">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b9dd-141">Para dar de alta una conexión en una transacción, inscriba las tareas que usan la conexión en la transacción.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-141">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="0b9dd-142">Para más información, vea [Conexiones de Integration Services &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="0b9dd-142">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
10. <span data-ttu-id="0b9dd-143">Repita los pasos 6 a 9 para cada tarea y cada contenedor que inician una transacción.</span><span class="sxs-lookup"><span data-stu-id="0b9dd-143">Repeat steps 6 through 9 for each task and container that starts a transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9dd-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b9dd-144">See Also</span></span>  
 [<span data-ttu-id="0b9dd-145">Transacciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="0b9dd-145">Integration Services Transactions</span></span>](integration-services-transactions.md)  
  
  
