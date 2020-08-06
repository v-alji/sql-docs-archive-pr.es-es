---
title: 'Lección 1: Publicación de datos con la replicación de mezcla | Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: c3c6e0b6-54cd-4b7d-8efb-2cefe14fcd7f
author: rothja
ms.author: jroth
ms.openlocfilehash: ba1d8829d84c02d1436013af80de4bf0979049e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748069"
---
# <a name="lesson-1-publishing-data-using-merge-replication"></a><span data-ttu-id="f04a1-102">Lección 1: Publicar datos con la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="f04a1-102">Lesson 1: Publishing Data Using Merge Replication</span></span>
  <span data-ttu-id="f04a1-103">En esta lección, creará una publicación de combinación con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para publicar un subconjunto de las tablas **Employee**, **SalesOrderHeader**y **SalesOrderDetail** en la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f04a1-103">In this lesson, you will create a merge publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a subset of the **Employee**, **SalesOrderHeader**, and **SalesOrderDetail** tables in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="f04a1-104">Estas tablas están filtradas con filtros de fila con parámetros para que cada suscripción contenga una partición única de los datos.</span><span class="sxs-lookup"><span data-stu-id="f04a1-104">These tables are filtered with parameterized row filters so that each subscription contains a unique partition of the data.</span></span> <span data-ttu-id="f04a1-105">También agregará el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que usa el Agente de mezcla a la lista de acceso a la publicación (PAL).</span><span class="sxs-lookup"><span data-stu-id="f04a1-105">You will also add the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Merge Agent to the publication access list (PAL).</span></span> <span data-ttu-id="f04a1-106">Para realizar este tutorial, es preciso que haya finalizado el anterior, [Preparar el servidor para replicación](tutorial-preparing-the-server-for-replication.md).</span><span class="sxs-lookup"><span data-stu-id="f04a1-106">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="f04a1-107">Para crear publicaciones y definir artículos</span><span class="sxs-lookup"><span data-stu-id="f04a1-107">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="f04a1-108">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y luego expanda el nodo del servidor.</span><span class="sxs-lookup"><span data-stu-id="f04a1-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="f04a1-109">Expanda la carpeta **Replicación** , haga clic con el botón derecho en la carpeta **Publicaciones locales**y, después, haga clic en **Nueva publicación**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-109">Expand the **Replication** folder, right-click **Local Publications**, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="f04a1-110">Se iniciará el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="f04a1-110">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="f04a1-111">En la página Base de datos de publicaciones, seleccione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-111">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f04a1-112">En la página Tipo de publicación, seleccione **Publicación de combinación**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-112">On the Publication Type page, select **Merge publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="f04a1-113">En la página Tipos de suscriptor, asegúrese de que solo esté seleccionado [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o posterior y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-113">On the Subscriber Types page, ensure that only [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later is selected, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="f04a1-114">En la página Artículos, expanda el nodo **Tablas** , seleccione **SalesOrderHeader** y **SalesOrderDetail**, luego expanda **Employee**, seleccione **EmployeeID** o **LoginID**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-114">On the Articles page, expand the **Tables** node, select **SalesOrderHeader** and **SalesOrderDetail**, then expand **Employee**, select **EmployeeID** or **LoginID**, and then click **Next**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="f04a1-115">Las columnas necesarias adicionales se seleccionan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f04a1-115">Additional required columns are automatically selected.</span></span> <span data-ttu-id="f04a1-116">Seleccione cualquiera de las columnas seleccionadas automáticamente y vea la nota que hay bajo la lista **Objetos que se van a publicar** para obtener una explicación de por qué se necesita la columna.</span><span class="sxs-lookup"><span data-stu-id="f04a1-116">Select any of  the automatically selected columns and view the note below the **Objects to publish** list for an explanation why the column is required.</span></span>  
  
7.  <span data-ttu-id="f04a1-117">En la página Filtrar filas de tabla, haga clic en **Agregar** y luego en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-117">On the Filter Table Rows page, click **Add** and then click **Add Filter**.</span></span>  
  
8.  <span data-ttu-id="f04a1-118">En el cuadro de diálogo **Agregar filtro** , seleccione **Employee (HumanResources)** en **Seleccione la tabla que quiere filtrar**, haga clic en la columna **LoginID** , haga clic en la flecha derecha para agregar la columna a la cláusula WHERE de la consulta del filtro y modifique la cláusula WHERE de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="f04a1-118">In the **Add Filter** dialog box, select **Employee (HumanResources)** in **Select the table to filter**, click the **LoginID** column, click the right arrow to add the column to the WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [LoginID] = HOST_NAME()  
    ```  
  
9. <span data-ttu-id="f04a1-119">Haga clic en **Una fila de esta tabla irá a una sola suscripción**y luego en **Aceptar**</span><span class="sxs-lookup"><span data-stu-id="f04a1-119">Click **A row from this table will go to only one subscription**, and click **OK**.</span></span>  
  
10. <span data-ttu-id="f04a1-120">En la página **Filtrar filas de tabla** , haga clic en **Employee (Human Resources)**, haga clic en **Agregar** y, después, en **Agregar combinación para ampliar el filtro seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-120">On the **Filter Table Rows** page, click **Employee (Human Resources)**, click **Add,** and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
11. <span data-ttu-id="f04a1-121">En el cuadro de diálogo **Agregar combinación** , seleccione **Sales.SalesOrderHeader** en **Tabla combinada**, haga clic en **Escribir instrucción de combinación manualmente**y complete la instrucción de combinación de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="f04a1-121">In the **Add Join** dialog box, select **Sales.SalesOrderHeader** under **Joined table**, click **Write the join statement manually**, and complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
    ```  
  
12. <span data-ttu-id="f04a1-122">En **Especifique las opciones de combinación**, seleccione **Clave única**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-122">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="f04a1-123">En la página Filtrar filas de tabla, haga clic en **SalesOrderHeader**, haga clic en **Agregar**y luego en **Agregar combinación para ampliar el filtro seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-123">On the Filter Table Rows page, click **SalesOrderHeader**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
14. <span data-ttu-id="f04a1-124">En el cuadro de diálogo **Agregar combinación** , seleccione **Sales.SalesOrderDetail** en **Tabla combinada**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-124">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**.</span></span>  
  
15. <span data-ttu-id="f04a1-125">Haga clic en **Escribir instrucción de combinación manualmente**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-125">Click **Write the join statement manually**.</span></span>  
  
16. <span data-ttu-id="f04a1-126">En **Columnas de la tabla filtrada**, seleccione **BusinessEntityID**y haga clic en el botón de flecha para copiar el nombre de columna a la instrucción de combinación.</span><span class="sxs-lookup"><span data-stu-id="f04a1-126">In **Filtered table columns**, select **BusinessEntityID**, then click the arrow button to copy the column name to the loin statement.</span></span>  
  
17. <span data-ttu-id="f04a1-127">En el cuadro **Instrucción de combinación** , complete la instrucción de combinación de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="f04a1-127">In the **Join statement** box, complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.BusinessEntityID = SalesOrderHeader.SalesPersonID  
    ```  
  
18. <span data-ttu-id="f04a1-128">En **Especifique las opciones de combinación**, seleccione **Clave única**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-128">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="f04a1-129">En la página **Filtrar filas de tabla** , haga clic en **SalesOrderHeader (Sales)**, haga clic en **Agregar**y, después, en **Agregar combinación para ampliar el filtro seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-129">On the **Filter Table Rows** page, click **SalesOrderHeader (Sales)**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
20. <span data-ttu-id="f04a1-130">En el cuadro de diálogo **Agregar combinación** , seleccione **Sales.SalesOrderDetail** en **Tabla combinada**, haga clic en **Aceptar**y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-130">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**, click **OK**, and then click **Next**.</span></span>  
  
21. <span data-ttu-id="f04a1-131">Seleccione **Crear una instantánea inmediatamente**, desactive **Programar el Agente de instantáneas para ejecutarse**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-131">Select **Create a snapshot immediately**, clear **Schedule the snapshot agent to run at the following times**, and click **Next**.</span></span>  
  
22. <span data-ttu-id="f04a1-132">En la página seguridad del agente, haga clic en **configuración de seguridad**, escriba \<_Machine_Name> _**\ repl_snapshot** en el cuadro **cuenta de proceso** , proporcione la contraseña para esta cuenta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-132">On the Agent Security page, click **Security Settings**, type \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span> <span data-ttu-id="f04a1-133">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="f04a1-133">Click **Finish**.</span></span>  
  
23. <span data-ttu-id="f04a1-134">En la página Finalización del asistente, escriba **AdvWorksSalesOrdersMerge** en el cuadro **Nombre de publicación** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-134">On the Complete the Wizard page, enter **AdvWorksSalesOrdersMerge** in the **Publication name** box and click **Finish**.</span></span>  
  
24. <span data-ttu-id="f04a1-135">Una vez creada la publicación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-135">After the publication is created, click **Close**.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="f04a1-136">Para ver el estado de la generación de instantáneas</span><span class="sxs-lookup"><span data-stu-id="f04a1-136">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="f04a1-137">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor y luego la carpeta **Replicación** .</span><span class="sxs-lookup"><span data-stu-id="f04a1-137">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="f04a1-138">En la carpeta Publicaciones locales, haga clic con el botón derecho en **AdvWorksSalesOrdersMerge**y luego haga clic en **Ver estado del Agente de instantáneas**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-138">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="f04a1-139">Se muestra el estado actual del trabajo del Agente de instantáneas para la publicación.</span><span class="sxs-lookup"><span data-stu-id="f04a1-139">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="f04a1-140">Compruebe que el trabajo de instantáneas sea correcto antes de continuar con la siguiente lección.</span><span class="sxs-lookup"><span data-stu-id="f04a1-140">Ensure that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-merge-agent-login-to-the-pal"></a><span data-ttu-id="f04a1-141">Para agregar el inicio de sesión del Agente de mezcla para la lista de acceso de la publicación (PAL)</span><span class="sxs-lookup"><span data-stu-id="f04a1-141">To add the Merge Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="f04a1-142">Conéctese al publicador en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda el nodo del servidor y luego la carpeta **Replicación** .</span><span class="sxs-lookup"><span data-stu-id="f04a1-142">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="f04a1-143">En la carpeta Publicaciones locales, haga clic con el botón derecho en **AdvWorksSalesOrdersMerge**y luego haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-143">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="f04a1-144">Se mostrará el cuadro de diálogo **Propiedades de la publicación** .</span><span class="sxs-lookup"><span data-stu-id="f04a1-144">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="f04a1-145">Seleccione la página **Lista de acceso a la publicación** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-145">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="f04a1-146">En el cuadro de diálogo Agregar acceso de publicación, seleccione _<nombre_equipo>_**\repl_merge** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-146">In the Add Publication Access dialog box, select _<Machine_Name>_**\repl_merge** and click **OK**.</span></span> <span data-ttu-id="f04a1-147">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="f04a1-147">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f04a1-148">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f04a1-148">Next Steps</span></span>  
 <span data-ttu-id="f04a1-149">Ha creado correctamente la publicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="f04a1-149">You have successfully created the merge publication.</span></span> <span data-ttu-id="f04a1-150">A continuación se suscribirá a esta publicación.</span><span class="sxs-lookup"><span data-stu-id="f04a1-150">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="f04a1-151">Consulte la [Lección 2: Crear una suscripción a la publicación de combinación](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="f04a1-151">See [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04a1-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f04a1-152">See Also</span></span>  
 <span data-ttu-id="f04a1-153">[Filtrar datos publicados](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="f04a1-153">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="f04a1-154">[Filtros de fila con parámetros](merge/parameterized-filters-parameterized-row-filters.md) </span><span class="sxs-lookup"><span data-stu-id="f04a1-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span></span>  
 [<span data-ttu-id="f04a1-155">Definir un artículo</span><span class="sxs-lookup"><span data-stu-id="f04a1-155">Define an Article</span></span>](publish/define-an-article.md)  
  
  
