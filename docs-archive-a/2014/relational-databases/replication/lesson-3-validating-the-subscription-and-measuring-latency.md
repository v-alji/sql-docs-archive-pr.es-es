---
title: 'Lección 3: Validación de la suscripción y medición de la latencia | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 147f7b93-1804-4e0b-9e17-57a51d035b2a
author: rothja
ms.author: jroth
ms.openlocfilehash: e4893c054d25d131eb2f88f32291606b0b789af7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749228"
---
# <a name="lesson-3-validating-the-subscription-and-measuring-latency"></a><span data-ttu-id="b60c4-102">Lección 3: Validar la suscripción y medir la latencia</span><span class="sxs-lookup"><span data-stu-id="b60c4-102">Lesson 3: Validating the Subscription and Measuring Latency</span></span>
  <span data-ttu-id="b60c4-103">En esta lección, utilizará testigos de seguimiento para comprobar que los cambios se replican en el suscriptor y para determinar la latencia, es decir, el tiempo que se requiere para que un cambio realizado en el publicador aparezca en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="b60c4-103">In this lesson, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency, the time it takes for a change made at the Publisher to appear to the Subscriber.</span></span> <span data-ttu-id="b60c4-104">Esta lección requiere que haya completado la lección anterior, [Lección 2: Crear una suscripción a la publicación transaccional](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="b60c4-104">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
### <a name="to-insert-a-tracer-token-and-view-information-on-the-token"></a><span data-ttu-id="b60c4-105">Para insertar un testigo de seguimiento y ver la información del token</span><span class="sxs-lookup"><span data-stu-id="b60c4-105">To insert a tracer token and view information on the token</span></span>  
  
1.  <span data-ttu-id="b60c4-106">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor, haga clic con el botón derecho en la carpeta **Replicación** y luego en **Iniciar el Monitor de replicación**.</span><span class="sxs-lookup"><span data-stu-id="b60c4-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, right-click the **Replication** folder, and then click **Launch Replication Monitor**.</span></span>  
  
     <span data-ttu-id="b60c4-107">Se inicia el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="b60c4-107">Replication Monitor launches.</span></span>  
  
2.  <span data-ttu-id="b60c4-108">Expanda un grupo de publicador en el panel izquierdo, expanda una instancia de publicador y, a continuación, haga clic en la publicación **AdvWorksProductTrans** .</span><span class="sxs-lookup"><span data-stu-id="b60c4-108">Expand a Publisher group in the left pane, expand the Publisher instance, and then click the **AdvWorksProductTrans** publication.</span></span>  
  
3.  <span data-ttu-id="b60c4-109">Haga clic en la pestaña **Testigos de seguimiento** .</span><span class="sxs-lookup"><span data-stu-id="b60c4-109">Click the **Tracer Tokens** tab.</span></span>  
  
4.  <span data-ttu-id="b60c4-110">Haga clic en **Insertar seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="b60c4-110">Click **Insert Tracer**.</span></span>  
  
5.  <span data-ttu-id="b60c4-111">Vea el tiempo transcurrido para el testigo de seguimiento en las siguientes columnas: **Publicador a distribuidor**, **Distribuidor a suscriptor**y **Latencia total**.</span><span class="sxs-lookup"><span data-stu-id="b60c4-111">View elapsed time for the tracer token in the following columns: **Publisher to Distributor**, **Distributor to Subscriber**, **Total Latency**.</span></span> <span data-ttu-id="b60c4-112">Un valor de **Pending** indica que el token no ha alcanzado un punto determinado.</span><span class="sxs-lookup"><span data-stu-id="b60c4-112">A value of **Pending** indicates that the token has not reached a given point.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b60c4-113">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b60c4-113">Next Steps</span></span>  
 <span data-ttu-id="b60c4-114">En esta lección, utilizó correctamente los testigos de seguimiento para comprobar que los cambios de datos se replican del publicador al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="b60c4-114">In this lesson, you successfully used tracer tokens to validate that data changes are being replicated from the Publisher to the Subscriber.</span></span> <span data-ttu-id="b60c4-115">También puede insertar, actualizar o eliminar datos en la tabla **Product** en el publicador y consultar la tabla **Product** en el suscriptor para ver esos cambios, una vez replicados.</span><span class="sxs-lookup"><span data-stu-id="b60c4-115">You can also insert, update, or delete data in the **Product** table at the Publisher and query the **Product** table at the Subscriber to view these changes after they are replicated.</span></span>  
  
 <span data-ttu-id="b60c4-116">Con esto finaliza el tutorial Replicar datos entre servidores conectados de forma continua.</span><span class="sxs-lookup"><span data-stu-id="b60c4-116">This completes the Replicating Data Between Continuously Connected Servers tutorial.</span></span> <span data-ttu-id="b60c4-117">Para realizar un tutorial similar que utiliza replicación de mezcla, vea [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b60c4-117">For a similar tutorial that uses merge replication, see [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60c4-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b60c4-118">See Also</span></span>  
 [<span data-ttu-id="b60c4-119">Medir la latencia y validar las conexiones de la replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="b60c4-119">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
