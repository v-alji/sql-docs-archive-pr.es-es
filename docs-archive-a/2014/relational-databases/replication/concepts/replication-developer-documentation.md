---
title: Guía para desarrolladores&#39;(replicación) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- developer's guide [SQL Server replication]
- programming [SQL Server replication]
- replication [SQL Server], development
ms.assetid: 7ee134ae-1cab-4a35-8017-8ac6d8fc64b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d9651aec1f02d19ea3494abf242f75049a4f33f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748077"
---
# <a name="developer39s-guide-replication"></a><span data-ttu-id="ec943-102">Guía para desarrolladores&#39;(replicación)</span><span class="sxs-lookup"><span data-stu-id="ec943-102">Developer&#39;s Guide (Replication)</span></span>
  <span data-ttu-id="ec943-103">La capacidad de configurar, mantener y supervisar mediante programación una topología de replicación permite simplificar las tareas de replicación repetidas y mejorar la experiencia del usuario en las aplicaciones basadas en la replicación.</span><span class="sxs-lookup"><span data-stu-id="ec943-103">The ability to programmatically configure, maintain, and monitor a replication topology enables you to both simplify repeated replication tasks and improve the user experience for your replication-based applications.</span></span> <span data-ttu-id="ec943-104">Al programar la replicación, se puede proporcionar a los usuarios finales funcionalidades de replicación personalizadas sin que sea necesario conocer los procedimientos almacenados de replicación o las aplicaciones ejecutables del agente de replicación, ni tener que usar la interfaz de usuario de replicación que implementa [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec943-104">By programming replication, your end-users can be provided with customized replication functionalities without having to be familiar with replication stored procedures and replication agent executables or having to using the replication user interface implemented by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ec943-105">A continuación se muestran escenarios en los que las aplicaciones podrían beneficiarse del acceso mediante programación a servicios de replicación:</span><span class="sxs-lookup"><span data-stu-id="ec943-105">The following are scenarios in which your applications might benefit from programmatic access to replication services:</span></span>  
  
-   <span data-ttu-id="ec943-106">Al agregar funcionalidades de replicación a una aplicación de usuario final, por ejemplo sincronizar una suscripción de extracción cuando el usuario hace clic en un botón.</span><span class="sxs-lookup"><span data-stu-id="ec943-106">Adding replication functionalities to an existing end-user application, such as synchronizing a pull subscription when the user clicks a button.</span></span>   
-   <span data-ttu-id="ec943-107">Al crear una interfaz de usuario basada en web para administrar la replicación de forma remota.</span><span class="sxs-lookup"><span data-stu-id="ec943-107">Creating a Web-based user interface for remotely administering replication.</span></span>    
-   <span data-ttu-id="ec943-108">Al crear una interfaz de usuario personalizada que exponga solo un subconjunto de la funcionalidad de administración, se puede utilizar para administrar varias topologías de replicación de forma remota desde una sola ubicación o que combinen las funcionalidades de administración y sincronización.</span><span class="sxs-lookup"><span data-stu-id="ec943-108">Creating a custom user interface that exposes only a subset of administration functionality, can be used to remotely administer multiple replication topologies from a single location, or that combine administration and synchronization functionalities.</span></span>    
-   <span data-ttu-id="ec943-109">Al mejorar una herramienta de supervisión existente agregando la capacidad de supervisar el estado de una publicación, suscripción o en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="ec943-109">Improving an existing monitoring tool by adding the ability to monitor the status of a publication, subscription, or at the Distributor.</span></span>    
-   <span data-ttu-id="ec943-110">Al crear una aplicación personalizada para administrar o sincronizar las suscripciones a un publicador de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ec943-110">Creating a custom application to administer or synchronize subscriptions to an Oracle publisher.</span></span>    
-   <span data-ttu-id="ec943-111">Al escribir reglas de negocios personalizadas que se ejecutan cuando se sincroniza una suscripción de mezcla.</span><span class="sxs-lookup"><span data-stu-id="ec943-111">Writing customized business rules that are executed when a merge subscription is synchronized.</span></span>    
-   <span data-ttu-id="ec943-112">Al generar scripts de [!INCLUDE[tsql](../../../includes/tsql-md.md)] que se pueden ejecutar varias veces al configurar nuevos suscriptores.</span><span class="sxs-lookup"><span data-stu-id="ec943-112">Generating [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts that can be run repeated when configuring new Subscribers.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="ec943-113">permite controlar mediante programación los agentes de replicación y administrar y supervisar mediante programación una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="ec943-113">enables you to programmatically control replication agents and to programmatically administer and monitor a replication topology.</span></span> <span data-ttu-id="ec943-114">Para obtener más información sobre la programación de la replicación, vea [Conceptos de la programación de replicación](replication-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="ec943-114">To learn more about programming replication, see [Replication Programming Concepts](replication-programming-concepts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec943-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ec943-115">In This Section</span></span>  
 [<span data-ttu-id="ec943-116">Conceptos de la programación de replicación</span><span class="sxs-lookup"><span data-stu-id="ec943-116">Replication Programming Concepts</span></span>](replication-programming-concepts.md)  
 <span data-ttu-id="ec943-117">Describe los pasos de planeamiento para desarrollar una aplicación que use la replicación.</span><span class="sxs-lookup"><span data-stu-id="ec943-117">Describes the planning steps to develop an application that uses replication.</span></span>  
  
 [<span data-ttu-id="ec943-118">Conceptos de procedimientos almacenados del sistema de replicación</span><span class="sxs-lookup"><span data-stu-id="ec943-118">Replication System Stored Procedures Concepts</span></span>](replication-system-stored-procedures-concepts.md)  
 <span data-ttu-id="ec943-119">Describe cómo se pueden usar los procedimientos almacenados del sistema para proporcionar acceso mediante programación en una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="ec943-119">Describes how system stored procedures can be used to proivide programmatic access in a replication topology.</span></span>  
  
 [<span data-ttu-id="ec943-120">Replication Management Objects Concepts (Conceptos de Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="ec943-120">Replication Management Objects Concepts</span></span>](replication-management-objects-concepts.md)  
 <span data-ttu-id="ec943-121">Explica los conceptos para utilizar Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="ec943-121">Explains the concepts for using Replication Management Objects (RMO).</span></span> <span data-ttu-id="ec943-122">El siguiente es un ensamblado de código administrado que encapsula las funcionalidades de replicación para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec943-122">This is a managed code assembly that encapsulates replication functionalities for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ec943-123">Conceptos de los ejecutables del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="ec943-123">Replication Agent Executables Concepts</span></span>](replication-agent-executables-concepts.md)  
 <span data-ttu-id="ec943-124">Describe el uso de los archivos ejecutables del Agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="ec943-124">Describes the use of Replication Agent Executable files.</span></span>  

  
  
