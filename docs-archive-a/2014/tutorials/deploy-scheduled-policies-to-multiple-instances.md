---
title: Implementar directivas programadas en varias instancias | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: f551b8e8-3668-4ed4-852f-bae826254f4f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 30faf94c2033be43ac035517e58d5a18c0c68ab8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744450"
---
# <a name="deploy-scheduled-policies-to-multiple-instances"></a><span data-ttu-id="15cc5-102">Implementar directivas programadas en varias instancias</span><span class="sxs-lookup"><span data-stu-id="15cc5-102">Deploy Scheduled Policies to Multiple Instances</span></span>
  <span data-ttu-id="15cc5-103">Mediante el uso de servidores registrados puede implementar directivas programadas en servidores administrados desde una ubicación central.</span><span class="sxs-lookup"><span data-stu-id="15cc5-103">By using Registered Servers, you can deploy scheduled policies to managed servers from a central location.</span></span> <span data-ttu-id="15cc5-104">Puede implementar directivas programadas desde un grupo de servidores locales o desde un Servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="15cc5-104">You can deploy scheduled policies from either a local server group, or from a Central Management Server.</span></span>  
  
 <span data-ttu-id="15cc5-105">En esta tarea realizará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15cc5-105">In this task, you will do the following:</span></span>  
  
1.  <span data-ttu-id="15cc5-106">Exportar las directivas programadas en la tarea anterior a una carpeta.</span><span class="sxs-lookup"><span data-stu-id="15cc5-106">Export the policies that you scheduled in the previous task to a folder.</span></span>  
  
2.  <span data-ttu-id="15cc5-107">Implementar las directivas programadas en instancias de destino administradas mediante servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="15cc5-107">Deploy the scheduled policies to target instances that are managed through Registered Servers.</span></span>  
  
 <span data-ttu-id="15cc5-108">Realizará estas tareas en el equipo en el que completó las tareas anteriores de esta lección.</span><span class="sxs-lookup"><span data-stu-id="15cc5-108">You will perform these tasks on the computer where you completed the previous tasks in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="15cc5-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="15cc5-109">Prerequisites</span></span>  
 <span data-ttu-id="15cc5-110">Esta tarea consta de los requisitos previos siguientes:</span><span class="sxs-lookup"><span data-stu-id="15cc5-110">This task has the following prerequisites:</span></span>  
  
-   <span data-ttu-id="15cc5-111">Debe haber completado las tareas anteriores de esta lección.</span><span class="sxs-lookup"><span data-stu-id="15cc5-111">You must have completed the previous tasks in this lesson.</span></span>  
  
-   <span data-ttu-id="15cc5-112">Las instancias en las que desee implementar las directivas programadas deben ejecutar [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="15cc5-112">The instances where you want to deploy the scheduled policies must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="15cc5-113">Automation requiere que las directivas estén almacenadas localmente, lo que no se admite en versiones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15cc5-113">Automation requires the policies to be stored locally, which is not supported on versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
-   <span data-ttu-id="15cc5-114">Los servidores en los que desea implementar las directivas programadas deben estar registrados en servidores registrados en el nodo grupos de servidores **locales** o **servidores de administración central** .</span><span class="sxs-lookup"><span data-stu-id="15cc5-114">The servers where you want to deploy the scheduled policies must be registered in Registered Servers in either the **Local Server Groups** or the **Central Management Servers** node.</span></span> <span data-ttu-id="15cc5-115">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="15cc5-115">For more information, see the following topics:</span></span>  
  
    -   [<span data-ttu-id="15cc5-116">Crear o editar un grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="15cc5-116">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
    -   <span data-ttu-id="15cc5-117">[Registra un servidor conectado &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="15cc5-117">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
    -   [<span data-ttu-id="15cc5-118">Crear un servidor de administración central y un grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="15cc5-118">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-export-the-scheduled-policies-as-xml-files"></a><span data-ttu-id="15cc5-119">Para exportar las directivas programadas como archivos .xml</span><span class="sxs-lookup"><span data-stu-id="15cc5-119">To export the scheduled policies as .xml files</span></span>  
  
1.  <span data-ttu-id="15cc5-120">En el servidor donde configuró las directivas programadas en la tarea anterior, expanda **Administración**, expanda **Administración de directivas**y, a continuación, haga clic en **directivas**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-120">On the server where you configured scheduled policies in the previous task, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span>  
  
2.  <span data-ttu-id="15cc5-121">En el menú **Ver** , haga clic en **Detalles del Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-121">On the **View** menu, click **Object Explorer Details**.</span></span>  
  
3.  <span data-ttu-id="15cc5-122">En el panel de **detalles del explorador de objetos** , seleccione todas las directivas de prácticas recomendadas programadas que desee implementar en otros servidores mediante servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="15cc5-122">In the **Object Explorer Details** pane, select all the scheduled best practices policies that you want to deploy to other servers through Registered Servers.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15cc5-123">Puede hacer clic en el encabezado **categoría** para ordenar las directivas por categoría.</span><span class="sxs-lookup"><span data-stu-id="15cc5-123">You can click the **Category** heading to sort the policies by category.</span></span>  
  
4.  <span data-ttu-id="15cc5-124">Haga clic con el botón secundario en la selección y luego haga clic en **exportar Directiva**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-124">Right-click the selection, and then click **Export Policy**.</span></span>  
  
5.  <span data-ttu-id="15cc5-125">Si seleccionó varias directivas para exportar, en el cuadro de diálogo **Buscar carpeta** , seleccione una carpeta de destino o cree una nueva carpeta.</span><span class="sxs-lookup"><span data-stu-id="15cc5-125">If you selected multiple policies to export, in the **Browse For Folder** dialog box, select a destination folder, or create a new folder.</span></span> <span data-ttu-id="15cc5-126">En esta lección, cree una nueva carpeta con la ruta de acceso **c:\ Scheduled_BP_Policies**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-126">For this lesson, create a new folder with the path **C:\Scheduled_BP_Policies**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="15cc5-127">Si solo ha seleccionado una directiva para exportar, en el cuadro de diálogo **exportar Directiva** , cree una nueva carpeta con la ruta de acceso **c:\ Scheduled_BP_Policies**, haga clic en **abrir**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-127">If you only selected one policy to export, in the **Export Policy** dialog box, create a new folder with the path **C:\Scheduled_BP_Policies**, click **Open**, and then click **Save**.</span></span>  
  
     <span data-ttu-id="15cc5-128">Los archivos de directiva .xml se crean en la ubicación de carpeta.</span><span class="sxs-lookup"><span data-stu-id="15cc5-128">The .xml policy files are created in the folder location.</span></span>  
  
### <a name="to-deploy-the-scheduled-policies-to-servers-that-are-managed-through-registered-servers"></a><span data-ttu-id="15cc5-129">Para implementar las directivas programadas en servidores administrados mediante servidores registrados</span><span class="sxs-lookup"><span data-stu-id="15cc5-129">To deploy the scheduled policies to servers that are managed through Registered Servers</span></span>  
  
1.  <span data-ttu-id="15cc5-130">En el menú **Ver** , haga clic en **Servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-130">On the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="15cc5-131">Expanda **motor de base de datos**, expanda grupos de servidores **locales** o **servidores de administración central**, haga clic con el botón secundario en el nodo en el que desea implementar las directivas y, a continuación, haga clic en **importar directivas**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-131">Expand **Database Engine**, expand either **Local Server Groups** or **Central Management Servers**, right-click the node that you want to deploy the policies to, and then click **Import Policies**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15cc5-132">Si hace clic con el botón secundario en **grupos de servidores locales** o en el propio servidor de administración central, las directivas se implementarán en todos los servidores administrados.</span><span class="sxs-lookup"><span data-stu-id="15cc5-132">If you right-click **Local Server Groups** or the Central Management Server itself, the policies will be deployed to all managed servers.</span></span> <span data-ttu-id="15cc5-133">Si hace clic con el botón secundario en un grupo de servidores concreto, las directivas solo se implementarán en servidores de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="15cc5-133">If you right-click a specific server group, the policies will only be deployed to servers in that group.</span></span> <span data-ttu-id="15cc5-134">Si hace clic con el botón secundario en un servidor registrado, las directivas solo se implementarán en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="15cc5-134">If you right-click a specific registered server, the policies will only be deployed to that server.</span></span>  
  
3.  <span data-ttu-id="15cc5-135">Junto a **archivos para importar**, haga clic en el botón de puntos suspensivos (**...**).</span><span class="sxs-lookup"><span data-stu-id="15cc5-135">Next to **Files to import**, click the ellipsis button (**...**).</span></span>  
  
4.  <span data-ttu-id="15cc5-136">En el cuadro de diálogo **seleccionar Directiva** , busque la ubicación de la carpeta en la que guardó las directivas programadas.</span><span class="sxs-lookup"><span data-stu-id="15cc5-136">In the **Select Policy** dialog box, browse to the folder location where you saved the scheduled policies.</span></span> <span data-ttu-id="15cc5-137">En este ejemplo, vaya a la ubicación **c:\ Scheduled_BP_Policies**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-137">For this example, browse to the location **C:\Scheduled_BP_Policies**.</span></span>  
  
5.  <span data-ttu-id="15cc5-138">Seleccione las directivas que desea importar a las instancias de destino y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-138">Select the policies that you want to import to the target instances, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="15cc5-139">En el cuadro de diálogo **importar** , en la lista Estado de la **Directiva** , seleccione el estado de directiva deseado.</span><span class="sxs-lookup"><span data-stu-id="15cc5-139">In the **Import** dialog box, in the **Policy state** list, select the desired policy state.</span></span> <span data-ttu-id="15cc5-140">Puede elegir entre conservar el estado de directiva, habilitar, o deshabilitar las directivas al importar.</span><span class="sxs-lookup"><span data-stu-id="15cc5-140">You can choose to preserve the policy state, enable, or disable the policies on import.</span></span> <span data-ttu-id="15cc5-141">Tenga en cuenta que las directivas deben estar habilitadas para ejecutarse según una programación.</span><span class="sxs-lookup"><span data-stu-id="15cc5-141">Be aware that the policies must be enabled to run on a schedule.</span></span>  
  
7.  <span data-ttu-id="15cc5-142">Haga clic en **Aceptar** para importar las directivas a todas las instancias de destino.</span><span class="sxs-lookup"><span data-stu-id="15cc5-142">Click **OK** to import the policies to all the target instances.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15cc5-143">Si hay algún error, el cuadro de diálogo **importar** no desaparecerá.</span><span class="sxs-lookup"><span data-stu-id="15cc5-143">If there are any errors, the **Import** dialog box does not disappear.</span></span> <span data-ttu-id="15cc5-144">Haga clic en la página **registro** para revisar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="15cc5-144">Click the **Log** page to review the messages.</span></span> <span data-ttu-id="15cc5-145">Haga clic en **Cancelar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="15cc5-145">Click **Cancel** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="15cc5-146">Para ver las directivas de una instancia de destino, conéctese a la instancia, abra Explorador de objetos, expanda **Administración**y, a continuación, expanda **directivas**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-146">To view the policies from a target instance, connect to the instance, open Object Explorer, expand **Management**, and then expand **Policies**.</span></span> <span data-ttu-id="15cc5-147">Debería ver las directivas importadas en el nodo **directivas** .</span><span class="sxs-lookup"><span data-stu-id="15cc5-147">You should see the imported policies in the **Policies** node.</span></span> <span data-ttu-id="15cc5-148">Si hace doble clic en cada directiva, podrá ver el programa, o cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="15cc5-148">If you double-click each policy, you can view the schedule, or change the settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15cc5-149">Para ver los resultados de la evaluación después de la ejecución de una directiva programada, abra el registro de historial de directivas en la instancia de destino.</span><span class="sxs-lookup"><span data-stu-id="15cc5-149">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="15cc5-150">Para abrir el registro, haga clic con el botón secundario en **Administración de directivas**y, a continuación, haga clic en **Ver historial**.</span><span class="sxs-lookup"><span data-stu-id="15cc5-150">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="15cc5-151">Resumen</span><span class="sxs-lookup"><span data-stu-id="15cc5-151">Summary</span></span>  
 <span data-ttu-id="15cc5-152">Este tutorial le ha mostrado la forma de realizar evaluaciones tanto programadas como a petición de las directivas de prácticas recomendadas en una o varias instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15cc5-152">This tutorial has shown you how to perform both on-demand and scheduled evaluations of the best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="next"></a><span data-ttu-id="15cc5-153">Siguientes</span><span class="sxs-lookup"><span data-stu-id="15cc5-153">Next</span></span>  
 <span data-ttu-id="15cc5-154">Este tutorial ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="15cc5-154">This tutorial is finished.</span></span> <span data-ttu-id="15cc5-155">Para volver al inicio, vea [Tutorial: evaluar las prácticas recomendadas mediante la administración basada en directivas](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="15cc5-155">To return to the start, see [Tutorial: Evaluating Best Practices by Using Policy-Based Management](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="15cc5-156">Para ver una lista de los [!INCLUDE[ssDE](../includes/ssde-md.md)] tutoriales, haga clic en [motor de base de datos tutoriales](../relational-databases/database-engine-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="15cc5-156">To see a list of [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorials, click [Database Engine Tutorials](../relational-databases/database-engine-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15cc5-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15cc5-157">See Also</span></span>  
 [<span data-ttu-id="15cc5-158">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="15cc5-158">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
