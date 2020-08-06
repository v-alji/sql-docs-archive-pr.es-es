---
title: Programar las directivas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 59417a54-55f1-4468-ba41-368aa852c2d4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 1bce1b9d650606e9485899c34c72ca6b27a72dae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747762"
---
# <a name="schedule-the-policies"></a><span data-ttu-id="9a509-102">Programar las directivas</span><span class="sxs-lookup"><span data-stu-id="9a509-102">Schedule the Policies</span></span>
  <span data-ttu-id="9a509-103">En esta tarea, programará las directivas de prácticas recomendadas que importó en la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="9a509-103">In this task, you will schedule the best practices policies that you imported in the previous task.</span></span>  
  
### <a name="to-schedule-the-best-practices-policies"></a><span data-ttu-id="9a509-104">Para programar las directivas de prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="9a509-104">To schedule the best practices policies</span></span>  
  
1.  <span data-ttu-id="9a509-105">En Explorador de objetos, expanda **Administración**, expanda **Administración de directivas**, expanda **directivas**, haga clic con el botón secundario en una directiva de prácticas recomendadas y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9a509-105">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Policies**, right-click a best practices policy, and then click **Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a509-106">Como alternativa, para ver fácilmente qué directivas están asociadas a los procedimientos recomendados y ordenar las categorías de prácticas recomendadas, expanda **Administración**, expanda **Administración de directivas**y, a continuación, haga clic en **directivas**.</span><span class="sxs-lookup"><span data-stu-id="9a509-106">As an alternative, to easily see which policies are associated with best practices and to sort the best practices categories, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span> <span data-ttu-id="9a509-107">En el menú **Ver** , haga clic en **Detalles del Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="9a509-107">On the **View** menu, click **Object Explorer Details**.</span></span> <span data-ttu-id="9a509-108">En el panel de **detalles del explorador de objetos** , haga clic en el encabezado **categoría** para ordenar las directivas por categoría.</span><span class="sxs-lookup"><span data-stu-id="9a509-108">In the **Object Explorer Details** pane, click the **Category** heading to sort the policies by category.</span></span> <span data-ttu-id="9a509-109">Las directivas de prácticas recomendadas tienen el prefijo **prácticas recomendadas de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="9a509-109">The best practices policies have the prefix **Microsoft Best Practices**.</span></span> <span data-ttu-id="9a509-110">Haga clic con el botón secundario en la Directiva que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9a509-110">Right-click the policy that you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9a509-111">En la página **General** del cuadro de diálogo **abrir Directiva** , en la lista **modo de evaluación** , haga clic **en programación**.</span><span class="sxs-lookup"><span data-stu-id="9a509-111">On the **General** page of the **Open Policy** dialog box, in the **Evaluation Mode** list, click **On schedule**.</span></span>  
  
3.  <span data-ttu-id="9a509-112">Junto al cuadro **programación** , haga clic en **elegir** para especificar una programación existente o haga clic en **nuevo** para crear una nueva programación.</span><span class="sxs-lookup"><span data-stu-id="9a509-112">Next to the **Schedule** box, click **Pick** to specify an existing schedule, or click **New** to create a new schedule.</span></span>  
  
4.  <span data-ttu-id="9a509-113">Después de configurar una programación, puede activar la casilla **habilitada** situada cerca de la parte superior de la página para habilitar la Directiva programada.</span><span class="sxs-lookup"><span data-stu-id="9a509-113">After you have configured a schedule, you can select the **Enabled** check box near the top of the page to enable the scheduled policy.</span></span>  
  
5.  <span data-ttu-id="9a509-114">Repita los pasos 1 a 4 con cada directiva que desee programar.</span><span class="sxs-lookup"><span data-stu-id="9a509-114">Repeats steps 1 through 4 for each policy that you want to schedule.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a509-115">Para ver los resultados de la evaluación después de la ejecución de una directiva programada, abra el registro de historial de directivas en la instancia de destino.</span><span class="sxs-lookup"><span data-stu-id="9a509-115">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="9a509-116">Para abrir el registro, haga clic con el botón secundario en **Administración de directivas**y, a continuación, haga clic en **Ver historial**.</span><span class="sxs-lookup"><span data-stu-id="9a509-116">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="9a509-117">Resumen</span><span class="sxs-lookup"><span data-stu-id="9a509-117">Summary</span></span>  
 <span data-ttu-id="9a509-118">Configuró las directivas programadas para ejecutarse en una instancia única de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a509-118">You configured scheduled policies to run on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9a509-119">Si desea implementarlas en varias instancias, continúe con la siguiente tarea de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="9a509-119">If you want to deploy scheduled policies to multiple instances, continue to the next task in this tutorial.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9a509-120">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9a509-120">Next Steps</span></span>  
 [<span data-ttu-id="9a509-121">Implementar directivas programadas en varias instancias</span><span class="sxs-lookup"><span data-stu-id="9a509-121">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
  
