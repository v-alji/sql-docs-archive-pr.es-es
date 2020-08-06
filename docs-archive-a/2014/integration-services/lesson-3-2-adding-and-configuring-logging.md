---
title: 'Paso 2: Agregar y configurar el registro | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56105f3f-e500-4669-8c8e-acf434527727
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f2cdce6f34a19e22830d357d20f5d99cff8c14f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745899"
---
# <a name="step-2-adding-and-configuring-logging"></a><span data-ttu-id="ffd4e-102">Paso 2: Adición y configuración de registro</span><span class="sxs-lookup"><span data-stu-id="ffd4e-102">Step 2: Adding and Configuring Logging</span></span>
  <span data-ttu-id="ffd4e-103">En esta tarea, habilitará el registro del flujo de datos del paquete Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-103">In this task, you will enable logging for the data flow in the Lesson 3.dtsx package.</span></span> <span data-ttu-id="ffd4e-104">A continuación, configurará un proveedor de registro de archivos de texto para registrar los eventos PipelineExecutionPlan y PipelineExecuteTrees.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-104">Then, you will configure a Text File log provider to log the PipelineExecutionPlan and PipelineExecuteTrees events.</span></span> <span data-ttu-id="ffd4e-105">El proveedor de registro de archivos de texto crea registros que pueden verse y transportarse con facilidad.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-105">The Text Files log provider creates logs that are easy to view and easily transportable.</span></span> <span data-ttu-id="ffd4e-106">La sencillez de estos archivos de registro hace que sean especialmente útiles durante la fase de prueba básica de un paquete.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-106">The simplicity of these log files makes these files especially useful during the basic testing phase of a package.</span></span> <span data-ttu-id="ffd4e-107">También puede ver las entradas del archivo de registro en la ventana Registrar eventos del Diseñador de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffd4e-107">You can also view the log entries in the Log Events window of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
### <a name="to-add-logging-to-the-package"></a><span data-ttu-id="ffd4e-108">Para agregar el registro al paquete</span><span class="sxs-lookup"><span data-stu-id="ffd4e-108">To add logging to the package</span></span>  
  
1.  <span data-ttu-id="ffd4e-109">En el menú **SSIS** , haga clic en **Registro**.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-109">On the **SSIS** menu, click **Logging**.</span></span>  
  
2.  <span data-ttu-id="ffd4e-110">En el cuadro de diálogo **Configurar registros de SSIS** , asegúrese de que en el panel **Contenedores** el objeto situado en la posición superior, que representa el paquete de la lección 3, está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-110">In the **Configure SSIS Logs** dialog box, in the **Containers** pane, make sure that the topmost object, which represents the Lesson 3 package, is selected.</span></span>  
  
3.  <span data-ttu-id="ffd4e-111">En la pestaña **Proveedores y registros** , en el cuadro **Tipo de proveedor** , seleccione **Proveedor de registro SSIS para archivos de texto**y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-111">On the **Providers and Logs** tab, in the **Provider type** box, select **SSIS log provider for Text files**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="ffd4e-112">Integration Services agrega un nuevo proveedor de registro de archivos de texto al paquete con el nombre predeterminado **proveedor de registro SSIS para archivos de texto**.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-112">Integration Services adds a new Text File log provider to the package with the default name **SSIS log provider for text files**.</span></span> <span data-ttu-id="ffd4e-113">Ahora puede configurar el nuevo proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-113">You can now configure the new log provider.</span></span>  
  
4.  <span data-ttu-id="ffd4e-114">En la columna **nombre** , escriba `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="ffd4e-114">In the **Name** column, type `Lesson 3 Log File`.</span></span>  
  
5.  <span data-ttu-id="ffd4e-115">Si lo desea, modifique el campo **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-115">Optionally, modify the **Description**.</span></span>  
  
6.  <span data-ttu-id="ffd4e-116">En la columna **Configuración** haga clic en **\<New Connection>** para especificar el destino en el que se escribe la información de registro.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-116">In the **Configuration** column, click **\<New Connection>** to specify the destination to which the log information is written.</span></span>  
  
     <span data-ttu-id="ffd4e-117">En el cuadro de diálogo **Editor del administrador de conexiones de archivos** , en **Tipo de uso**, seleccione **Crear archivo**y, a continuación, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-117">In the **File Connection Manager Editor** dialog box, for **Usage type**, select **Create file**, and then click **Browse**.</span></span> <span data-ttu-id="ffd4e-118">De forma predeterminada, el cuadro de diálogo **Seleccionar archivo** abre la carpeta del proyecto, pero puede guardar la información de registro en cualquier ubicación.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-118">By default, the **Select File** dialog box opens the project folder, but you can save log information to any location.</span></span>  
  
7.  <span data-ttu-id="ffd4e-119">En el cuadro de diálogo **Seleccionar archivo** , en el cuadro **nombre de archivo** `TutorialLog.log` , escriba y haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-119">In the **Select File** dialog box, in the **File name** box type `TutorialLog.log`, and click **Open**.</span></span>  
  
8.  <span data-ttu-id="ffd4e-120">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Editor del administrador de conexiones de archivos** .</span><span class="sxs-lookup"><span data-stu-id="ffd4e-120">Click **OK** to close the **File Connection Manager Editor** dialog box.</span></span>  
  
9. <span data-ttu-id="ffd4e-121">En el panel **Contenedores** , expanda todos los nodos de la jerarquía del contenedor de paquetes y, a continuación, desactive todas las casillas, incluida **Extract Sample Currency Data** .</span><span class="sxs-lookup"><span data-stu-id="ffd4e-121">In the **Containers** pane, expand all nodes of the package container hierarchy, and then clear all check boxes, including the **Extract Sample Currency Data** check box.</span></span> <span data-ttu-id="ffd4e-122">Ahora, active la casilla **Extract Sample Currency Data** para obtener solo los eventos de este nodo.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-122">Now select the check box for **Extract Sample Currency Data** to get only the events for this node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ffd4e-123"> Si la casilla **Extract Sample Currency Data** está atenuada en lugar de activada, la tarea utiliza la configuración de registro del contenedor primario y no se pueden habilitar los eventos de registro específicos de la tarea.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-123">If the state of the **Extract Sample Currency Data** check box is dimmed instead of selected, the task uses the log settings of the parent container and you cannot enable the log events that are specific to the task.</span></span>  
  
10. <span data-ttu-id="ffd4e-124">En la columna **Eventos** de la pestaña **Detalles** , seleccione los eventos **PipelineExecutionPlan** y **PipelineExecutionTrees** .</span><span class="sxs-lookup"><span data-stu-id="ffd4e-124">On the **Details** tab, in the **Events** column, select the **PipelineExecutionPlan** and **PipelineExecutionTrees** events.</span></span>  
  
11. <span data-ttu-id="ffd4e-125">Haga clic en **Avanzadas** para revisar los detalles que el proveedor de registro escribirá en el registro para cada evento.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-125">Click **Advanced** to review the details that the log provider will write to the log for each event.</span></span> <span data-ttu-id="ffd4e-126">De forma predeterminada, todas las categorías de información se seleccionan automáticamente para los eventos que se especifiquen.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-126">By default, all information categories are automatically selected for the events you specify.</span></span>  
  
12. <span data-ttu-id="ffd4e-127">Haga clic en **Básicas** para ocultar las categorías de información.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-127">Click **Basic** to hide the information categories.</span></span>  
  
13. <span data-ttu-id="ffd4e-128">En la pestaña **proveedor y registros** , en la columna **nombre** , seleccione `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="ffd4e-128">On the **Provider and Logs** tab, in the **Name** column, select `Lesson 3 Log File`.</span></span> <span data-ttu-id="ffd4e-129">Una vez que haya creado un proveedor de registro para el paquete, si lo desea, puede anular su selección para desactivar temporalmente el registro, sin tener que eliminar un proveedor de registro y crearlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-129">Once you have created a log provider for your package, you can optionally deselect it to temporarily turn off logging, without having to delete and re-create a log provider.</span></span>  
  
14. <span data-ttu-id="ffd4e-130">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffd4e-130">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ffd4e-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ffd4e-131">Next Steps</span></span>  
 [<span data-ttu-id="ffd4e-132">Paso 3: Prueba del paquete del tutorial de la lección 3</span><span class="sxs-lookup"><span data-stu-id="ffd4e-132">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
  
