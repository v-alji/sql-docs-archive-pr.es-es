---
title: Realizar una evaluación a petición mediante Explorador de objetos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: ee6d3b79-18bc-49d3-8a1d-0c0905b990f0
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e32876978ac462af361986d84e11ef3dc0f278e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662423"
---
# <a name="perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="abcb1-102">Realizar una evaluación a petición usando Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="abcb1-102">Perform an On-Demand Evaluation by Using Object Explorer</span></span>
  <span data-ttu-id="abcb1-103">En esta tarea, utilizará el Explorador de objetos para realizar una evaluación a petición de las directivas de prácticas recomendadas para [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] en una instancia única de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abcb1-103">In this task, you will use Object Explorer to perform an on-demand evaluation of best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abcb1-104">También puede evaluar las directivas en una instancia única a través de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="abcb1-104">You can also evaluate policies on a single instance through Registered Servers.</span></span> <span data-ttu-id="abcb1-105">Para obtener más información, consulte [realizar una evaluación a petición mediante el uso de servidores registrados](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="abcb1-105">For more information, see [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="abcb1-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="abcb1-106">Prerequisites</span></span>  
 <span data-ttu-id="abcb1-107">Esta lección se basa en la versión de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abcb1-107">This lesson is based on the version of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abcb1-108">Para realizar una evaluación a petición de las directivas de prácticas recomendadas en las instancias que ejecutan [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] , debe usar el procedimiento del tema [realizar una evaluación a petición mediante el uso de servidores registrados](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="abcb1-108">To perform an on-demand evaluation of best practices policies against instances that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you must use the procedure in the topic [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
### <a name="to-perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="abcb1-109">Realizar una evaluación a petición usando Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="abcb1-109">To perform an on-demand evaluation by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="abcb1-110">Inicie [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]y después conéctese a [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abcb1-110">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="abcb1-111">En Explorador de objetos, expanda **Administración**, expanda **Administración de directivas**, haga clic con el botón secundario en **directivas**y, a continuación, haga clic en **evaluar**.</span><span class="sxs-lookup"><span data-stu-id="abcb1-111">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and then click **Evaluate**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="abcb1-112">De forma predeterminada, la instancia local se utiliza como el origen de las directivas.</span><span class="sxs-lookup"><span data-stu-id="abcb1-112">By default, the local instance is used as the source of the policies.</span></span> <span data-ttu-id="abcb1-113">Si ha importado las directivas de prácticas recomendadas previamente, se enumerarán junto con cualquier otra directiva que haya creado.</span><span class="sxs-lookup"><span data-stu-id="abcb1-113">If you have previously imported best practices policies, they will be listed, together with any other policies that you have created.</span></span> <span data-ttu-id="abcb1-114">Puede seleccionar cualquiera de las directivas de procedimientos recomendados importados y, a continuación, hacer clic en **evaluar**.</span><span class="sxs-lookup"><span data-stu-id="abcb1-114">You can select any of the imported best practices policies, and then click **Evaluate**.</span></span> <span data-ttu-id="abcb1-115">Si no ha importado las directivas de prácticas recomendadas, continúe con este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="abcb1-115">If you have not imported the best practices policies, continue with this procedure.</span></span>  
  
3.  <span data-ttu-id="abcb1-116">En el cuadro de diálogo **evaluar directivas** , junto al cuadro **origen** , haga clic en el botón de puntos suspensivos (**...**).</span><span class="sxs-lookup"><span data-stu-id="abcb1-116">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
4.  <span data-ttu-id="abcb1-117">En el cuadro de diálogo **Seleccionar origen** , puede seleccionar **archivos** o **servidor** como origen de los archivos de directivas que se van a evaluar.</span><span class="sxs-lookup"><span data-stu-id="abcb1-117">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="abcb1-118">Si hace clic en **servidor**, puede realizar una evaluación a petición de las directivas de prácticas recomendadas que se importaron previamente en la administración basada en directivas en un servidor local o remoto.</span><span class="sxs-lookup"><span data-stu-id="abcb1-118">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="abcb1-119">En este tutorial, hará clic en **archivos**y, a continuación, seleccionará los archivos de directivas individuales que desea evaluar.</span><span class="sxs-lookup"><span data-stu-id="abcb1-119">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="abcb1-120">Para ello, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="abcb1-120">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="abcb1-121">Haga clic en **archivos**.</span><span class="sxs-lookup"><span data-stu-id="abcb1-121">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="abcb1-122">Junto a **archivos**, haga clic en el botón de puntos suspensivos (**...**).</span><span class="sxs-lookup"><span data-stu-id="abcb1-122">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="abcb1-123">En el cuadro de diálogo **seleccionar Directiva** , busque la carpeta siguiente, que contiene las directivas de prácticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="abcb1-123">In the **Select Policy** dialog box, browse to the following folder, which contains the best practices policies:</span></span>  
  
         <span data-ttu-id="abcb1-124">**C:\Archivos de programa (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="abcb1-124">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="abcb1-125">La ruta de acceso puede variar según dónde instalara los archivos de programa de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , si ejecuta un sistema operativo de 32 bits o de 64 bits y el identificador de idioma.</span><span class="sxs-lookup"><span data-stu-id="abcb1-125">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
    4.  <span data-ttu-id="abcb1-126">Seleccione uno o varios archivos de directivas. XML para evaluar y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="abcb1-126">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="abcb1-127">La lista de archivos seleccionados aparece en el cuadro **archivos** .</span><span class="sxs-lookup"><span data-stu-id="abcb1-127">The list of selected files appears in the **Files** box.</span></span>  
  
    5.  <span data-ttu-id="abcb1-128">En el cuadro de diálogo **Seleccionar origen** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="abcb1-128">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="abcb1-129">Si aparece el cuadro de diálogo **cargando directivas** , haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="abcb1-129">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="abcb1-130">Las directivas que ha seleccionado se muestran en la página **selección de directiva** .</span><span class="sxs-lookup"><span data-stu-id="abcb1-130">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="abcb1-131">Tenga en cuenta que un icono de advertencia al lado de una directiva indica que la directiva contiene scripts.</span><span class="sxs-lookup"><span data-stu-id="abcb1-131">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
5.  <span data-ttu-id="abcb1-132">Haga clic en **evaluar** para evaluar las directivas.</span><span class="sxs-lookup"><span data-stu-id="abcb1-132">Click **Evaluate** to evaluate the policies.</span></span>  
  
     <span data-ttu-id="abcb1-133">En la tabla de **resultados** , se enumeran los resultados de cada Directiva.</span><span class="sxs-lookup"><span data-stu-id="abcb1-133">In the **Results** table, the results for each policy are listed.</span></span> <span data-ttu-id="abcb1-134">Un icono con una "x" roja indica que se produjo un error en el cumplimiento de la directiva.</span><span class="sxs-lookup"><span data-stu-id="abcb1-134">A red "x" icon indicates that policy compliance failed.</span></span>  
  
6.  <span data-ttu-id="abcb1-135">En el caso de algunos errores de las directivas, la administración basada en directivas le permite aplicar inmediatamente el cumplimiento de las directivas en el destino.</span><span class="sxs-lookup"><span data-stu-id="abcb1-135">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="abcb1-136">Con tales errores, una casilla aparecerá al lado de la directiva que ha generado el error.</span><span class="sxs-lookup"><span data-stu-id="abcb1-136">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="abcb1-137">Si activa la casilla, el botón **aplicar** está disponible.</span><span class="sxs-lookup"><span data-stu-id="abcb1-137">If you select the check box, the **Apply** button becomes available.</span></span> <span data-ttu-id="abcb1-138">Al hacer clic en **aplicar**, la configuración no compatible se actualizará automáticamente en la instancia de destino.</span><span class="sxs-lookup"><span data-stu-id="abcb1-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instance.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="abcb1-139">Asegúrese de que entiende totalmente la configuración de las directivas antes de actualizar una instancia de destino automáticamente.</span><span class="sxs-lookup"><span data-stu-id="abcb1-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="abcb1-140">Se recomienda que después de activar una o varias casillas, haga clic en **script**y elija una ubicación de salida para que pueda revisar el [!INCLUDE[tsql](../includes/tsql-md.md)] código subyacente antes de aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="abcb1-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
7.  <span data-ttu-id="abcb1-141">Para ver los resultados detallados de una directiva, haga clic en la Directiva en la tabla de **resultados** .</span><span class="sxs-lookup"><span data-stu-id="abcb1-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="abcb1-142">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="abcb1-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="abcb1-143">Realizar una evaluación a petición usando servidores registrados</span><span class="sxs-lookup"><span data-stu-id="abcb1-143">Perform an On-Demand Evaluation by Using Registered Servers</span></span>](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md)  
  
  
