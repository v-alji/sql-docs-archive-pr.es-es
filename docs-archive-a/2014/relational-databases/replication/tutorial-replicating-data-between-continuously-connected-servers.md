---
title: 'Tutorial: Replicar datos entre servidores conectados de forma continua | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- tutorials [SQL Server replication]
- replication [SQL Server], tutorials
- wizards [SQL Server replication]
ms.assetid: 7b18a04a-2c3d-4efe-a0bc-c3f92be72fd0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 415cac62112c1c1d2aa6c42ec189c2614ec03923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677524"
---
# <a name="tutorial-replicating-data-between-continuously-connected-servers"></a><span data-ttu-id="92c4b-102">Tutorial: Replicar datos entre servidores conectados de forma continua</span><span class="sxs-lookup"><span data-stu-id="92c4b-102">Tutorial: Replicating Data Between Continuously Connected Servers</span></span>
  <span data-ttu-id="92c4b-103">La replicación es una buena solución para el problema de mover datos entre servidores conectados de forma continua.</span><span class="sxs-lookup"><span data-stu-id="92c4b-103">Replication is a good solution to the problem of moving data between continuously connected servers.</span></span> <span data-ttu-id="92c4b-104">La utilización de asistentes para replicación le facilitará la configuración y administración de una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="92c4b-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="92c4b-105">Este tutorial le mostrará cómo configurar una topología de replicación para servidores conectados de forma continua.</span><span class="sxs-lookup"><span data-stu-id="92c4b-105">This tutorial shows you how to configure a replication topology for continuously connected servers.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="92c4b-106">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="92c4b-106">What You Will Learn</span></span>  
 <span data-ttu-id="92c4b-107">Este tutorial le mostrará cómo publicar datos de una base de datos a otra con la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="92c4b-107">This tutorial will show you how to publish data from one database to another using transactional replication.</span></span> <span data-ttu-id="92c4b-108">En la primera lección se muestra cómo utilizar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para crear una publicación.</span><span class="sxs-lookup"><span data-stu-id="92c4b-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="92c4b-109">En las siguientes lecciones se explica cómo crear y validar una suscripción y cómo medir la latencia.</span><span class="sxs-lookup"><span data-stu-id="92c4b-109">Later lessons show how to create and validate a subscription and how to measure latency.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c4b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92c4b-110">Requirements</span></span>  
 <span data-ttu-id="92c4b-111">Este tutorial está destinado a usuarios que están familiarizados con las operaciones básicas de las bases de datos, pero que tienen una experiencia limitada en operaciones de replicación.</span><span class="sxs-lookup"><span data-stu-id="92c4b-111">This tutorial is intended for users who are familiar with basic database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="92c4b-112">Para realizar este tutorial, es preciso que haya finalizado el anterior, [Preparar el servidor para replicación](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="92c4b-112">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="92c4b-113">Para utilizar este tutorial, el sistema debe contar con los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="92c4b-113">To use this tutorial, your system must have the following components:</span></span>  
  
-   <span data-ttu-id="92c4b-114">En el publicador (servidor de origen):</span><span class="sxs-lookup"><span data-stu-id="92c4b-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="92c4b-115">Cualquier edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], excepto Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) o [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92c4b-115">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="92c4b-116">Estas ediciones no pueden ser publicadores de replicación.</span><span class="sxs-lookup"><span data-stu-id="92c4b-116">These editions cannot be replication Publishers.</span></span>  
  
    -   [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] <span data-ttu-id="92c4b-117">Base de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="92c4b-117">sample database.</span></span> <span data-ttu-id="92c4b-118">Con el objeto de mejorar la seguridad, las bases de datos de ejemplo no se instalan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="92c4b-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="92c4b-119">En el suscriptor (servidor de destino):</span><span class="sxs-lookup"><span data-stu-id="92c4b-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="92c4b-120">Cualquier edición de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], excepto [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92c4b-120">Any edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="92c4b-121">no puede ser un suscriptor de replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="92c4b-121">cannot be a Subscriber in transactional replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92c4b-122">La replicación no se instala de forma predeterminada en [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92c4b-122">Replication is not installed on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92c4b-123">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , debe conectarse al publicador y al suscriptor con un inicio de sesión de que sea miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="92c4b-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="92c4b-124">**Tiempo estimado para completar este tutorial: 30 minutos.**</span><span class="sxs-lookup"><span data-stu-id="92c4b-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="92c4b-125">Lecciones de este tutorial</span><span class="sxs-lookup"><span data-stu-id="92c4b-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="92c4b-126">Lección 1: Publicar datos con la replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="92c4b-126">Lesson 1: Publishing Data Using Transactional Replication</span></span>](lesson-1-publishing-data-using-transactional-replication.md)  
  
-   [<span data-ttu-id="92c4b-127">Lección 2: Crear una suscripción a la publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="92c4b-127">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>](lesson-2-creating-a-subscription-to-the-transactional-publication.md)  
  
-   [<span data-ttu-id="92c4b-128">Lección 3: Validar la suscripción y medir la latencia</span><span class="sxs-lookup"><span data-stu-id="92c4b-128">Lesson 3: Validating the Subscription and Measuring Latency</span></span>](lesson-3-validating-the-subscription-and-measuring-latency.md)  
  
 [<span data-ttu-id="92c4b-129">Inicio del tutorial</span><span class="sxs-lookup"><span data-stu-id="92c4b-129">Start the Tutorial</span></span>](transactional/transactional-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="92c4b-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92c4b-130">See Also</span></span>  
 [<span data-ttu-id="92c4b-131">Conceptos de la programación de replicación</span><span class="sxs-lookup"><span data-stu-id="92c4b-131">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
