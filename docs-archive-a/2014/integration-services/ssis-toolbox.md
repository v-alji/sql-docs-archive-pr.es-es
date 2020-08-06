---
title: Cuadro de herramientas de SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.toolboxcommon.F1
- sql12.dts.designer.toolbox.F1
- sql12.dts.designer.toolboxfavorites.F1
ms.assetid: 552ff592-eeef-46e8-b4a2-9b2384c869aa
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed35218c84c77d3116ab8c897fe51fab5d6359aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747115"
---
# <a name="ssis-toolbox"></a><span data-ttu-id="632ee-102">Cuadro de herramientas de SSIS</span><span class="sxs-lookup"><span data-stu-id="632ee-102">SSIS Toolbox</span></span>
  <span data-ttu-id="632ee-103">Todos los componentes instalados en el equipo local, incluidos los componentes de terceros generados para SQL Server 2008 y 2008 R2, aparecen ahora automáticamente en el nuevo **Cuadro de herramientas de SSIS**.</span><span class="sxs-lookup"><span data-stu-id="632ee-103">All components that are installed on the local machine, including third-party components built for SQL Server 2008 and 2008 R2, now automatically appear in the new **SSIS Toolbox**.</span></span> <span data-ttu-id="632ee-104">Al instalar componentes adicionales, haga clic con el botón derecho en el cuadro de herramientas y, después, haga clic en **Actualizar cuadro de herramientas** para agregar los componentes.</span><span class="sxs-lookup"><span data-stu-id="632ee-104">When you install additional components, right-click inside the toolbox and then click **Refresh Toolbox** to add the components.</span></span>  
  
 <span data-ttu-id="632ee-105">Puede obtener acceso fácilmente a más información acerca de un componente del cuadro de herramientas si hace clic en el componente para ver una descripción en la parte inferior del cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="632ee-105">You can easily access more information about a component from the toolbox, by clicking the component to view a description at the bottom of the toolbox.</span></span> <span data-ttu-id="632ee-106">Haga clic en el botón Ayuda al lado de la descripción para mostrar el tema de los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="632ee-106">Click the Help button next to the description to display the Books Online topic.</span></span> <span data-ttu-id="632ee-107">En el caso de algunos componentes, también es posible tener acceso a ejemplos que muestran cómo configurarlos y utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="632ee-107">For certain components, you can also access samples that demonstrate how to configure and use the components.</span></span> <span data-ttu-id="632ee-108">Los ejemplos están disponibles en [MSDN](https://go.microsoft.com/fwlink/?LinkId=259189).</span><span class="sxs-lookup"><span data-stu-id="632ee-108">The samples are available on [MSDN](https://go.microsoft.com/fwlink/?LinkId=259189).</span></span> <span data-ttu-id="632ee-109">Para tener acceso a los ejemplos desde el **Cuadro de herramientas de SSIS**, haga clic en el vínculo **Buscar muestras** que aparece debajo de la descripción.</span><span class="sxs-lookup"><span data-stu-id="632ee-109">To access the samples from the **SSIS Toolbox**, click the **Find Samples** link that appears below the description.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="632ee-110">A diferencia de las versiones anteriores de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], no es posible quitar componentes instalados desde el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="632ee-110">Unlike previous versions of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], you cannot remove installed components from the toolbox.</span></span>  
  
 <span data-ttu-id="632ee-111">En el **Cuadro de herramientas de SSIS**, los componentes de flujo de control y flujo de datos están organizados en categorías.</span><span class="sxs-lookup"><span data-stu-id="632ee-111">In the **SSIS Toolbox**, control flow and data flow components are organized into categories.</span></span>  <span data-ttu-id="632ee-112">Puede expandir y contraer las categorías para ver y puede cambiar la organización de componentes de acuerdo con sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="632ee-112">You can expand and collapse categories for viewing and you can change the organization of components according to your preferences.</span></span>  <span data-ttu-id="632ee-113">Para restaurar la organización predeterminada, haga clic con el botón derecho dentro del cuadro de herramientas y, después, haga clic en **Restaurar valores predeterminados del cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="632ee-113">You can restore the default organization, by right-clicking inside the toolbox and then click **Restore Toolbox Defaults**.</span></span>  
  
 <span data-ttu-id="632ee-114">Las categorías **Favoritos** y **Común** aparecen en el cuadro de herramientas al seleccionar las pestañas **Flujo de control**, **Flujo de datos**y **Controladores de eventos** .</span><span class="sxs-lookup"><span data-stu-id="632ee-114">The **Favorites** and **Common** categories appear in the toolbox when you select the **Control Flow**, **Data Flow**, and **Event Handlers** tabs.</span></span> <span data-ttu-id="632ee-115">La categoría **otras tareas** aparece en el cuadro de herramientas cuando se selecciona la pestaña **flujo de control** o la pestaña controladores de **eventos** . Las **otras categorías transformaciones**, **otros orígenes**y **otros destinos** aparecen en el cuadro de herramientas al seleccionar la pestaña **flujo de datos** .</span><span class="sxs-lookup"><span data-stu-id="632ee-115">The **Other Tasks** category appears in the toolbox when you select the **Control Flow** tab or the **Event Handlers** tab. The **Other Transforms**, **Other Sources**, and **Other Destinations** categories appear in the toolbox when you select the **Data Flow** tab.</span></span>  
  
 <span data-ttu-id="632ee-116">Cuando se crea un proyecto de SSIS o se abre un proyecto existente, el **Cuadro de herramientas de SSIS** se muestra automáticamente.</span><span class="sxs-lookup"><span data-stu-id="632ee-116">When you create a new SSIS project or open an existing project, the **SSIS Toolbox** is automatically displayed.</span></span> <span data-ttu-id="632ee-117">También puede abrir el cuadro de herramientas haciendo clic en el botón Cuadro de herramientas situado en la esquina superior derecha de la superficie de diseño del paquete.</span><span class="sxs-lookup"><span data-stu-id="632ee-117">You can also open the toolbox by clicking the toolbox button that is located in the top-right corner of the package design surface.</span></span>  
  
 <span data-ttu-id="632ee-118">Puede acoplar el cuadro de herramientas, establecer que se contraiga cuando se acople, y cerrar el cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="632ee-118">You can dock the toolbox, set it to collapse when docked, and you can close the toolbox.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="632ee-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="632ee-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="632ee-120">Mover elementos del cuadro de herramientas de SSIS</span><span class="sxs-lookup"><span data-stu-id="632ee-120">Move SSIS Toolbox Items</span></span>](../../2014/integration-services/move-ssis-toolbox-items.md)  
  
  
