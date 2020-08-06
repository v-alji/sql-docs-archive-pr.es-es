---
title: Realizar una evaluación a petición mediante el uso de servidores registrados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: c14034ef-6e0b-4df5-8072-bfb8d90b3172
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a3a06efaabff7e94e5b560744f0e1c739831042a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662424"
---
# <a name="perform-an-on-demand-evaluation-by-using-registered-servers"></a><span data-ttu-id="4f2a1-102">Realizar una evaluación a petición usando servidores registrados</span><span class="sxs-lookup"><span data-stu-id="4f2a1-102">Perform an On-Demand Evaluation by Using Registered Servers</span></span>

  <span data-ttu-id="4f2a1-103">Puede realizar una evaluación a petición de las directivas de prácticas recomendadas con una o más instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizando servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-103">You can perform an on-demand evaluation of best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by using Registered Servers.</span></span> <span data-ttu-id="4f2a1-104">Puede utilizar grupos de servidores locales o un servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-104">You can use either local server groups or a central management server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f2a1-105">Puede realizar una evaluación a petición de las directivas de prácticas recomendadas con los miembros del grupo de servidores que ejecutan [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] o una versión posterior de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f2a1-105">You can perform an on-demand evaluation of best practices policies against server group members that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] or a later version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4f2a1-106">Sin embargo, puede recibir un error de excepción si hay algunas propiedades a las que se haga referencia en una directiva que no se admita en [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] o [!INCLUDE[ssVersion2000](../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f2a1-106">However, you may receive an exception error if there are some properties that are referred to by a policy that are not supported in [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] or [!INCLUDE[ssVersion2000](../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4f2a1-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4f2a1-107">Prerequisites</span></span>  
 <span data-ttu-id="4f2a1-108">Para realizar esta tarea, debe haber configurado uno o más registros de servidor en los servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-108">To perform this task, you must have configured one or more server registrations in Registered Servers.</span></span> <span data-ttu-id="4f2a1-109">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f2a1-109">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="4f2a1-110">Crear o editar un grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4f2a1-110">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   <span data-ttu-id="4f2a1-111">[Registra un servidor conectado &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a1-111">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
-   [<span data-ttu-id="4f2a1-112">Crear un servidor de administración central y un grupo de servidores &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4f2a1-112">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-evaluate-best-practices-policies-against-a-server-group"></a><span data-ttu-id="4f2a1-113">Para evaluar las directivas de prácticas recomendadas con un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="4f2a1-113">To evaluate best practices policies against a server group</span></span>  
  
1.  <span data-ttu-id="4f2a1-114">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], en el menú **Ver** , haga clic en **Servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-114">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="4f2a1-115">Expanda **motor de base de datos**y, a continuación, expanda **grupos**de servidores locales o **servidores de administración central**, en función de la configuración.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-115">Expand **Database Engine**, and then expand either **Local Server Groups**, or **Central Management Servers**, depending on your configuration.</span></span>  
  
3.  <span data-ttu-id="4f2a1-116">Realice cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4f2a1-116">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="4f2a1-117">Para evaluar las directivas en todos los servidores administrados por el grupo de servidores local o el servidor de administración central, haga clic con el botón secundario en el nombre del grupo de servidores local o en el nombre del servidor de administración central y, a continuación, haga clic en **evaluar directivas**.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-117">To evaluate the policies against all servers that are managed by the local server group or the central management server, right-click the local server group name or the central management server name, and then click **Evaluate Policies**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="4f2a1-118">Al evaluar las directivas a través de un servidor de administración central, no se evalúan con el propio servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-118">When you evaluate policies through a central management server, the policies are not evaluated against the central management server itself.</span></span>  
  
    -   <span data-ttu-id="4f2a1-119">Para evaluar las directivas con respecto a un servidor o grupo de servidores específico, expanda **grupos de servidores locales** o el nombre del servidor de administración central, haga clic con el botón secundario en el servidor o grupo de servidores del que desee evaluar las directivas y, a continuación, haga clic en **evaluar directivas**.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-119">To evaluate the policies against a specific server or server group, expand **Local Server Groups** or the central management server name, right-click the server or server group that you want to evaluate policies against, and then click **Evaluate Policies**.</span></span>  
  
4.  <span data-ttu-id="4f2a1-120">En el cuadro de diálogo **evaluar directivas** , junto al cuadro **origen** , haga clic en el botón de puntos suspensivos (**...**).</span><span class="sxs-lookup"><span data-stu-id="4f2a1-120">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="4f2a1-121">En el cuadro de diálogo **Seleccionar origen** , puede seleccionar **archivos** o **servidor** como origen de los archivos de directivas que se van a evaluar.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-121">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="4f2a1-122">Si hace clic en **servidor**, puede realizar una evaluación a petición de las directivas de prácticas recomendadas que se importaron previamente en la administración basada en directivas en un servidor local o remoto.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-122">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="4f2a1-123">En este tutorial, hará clic en **archivos**y, a continuación, seleccionará los archivos de directivas individuales que desea evaluar.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-123">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="4f2a1-124">Para ello, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4f2a1-124">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="4f2a1-125">Haga clic en **archivos**.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-125">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="4f2a1-126">Junto a **archivos**, haga clic en el botón de puntos suspensivos (**...**).</span><span class="sxs-lookup"><span data-stu-id="4f2a1-126">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="4f2a1-127">Seleccione uno o varios archivos de directivas. XML para evaluar y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-127">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="4f2a1-128">La lista de archivos seleccionados aparece en el cuadro **archivos** .</span><span class="sxs-lookup"><span data-stu-id="4f2a1-128">The list of selected files appears in the **Files** box.</span></span>  
  
    4.  <span data-ttu-id="4f2a1-129">En el cuadro de diálogo **Seleccionar origen** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-129">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="4f2a1-130">Si aparece el cuadro de diálogo **cargando directivas** , haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-130">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="4f2a1-131">Las directivas que ha seleccionado se muestran en la página **selección de directiva** .</span><span class="sxs-lookup"><span data-stu-id="4f2a1-131">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="4f2a1-132">Tenga en cuenta que un icono de advertencia al lado de una directiva indica que la directiva contiene scripts.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-132">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
6.  <span data-ttu-id="4f2a1-133">Haga clic en **evaluar** para evaluar las directivas.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-133">Click **Evaluate** to evaluate the policies.</span></span>  
  
7.  <span data-ttu-id="4f2a1-134">En el caso de algunos errores de las directivas, la administración basada en directivas le permite aplicar inmediatamente el cumplimiento de las directivas en el destino.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-134">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="4f2a1-135">Con tales errores, una casilla aparecerá al lado de la directiva que ha generado el error.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-135">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="4f2a1-136">Si activa la casilla o hace clic en la fila que contiene la Directiva con errores, las casillas aparecen en el panel **detalles de destino** junto a las instancias de destino que no pudieron realizar la evaluación.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-136">If you select the check box, or click the row with the failed policy, check boxes appear in the **Target details** pane next to the target instances that failed the evaluation.</span></span> <span data-ttu-id="4f2a1-137">Si se selecciona cualquiera de las casillas, el botón **aplicar** está disponible.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-137">If any of the check boxes are selected, the **Apply** button becomes available.</span></span> <span data-ttu-id="4f2a1-138">Al hacer clic en **aplicar**, la configuración no compatible se actualizará automáticamente en las instancias de destino seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instances that you selected.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="4f2a1-139">Asegúrese de que entiende totalmente la configuración de las directivas antes de actualizar una instancia de destino automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="4f2a1-140">Se recomienda que después de activar una o varias casillas, haga clic en **script**y elija una ubicación de salida para que pueda revisar el [!INCLUDE[tsql](../includes/tsql-md.md)] código subyacente antes de aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
8.  <span data-ttu-id="4f2a1-141">Para ver los resultados detallados de una directiva, haga clic en la Directiva en la tabla de **resultados** .</span><span class="sxs-lookup"><span data-stu-id="4f2a1-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span> <span data-ttu-id="4f2a1-142">En la tabla **detalles del destino** se muestran los detalles de cada instancia.</span><span class="sxs-lookup"><span data-stu-id="4f2a1-142">The **Target details** table shows the details for each instance.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="4f2a1-143">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="4f2a1-143">Next Lesson</span></span>  
 [<span data-ttu-id="4f2a1-144">Lección 2: Evaluación de las directivas de procedimientos recomendados de forma programada</span><span class="sxs-lookup"><span data-stu-id="4f2a1-144">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f2a1-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f2a1-145">See Also</span></span>  
 <span data-ttu-id="4f2a1-146">[Supervisar y aplicar las prácticas recomendadas mediante la administración basada en directivas](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="4f2a1-146">[Monitor and Enforce Best Practices by Using Policy-Based Management](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md) </span></span>  
 [<span data-ttu-id="4f2a1-147">Administrar varios servidores mediante servidores de administración central</span><span class="sxs-lookup"><span data-stu-id="4f2a1-147">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
