---
title: 'Tutorial: Preparar el servidor para la replicación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: ce30a095-2975-4387-9377-94a461ac78ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1f036ff2a111ee6b5f97655b9bebaf34391a436
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677526"
---
# <a name="tutorial-preparing-the-server-for-replication"></a><span data-ttu-id="a83e7-102">Tutorial: Preparar el servidor para la replicación</span><span class="sxs-lookup"><span data-stu-id="a83e7-102">Tutorial: Preparing the Server for Replication</span></span>
  <span data-ttu-id="a83e7-103">Es importante planificar la seguridad antes de configurar la topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="a83e7-103">It is important to plan for security before you configure your replication topology.</span></span> <span data-ttu-id="a83e7-104">En este tutorial se muestra cómo proteger una topología de replicación y cómo configurar la distribución, que es el primer paso en la replicación de datos.</span><span class="sxs-lookup"><span data-stu-id="a83e7-104">This tutorial shows you how to better secure a replication topology as well as how to configure distribution, which is the first step in replicating data.</span></span> <span data-ttu-id="a83e7-105">Debe finalizar este tutorial antes que cualquiera de los otros tutoriales.</span><span class="sxs-lookup"><span data-stu-id="a83e7-105">You must complete this tutorial before any of the others.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a83e7-106">Para replicar datos de forma segura entre servidores, debe implementar todas las recomendaciones de [Prácticas recomendadas de seguridad de replicación](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="a83e7-106">To replicate data securely between servers, you should implement all of the recommendations in [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="a83e7-107">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="a83e7-107">What You Will Learn</span></span>  
 <span data-ttu-id="a83e7-108">En este tutorial aprenderá a preparar un servidor de manera que la replicación se ejecute de forma segura con los privilegios mínimos.</span><span class="sxs-lookup"><span data-stu-id="a83e7-108">In this tutorial you will learn how to prepare a server so that replication can run securely with least privileges.</span></span> <span data-ttu-id="a83e7-109">En la primera lección se muestra cómo crear cuentas de servicio de Windows utilizadas para ejecutar agentes de replicación.</span><span class="sxs-lookup"><span data-stu-id="a83e7-109">The first lesson shows how to create the Windows service accounts used to run replication agents.</span></span> <span data-ttu-id="a83e7-110">En la segunda lección se muestra cómo configurar la carpeta utilizada para generar y almacenar instantáneas de publicación.</span><span class="sxs-lookup"><span data-stu-id="a83e7-110">The second lesson shows how to configure the folder used to generate and store publication snapshots.</span></span> <span data-ttu-id="a83e7-111">En la tercera lección se muestra cómo configurar la distribución y establecer permisos.</span><span class="sxs-lookup"><span data-stu-id="a83e7-111">The third lesson shows how to configure distribution and set permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a83e7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a83e7-112">Requirements</span></span>  
 <span data-ttu-id="a83e7-113">Este tutorial está destinado a usuarios que están familiarizados con las operaciones básicas de las bases de datos, pero que tienen una experiencia limitada en operaciones de replicación.</span><span class="sxs-lookup"><span data-stu-id="a83e7-113">This tutorial is intended for users familiar with fundamental database operations, but who have limited exposure to replication.</span></span>  
  
 <span data-ttu-id="a83e7-114">Para utilizar este tutorial, el sistema debe tener instalados los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="a83e7-114">To use this tutorial, your system must have the following components installed:</span></span>  
  
-   [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] <span data-ttu-id="a83e7-115">con la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a83e7-115">with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="a83e7-116">Con el objeto de mejorar la seguridad, las bases de datos de ejemplo no se instalan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a83e7-116">To enhance security, the sample databases are not installed by default.</span></span>  
  
 <span data-ttu-id="a83e7-117">**Tiempo estimado para completar este tutorial: 30 minutos.**</span><span class="sxs-lookup"><span data-stu-id="a83e7-117">**Estimated time to complete this tutorial: 30 minutes.**</span></span>  
  
## <a name="lessons-in-this-tutorial"></a><span data-ttu-id="a83e7-118">Lecciones de este tutorial</span><span class="sxs-lookup"><span data-stu-id="a83e7-118">Lessons in This Tutorial</span></span>  
  
-   [<span data-ttu-id="a83e7-119">Lección 1: Creación de cuentas de Windows para replicación</span><span class="sxs-lookup"><span data-stu-id="a83e7-119">Lesson 1: Creating Windows Accounts for Replication</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
-   [<span data-ttu-id="a83e7-120">Lección 2: Preparar la carpeta de instantáneas</span><span class="sxs-lookup"><span data-stu-id="a83e7-120">Lesson 2: Preparing the Snapshot Folder</span></span>](lesson-2-preparing-the-snapshot-folder.md)  
  
-   [<span data-ttu-id="a83e7-121">Lección 3: Configurar la distribución</span><span class="sxs-lookup"><span data-stu-id="a83e7-121">Lesson 3: Configuring Distribution</span></span>](lesson-3-configuring-distribution.md)  
  
 [<span data-ttu-id="a83e7-122">Inicio del tutorial</span><span class="sxs-lookup"><span data-stu-id="a83e7-122">Start the Tutorial</span></span>](lesson-1-creating-windows-accounts-for-replication.md)  
  
## <a name="see-also"></a><span data-ttu-id="a83e7-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a83e7-123">See Also</span></span>  
 <span data-ttu-id="a83e7-124">[Configurar distribución](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="a83e7-124">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="a83e7-125">Seguridad de Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a83e7-125">SQL Server Replication Security</span></span>](security/view-and-modify-replication-security-settings.md)  
  
  
