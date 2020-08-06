---
title: Transacciones heredadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], inherited
- child packages
- inherited transactions [Integration Services]
ms.assetid: 90db5564-d41e-4cfe-8c9e-4e68d41eff1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ecb480420fe9f2492c29fad37ee3cc6e6501e3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673187"
---
# <a name="inherited-transactions"></a><span data-ttu-id="d1b77-102">Transacciones heredadas</span><span class="sxs-lookup"><span data-stu-id="d1b77-102">Inherited Transactions</span></span>
  <span data-ttu-id="d1b77-103">Un paquete puede ejecutar otro paquete, utilizando la tarea Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="d1b77-103">A package can run another package by using the Execute Package task.</span></span> <span data-ttu-id="d1b77-104">El paquete secundario, que es el que ejecuta la tarea Ejecutar paquete, puede crear su propia transacción de paquete o heredar la del paquete primario.</span><span class="sxs-lookup"><span data-stu-id="d1b77-104">The child package, which is the package run by the Execute Package task, may create its own package transaction, or it may inherit the parent package transaction.</span></span>  
  
 <span data-ttu-id="d1b77-105">Un paquete secundario hereda la transacción de paquete primario si se cumplen las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1b77-105">A child package inherits the parent package transaction if both of the following are true:</span></span>  
  
-   <span data-ttu-id="d1b77-106">Una tarea Ejecutar paquete invoca al paquete.</span><span class="sxs-lookup"><span data-stu-id="d1b77-106">The package is invoked by an Execute Package task.</span></span>  
  
-   <span data-ttu-id="d1b77-107">La tarea Ejecutar paquete que invocó al paquete también se combina con la transacción del paquete primario.</span><span class="sxs-lookup"><span data-stu-id="d1b77-107">The Execute Package task that invoked the package also joined the parent package transaction.</span></span>  
  
 <span data-ttu-id="d1b77-108">Los contenedores y tareas del paquete secundario no se pueden combinar con la transacción del paquete primario, a menos que el propio paquete secundario se combine con la transacción.</span><span class="sxs-lookup"><span data-stu-id="d1b77-108">Containers and tasks in the child package cannot join the parent package transaction unless the child package itself joins the transaction.</span></span>  
  
## <a name="illustration-of-package-transactions"></a><span data-ttu-id="d1b77-109">Ilustración de transacciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="d1b77-109">Illustration of Package Transactions</span></span>  
 <span data-ttu-id="d1b77-110">En el diagrama siguiente, hay tres paquetes que utilizan transacciones.</span><span class="sxs-lookup"><span data-stu-id="d1b77-110">In the following diagram, there are three packages that all use transactions.</span></span> <span data-ttu-id="d1b77-111">Cada paquete contiene varias tareas.</span><span class="sxs-lookup"><span data-stu-id="d1b77-111">Each package contains multiple tasks.</span></span> <span data-ttu-id="d1b77-112">Para resaltar el comportamiento de las transacciones, solo se muestran las tareas Ejecutar paquete.</span><span class="sxs-lookup"><span data-stu-id="d1b77-112">To emphasize the behavior of the transactions, only the Execute Package tasks are shown.</span></span> <span data-ttu-id="d1b77-113">El paquete A ejecuta los paquetes B y C. A su vez, el paquete B ejecuta los paquetes D y E, y el paquete C ejecuta el paquete F.</span><span class="sxs-lookup"><span data-stu-id="d1b77-113">Package A runs packages B and C. In turn, package B runs packages D and E, and package C runs package F.</span></span>  
  
 <span data-ttu-id="d1b77-114">Los paquetes y las tareas tienen los siguientes atributos de transacción:</span><span class="sxs-lookup"><span data-stu-id="d1b77-114">Packages and tasks have the following transaction attributes:</span></span>  
  
-   <span data-ttu-id="d1b77-115">**TransactionOption** se establece en **Required** en los paquetes A y C</span><span class="sxs-lookup"><span data-stu-id="d1b77-115">**TransactionOption** is set to **Required** on packages A and C</span></span>  
  
-   <span data-ttu-id="d1b77-116">**TransactionOption** se establece en **Supported** en los paquetes B y D, y en las tareas Ejecutar paquete B, Ejecutar paquete D y Ejecutar paquete F.</span><span class="sxs-lookup"><span data-stu-id="d1b77-116">**TransactionOption** is set to **Supported** on packages B and D, and on the tasks Execute Package B, Execute Package D, and Execute Package F.</span></span>  
  
-   <span data-ttu-id="d1b77-117">**TransactionOption** se establece en **NotSupported** en el paquete E y en las tareas Ejecutar paquete C y Ejecutar paquete E.</span><span class="sxs-lookup"><span data-stu-id="d1b77-117">**TransactionOption** is set to **NotSupported** on package E, and on the tasks Execute Package C and Execute Package E.</span></span>  
  
 <span data-ttu-id="d1b77-118">![Flujo de transacciones heredadas](media/mw-dts-executepack.gif "Flujo de transacciones heredadas")</span><span class="sxs-lookup"><span data-stu-id="d1b77-118">![Flow of inherited transactions](media/mw-dts-executepack.gif "Flow of inherited transactions")</span></span>  
  
 <span data-ttu-id="d1b77-119">Solo los paquetes B, D y F pueden heredar transacciones de sus paquetes primarios.</span><span class="sxs-lookup"><span data-stu-id="d1b77-119">Only packages B, D, and F can inherit transactions from their parent packages.</span></span>  
  
 <span data-ttu-id="d1b77-120">Los paquetes B y D heredan la transacción iniciada por el paquete A. </span><span class="sxs-lookup"><span data-stu-id="d1b77-120">Packages B and D inherit the transaction that was started by package A.</span></span>  
  
 <span data-ttu-id="d1b77-121">El paquete F hereda la transacción iniciada por el paquete C.</span><span class="sxs-lookup"><span data-stu-id="d1b77-121">Package F inherits the transaction that was started by package C.</span></span>  
  
 <span data-ttu-id="d1b77-122">Los paquetes A y C controlan sus propias transacciones.</span><span class="sxs-lookup"><span data-stu-id="d1b77-122">Packages A and C control their own transactions.</span></span>  
  
 <span data-ttu-id="d1b77-123">El paquete E no utiliza transacciones.</span><span class="sxs-lookup"><span data-stu-id="d1b77-123">Package E does not use transactions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d1b77-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="d1b77-124">Related Tasks</span></span>  
 [<span data-ttu-id="d1b77-125">Configurar un paquete para el uso de transacciones</span><span class="sxs-lookup"><span data-stu-id="d1b77-125">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
  
