---
title: 'Tutorial: Replicar datos con clientes móviles | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: af673514-30c7-403a-9d18-d01e1a095115
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdf8be7cb0da11f0aa1022ba656d50c10826ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677522"
---
# <a name="tutorial-replicating-data-with-mobile-clients"></a><span data-ttu-id="21299-102">Tutorial: Replicar datos con clientes móviles</span><span class="sxs-lookup"><span data-stu-id="21299-102">Tutorial: Replicating Data with Mobile Clients</span></span>
  <span data-ttu-id="21299-103">La replicación es una buena solución al problema de mover datos entre un servidor central y clientes móviles que solo se conectan en determinadas ocasiones.</span><span class="sxs-lookup"><span data-stu-id="21299-103">Replication is a good solution to the problem of moving data between a central server and mobile clients that are only occasionally connected.</span></span> <span data-ttu-id="21299-104">La utilización de asistentes para replicación le facilitará la configuración y administración de una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="21299-104">Using replication's wizards, you can easily configure and administer a replication topology.</span></span> <span data-ttu-id="21299-105">Este tutorial le mostrará cómo configurar una topología de replicación para clientes móviles.</span><span class="sxs-lookup"><span data-stu-id="21299-105">This tutorial shows you how to configure a replication topology for mobile clients.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="21299-106">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="21299-106">What You Will Learn</span></span>  
 <span data-ttu-id="21299-107">En este tutorial utilizará la replicación de mezcla para publicar datos de una base de datos central en uno o más usuarios móviles para que cada usuario obtenga un subconjunto de datos filtrado de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="21299-107">In this tutorial you will use merge replication to publish data from a central database to one or more mobile users so that each user gets a uniquely filtered subset of the data.</span></span> <span data-ttu-id="21299-108">En la primera lección se muestra cómo utilizar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para crear una publicación.</span><span class="sxs-lookup"><span data-stu-id="21299-108">The first lesson shows how to use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a publication.</span></span> <span data-ttu-id="21299-109">Las lecciones posteriores muestran cómo crear y sincronizar una suscripción.</span><span class="sxs-lookup"><span data-stu-id="21299-109">Later lessons show how to create and synchronize a subscription.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21299-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21299-110">Requirements</span></span>  
 <span data-ttu-id="21299-111">Este tutorial está destinado a usuarios que están familiarizados con las operaciones básicas de las bases de datos, pero que tienen una experiencia limitada en operaciones de replicación.</span><span class="sxs-lookup"><span data-stu-id="21299-111">This tutorial is intended for users familiar with fundamental database operations, but who have limited experience with replication.</span></span> <span data-ttu-id="21299-112">Antes de comenzar este tutorial, debe completar [el tutorial: preparar el servidor para la replicación](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="21299-112">Before you start this tutorial, you must complete [Tutorial: Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
 <span data-ttu-id="21299-113">Para utilizar este tutorial, el sistema debe tener instalados los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="21299-113">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   <span data-ttu-id="21299-114">En el publicador (servidor de origen):</span><span class="sxs-lookup"><span data-stu-id="21299-114">At the Publisher server (source):</span></span>  
  
    -   <span data-ttu-id="21299-115">Cualquier edición de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], excepto Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) o [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21299-115">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for Express ([!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]) or [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> <span data-ttu-id="21299-116">Estas ediciones no pueden ser publicadores de replicación.</span><span class="sxs-lookup"><span data-stu-id="21299-116">These editions cannot be a replication Publisher.</span></span>  
  
    -   <span data-ttu-id="21299-117">La base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21299-117">The [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="21299-118">Con el objeto de mejorar la seguridad, las bases de datos de ejemplo no se instalan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="21299-118">To enhance security, the sample databases are not installed by default.</span></span>  
  
-   <span data-ttu-id="21299-119">En el suscriptor (servidor de destino):</span><span class="sxs-lookup"><span data-stu-id="21299-119">Subscriber server (destination):</span></span>  
  
    -   <span data-ttu-id="21299-120">Cualquier edición de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], excepto [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21299-120">Any edition of [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], except for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="21299-121">no es compatible con la publicación creada en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="21299-121">is not supported by the publication created in this tutorial.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="21299-122">La replicación no se instala de manera predeterminada en [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21299-122">Replication is not installed by default on [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21299-123">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], debe conectarse al publicador y al suscriptor con un inicio de sesión que sea miembro del rol fijo de servidor sysadmin.</span><span class="sxs-lookup"><span data-stu-id="21299-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you must connect to the Publisher and Subscriber using a login that is a member of the sysadmin fixed server role.</span></span>  
  
 <span data-ttu-id="21299-124">**Tiempo estimado para completar este tutorial: 30 minutos.**</span><span class="sxs-lookup"><span data-stu-id="21299-124">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="21299-125">Lecciones de este tutorial</span><span class="sxs-lookup"><span data-stu-id="21299-125">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="21299-126">Lección 1: Publicación de datos con la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="21299-126">Lesson 1: Publishing Data Using Merge Replication</span></span>](lesson-1-publishing-data-using-merge-replication.md)  
  
-   [<span data-ttu-id="21299-127">Lección 2: Creación de una suscripción a la publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="21299-127">Lesson 2: Creating a Subscription to the Merge Publication</span></span>](lesson-2-creating-a-subscription-to-the-merge-publication.md)  
  
 [<span data-ttu-id="21299-128">Inicio del tutorial</span><span class="sxs-lookup"><span data-stu-id="21299-128">Start the Tutorial</span></span>](merge/merge-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="21299-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21299-129">See Also</span></span>  
 [<span data-ttu-id="21299-130">Conceptos de la programación de replicación</span><span class="sxs-lookup"><span data-stu-id="21299-130">Replication Programming Concepts</span></span>](concepts/replication-programming-concepts.md)  
  
  
