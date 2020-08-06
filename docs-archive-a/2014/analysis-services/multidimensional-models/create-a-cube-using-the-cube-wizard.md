---
title: Crear un cubo con el Asistente para cubos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], creating
ms.assetid: d46d659c-3a4e-4364-94ac-f5eb6ba0ec25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 441c296c0fd71b2a9c2b8332743da6224839a471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748362"
---
# <a name="create-a-cube-using-the-cube-wizard"></a><span data-ttu-id="dbb30-102">Crear un cubo con el Asistente para cubos</span><span class="sxs-lookup"><span data-stu-id="dbb30-102">Create a Cube Using the Cube Wizard</span></span>
  <span data-ttu-id="dbb30-103">Puede crear un nuevo cubo usando el Asistente para cubos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dbb30-103">You can create a new cube by using the Cube Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-cube"></a><span data-ttu-id="dbb30-104">Para crear un nuevo cubo</span><span class="sxs-lookup"><span data-stu-id="dbb30-104">To create a new cube</span></span>  
  
1.  <span data-ttu-id="dbb30-105">En **Explorador de soluciones**, haga clic con el botón secundario en **cubos**y, a continuación, haga clic en **nuevo cubo**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-105">In **Solution Explorer**, right-click **Cubes**, and then click **New Cube**.</span></span>  
  
2.  <span data-ttu-id="dbb30-106">En la página **Seleccionar método de creación** del Asistente para cubos, active la opción **Usar tablas existentes**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-106">On the **Select Creation Method** page of the Cube Wizard, select **Use existing tables**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbb30-107">Es posible que tenga que crear un cubo sin que sea necesario usar tablas existentes.</span><span class="sxs-lookup"><span data-stu-id="dbb30-107">You might occasionally have to create a cube without using existing tables.</span></span> <span data-ttu-id="dbb30-108">Para crear un cubo vacío, seleccione **Crear un cubo vacío**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-108">To create an empty cube, select **Create an empty cube**.</span></span> <span data-ttu-id="dbb30-109">Para generar tablas, seleccione **Generar tablas en el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-109">To generate tables, select **Generate tables in the data source**.</span></span>  
  
3.  <span data-ttu-id="dbb30-110">En la página **Seleccionar tablas de grupos de medida** , realice los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dbb30-110">On the **Select Measure Group Tables** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="dbb30-111">En la lista **Vista del origen de datos** , seleccione una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="dbb30-111">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="dbb30-112">En la lista **Tablas de grupos de medida** , seleccione las tablas que se van a usar para crear grupos de medida.</span><span class="sxs-lookup"><span data-stu-id="dbb30-112">In the **Measure group tables** list, select the tables that will be used to create measure groups.</span></span>  
  
    3.  <span data-ttu-id="dbb30-113">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-113">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="dbb30-114">En la página **Seleccionar medidas** , seleccione las medidas que desee incluir en el cubo y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-114">On the **Select Measures** page, select the measures that you want to include in the cube, and then click **Next**.</span></span>  
  
     <span data-ttu-id="dbb30-115">Si lo desea, puede cambiar los nombres de las medidas y de los grupos de medida.</span><span class="sxs-lookup"><span data-stu-id="dbb30-115">Optionally, you can change the names of the measures and measure groups.</span></span>  
  
5.  <span data-ttu-id="dbb30-116">En la página **Seleccionar dimensiones existentes** , seleccione las dimensiones existentes que se incluirán en el cubo y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-116">On the **Select Existing Dimensions** page, select the existing dimensions to include in the cube, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbb30-117"> La página **Seleccionar dimensiones existentes** aparece cuando existen dimensiones en la base de datos de cualquiera de los grupos de medida seleccionados.</span><span class="sxs-lookup"><span data-stu-id="dbb30-117">The **Select Existing Dimensions** page appears if dimensions already exist in the database for any of the selected measure groups.</span></span>  
  
6.  <span data-ttu-id="dbb30-118">En la página **Seleccionar nuevas dimensiones** , seleccione las nuevas dimensiones que se van a crear y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-118">On the **Select New Dimensions** page, select the new dimensions to create, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbb30-119"> La página **Seleccionar nuevas dimensiones** se muestra cuando cualquier tabla es un buen candidato para las tablas de dimensiones y las dimensiones existentes no utilizan aun las tablas.</span><span class="sxs-lookup"><span data-stu-id="dbb30-119">The **Select New Dimensions** page appears if any tables would be good candidates for dimension tables, and the tables have not already been used by existing dimensions.</span></span>  
  
7.  <span data-ttu-id="dbb30-120">En la página **Seleccionar claves de dimensiones ausentes** , seleccione una clave para la dimensión y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-120">On the **Select Missing Dimension Keys** page, select a key for the dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbb30-121"> La página **Seleccionar claves de dimensiones ausentes** se muestra cuando no se ha definido una clave para alguna de las tablas de dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="dbb30-121">The **Select Missing Dimension Keys** page appears if any of the dimension tables that you specified do not have a key defined.</span></span>  
  
8.  <span data-ttu-id="dbb30-122">En la página **Finalización del asistente** , escriba un nombre para el nuevo cubo y revise la estructura del cubo.</span><span class="sxs-lookup"><span data-stu-id="dbb30-122">On the **Completing the Wizard** page, enter a name for the new cube and review the cube structure.</span></span> <span data-ttu-id="dbb30-123">Si desea realizar modificaciones, haga clic **Atrás**; de lo contrario, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="dbb30-123">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dbb30-124">El Diseñador de cubos se puede usar cuando el Asistente para cubos haya completado la configuración del cubo.</span><span class="sxs-lookup"><span data-stu-id="dbb30-124">You can use Cube Designer after you complete the Cube Wizard to configure the cube.</span></span> <span data-ttu-id="dbb30-125">Además, puede usar el Diseñador de dimensiones para agregar, quitar y configurar atributos y jerarquías de las dimensiones que haya creado.</span><span class="sxs-lookup"><span data-stu-id="dbb30-125">You can also use Dimension Designer to add, remove, and configure attributes and hierarchies in the dimensions that you created.</span></span>  
  
  
