---
title: 'Lección 2: Creación de una suscripción a la publicación de combinación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 06722baa-9065-443e-b1d5-99036cf89074
author: rothja
ms.author: jroth
ms.openlocfilehash: 2ca4f9cdf9c40d80b428d65b4201be61c2ea3eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674066"
---
# <a name="lesson-2-creating-a-subscription-to-the-merge-publication"></a><span data-ttu-id="936d7-102">Lección 2: Crear una suscripción a la publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="936d7-102">Lesson 2: Creating a Subscription to the Merge Publication</span></span>
  <span data-ttu-id="936d7-103">En esta lección, creará una suscripción con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="936d7-103">In this lesson, you will create the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="936d7-104">Luego establecerá los permisos en la base de datos de suscripciones y generará manualmente la instantánea de datos filtrados para la nueva suscripción.</span><span class="sxs-lookup"><span data-stu-id="936d7-104">You will then set permissions on the subscription database and manually generate the filtered data snapshot for the new subscription.</span></span> <span data-ttu-id="936d7-105">Para realizar esta lección es necesario haber completado la lección anterior, [Lección 1: Publicar datos con la replicación de mezcla](lesson-1-publishing-data-using-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="936d7-105">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Merge Replication](lesson-1-publishing-data-using-merge-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="936d7-106">Para crear la suscripción</span><span class="sxs-lookup"><span data-stu-id="936d7-106">To create the subscription</span></span>  
  
1.  <span data-ttu-id="936d7-107">Conéctese al suscriptor en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor, expanda la carpeta **Replicación** , haga clic con el botón derecho en la carpeta **Suscripciones locales** y, después, haga clic en **Nueva suscripción**.</span><span class="sxs-lookup"><span data-stu-id="936d7-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, expand the **Replication** folder, right-click the **Local Subscriptions** folder, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="936d7-108">Se iniciará el Asistente para nueva suscripción.</span><span class="sxs-lookup"><span data-stu-id="936d7-108">The New Subscription Wizard launches.</span></span>  
  
2.  <span data-ttu-id="936d7-109">En la página **Publicación** , haga clic en **Buscar publicador de SQL Server** en la lista **Publicador** .</span><span class="sxs-lookup"><span data-stu-id="936d7-109">On the **Publication** page, click **Find SQL Server Publisher** in the **Publisher** list.</span></span>  
  
3.  <span data-ttu-id="936d7-110">En el cuadro de diálogo **Conectar al servidor** , escriba el nombre de la instancia del publicador en el cuadro **Nombre del servidor** y, después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="936d7-110">In the **Connect to Server** dialog box, enter the name of the Publisher instance in the **Server name** box, and click **Connect**.</span></span>  
  
4.  <span data-ttu-id="936d7-111">Haga clic en **AdvWorksSalesOrdersMerge**y en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="936d7-111">Click **AdvWorksSalesOrdersMerge**, and click **Next**.</span></span>  
  
5.  <span data-ttu-id="936d7-112">En la página Ubicación del Agente de mezcla, haga clic en **Ejecutar cada agente en su suscriptor**y, luego, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="936d7-112">On the Merge Agent Location page, click **Run each agent at its Subscriber**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="936d7-113">En la página Suscriptores, seleccione el nombre de instancia del servidor del suscriptor y, en **Base de datos de suscripciones**, seleccione **\<New Database>** en la lista.</span><span class="sxs-lookup"><span data-stu-id="936d7-113">On the Subscribers page, select the instance name of the Subscriber server, and under **Subscription Database**, select **\<New Database>** from the list.</span></span>  
  
7.  <span data-ttu-id="936d7-114">En el cuadro de diálogo **Nueva base de datos** , escriba **SalesOrdersReplica** en el cuadro **Nombre de la base de datos** , haga clic en **Aceptar**y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="936d7-114">In the **New Database** dialog box, enter **SalesOrdersReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="936d7-115">En la página seguridad de Agente de mezcla, haga clic en el botón de puntos suspensivos (**...**), escriba \<_Machine_Name> _**\ repl_merge** en el cuadro **cuenta de proceso** , proporcione la contraseña de esta cuenta, haga clic en **Aceptar**, haga clic en **siguiente**y, a continuación, haga clic en **siguiente** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="936d7-115">On the Merge Agent Security page, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_merge** in the **Process account** box, supply the password for this account, click **OK**, click **Next**, and then click **Next** again.</span></span>  
  
9. <span data-ttu-id="936d7-116">En la página Inicializar suscripciones, seleccione **En la primera sincronización** de la lista **Inicializar cuando** , haga clic en **Siguiente**y, después, otra vez en **Siguiente** .</span><span class="sxs-lookup"><span data-stu-id="936d7-116">On the Initialize Subscriptions page, select **At first synchronization** from the **Initialize When** list, click **Next**, and then click **Next** again.</span></span>  
  
10. <span data-ttu-id="936d7-117">En la página valores de HOST_NAME, escriba un valor de `adventure-works\pamela0` en el cuadro de **host_name valor** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="936d7-117">On the HOST_NAME Values page, enter a value of `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="936d7-118">Haga clic de nuevo en **Finalizar** y, una vez creada la suscripción, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="936d7-118">Click **Finish** again, and after the subscription is created, click **Close**.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="936d7-119">Establecer permisos de base de datos en el suscriptor</span><span class="sxs-lookup"><span data-stu-id="936d7-119">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="936d7-120">Conéctese al suscriptor en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda **Bases de datos**, **SalesOrdersReplica**y **Seguridad**, haga clic con el botón derecho en **Usuarios**y, después, seleccione **Nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="936d7-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **SalesOrdersReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="936d7-121">En la página **General** , escriba \<_Machine_Name> _ **\ repl_merge** en el cuadro **nombre de usuario** , haga clic en el botón de puntos suspensivos (**...**) \<_Machine_Name> , haga clic en **examinar**, seleccione _ **\ repl_merge**, haga clic en **Aceptar**, haga clic en **Comprobar nombres**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="936d7-121">On the **General** page, enter \<_Machine_Name>_**\repl_merge** in the **User name** box, click the ellipsis (**...**) button, click **Browse**, select \<_Machine_Name>_**\repl_merge**, click **OK**, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="936d7-122">En **Pertenencia al rol de la base de datos**, seleccione **db_owner**y haga clic en **Aceptar** para crear el usuario.</span><span class="sxs-lookup"><span data-stu-id="936d7-122">In **Database role membership**, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-create-the-filtered-data-snapshot-for-the-subscription"></a><span data-ttu-id="936d7-123">Para crear la instantánea de datos filtrados para la suscripción</span><span class="sxs-lookup"><span data-stu-id="936d7-123">To create the filtered data snapshot for the subscription</span></span>  
  
1.  <span data-ttu-id="936d7-124">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor y luego la carpeta **Replicación** .</span><span class="sxs-lookup"><span data-stu-id="936d7-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="936d7-125">En la carpeta **Publicaciones locales** , haga clic con el botón derecho en la publicación **AdvWorksSalesOrdersMerge** y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="936d7-125">In the **Local Publications** folder, right-click the **AdvWorksSalesOrdersMerge** publication, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="936d7-126">Se mostrará el cuadro de diálogo **Propiedades de la publicación** .</span><span class="sxs-lookup"><span data-stu-id="936d7-126">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="936d7-127">Seleccione la página **Particiones de datos** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="936d7-127">Select the **Data Partitions** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="936d7-128">En el cuadro de diálogo **Agregar partición de datos** , escriba `adventure-works\pamela0` en el cuadro de **host_name valor** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="936d7-128">In the **Add Data Partition** dialog box, type `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="936d7-129">Seleccione la partición agregada recientemente, haga clic en **Generar instantáneas seleccionadas ahora**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="936d7-129">Select the newly added partition, click **Generate the selected snapshots now**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="936d7-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="936d7-130">Next Steps</span></span>  
 <span data-ttu-id="936d7-131">Ha creado correctamente una suscripción a la publicación de combinación y ha generado la instantánea filtrada para la nueva partición de datos de la suscripción, de manera que esté disponible cuando se inicialice la suscripción.</span><span class="sxs-lookup"><span data-stu-id="936d7-131">You have successfully created a subscription to the merge publication and generated the filtered snapshot for the new subscription's data partition so that it will be available when the subscription is initialized.</span></span> <span data-ttu-id="936d7-132">A continuación, concederá derechos al Agente de mezcla en la base de datos de suscripciones y ejecutará el Agente de mezcla para iniciar la sincronización e inicializar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="936d7-132">Next, you will grant rights to the Merge Agent on the subscription database and run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="936d7-133">Vea [Lección 3: Sincronizar la suscripción con la publicación de combinación](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="936d7-133">See [Lesson 3: Synchronizing the Subscription to the Merge Publication](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936d7-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="936d7-134">See Also</span></span>  
 <span data-ttu-id="936d7-135">[Subscribe to Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="936d7-135">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="936d7-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="936d7-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="936d7-137">Instantáneas para publicaciones de combinación con filtros con parámetros</span><span class="sxs-lookup"><span data-stu-id="936d7-137">Snapshots for Merge Publications with Parameterized Filters</span></span>](snapshots-for-merge-publications-with-parameterized-filters.md)  
  
  
