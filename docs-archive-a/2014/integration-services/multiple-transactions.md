---
title: Varias transacciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], multiple
- multiple transactions
ms.assetid: c3664a94-be89-40c0-a3a0-84b74a7fedbe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ff909c92a23c965047edc0fcf278e17e4c76d94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673092"
---
# <a name="multiple-transactions"></a><span data-ttu-id="409a0-102">Varias transacciones</span><span class="sxs-lookup"><span data-stu-id="409a0-102">Multiple Transactions</span></span>
  <span data-ttu-id="409a0-103">Un paquete puede incluir transacciones no relacionadas en un paquete de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="409a0-103">It is possible for a package to include unrelated transactions in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="409a0-104">Cuando un contenedor situado en medio de una jerarquía de contenedores anidados no admite transacciones, los contenedores situados en un nivel superior o inferior de la jerarquía inician transacciones independientes, si están configurados para admitir transacciones.</span><span class="sxs-lookup"><span data-stu-id="409a0-104">Any time a container in the middle of a nested container hierarchy does not support transactions, the containers above or below it in the hierarchy start separate transactions if they are configured to support transactions.</span></span> <span data-ttu-id="409a0-105">Las transacciones se confirman o se revierten en orden, desde la tarea más interna en la jerarquía de contenedores anidados hasta el paquete.</span><span class="sxs-lookup"><span data-stu-id="409a0-105">The transactions commit or roll back in order from the innermost task in the nested container hierarchy to the package.</span></span> <span data-ttu-id="409a0-106">Sin embargo, una vez confirmada la transacción interna, no se revierte aunque se anule una transacción externa.</span><span class="sxs-lookup"><span data-stu-id="409a0-106">However, after the inner transaction commits, it does not roll back if an outer transaction is aborted.</span></span>

## <a name="illustration-of-multiple-transactions"></a><span data-ttu-id="409a0-107">Ilustración de varias transacciones</span><span class="sxs-lookup"><span data-stu-id="409a0-107">Illustration of Multiple Transactions</span></span>
 <span data-ttu-id="409a0-108">Por ejemplo, un paquete tiene un contenedor de secuencias con dos contenedores de bucles Foreach y cada contenedor incluye dos tareas Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="409a0-108">For example, a package has a Sequence container that holds two Foreach Loop containers, and each container include two Execute SQL tasks.</span></span> <span data-ttu-id="409a0-109">El contenedor de secuencias y las tareas Ejecutar SQL admiten transacciones, pero los contenedores de bucles Foreach no las admiten.</span><span class="sxs-lookup"><span data-stu-id="409a0-109">The Sequence container supports transactions, the Foreach Loop containers do not, and the Execute SQL tasks do.</span></span> <span data-ttu-id="409a0-110">En este ejemplo, cada tarea Ejecutar SQL iniciaría su propia transacción, que no se revertiría aunque se anulara la tarea de secuencia.</span><span class="sxs-lookup"><span data-stu-id="409a0-110">In this example, each Execute SQL task would start its own transaction and would not roll back if the transaction on the Sequence task was aborted.</span></span>

 <span data-ttu-id="409a0-111">Las propiedades de TransactionOption del contenedor de secuencias, el contenedor de bucles Foreach y las tareas Ejecutar SQL se establecen de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="409a0-111">The TransactionOption properties of the Sequence container, Foreach Loop container and the Execute SQL tasks are set as follows:</span></span>

-   <span data-ttu-id="409a0-112">La propiedad TransactionOption del contenedor de secuencias se establece en **Required**.</span><span class="sxs-lookup"><span data-stu-id="409a0-112">The TransactionOption property of the Sequence container is set to **Required**.</span></span>

-   <span data-ttu-id="409a0-113">Las propiedades TransactionOption de los contenedores de bucles Foreach se establecen en **NotSupported**.</span><span class="sxs-lookup"><span data-stu-id="409a0-113">The TransactionOption properties of the Foreach Loop containers are set to **NotSupported**.</span></span>

-   <span data-ttu-id="409a0-114">Las propiedades de TransactionOption las tareas Ejecutar SQL se establecen en **Required**.</span><span class="sxs-lookup"><span data-stu-id="409a0-114">The TransactionOption properties of the Execute SQL tasks are set to **Required**.</span></span>

 <span data-ttu-id="409a0-115">En el diagrama siguiente se muestran las cinco transacciones no relacionadas del paquete.</span><span class="sxs-lookup"><span data-stu-id="409a0-115">The following diagram shows the five unrelated transactions in the package.</span></span> <span data-ttu-id="409a0-116">El contenedor de secuencias inicia una transacción y las tareas Ejecutar SQL inician las otras cuatro.</span><span class="sxs-lookup"><span data-stu-id="409a0-116">One transaction is started by the Sequence container and four transactions are started by the Execute SQL tasks.</span></span>

 <span data-ttu-id="409a0-117">![Implementación de varias transacciones](media/mw-dts-trans2.gif "Implementación de varias transacciones")</span><span class="sxs-lookup"><span data-stu-id="409a0-117">![Implementation of multiple transactions](media/mw-dts-trans2.gif "Implementation of multiple transactions")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="409a0-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="409a0-118">Related Tasks</span></span>
 [<span data-ttu-id="409a0-119">Configurar un paquete para el uso de transacciones</span><span class="sxs-lookup"><span data-stu-id="409a0-119">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)


