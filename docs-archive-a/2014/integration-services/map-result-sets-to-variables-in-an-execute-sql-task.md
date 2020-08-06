---
title: Asignar conjuntos de resultados a variables en una tarea ejecutar SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- result sets [Integration Services]
- mapping result sets to variables [Integration Services]
- variables [Integration Services], mapping result sets to
ms.assetid: f76738b6-dc75-4ff9-a3dd-8b083d8e410e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 124982a32aa9987d3dc573c732be4db4d41e8346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672157"
---
# <a name="map-result-sets-to-variables-in-an-execute-sql-task"></a><span data-ttu-id="b4ecd-102">Asignar conjuntos de resultados a variables en una tarea Ejecutar SQL</span><span class="sxs-lookup"><span data-stu-id="b4ecd-102">Map Result Sets to Variables in an Execute SQL Task</span></span>
  <span data-ttu-id="b4ecd-103">Este tema describe cómo crear una asignación entre un conjunto de resultados y una variable en una tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-103">This topic describes how to create a mapping between a result set and a variable in an Execute SQL task.</span></span> <span data-ttu-id="b4ecd-104">La asignación de un conjunto de resultados a una variable hace que el conjunto de resultados esté disponible para otros elementos del paquete.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-104">Mapping a result set to a variable makes the result set available to other elements in the package.</span></span> <span data-ttu-id="b4ecd-105">Por ejemplo, un script de la tarea Script puede leer la variable y luego utilizar los valores del conjunto de resultados, o un origen XML puede consumir el conjunto de resultados almacenados en una variable.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-105">For example, a script in a Script task can read the variable and then use the values from the result set or an XML source can consume the result set stored in a variable.</span></span> <span data-ttu-id="b4ecd-106">Si un paquete primario genera el conjunto de resultados, este conjunto de resultados se puede poner a disposición de un paquete secundario llamado por la tarea Ejecutar paquete asignando el conjunto de resultados a una variable del paquete primario, y luego creando una configuración de variable de paquete primario en el paquete secundario a fin de almacenar el valor de la variable primaria.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-106">If the result set is generated by a parent package, the result set can be made available to a child package called by an Execute Package task by mapping the result set to a variable in the parent package, and then creating a parent package variable configuration in the child package to store the parent variable value.</span></span>  
  
 <span data-ttu-id="b4ecd-107">Para obtener descripciones de los diferentes tipos de conjuntos de resultados y los tipos de datos de variables que se pueden asignar a conjuntos de resultados, vea [Conjuntos de resultados en la tarea Ejecutar SQL](control-flow/execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="b4ecd-107">For descriptions of the different types of result sets and the variable data types that you can map to result sets, see [Result Sets in the Execute SQL Task](control-flow/execute-sql-task.md).</span></span>  
  
### <a name="to-map-a-result-set-to-a-variable"></a><span data-ttu-id="b4ecd-108">Para asignar un conjunto de resultados a una variable</span><span class="sxs-lookup"><span data-stu-id="b4ecd-108">To map a result set to a variable</span></span>  
  
1.  <span data-ttu-id="b4ecd-109">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b4ecd-110">En el **Explorador de soluciones**, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-110">In **Solution Explorer**, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b4ecd-111">Haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="b4ecd-111">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="b4ecd-112">Si el paquete no incluye en ese momento una tarea Ejecutar SQL, agregue una al flujo de control del paquete.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-112">If the package does not already include an Execute SQL task, add one to the control flow of the package.</span></span> <span data-ttu-id="b4ecd-113">Para obtener más información, vea [Agregar o eliminar una tarea o un contenedor en un flujo de control](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="b4ecd-113">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="b4ecd-114">.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-114">.</span></span>  
  
5.  <span data-ttu-id="b4ecd-115">Haga doble clic en la tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-115">Double-click the Execute SQL task.</span></span>  
  
6.  <span data-ttu-id="b4ecd-116">En el cuadro de diálogo **Editor de la tarea Ejecutar SQL** , en la página **General** , seleccione el tipo de conjunto de resultados **Fila única**, **Conjunto de resultados completo**o **XML** .</span><span class="sxs-lookup"><span data-stu-id="b4ecd-116">In the **Execute SQL Task Editor** dialog box, on the **General** page, select the **Single row**, **Full result set**, or **XML** result set type.</span></span>  
  
     <span data-ttu-id="b4ecd-117">Para obtener descripciones de los distintos conjuntos de resultados, vea [Conjuntos de resultados en la tarea Ejecutar SQL](result-sets-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="b4ecd-117">For descriptions of the different result sets, see [Result Sets in the Execute SQL Task](result-sets-in-the-execute-sql-task.md)</span></span>  
  
7.  <span data-ttu-id="b4ecd-118">Haga clic en **Conjunto de resultados**.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-118">Click **Result Set**.</span></span>  
  
8.  <span data-ttu-id="b4ecd-119">Para agregar una asignación de conjunto de resultados, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-119">To add a result set mapping, click **Add**.</span></span>  
  
9. <span data-ttu-id="b4ecd-120">En la lista **Nombre de variable** , seleccione una variable o cree una variable nueva.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-120">From the **Variables Name** list, select a variable or create a new variable.</span></span> <span data-ttu-id="b4ecd-121">Para más información, vea [Agregar, eliminar, cambiar el ámbito de la variable definida por el usuario en un paquete](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="b4ecd-121">For more information, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
     <span data-ttu-id="b4ecd-122">Para obtener descripciones de los tipos de datos de variables que se pueden asignar a los distintos conjuntos de resultados, vea [Conjuntos de resultados en la tarea Ejecutar SQL](result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="b4ecd-122">For descriptions of the variable data types that you can map to the different result sets, see [Result Sets in the Execute SQL Task](result-sets-in-the-execute-sql-task.md).</span></span>  
  
     <span data-ttu-id="b4ecd-123">Para obtener información sobre cómo asignar una variable a una sola columna y cómo asignar varias variables a varias columnas, vea la sección **Llenar una variable con un conjunto de resultados** de [Result Sets in the Execute SQL Task](control-flow/execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="b4ecd-123">For information on how to map a variable to a single column and to map multiple variables to multiple columns, see the **Populating a Variable with a Result Set** section in [Result Sets in the Execute SQL Task](control-flow/execute-sql-task.md).</span></span>  
  
10. <span data-ttu-id="b4ecd-124">En la lista **Nombre del resultado** , opcionalmente, modifique el nombre del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-124">In the **Result Name** list, optionally, modify the name of the result set.</span></span>  
  
     <span data-ttu-id="b4ecd-125">En general, puede usar el nombre de columna como nombre del conjunto de resultados, o puede usar la posición ordinal de la columna en la lista de columnas como conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-125">In general, you can use the column name as the result set name, or you can use the ordinal position of the column in the column list as the result set.</span></span> <span data-ttu-id="b4ecd-126">La posibilidad de usar un nombre de columna como el nombre del conjunto de resultados depende del proveedor para el que se haya configurado la tarea.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-126">The ability to use a column name as the result set name depends on the provider that the task is configured to use.</span></span> <span data-ttu-id="b4ecd-127">No todos los proveedores ponen los nombres de columna a disposición.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-127">Not all providers make column names available.</span></span>  
  
11. <span data-ttu-id="b4ecd-128">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4ecd-128">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ecd-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4ecd-129">See Also</span></span>  
 <span data-ttu-id="b4ecd-130">[Tarea ejecutar SQL](control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="b4ecd-130">[Execute SQL Task](control-flow/execute-sql-task.md) </span></span>  
 <span data-ttu-id="b4ecd-131">[Conjuntos de resultados en la tarea ejecutar SQL](result-sets-in-the-execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="b4ecd-131">[Result Sets in the Execute SQL Task](result-sets-in-the-execute-sql-task.md) </span></span>  
 <span data-ttu-id="b4ecd-132">[Tarea ejecutar paquete](control-flow/execute-package-task.md) </span><span class="sxs-lookup"><span data-stu-id="b4ecd-132">[Execute Package Task](control-flow/execute-package-task.md) </span></span>  
 <span data-ttu-id="b4ecd-133">[Configuraciones de paquetes](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="b4ecd-133">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="b4ecd-134">[Crear configuraciones de paquetes](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="b4ecd-134">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 <span data-ttu-id="b4ecd-135">[Usar los valores de variables y parámetros en un paquete secundario](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md) </span><span class="sxs-lookup"><span data-stu-id="b4ecd-135">[Use the Values of Variables and Parameters in a Child Package](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md) </span></span>  
 [<span data-ttu-id="b4ecd-136">Variables de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b4ecd-136">Integration Services &#40;SSIS&#41; Variables</span></span>](integration-services-ssis-variables.md)  
  
  