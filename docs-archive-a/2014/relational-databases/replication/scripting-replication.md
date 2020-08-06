---
title: Crear script para la replicación | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server replication], replication objects
- merge replication scripting [SQL Server replication]
- replication [SQL Server], scripting
- snapshot replication [SQL Server], scripting
- scripts [SQL Server replication]
- transactional replication, scripting
ms.assetid: e50fac44-54c0-470c-a4ea-9c111fa4322b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e865e2664a399bca4738c1fc157bef176f35e96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662780"
---
# <a name="scripting-replication"></a><span data-ttu-id="37265-102">Crear script para la replicación</span><span class="sxs-lookup"><span data-stu-id="37265-102">Scripting Replication</span></span>
  <span data-ttu-id="37265-103">Todos los componentes de replicación de una topología deben convertirse en script como parte de un plan de recuperación de desastres y, además, los scripts también pueden utilizarse para automatizar tareas repetitivas.</span><span class="sxs-lookup"><span data-stu-id="37265-103">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="37265-104">Un script  contiene los procedimientos almacenados del sistema Transact-SQL necesarios para implementar los componentes de replicación a los que se refieren los scripts, como una publicación o una suscripción.</span><span class="sxs-lookup"><span data-stu-id="37265-104">A script contains the Transact-SQL system stored procedures necessary to implement the replication component(s) scripted, such as a publication or subscription.</span></span> <span data-ttu-id="37265-105">Los scripts se pueden crear en un asistente (como el Asistente para nueva publicación) o en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] después de crear un componente.</span><span class="sxs-lookup"><span data-stu-id="37265-105">Scripts can be created in a wizard (such as the New Publication Wizard) or in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] after you create a component.</span></span> <span data-ttu-id="37265-106">Puede ver, modificar y ejecutar el script mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="37265-106">You can view, modify, and run the script using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or **sqlcmd**.</span></span> <span data-ttu-id="37265-107">Los scripts se pueden almacenar con los archivos de copia de seguridad para utilizarlas en el caso de que se deba volver a configurar una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="37265-107">Scripts can be stored with backup files to be used in case a replication topology must be reconfigured.</span></span>  
  
 <span data-ttu-id="37265-108">Si se producen cambios en alguna propiedad, es necesario volver a generar el script de un componente.</span><span class="sxs-lookup"><span data-stu-id="37265-108">A component should be re-scripted if any property changes are made.</span></span> <span data-ttu-id="37265-109">Si utiliza procedimientos almacenados personalizados con la replicación transaccional, debe guardar una copia de cada procedimiento con los scripts; la copia se debe actualizar si el procedimiento cambia (los procedimientos se actualizan normalmente como consecuencia de cambios de esquema o cambios en los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37265-109">If you use custom stored procedures with transactional replication, a copy of each procedure should be stored with the scripts; the copy should be updated if the procedure changes (procedures are typically updated due to schema changes or changing application requirements).</span></span> <span data-ttu-id="37265-110">Para obtener más información sobre los procedimientos personalizados, vea [Especificar cómo se propagan los cambios para los artículos transaccionales](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="37265-110">For more information about custom procedures, see [Specify How Changes Are Propagated for Transactional Articles](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
 <span data-ttu-id="37265-111">Para las publicaciones de combinación que utilizan filtros con parámetros, los scripts de publicación contienen las llamadas al procedimiento almacenado para crear particiones de datos.</span><span class="sxs-lookup"><span data-stu-id="37265-111">For merge publications that use parameterized filters, publication scripts contain the stored procedure calls to create data partitions.</span></span> <span data-ttu-id="37265-112">El script proporciona una referencia para las particiones creadas y una forma de volver a crear una o más divisiones en caso necesario.</span><span class="sxs-lookup"><span data-stu-id="37265-112">The script provides a reference for the partitions created and a way in which to re-create one or more partitions if necessary.</span></span>  
  
## <a name="example-of-automating-a-task-with-scripts"></a><span data-ttu-id="37265-113">Ejemplo de automatización de una tarea con scripts</span><span class="sxs-lookup"><span data-stu-id="37265-113">Example of Automating a Task with Scripts</span></span>  
 <span data-ttu-id="37265-114">En el ejemplo [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)]se implementa la replicación de mezcla para distribuir datos al personal de ventas que no trabaja en la oficina central.</span><span class="sxs-lookup"><span data-stu-id="37265-114">Consider [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], which implements merge replication to distribute data to its remote sales force.</span></span> <span data-ttu-id="37265-115">Un representante de ventas descarga todos los datos que pertenecen a los clientes de su zona utilizando suscripciones de extracción.</span><span class="sxs-lookup"><span data-stu-id="37265-115">A sales representative downloads all the data that pertains to the customers in her territory using pull subscriptions.</span></span> <span data-ttu-id="37265-116">Cuando trabaja sin conexión, el representante de ventas actualiza los datos e incluye clientes y pedidos nuevos.</span><span class="sxs-lookup"><span data-stu-id="37265-116">When working offline, the sales representative updates data and enters new customers and orders.</span></span> <span data-ttu-id="37265-117">Como [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] dispone de más de 50 representantes de ventas en diferentes zonas, llevaría mucho tiempo crear las diferentes suscripciones necesarias en cada uno de los suscriptores con el Asistente para nuevas suscripciones.</span><span class="sxs-lookup"><span data-stu-id="37265-117">Because [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] has more than fifty sales representatives in different territories, it would be time-consuming to create the different subscriptions at each Subscriber with the New Subscription Wizard.</span></span> <span data-ttu-id="37265-118">En su lugar, el administrador de la replicación puede seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="37265-118">Instead, the replication administrator can follow these steps:</span></span>  
  
1.  <span data-ttu-id="37265-119">Establezca las publicaciones de combinación necesarias con particiones basadas en el representante de ventas o en su zona.</span><span class="sxs-lookup"><span data-stu-id="37265-119">Set up the necessary merge publications with partitions based on the sales representative or their territory.</span></span>  
  
2.  <span data-ttu-id="37265-120">Cree una suscripción de extracción para un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="37265-120">Create a pull subscription for one Subscriber.</span></span>  
  
3.  <span data-ttu-id="37265-121">Genere un script basado en esa suscripción de extracción.</span><span class="sxs-lookup"><span data-stu-id="37265-121">Generate a script based on that pull subscription.</span></span>  
  
4.  <span data-ttu-id="37265-122">Modifique el script, cambiando valores como el nombre del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="37265-122">Modify the script, changing such values as the name of the Subscriber.</span></span>  
  
5.  <span data-ttu-id="37265-123">Ejecute el script en varios suscriptores para generar las suscripciones de extracción requeridas.</span><span class="sxs-lookup"><span data-stu-id="37265-123">Run the script at multiple Subscribers to generate the required pull subscriptions.</span></span>  
  
## <a name="script-replication-objects"></a><span data-ttu-id="37265-124">Generar script de objetos de replicación</span><span class="sxs-lookup"><span data-stu-id="37265-124">Script Replication Objects</span></span>  
 <span data-ttu-id="37265-125">Genere script de objetos de replicación desde los asistentes de replicación o desde la carpeta **Replicación** de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37265-125">Script replication objects from the replication wizards or from the **Replication** folder in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="37265-126">Si genera script desde los asistentes, puede elegir crear objetos y generar script, o solo generar script.</span><span class="sxs-lookup"><span data-stu-id="37265-126">If you script from the wizards, you can choose to create objects and script them, or you can choose only to script them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="37265-127">Todas las contraseñas se generan como NULL.</span><span class="sxs-lookup"><span data-stu-id="37265-127">All passwords are scripted as NULL.</span></span> <span data-ttu-id="37265-128">Cuando sea posible, pida a los usuarios que proporcionen credenciales de seguridad en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="37265-128">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="37265-129">Si almacena credenciales en un archivo de script, debe proteger el archivo para evitar el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="37265-129">If you store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="37265-130">Para obtener más información sobre el uso de los asistentes de replicación, vea:</span><span class="sxs-lookup"><span data-stu-id="37265-130">For more information about using the replication wizards, see:</span></span>  
  
-   [<span data-ttu-id="37265-131">Configurar la publicación y la distribución</span><span class="sxs-lookup"><span data-stu-id="37265-131">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
-   <span data-ttu-id="37265-132">[Create a Publication](publish/create-a-publication.md) (Creación de una publicación)</span><span class="sxs-lookup"><span data-stu-id="37265-132">[Create a Publication](publish/create-a-publication.md)</span></span>  
  
-   <span data-ttu-id="37265-133">[Create a Push Subscription](create-a-push-subscription.md) (Creación de una suscripción de inserción)</span><span class="sxs-lookup"><span data-stu-id="37265-133">[Create a Push Subscription](create-a-push-subscription.md)</span></span>  
  
-   [<span data-ttu-id="37265-134">Crear una suscripción de extracción</span><span class="sxs-lookup"><span data-stu-id="37265-134">Create a Pull Subscription</span></span>](create-a-pull-subscription.md)  
  
#### <a name="to-script-an-object-from-a-replication-wizard"></a><span data-ttu-id="37265-135">Para generar el script de un objeto desde un asistente de replicación</span><span class="sxs-lookup"><span data-stu-id="37265-135">To script an object from a replication wizard</span></span>  
  
1.  <span data-ttu-id="37265-136">En la página **Acciones del asistente** de un asistente, active la casilla adecuada para el asistente:</span><span class="sxs-lookup"><span data-stu-id="37265-136">On the **Wizard Actions** page of a wizard, select the check box appropriate for the wizard:</span></span>  
  
    -   <span data-ttu-id="37265-137">**Generar un archivo de script con pasos para crear una publicación**</span><span class="sxs-lookup"><span data-stu-id="37265-137">**Generate a script file with steps to create a publication**</span></span>  
  
    -   <span data-ttu-id="37265-138">**Generar un archivo de script con pasos para crear las suscripciones**</span><span class="sxs-lookup"><span data-stu-id="37265-138">**Generate a script file with steps to create the subscription(s)**</span></span>  
  
    -   <span data-ttu-id="37265-139">**Generar un archivo de script con pasos para configurar la distribución**</span><span class="sxs-lookup"><span data-stu-id="37265-139">**Generate a script file with steps to configure distribution**</span></span>  
  
2.  <span data-ttu-id="37265-140">En la página **Propiedades del archivo de script** especifique las opciones.</span><span class="sxs-lookup"><span data-stu-id="37265-140">Specify options on the **Script File Properties** page.</span></span>  
  
3.  <span data-ttu-id="37265-141">Finalice el asistente.</span><span class="sxs-lookup"><span data-stu-id="37265-141">Complete the wizard.</span></span>  
  
#### <a name="to-script-an-object-from-management-studio"></a><span data-ttu-id="37265-142">Para generar script de un objeto en Management Studio</span><span class="sxs-lookup"><span data-stu-id="37265-142">To script an object from Management Studio</span></span>  
  
1.  <span data-ttu-id="37265-143">Conéctese al distribuidor, publicador o suscriptor en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y, a continuación, expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="37265-143">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="37265-144">Expanda la carpeta **Replicación** y, a continuación, expanda la carpeta **Publicaciones locales** o **Suscripciones locales** .</span><span class="sxs-lookup"><span data-stu-id="37265-144">Expand the **Replication** folder, and then expand the **Local Publications** folder or the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="37265-145">Haga clic con el botón secundario en una publicación o suscripción y, a continuación, haga clic en **Generar scripts**.</span><span class="sxs-lookup"><span data-stu-id="37265-145">Right-click a publication or subscription, and then click **Generate Scripts**.</span></span>  
  
4.  <span data-ttu-id="37265-146">Especifique las opciones en el cuadro de diálogo **Generar script SQL - \<ReplicationObject>** .</span><span class="sxs-lookup"><span data-stu-id="37265-146">Specify options in the **Generate SQL Script - \<ReplicationObject>** dialog box.</span></span>  
  
5.  <span data-ttu-id="37265-147">Haga clic en **Script a archivo**.</span><span class="sxs-lookup"><span data-stu-id="37265-147">Click **Script to File**.</span></span>  
  
6.  <span data-ttu-id="37265-148">Escriba un nombre de archivo en el cuadro de diálogo **Ubicación del archivo de script** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="37265-148">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="37265-149">Se muestra un mensaje de estado.</span><span class="sxs-lookup"><span data-stu-id="37265-149">A status message is displayed.</span></span>  
  
7.  <span data-ttu-id="37265-150">Haga clic en **Aceptar**y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="37265-150">Click **OK**, and then click **Close**.</span></span>  
  
#### <a name="to-script-multiple-objects-from-management-studio"></a><span data-ttu-id="37265-151">Para generar script de varios objetos desde Management Studio</span><span class="sxs-lookup"><span data-stu-id="37265-151">To script multiple objects from Management Studio</span></span>  
  
1.  <span data-ttu-id="37265-152">Conéctese al distribuidor, publicador o suscriptor en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y, a continuación, expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="37265-152">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="37265-153">Haga clic con el botón secundario en la carpeta **Replicación** y, a continuación, en **Generar scripts**.</span><span class="sxs-lookup"><span data-stu-id="37265-153">Right-click the **Replication** folder, and then click **Generate Scripts**.</span></span>  
  
3.  <span data-ttu-id="37265-154">Especifique las opciones en el cuadro de diálogo **Generar script SQL** .</span><span class="sxs-lookup"><span data-stu-id="37265-154">Specify options in the **Generate SQL Script** dialog box.</span></span>  
  
4.  <span data-ttu-id="37265-155">Haga clic en **Script a archivo**.</span><span class="sxs-lookup"><span data-stu-id="37265-155">Click **Script to File**.</span></span>  
  
5.  <span data-ttu-id="37265-156">Escriba un nombre de archivo en el cuadro de diálogo **Ubicación del archivo de script** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="37265-156">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="37265-157">Se muestra un mensaje de estado.</span><span class="sxs-lookup"><span data-stu-id="37265-157">A status message is displayed.</span></span>  
  
6.  <span data-ttu-id="37265-158">Haga clic en **Aceptar** y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="37265-158">Click **OK, and then** click **Close**.</span></span>  
  
  
