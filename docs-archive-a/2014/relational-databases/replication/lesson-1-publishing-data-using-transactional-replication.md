---
title: 'Lección 1: Publicación de datos con la replicación transaccional | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 9c55aa3c-4664-41fc-943f-e817c31aad5e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce20f4ed8863ede34c8709d2b77bf032e7d14a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744634"
---
# <a name="lesson-1-publishing-data-using-transactional-replication"></a><span data-ttu-id="e04ca-102">Lección 1: Publicar datos con la replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="e04ca-102">Lesson 1: Publishing Data Using Transactional Replication</span></span>
  <span data-ttu-id="e04ca-103">En esta lección, creará una publicación transaccional con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para publicar un subconjunto filtrado de la tabla **Product** en la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e04ca-103">In this lesson, you will create a transactional publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a filtered subset of the **Product** table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="e04ca-104">También agregará un inicio de sesión de SQL Server que utiliza el Agente de distribución para la lista de acceso a la publicación (PAL).</span><span class="sxs-lookup"><span data-stu-id="e04ca-104">You will also add the SQL Server login used by the Distribution Agent to the publication access list (PAL).</span></span> <span data-ttu-id="e04ca-105">Antes de iniciar este tutorial, deberá haber finalizado el tutorial anterior, [Preparar el servidor para replicación](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e04ca-105">Before starting this tutorial, you should have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="e04ca-106">Para crear publicaciones y definir artículos</span><span class="sxs-lookup"><span data-stu-id="e04ca-106">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="e04ca-107">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="e04ca-107">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="e04ca-108">Expanda la carpeta **Replicación** , haga clic con el botón derecho en la carpeta **Publicaciones locales** y, después, haga clic en **Nueva publicación**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-108">Expand the **Replication** folder, right-click the **Local Publications** folder, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="e04ca-109">Se iniciará el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="e04ca-109">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="e04ca-110">En la página Base de datos de publicaciones, seleccione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-110">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="e04ca-111">En la página Tipo de publicación, seleccione **Publicación transaccional**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-111">On the Publication Type page, select **Transactional publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="e04ca-112">En la página Artículos, expanda el nodo **Tablas** , active la casilla **Product** , expanda **Product** y, a continuación, desactive las casillas **ListPrice** y **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="e04ca-112">On the Articles page, expand the **Tables** node, select the **Product** check box, then expand **Product** and clear the **ListPrice** and **StandardCost** check boxes.</span></span> <span data-ttu-id="e04ca-113">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="e04ca-114">En la página Filtrar filas de tabla, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-114">On the Filter Table Rows page, click **Add**.</span></span>  
  
7.  <span data-ttu-id="e04ca-115">En el cuadro de diálogo **Agregar filtro** , haga clic en la columna **SafetyStockLevel** , haga clic en la flecha derecha para agregar la columna a la cláusula WHERE de la instrucción Filtrar en la consulta del filtro y modifique la cláusula WHERE de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="e04ca-115">In the **Add Filter** dialog box, click the **SafetyStockLevel** column, click the right arrow to add the column to the Filter statement WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [SafetyStockLevel] < 500  
    ```  
  
8.  <span data-ttu-id="e04ca-116">Haga clic en **Aceptar** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-116">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="e04ca-117">Active la casilla **Crear una instantánea inmediatamente y mantenerla disponible para inicializar suscripciones** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-117">Select the **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** check box, and click **Next**.</span></span>  
  
10. <span data-ttu-id="e04ca-118">En la página Seguridad del agente, desactive la casilla **Usar la configuración de seguridad del Agente de instantáneas** .</span><span class="sxs-lookup"><span data-stu-id="e04ca-118">On the Agent Security page, clear **Use the security settings from the Snapshot Agent** check box.</span></span>  
  
11. <span data-ttu-id="e04ca-119">Haga clic en **configuración de seguridad** para el agente de instantáneas, escriba \<_Machine_Name> _**\ repl_snapshot** en el cuadro **cuenta de proceso** , proporcione la contraseña para esta cuenta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-119">Click **Security Settings** for the Snapshot Agent, enter \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="e04ca-120">Repita el paso anterior para establecer repl_logreader como la cuenta de proceso para el Agente de registro del LOG y, después, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-120">Repeat the previous step to set repl_logreader as the process account for the Log Reader Agent, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="e04ca-121">En la página Finalización del asistente, escriba **AdvWorksProductTrans** en el cuadro **Nombre de publicación** y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-121">On the Complete the Wizard page, type **AdvWorksProductTrans** in the **Publication name** box, and click **Finish**.</span></span>  
  
14. <span data-ttu-id="e04ca-122">Una vez se haya creado la publicación, haga clic en **Cerrar** para finalizar el asistente.</span><span class="sxs-lookup"><span data-stu-id="e04ca-122">After the publication is created, click **Close** to complete the wizard.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="e04ca-123">Para ver el estado de la generación de instantáneas</span><span class="sxs-lookup"><span data-stu-id="e04ca-123">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="e04ca-124">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor y luego la carpeta **Replicación** .</span><span class="sxs-lookup"><span data-stu-id="e04ca-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="e04ca-125">En la carpeta **Publicaciones locales** , haga clic con el botón derecho en **AdvWorksProductTrans**y luego en **Ver estado del Agente de instantáneas**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-125">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="e04ca-126">Se muestra el estado actual del trabajo del Agente de instantáneas para la publicación.</span><span class="sxs-lookup"><span data-stu-id="e04ca-126">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="e04ca-127">Compruebe que el trabajo de instantáneas sea correcto antes de continuar con la siguiente lección.</span><span class="sxs-lookup"><span data-stu-id="e04ca-127">Verify that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-distribution-agent-login-to-the-pal"></a><span data-ttu-id="e04ca-128">Para agregar el inicio de sesión del Agente de distribución para la lista de acceso de la publicación (PAL)</span><span class="sxs-lookup"><span data-stu-id="e04ca-128">To add the Distribution Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="e04ca-129">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor y luego la carpeta **Replicación** .</span><span class="sxs-lookup"><span data-stu-id="e04ca-129">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="e04ca-130">En la carpeta **Publicaciones locales** , haga clic con el botón derecho en **AdvWorksProductTrans**y luego en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-130">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="e04ca-131">Se mostrará el cuadro de diálogo **Propiedades de la publicación** .</span><span class="sxs-lookup"><span data-stu-id="e04ca-131">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="e04ca-132">Seleccione la página **Lista de acceso a la publicación** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-132">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="e04ca-133">\En el cuadro de diálogo **Agregar acceso de publicación**, seleccione _<nombre_equipo>_**\repl_distribution** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-133">\In the **Add Publication Access** dialog box, select _<Machine_Name>_**\repl_distribution** and click **OK**.</span></span> <span data-ttu-id="e04ca-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e04ca-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e04ca-135">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e04ca-135">Next Steps</span></span>  
 <span data-ttu-id="e04ca-136">Ha creado correctamente la publicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="e04ca-136">You have successfully created the transactional publication.</span></span> <span data-ttu-id="e04ca-137">A continuación se suscribirá a esta publicación.</span><span class="sxs-lookup"><span data-stu-id="e04ca-137">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="e04ca-138">Consulte [Lección 2: Crear una suscripción a la publicación transaccional](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="e04ca-138">See [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e04ca-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e04ca-139">See Also</span></span>  
 <span data-ttu-id="e04ca-140">[Filtrar datos publicados](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="e04ca-140">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="e04ca-141">[Define an Article](publish/define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="e04ca-141">[Define an Article](publish/define-an-article.md) </span></span>  
 [<span data-ttu-id="e04ca-142">Crear y aplicar la instantánea</span><span class="sxs-lookup"><span data-stu-id="e04ca-142">Create and Apply the Snapshot</span></span>](create-and-apply-the-snapshot.md)  
  
  
