---
title: Conceptos de los ejecutables del Agente de replicación | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- programming interfaces [SQL Server replication]
- programming [SQL Server replication], agents
- replication [SQL Server], agents and profiles
- agents [SQL Server replication], executables
- command prompt [SQL Server replication]
ms.assetid: cba476df-d4ea-44c9-bb86-81488971e328
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73f9fe0d1a98fa1afc813cd113dcced685b4f98a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750753"
---
# <a name="replication-agent-executables-concepts"></a><span data-ttu-id="0be89-102">Conceptos de los ejecutables del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="0be89-102">Replication Agent Executables Concepts</span></span>
  <span data-ttu-id="0be89-103">Los agentes de replicación se pueden controlar mediante programación de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="0be89-103">Replication agents can be controlled programmatically in the following ways:</span></span>  
  
-   <span data-ttu-id="0be89-104">Mediante las interfaces de programación del agente administrado en el espacio de nombres <xref:Microsoft.SqlServer.Replication>.</span><span class="sxs-lookup"><span data-stu-id="0be89-104">Using the managed agent programming interfaces in the <xref:Microsoft.SqlServer.Replication> Namespace.</span></span>  
  
-   <span data-ttu-id="0be89-105">Invocando a los archivos ejecutables de agente desde el símbolo del sistema con un conjunto proporcionado de parámetros.</span><span class="sxs-lookup"><span data-stu-id="0be89-105">Invoking agent executable files from the command prompt with a supplied set of parameters.</span></span>  
  
 <span data-ttu-id="0be89-106">Invocar directamente a los agentes de replicación desde el símbolo del sistema permite obtener acceso a los agentes mediante programación desde scripting de la línea de comandos en archivos por lotes.</span><span class="sxs-lookup"><span data-stu-id="0be89-106">Directly invoking replication agents from the command prompt enables agents to be programmatically accessed from command-line scripting in batch files.</span></span> <span data-ttu-id="0be89-107">Cuando un agente se invoca desde el símbolo del sistema, se ejecuta en la cuenta de seguridad de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows del usuario que invocó al agente o inició el archivo por lotes.</span><span class="sxs-lookup"><span data-stu-id="0be89-107">When an agent is invoked from the command prompt, it runs under the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows security account of the user that invoked the agent or started the batch file.</span></span>  
  
 <span data-ttu-id="0be89-108">Las instancias de los agentes de replicación siguientes se pueden ejecutar con archivos ejecutables.</span><span class="sxs-lookup"><span data-stu-id="0be89-108">Instances of the following replication agents can be run using executable files.</span></span>  
  
-   [<span data-ttu-id="0be89-109">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="0be89-109">Replication Distribution Agent</span></span>](../agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="0be89-110">Agente de registro del LOG de replicación</span><span class="sxs-lookup"><span data-stu-id="0be89-110">Replication Log Reader Agent</span></span>](../agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="0be89-111">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="0be89-111">Replication Merge Agent</span></span>](../agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="0be89-112">Agente de lectura de cola de replicación</span><span class="sxs-lookup"><span data-stu-id="0be89-112">Replication Queue Reader Agent</span></span>](../agents/replication-queue-reader-agent.md)  
  
-   [<span data-ttu-id="0be89-113">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="0be89-113">Replication Snapshot Agent</span></span>](../agents/replication-snapshot-agent.md)  
  
 <span data-ttu-id="0be89-114">Al invocar los agentes de replicación, puede utilizar los perfiles de rendimiento para pasar automáticamente un conjunto definido de parámetros a la aplicación ejecutable del agente.</span><span class="sxs-lookup"><span data-stu-id="0be89-114">When invoking replication agents, you can use performance profiles to automatically pass a defined set of parameters to the agent executable.</span></span> <span data-ttu-id="0be89-115">Para obtener más información, consulte [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0be89-115">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0be89-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0be89-116">Examples</span></span>  
 <span data-ttu-id="0be89-117">En los ejemplos siguientes se muestra cómo invocar los agentes de replicación desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="0be89-117">The following examples show how to invoke replication agents from the command prompt.</span></span> <span data-ttu-id="0be89-118">Los agentes de replicación también se pueden invocar utilizando Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="0be89-118">Replication agents can also be invoked using Replication Management Objects (RMO).</span></span> <span data-ttu-id="0be89-119">Para obtener más información, vea [Sincronizar suscripciones &#40;replicación&#41;](../synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="0be89-119">For more information, see [Synchronize Subscriptions &#40;Replication&#41;](../synchronize-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0be89-120">Los saltos de línea de estos ejemplos se agregaron para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="0be89-120">Line breaks in these examples were added to improve readability.</span></span> <span data-ttu-id="0be89-121">En un archivo por lotes, los comandos se deben realizar en una única línea.</span><span class="sxs-lookup"><span data-stu-id="0be89-121">In a batch file, commands must be made in a single line.</span></span>  
  
### <a name="running-the-snapshot-agent"></a><span data-ttu-id="0be89-122">Ejecutar el Agente de instantáneas</span><span class="sxs-lookup"><span data-stu-id="0be89-122">Running the Snapshot Agent</span></span>  
 <span data-ttu-id="0be89-123">Este archivo por lotes de ejemplo invoca al Agente de instantáneas desde el símbolo del sistema para generar una instantánea para la publicación **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="0be89-123">This example batch file invokes the Snapshot Agent from the command prompt to generate a snapshot for the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare variables  
SET Publisher=%InstanceName%;  
SET PublicationDB=AdventureWorks2012;   
SET Publication=AdvWorksSalesOrdersMerge;   
  
REM --Start the Snapshot Agent to generate the snapshot for AdvWorksSalesOrdersMerge.  
"C:\Program Files\Microsoft SQL Server\120\COM\SNAPSHOT.EXE" -Publication %Publication%   
-Publisher %Publisher% -Distributor %Publisher% -PublisherDB %PublicationDB%   
-ReplicationType 2 -OutputVerboseLevel 1 -DistributorSecurityMode 1 ;  
  
```  
  
### <a name="running-the-distribution-agent"></a><span data-ttu-id="0be89-124">Ejecutar el Agente de distribución</span><span class="sxs-lookup"><span data-stu-id="0be89-124">Running the Distribution Agent</span></span>  
 <span data-ttu-id="0be89-125">Este archivo por lotes de ejemplo invoca al Agente de distribución desde el símbolo del sistema para replicar continuamente los cambios desde la publicación **AdvWorksProductTran** a un suscriptor de inserción.</span><span class="sxs-lookup"><span data-stu-id="0be89-125">This example batch file invokes the Distribution Agent from the command prompt to continuously replicate changes from the **AdvWorksProductTran** publication to a push subscriber.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksProductsTran;  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4 ;  
  
```  
  
### <a name="running-the-merge-agent"></a><span data-ttu-id="0be89-126">Ejecutar el Agente de mezcla</span><span class="sxs-lookup"><span data-stu-id="0be89-126">Running the Merge Agent</span></span>  
 <span data-ttu-id="0be89-127">Este archivo por lotes de ejemplo invoca al Agente de mezcla desde el símbolo del sistema para sincronizar una suscripción de extracción a la publicación **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="0be89-127">This example batch file invokes the Merge Agent from the command prompt to synchronize a pull subscription to the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksSalesOrdersMerge;  
  
REM --Start the Merge Agent with concurrent upload and download processes.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE" -Publication %Publication%    
-Publisher %Publisher%  -Subscriber  %Subscriber%  -Distributor %Publisher%    
-PublisherDB %PublicationDB%  -SubscriberDB %SubscriptionDB% -PublisherSecurityMode 1    
-OutputVerboseLevel 2  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1    
-Validate 3  -ParallelUploadDownload 1 ;  
  
```  
  
  
