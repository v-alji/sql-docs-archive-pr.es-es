---
title: Desconectar usuarios y sesiones en Analysis Services Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ending user activity [Analysis Services]
- connections [Analysis Services]
- sessions [Analysis Services]
ms.assetid: 3b0145a2-f21d-4dd0-a09e-83afeb2ff4a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: bac20b663b0a65902c70e7a3c3bfe3f27b7bf061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745492"
---
# <a name="disconnect-users-and-sessions-on-analysis-services-server"></a><span data-ttu-id="3bc63-102">Desconectar usuarios y sesiones en el servidor de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3bc63-102">Disconnect Users and Sessions on Analysis Services Server</span></span>
  <span data-ttu-id="3bc63-103">Como administrador de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] puede que desee la actividad del usuario final como parte de la administración de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3bc63-103">An administrator of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] may want to end user activity as part of workload management.</span></span> <span data-ttu-id="3bc63-104">Esto se lleva a cabo cancelando sesiones y conexiones.</span><span class="sxs-lookup"><span data-stu-id="3bc63-104">You do this by canceling sessions and connections.</span></span> <span data-ttu-id="3bc63-105">Las sesiones se pueden formar automáticamente cuando se ejecuta una consulta (implícito) o definirse en el momento en que las crea el administrador (explícito).</span><span class="sxs-lookup"><span data-stu-id="3bc63-105">Sessions can be formed automatically when a query is run (implicit), or named at the time of creation by the administrator (explicit).</span></span> <span data-ttu-id="3bc63-106">Las conexiones son conductos abiertos con los que se pueden ejecutar las consultas.</span><span class="sxs-lookup"><span data-stu-id="3bc63-106">Connections are open conduits over which queries can be run.</span></span> <span data-ttu-id="3bc63-107">Tanto las sesiones como las conexiones se pueden terminar aunque estén activas.</span><span class="sxs-lookup"><span data-stu-id="3bc63-107">Both sessions and connections can be ended while they are active.</span></span> <span data-ttu-id="3bc63-108">Por ejemplo, es posible que un administrador desee finalizar el procesamiento de una sesión si dicho procesamiento está tardando demasiado o si han surgido dudas sobre si el comando que se está ejecutando está correctamente escrito.</span><span class="sxs-lookup"><span data-stu-id="3bc63-108">For example, an administrator may want to end processing for a session if the processing is taking too long or if some doubt has arisen as to whether the command being executed was written correctly.</span></span>  
  
## <a name="ending-sessions-and-connections"></a><span data-ttu-id="3bc63-109">Terminar sesiones y conexiones</span><span class="sxs-lookup"><span data-stu-id="3bc63-109">Ending Sessions and Connections</span></span>  
 <span data-ttu-id="3bc63-110">Para administrar sesiones y conexiones, puede utilizar las vistas de administración dinámica (DMV) y XMLA:</span><span class="sxs-lookup"><span data-stu-id="3bc63-110">To manage sessions and connections, you can use Dynamic Management Views (DMVs) and XMLA:</span></span>  
  
1.  <span data-ttu-id="3bc63-111">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a una instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="3bc63-111">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to an Analysis Services instance.</span></span>  
  
2.  <span data-ttu-id="3bc63-112">Pegue una de las siguientes consultas de DMV en una ventana de consulta MDX para obtener una lista de todas las sesiones, conexiones y comandos que se están ejecutando actualmente:</span><span class="sxs-lookup"><span data-stu-id="3bc63-112">Paste any one of the following DMV queries in an MDX query window to get a list of all sessions, connections, and commands that are currently executing:</span></span>  
  
     `Select * from $System.Discover_Sessions`  
  
     `Select * from $System.Discover_Connections`  
  
     `Select * from $System.Discover_Commands`  
  
3.  <span data-ttu-id="3bc63-113">Presione F5 para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="3bc63-113">Press F5 to execute the query.</span></span>  
  
     <span data-ttu-id="3bc63-114">La consulta de DMV devuelve información de conexión y de sesión en un conjunto de resultados tabulares cuya lectura y copia es más fácil.</span><span class="sxs-lookup"><span data-stu-id="3bc63-114">The DMV query returns session and connection information in a tabular result set that is easier read and copy from.</span></span>  
  
 <span data-ttu-id="3bc63-115">Mantenga la ventana de consulta abierta.</span><span class="sxs-lookup"><span data-stu-id="3bc63-115">Keep the query window open.</span></span> <span data-ttu-id="3bc63-116">En el paso siguiente, querrá volver a esta página para copiar los SPID de la sesión que desea desconectar.</span><span class="sxs-lookup"><span data-stu-id="3bc63-116">In the next step, you will want to return to this page to copy the SPIDs of the session you want to disconnect.</span></span>  
  
 <span data-ttu-id="3bc63-117">Para terminar una sesión, abra una segunda ventana de consulta XMLA.</span><span class="sxs-lookup"><span data-stu-id="3bc63-117">To end a session, open a second XMLA query window.</span></span>  
  
1.  <span data-ttu-id="3bc63-118">Pegue la siguiente sintaxis en una ventana de consulta MDX, reemplazando el marcador de posición ConnectionID, SessionID o SPID con un valor válido que copió en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="3bc63-118">Paste the following syntax into an MDX query window, replacing the ConnectionID, SessionID, or SPID placeholder with a valid value copied from the previous step.</span></span>  
  
    ```  
    <Cancel xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  
       <ConnectionID>111</ConnectionID>  
       <SessionID>222</SessionID>  
       <SPID>333</SPID>  
  
    <CancelAssociated>1</CancelAssociated>  
    </Cancel>  
  
    ```  
  
2.  <span data-ttu-id="3bc63-119">Presione F5 para ejecutar el comando de cancelación.</span><span class="sxs-lookup"><span data-stu-id="3bc63-119">Press F5 to execute the cancel command.</span></span>  
  
 <span data-ttu-id="3bc63-120">La finalización de una conexión cancela todas las sesiones y SPID, cerrando la sesión del host.</span><span class="sxs-lookup"><span data-stu-id="3bc63-120">Ending a connection cancels all sessions and SPIDs, closing the host session.</span></span>  
  
 <span data-ttu-id="3bc63-121">La finalización de una sesión detiene todos los comandos (SPID) que se estén ejecutando como parte de dicha sesión.</span><span class="sxs-lookup"><span data-stu-id="3bc63-121">Ending a session stops all commands (SPIDs) that are running as part of that session.</span></span>  
  
 <span data-ttu-id="3bc63-122">La finalización de un SPID cancela un comando concreto.</span><span class="sxs-lookup"><span data-stu-id="3bc63-122">Ending a SPID cancels a particular commend.</span></span>  
  
 <span data-ttu-id="3bc63-123">En muy pocos casos, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no cerrará una conexión si no puede realizar el seguimiento de todas las sesiones y SPID asociados a la conexión (por ejemplo, cuando haya varias sesiones abiertas en un escenario HTTP).</span><span class="sxs-lookup"><span data-stu-id="3bc63-123">In rare cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will not close a connection if it cannot track all the sessions and SPIDs associated with the connection (for example, when multiple sessions are open in an HTTP scenario).</span></span>  
  
 <span data-ttu-id="3bc63-124">Para obtener más información sobre el XMLA al que se hace referencia en este tema, vea [Método Execute &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) y [Elemento Cancel &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="3bc63-124">For more information about the XMLA referenced in this topic, see [Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) and [Cancel Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc63-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bc63-125">See Also</span></span>  
 <span data-ttu-id="3bc63-126">[Administrar conexiones y sesiones &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span><span class="sxs-lookup"><span data-stu-id="3bc63-126">[Managing Connections and Sessions &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span></span>  
 <span data-ttu-id="3bc63-127">[Elemento BeginSession &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="3bc63-127">[BeginSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span></span>  
 <span data-ttu-id="3bc63-128">[Elemento EndSession &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="3bc63-128">[EndSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span></span>  
 [<span data-ttu-id="3bc63-129">Session, elemento &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="3bc63-129">Session Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/session-element-xmla)  
  
  
