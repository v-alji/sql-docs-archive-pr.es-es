---
title: Información de publicación, testigos de seguimiento (publicación transaccional, SQL Server 2005 y versiones posteriores) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.tracertokens.f1
ms.assetid: a115ba95-17ae-45df-91bd-5a1a35f3745f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af84ab9b9122a55367780976056ce95aa597f62a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748046"
---
# <a name="publication-information-tracer-tokens-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="9cc63-102">Información de la publicación, Testigos de seguimiento (Publicación transaccional, SQL Server 2005 y posterior)</span><span class="sxs-lookup"><span data-stu-id="9cc63-102">Publication Information, Tracer Tokens (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="9cc63-103"> La pestaña **Testigos de seguimiento** le permitirá validar las conexiones y medir la latencia de un sistema que utiliza la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="9cc63-103">The **Tracer Tokens** tab allows you to validate connections and to measure the latency of a system that uses transactional replication.</span></span> <span data-ttu-id="9cc63-104">Se escribe un token (una pequeña cantidad de datos) en el registro de transacción de la base de datos de publicaciones, marcado como si fuese una transacción replicada, y se envía a través del sistema, de forma que permite calcular:</span><span class="sxs-lookup"><span data-stu-id="9cc63-104">A token (a small amount of data) is written to the transaction log of the publication database, marked as though it were a typical replicated transaction, and sent through the system, allowing a calculation of:</span></span>  
  
-   <span data-ttu-id="9cc63-105">Cuánto tiempo transcurre desde que se confirma una transacción en el publicador hasta que se inserta el comando correspondiente en la base de datos de distribución del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="9cc63-105">How much time elapses between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span>  
  
-   <span data-ttu-id="9cc63-106">Cuánto tiempo transcurre desde que se inserta un comando en la base de datos de distribución hasta que se confirma la transacción correspondiente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9cc63-106">How much time elapses between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span>  
  
 <span data-ttu-id="9cc63-107">A partir de estos cálculos, podrá responder a diversas preguntas, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9cc63-107">From these calculations, you can answer a number of questions, including:</span></span>  
  
-   <span data-ttu-id="9cc63-108">¿Qué suscriptores tardan más en recibir un cambio del publicador?</span><span class="sxs-lookup"><span data-stu-id="9cc63-108">Which Subscribers take the longest to receive a change from the Publisher?</span></span>  
  
-   <span data-ttu-id="9cc63-109">De los suscriptores que esperan recibir el testigo de seguimiento, ¿cuáles, si los hay, no lo han recibido?</span><span class="sxs-lookup"><span data-stu-id="9cc63-109">Of the Subscribers expected to receive the tracer token, which, if any, have not received it?</span></span>  
  
## <a name="options"></a><span data-ttu-id="9cc63-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="9cc63-110">Options</span></span>  
 <span data-ttu-id="9cc63-111">Para cambiar la manera que la cuadrícula muestra los datos, haga clic con el botón secundario en la cuadrícula y, a continuación, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9cc63-111">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="9cc63-112">**Ordenar**: ordene en una o más columnas en el cuadro de diálogo **Ordenar columnas** .</span><span class="sxs-lookup"><span data-stu-id="9cc63-112">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="9cc63-113">**Elegir columnas para mostrar**: seleccione las columnas que se mostrarán y el orden en el que se mostrarán en el cuadro de diálogo **Elegir columnas** .</span><span class="sxs-lookup"><span data-stu-id="9cc63-113">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="9cc63-114">**Filtro**: filtre filas en la cuadrícula basándose en los valores de columna en el cuadro de diálogo **Configuración del filtro** .</span><span class="sxs-lookup"><span data-stu-id="9cc63-114">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="9cc63-115">**Borrar filtro**: borre cualquier configuración de filtro para la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="9cc63-115">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="9cc63-116">La configuración del filtro es específica de cada cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="9cc63-116">Filter settings are specific to each grid.</span></span> <span data-ttu-id="9cc63-117">La selección y ordenación de las columnas se aplica a todas las cuadrículas del mismo tipo, como la cuadrícula de las publicaciones para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="9cc63-117">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="9cc63-118">**Insertar seguimiento**</span><span class="sxs-lookup"><span data-stu-id="9cc63-118">**Insert Tracer**</span></span>  
 <span data-ttu-id="9cc63-119">Haga clic para insertar un testigo de seguimiento en el registro de transacciones del publicador.</span><span class="sxs-lookup"><span data-stu-id="9cc63-119">Click to insert a tracer token in the transaction log at the Publisher.</span></span>  
  
 <span data-ttu-id="9cc63-120">**Hora de inserción**</span><span class="sxs-lookup"><span data-stu-id="9cc63-120">**Time inserted**</span></span>  
 <span data-ttu-id="9cc63-121">Seleccione la hora de inserción del testigo de seguimiento para mostrar la información de latencia a partir de ese momento.</span><span class="sxs-lookup"><span data-stu-id="9cc63-121">Select a time at which a tracer token was inserted to display latency information from that time.</span></span> <span data-ttu-id="9cc63-122">De forma predeterminada, se mostrará la información a partir de la hora más reciente.</span><span class="sxs-lookup"><span data-stu-id="9cc63-122">By default, information from the most recent time is displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9cc63-123">La información del testigo de seguimiento se guarda durante el mismo período que otros datos del historial, que depende del período de retención de historial de la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="9cc63-123">Tracer token information is retained for the same time period as other historical data, which is governed by the history retention period of the distribution database.</span></span> <span data-ttu-id="9cc63-124">Para obtener información sobre cómo cambiar las propiedades de la base de datos de distribución, vea [Ver y modificar las propiedades del distribuidor y del publicador](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9cc63-124">For information about changing distribution database properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
 <span data-ttu-id="9cc63-125">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="9cc63-125">**Subscription**</span></span>  
 <span data-ttu-id="9cc63-126">Nombre de cada suscripción a la publicación.</span><span class="sxs-lookup"><span data-stu-id="9cc63-126">The name of each subscription to the publication.</span></span>  
  
 <span data-ttu-id="9cc63-127">**Publicador a distribuidor**</span><span class="sxs-lookup"><span data-stu-id="9cc63-127">**Publisher to Distributor**</span></span>  
 <span data-ttu-id="9cc63-128">Tiempo que transcurre desde que se confirma una transacción en el publicador hasta que se inserta el comando correspondiente en la base de datos de distribución del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="9cc63-128">The elapsed time between a transaction being committed at the Publisher and the corresponding command being inserted in the distribution database at the Distributor.</span></span> <span data-ttu-id="9cc63-129">Si un valor muestra **Pendiente** indica que el token aún no ha llegado al distribuidor.</span><span class="sxs-lookup"><span data-stu-id="9cc63-129">A value of **Pending** indicates that the token has not yet reached the Distributor.</span></span> <span data-ttu-id="9cc63-130">Si persiste el estado pendiente, compruebe que se esté ejecutando el Agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="9cc63-130">If the pending state persists, ensure that the Log Reader Agent is running.</span></span>  
  
 <span data-ttu-id="9cc63-131">**Distribuidor a suscriptor**</span><span class="sxs-lookup"><span data-stu-id="9cc63-131">**Distributor to Subscriber**</span></span>  
 <span data-ttu-id="9cc63-132">Tiempo que transcurre desde que se inserta un comando en la base de datos de distribución hasta que se confirma la transacción correspondiente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9cc63-132">The elapsed time between a command being inserted in the distribution database and the corresponding transaction being committed at a Subscriber.</span></span> <span data-ttu-id="9cc63-133">Si un valor muestra **Pendiente** indica que el token aún no ha llegado al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9cc63-133">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span> <span data-ttu-id="9cc63-134">Si persiste el estado pendiente, compruebe que se esté ejecutando el Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="9cc63-134">If the pending state persists, ensure that the Distribution Agent is running.</span></span>  
  
 <span data-ttu-id="9cc63-135">**Latencia total**</span><span class="sxs-lookup"><span data-stu-id="9cc63-135">**Total Latency**</span></span>  
 <span data-ttu-id="9cc63-136">Tiempo que transcurre desde que se confirma una transacción en el publicador hasta que se confirma la transacción correspondiente en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9cc63-136">The elapsed time between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span> <span data-ttu-id="9cc63-137">Representa la latencia de un extremo a otro del sistema de replicación del suscriptor en dicho momento.</span><span class="sxs-lookup"><span data-stu-id="9cc63-137">This represents the end-to-end latency of the replication system for this Subscriber at this time.</span></span> <span data-ttu-id="9cc63-138">Si un valor muestra **Pendiente** indica que el token aún no ha llegado al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="9cc63-138">A value of **Pending** indicates that the token has not yet reached the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc63-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cc63-139">See Also</span></span>  
 <span data-ttu-id="9cc63-140">[Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="9cc63-140">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="9cc63-141">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9cc63-141">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="9cc63-142">[Medir la latencia y validar las conexiones para la replicación transaccional](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="9cc63-142">[Measure Latency and Validate Connections for Transactional Replication](monitor/measure-latency-and-validate-connections-for-transactional-replication.md) </span></span>  
 <span data-ttu-id="9cc63-143">[Supervisar el rendimiento con el monitor de replicación](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="9cc63-143">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="9cc63-144">[Monitoring Replication](monitoring-replication.md)  (Supervisar la replicación)</span><span class="sxs-lookup"><span data-stu-id="9cc63-144">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="9cc63-145">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="9cc63-145">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
