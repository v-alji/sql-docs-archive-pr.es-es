---
title: MSSQLSERVER_8525 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "8525"
helpviewer_keywords:
- 8525 (Database Engine error)
ms.assetid: 297867c1-691e-4d6b-a3be-a7575015ecfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 36db48ca2a9afd08dadcd12abc13b9978e227b00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674856"
---
# <a name="mssqlserver_8525"></a><span data-ttu-id="0562c-102">MSSQLSERVER_8525</span><span class="sxs-lookup"><span data-stu-id="0562c-102">MSSQLSERVER_8525</span></span>
    
## <a name="details"></a><span data-ttu-id="0562c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0562c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0562c-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="0562c-104">Product Name</span></span>|<span data-ttu-id="0562c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0562c-105">SQL Server</span></span>|  
|<span data-ttu-id="0562c-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="0562c-106">Event ID</span></span>|<span data-ttu-id="0562c-107">8525</span><span class="sxs-lookup"><span data-stu-id="0562c-107">8525</span></span>|  
|<span data-ttu-id="0562c-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="0562c-108">Event Source</span></span>|<span data-ttu-id="0562c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0562c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0562c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0562c-110">Component</span></span>|<span data-ttu-id="0562c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0562c-111">SQLEngine</span></span>|  
|<span data-ttu-id="0562c-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0562c-112">Symbolic Name</span></span>||  
|<span data-ttu-id="0562c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0562c-113">Message Text</span></span>|<span data-ttu-id="0562c-114">Se completó la transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="0562c-114">Distributed transaction completed.</span></span> <span data-ttu-id="0562c-115">Dé de alta esta sesión en una nueva transacción o en la transacción NULL.</span><span class="sxs-lookup"><span data-stu-id="0562c-115">Either enlist this session in a new transaction or the NULL transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0562c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="0562c-116">Explanation</span></span>  
 <span data-ttu-id="0562c-117">El modelo de programación para utilizar el Coordinador de transacciones distribuidas con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exige que las aplicaciones se den de alta y de baja explícitamente en una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="0562c-117">The programming model for using the Distributed Transaction Coordinator with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires applications to explicitly enlist to and defect from a distributed transaction.</span></span>  
  
 <span data-ttu-id="0562c-118">Este error se produce cuando se cumplen las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="0562c-118">This error occurs when the following four conditions are met:</span></span>  
  
-   <span data-ttu-id="0562c-119">La aplicación de ha dado de alta en una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="0562c-119">The application has enlisted into a distributed transaction.</span></span>  
  
-   <span data-ttu-id="0562c-120">La transacción ha finalizado (se ha confirmado o revertido) por alguna razón.</span><span class="sxs-lookup"><span data-stu-id="0562c-120">The transaction has ended, either committed or rolled back, for any reason.</span></span>  
  
-   <span data-ttu-id="0562c-121">La aplicación de usuario no se ha dado de baja explícitamente de una transacción distribuida o no se ha dado de alta explícitamente en una nueva transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="0562c-121">The user application has not explicitly defected from a distributed transaction or explicitly enlisted into a new distributed transaction.</span></span>  
  
-   <span data-ttu-id="0562c-122">La aplicación intenta realizar una operación transaccional que no es darse de baja de una transacción distribuida existente ni darse de alta en una nueva transacción distribuida, como emitir una consulta o iniciar una transacción local.</span><span class="sxs-lookup"><span data-stu-id="0562c-122">The application tries to do any transactional operation other than defecting from existing distributed transaction or enlisting to a new distributed transaction, such as issuing a query or starting a local transaction.</span></span>  
  
 <span data-ttu-id="0562c-123">El estado de error 1 se utiliza cuando la aplicación realiza una operación que crea transacciones locales y el estado 2 se utiliza cuando la aplicación intenta darse de alta en una sesión enlazada.</span><span class="sxs-lookup"><span data-stu-id="0562c-123">Error state 1 is used when the application performs an operation that creates local transactions, and state 2 is used when application tries to enlist to a bound session.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0562c-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0562c-124">User Action</span></span>  
 <span data-ttu-id="0562c-125">Después de que una aplicación se haya dado de alta en una transacción distribuida, la aplicación debe darse de baja explícitamente de la transacción distribuida o darse de alta en otra transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="0562c-125">After an application has enlisted into a distributed transaction, the application must explicitly defect from the distributed transaction or enlist to another distributed transaction.</span></span> <span data-ttu-id="0562c-126">Esto la dará de baja implícitamente de una transacción dada de alta previamente.</span><span class="sxs-lookup"><span data-stu-id="0562c-126">This will implicitly defect from a previous enlisted transaction.</span></span> <span data-ttu-id="0562c-127">Para obtener la sintaxis exacta para darse de baja o de alta en una transacción distribuida, vea el manual de la interfaz de programación para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0562c-127">For the exact syntax to defect from or enlist to a distributed transaction, see the programming interface manual for the application.</span></span>  
  
  
