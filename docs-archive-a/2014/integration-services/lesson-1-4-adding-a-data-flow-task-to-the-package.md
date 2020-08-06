---
title: 'Paso 4: Agregar una tarea Flujo de datos al paquete | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 96af3073-8f11-4444-b934-fe8613a2d084
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4fda1de99e9fcaa683f9063e2feb1b71886a5cd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673128"
---
# <a name="step-4-adding-a-data-flow-task-to-the-package"></a><span data-ttu-id="dbc70-102">Paso 4: Adición de una tarea Flujo de datos al paquete</span><span class="sxs-lookup"><span data-stu-id="dbc70-102">Step 4: Adding a Data Flow Task to the Package</span></span>
  <span data-ttu-id="dbc70-103">Una vez que ha creado los administradores de conexión para los datos de origen y de destino, la siguiente tarea consiste en agregar una tarea de flujo de datos al paquete.</span><span class="sxs-lookup"><span data-stu-id="dbc70-103">After you have created the connection managers for the source and destination data, the next task is to add a Data Flow task to your package.</span></span> <span data-ttu-id="dbc70-104">La tarea de flujo de datos encapsula el motor de flujo de datos que mueve datos entre orígenes y destinos, y proporciona la funcionalidad para transformar, limpiar y modificar los datos a medida que se mueven.</span><span class="sxs-lookup"><span data-stu-id="dbc70-104">The Data Flow task encapsulates the data flow engine that moves data between sources and destinations, and provides the functionality for transforming, cleaning, and modifying data as it is moved.</span></span> <span data-ttu-id="dbc70-105">En la tarea de flujo de datos se lleva a cabo la mayor parte del proceso de extracción, transformación y carga (ETL).</span><span class="sxs-lookup"><span data-stu-id="dbc70-105">The Data Flow task is where most of the work of an extract, transform, and load (ETL) process occurs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="dbc70-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]separa el flujo de datos del flujo de control.</span><span class="sxs-lookup"><span data-stu-id="dbc70-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates data flow from control flow.</span></span>  
  
### <a name="to-add-a-data-flow-task"></a><span data-ttu-id="dbc70-107">Para agregar una tarea de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="dbc70-107">To add a Data Flow task</span></span>  
  
1.  <span data-ttu-id="dbc70-108">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="dbc70-108">Click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="dbc70-109">En el **Cuadro de herramientas de SSIS**, expanda **Favoritos**y arrastre una **tarea Flujo de datos** a la superficie de diseño de la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="dbc70-109">In the **SSIS Toolbox**, expand **Favorites**, and drag a **Data Flow Task** onto the design surfaceof the **Control Flow** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbc70-110">Si el cuadro de herramientas de SSIS no está disponible, seleccione SSIS en el menú principal y, después, haga clic en el cuadro de herramientas de SSIS para mostrarlo.</span><span class="sxs-lookup"><span data-stu-id="dbc70-110">If the SSIS Toolbox isn't available, on the main menu select SSIS then SSIS Toolbox to display the SSIS Toolbox.</span></span>  
  
3.  <span data-ttu-id="dbc70-111">En la superficie de diseño **flujo de control** , haga clic con el botón secundario en la **tarea flujo de datos**recién agregada, haga clic en cambiar **nombre**y cambie el nombre a `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="dbc70-111">On the **Control Flow** design surface, right-click the newly added **Data Flow Task**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
     <span data-ttu-id="dbc70-112">Es aconsejable proporcionar nombres únicos a todos los componentes que se agregan a una superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="dbc70-112">It is good practice to provide unique names to all components that you add to a design surface.</span></span> <span data-ttu-id="dbc70-113">Para facilitar su uso y mantenimiento, los nombres deben describir la función que lleva a cabo cada componente.</span><span class="sxs-lookup"><span data-stu-id="dbc70-113">For ease of use and maintainability, the names should describe the function that each component performs.</span></span> <span data-ttu-id="dbc70-114">Seguir estas directrices de nomenclatura permite que los paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sean autodocumentados.</span><span class="sxs-lookup"><span data-stu-id="dbc70-114">Following these naming guidelines allows your [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to be self-documenting.</span></span> <span data-ttu-id="dbc70-115">Los paquetes también pueden documentarse mediante anotaciones.</span><span class="sxs-lookup"><span data-stu-id="dbc70-115">Another way to document your packages is by using annotations.</span></span> <span data-ttu-id="dbc70-116">Para obtener más información sobre cómo usar anotaciones, consulte [Usar anotaciones en paquetes](use-annotations-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="dbc70-116">For more information about annotations, see [Use Annotations in Packages](use-annotations-in-packages.md).</span></span>  
  
4.  <span data-ttu-id="dbc70-117">Haga clic con el botón secundario en la tarea flujo de datos, haga clic en **propiedades**y, en el ventana Propiedades, compruebe que la `LocaleID` propiedad está establecida en **Inglés (Estados Unidos)**.</span><span class="sxs-lookup"><span data-stu-id="dbc70-117">Right-click the Data Flow task, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dbc70-118">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="dbc70-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dbc70-119">Paso 5: Adición y configuración del origen de archivo plano</span><span class="sxs-lookup"><span data-stu-id="dbc70-119">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="dbc70-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbc70-120">See Also</span></span>  
 [<span data-ttu-id="dbc70-121">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="dbc70-121">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
