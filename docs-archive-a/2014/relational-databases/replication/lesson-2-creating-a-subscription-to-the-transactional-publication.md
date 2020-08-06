---
title: 'Lección 2: Creación de una suscripción a la publicación transaccional | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 5995b7d2-7c06-46f5-b96c-2bee879bcda2
author: rothja
ms.author: jroth
ms.openlocfilehash: dbf40fa259302dffdd6c0b8e8717b7c35b0cf92d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663331"
---
# <a name="lesson-2-creating-a-subscription-to-the-transactional-publication"></a><span data-ttu-id="cbd6b-102">Lección 2: Crear una suscripción a la publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="cbd6b-102">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>
  <span data-ttu-id="cbd6b-103">En esta lección, creará una suscripción con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbd6b-103">In this lesson, you will create a subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cbd6b-104">Para realizar esta lección es necesario haber completado la lección anterior, [Lección 1: Publicar datos con la replicación transaccional](lesson-1-publishing-data-using-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="cbd6b-104">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Transactional Replication](lesson-1-publishing-data-using-transactional-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="cbd6b-105">Para crear la suscripción</span><span class="sxs-lookup"><span data-stu-id="cbd6b-105">To create the subscription</span></span>  
  
1.  <span data-ttu-id="cbd6b-106">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor y luego la carpeta **Replicación** .</span><span class="sxs-lookup"><span data-stu-id="cbd6b-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="cbd6b-107">En la carpeta **Publicaciones locales** , haga clic con el botón derecho en la publicación **AdvWorksProductTrans** y, después, haga clic en **Nuevas suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-107">In the **Local Publications** folder, right-click the **AdvWorksProductTrans** publication, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="cbd6b-108">Se iniciará el Asistente para nueva suscripción.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-108">The New Subscription Wizard launches.</span></span>  
  
3.  <span data-ttu-id="cbd6b-109">En la página Publicación, seleccione **AdvWorksProductTrans**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-109">On the Publication page, select **AdvWorksProductTrans**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="cbd6b-110">En la página Ubicación del Agente de distribución, seleccione **Ejecutar todos los agentes en el distribuidor**y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-110">On the Distribution Agent Location page, select **Run all agents at the Distributor**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="cbd6b-111">En la página Suscriptores, si no se muestra el nombre de la instancia del suscriptor, haga clic en **Agregar suscriptor**y luego, en **Agregar suscriptor de SQL Server**, y escriba el nombre de la instancia del suscriptor en el cuadro de diálogo **Conectar al servidor** y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-111">On the Subscribers page, if the name of the Subscriber instance is not displayed, click **Add Subscriber**, click **Add SQL Server Subscriber**, enter the Subscriber instance name in the **Connect to Server** dialog box, and then click **Connect**.</span></span>  
  
6.  <span data-ttu-id="cbd6b-112">En la página suscriptores, seleccione el nombre de instancia del servidor del suscriptor y seleccione **\<New Database>** en **base de datos de suscripciones**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-112">On the Subscribers page, select the instance name of the Subscriber server, and select **\<New Database>** under **Subscription Database**.</span></span>  
  
7.  <span data-ttu-id="cbd6b-113">En el cuadro de diálogo **Nueva base de datos** , escriba **ProductReplica** en el cuadro **Nombre de la base de datos** , haga clic en **Aceptar**y luego, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-113">On the **New Database** dialog box, enter **ProductReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="cbd6b-114">En el cuadro de diálogo **seguridad de agente de distribución** , haga clic en el botón de puntos suspensivos (**...**), escriba \<_Machine_Name> _**\ Repl_distribution** en el cuadro **cuenta de proceso** , escriba la contraseña para esta cuenta, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-114">In the **Distribution Agent Security** dialog box, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_distribution** in the **Process account** box, enter the password for this account, click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="cbd6b-115">Haga clic en **Finalizar** para aceptar los valores predeterminados en las páginas restantes y finalizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-115">Click **Finish** to accept the default values on the remaining pages and complete the wizard.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="cbd6b-116">Establecer permisos de base de datos en el suscriptor</span><span class="sxs-lookup"><span data-stu-id="cbd6b-116">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="cbd6b-117">Conéctese al suscriptor en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda **Bases de datos**, **ProductReplica**y **Seguridad**, haga clic con el botón derecho en **Usuarios**y, después, seleccione **Nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-117">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **ProductReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="cbd6b-118">En la página **General** , en la lista **Tipo de usuario** , seleccione **Usuario de Windows**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-118">On the **General** page, in the **User type** list, select **Windows user**.</span></span>  
  
3.  <span data-ttu-id="cbd6b-119">Seleccione el cuadro **nombre de usuario** y haga clic en el botón de puntos suspensivos (...) y, en el cuadro Escriba **el nombre de objeto que desea seleccionar** , escriba <Machine_Name>**\ Repl_distribution**, haga clic en **Comprobar nombres**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-119">Select the **User name** box and click the ellipsis (...) button, in the **Enter the object name to select** box type <Machine_Name>**\repl_distribution**, click **Check Names**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="cbd6b-120">En la página **Pertenencia** , en el área **Pertenencia al rol de la base de datos** , seleccione **db_owner**y haga clic en **Aceptar** para crear el usuario.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-120">On the **Membership** page, in **Database role membership** area, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-view-the-synchronization-status-of-the-subscription"></a><span data-ttu-id="cbd6b-121">Para ver el estado de sincronización de la suscripción</span><span class="sxs-lookup"><span data-stu-id="cbd6b-121">To view the synchronization status of the subscription</span></span>  
  
1.  <span data-ttu-id="cbd6b-122">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor y luego la carpeta **Replicación** .</span><span class="sxs-lookup"><span data-stu-id="cbd6b-122">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="cbd6b-123">En la carpeta **Publicaciones locales** , expanda la publicación **AdvWorksProductTrans** , haga clic con el botón derecho en la suscripción de la base de datos **ProductReplica** y, después, haga clic en **Ver estado de sincronización**.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-123">In the **Local Publications** folder, expand the **AdvWorksProductTrans** publication, right-click the subscription in the **ProductReplica** database, and then click **View Synchronization Status**.</span></span>  
  
     <span data-ttu-id="cbd6b-124">Se mostrará el actual estado de sincronización de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-124">The current synchronization status of the subscription is displayed.</span></span>  
  
3.  <span data-ttu-id="cbd6b-125">Si la suscripción no está visible en **AdvWorksProductTrans**, presione F5 para actualizar la lista.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-125">If the subscription is not visible under **AdvWorksProductTrans**, press F5 to refresh the list.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cbd6b-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cbd6b-126">Next Steps</span></span>  
 <span data-ttu-id="cbd6b-127">Ha creado correctamente una suscripción a la publicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-127">You have successfully created a subscription to the transactional publication.</span></span> <span data-ttu-id="cbd6b-128">Dado que el Agente de distribución para esta suscripción se ejecuta continuamente, la suscripción se inicializa cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-128">Because the Distribution Agent for this subscription runs continuously, the subscription is initialized when it is created.</span></span> <span data-ttu-id="cbd6b-129">A continuación, utilizará testigos de seguimiento para comprobar que los cambios se replican en el suscriptor y para determinar la latencia.</span><span class="sxs-lookup"><span data-stu-id="cbd6b-129">Next, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency.</span></span> <span data-ttu-id="cbd6b-130">Vea [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span><span class="sxs-lookup"><span data-stu-id="cbd6b-130">See [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd6b-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbd6b-131">See Also</span></span>  
 <span data-ttu-id="cbd6b-132">[Inicializar una suscripción con una instantánea](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="cbd6b-132">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="cbd6b-133">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="cbd6b-133">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="cbd6b-134">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="cbd6b-134">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
