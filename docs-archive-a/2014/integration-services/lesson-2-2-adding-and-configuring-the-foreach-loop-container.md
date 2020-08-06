---
title: 'Paso 2: Agregar y configurar el contenedor de bucles Para cada uno | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 88a973cc-0f23-4ecf-adb6-5b06279c2df6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de5e8875c43edda618ccef4839c88c3b84a003cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663583"
---
# <a name="step-2-adding-and-configuring-the-foreach-loop-container"></a><span data-ttu-id="25fb7-102">Paso 2: Adición y configuración del contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="25fb7-102">Step 2: Adding and Configuring the Foreach Loop Container</span></span>
  <span data-ttu-id="25fb7-103">En esta tarea, agregará la capacidad de buscar en una carpeta de archivos planos y aplicará la misma transformación de flujo de datos utilizada en la lección 1 a cada uno de dichos archivos planos.</span><span class="sxs-lookup"><span data-stu-id="25fb7-103">In this task, you will add the ability to loop through a folder of flat files and apply the same data flow transformation used in Lesson 1 to each of those flat files.</span></span> <span data-ttu-id="25fb7-104">Para ello, agregará y configurará un contenedor de bucles Foreach para el flujo de control.</span><span class="sxs-lookup"><span data-stu-id="25fb7-104">You do this by adding and configuring a Foreach Loop container to the control flow.</span></span>  
  
 <span data-ttu-id="25fb7-105">El contenedor de bucles Foreach que agregue debe poder conectarse a cada uno de los archivos planos de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="25fb7-105">The Foreach Loop container that you add must be able to connect to each flat file in the folder.</span></span> <span data-ttu-id="25fb7-106">Puesto que todos los archivos de la carpeta tienen el mismo formato, el contenedor de bucles Foreach puede utilizar el mismo administrador de conexiones de archivos planos para conectarse a cada uno de estos archivos.</span><span class="sxs-lookup"><span data-stu-id="25fb7-106">Because all the files in the folder have the same format, the Foreach Loop container can use the same Flat File connection manager to connect to each of these files.</span></span> <span data-ttu-id="25fb7-107">El administrador de conexiones de archivos planos que el contenedor utilizará es el mismo administrador de conexiones de archivos planos que creó en la lección 1.</span><span class="sxs-lookup"><span data-stu-id="25fb7-107">The Flat File connection manager that the container will use is the same Flat File connection manager that you created in Lesson 1.</span></span>  
  
 <span data-ttu-id="25fb7-108">Actualmente, el administrador de conexiones de archivos planos de la lección 1 se conecta a un único archivo plano específico.</span><span class="sxs-lookup"><span data-stu-id="25fb7-108">Currently, the Flat File connection manager from Lesson 1 connects to only one, specific flat file.</span></span> <span data-ttu-id="25fb7-109">Para conectarse de forma iterativa a cada uno de los archivos planos de la carpeta, deberá configurar el contenedor de bucles Foreach y el administrador de conexiones de archivos planos de este modo:</span><span class="sxs-lookup"><span data-stu-id="25fb7-109">To iteratively connect to each flat file in the folder, you will have to configure both the Foreach Loop container and the Flat File connection manager as follows:</span></span>  
  
-   <span data-ttu-id="25fb7-110">**Contenedor de bucles Foreach:** Asignará el valor enumerado del contenedor a una variable de paquete definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="25fb7-110">**Foreach Loop container:** You will map the enumerated value of the container to a user-defined package variable.</span></span> <span data-ttu-id="25fb7-111">El contenedor utilizará esta variable definida por el usuario para modificar de forma dinámica la propiedad `ConnectionString` del administrador de conexiones de archivos planos y conectar de forma iterativa cada uno de los archivos planos de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="25fb7-111">The container will then use this user-defined variable to dynamically modify the `ConnectionString` property of the Flat File connection manager and iteratively connect to each flat file in the folder.</span></span>  
  
-   <span data-ttu-id="25fb7-112">**Administrador de conexiones de archivos planos:** Modificará el administrador de conexiones creado en la lección 1 mediante una variable definida por el usuario para rellenar la propiedad del administrador de conexiones `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="25fb7-112">**Flat File connection manager:** You will modify the connection manager that was created in Lesson 1 by using a user-defined variable to populate the connection manager's `ConnectionString` property.</span></span>  
  
 <span data-ttu-id="25fb7-113">En los procedimientos de esta tarea se muestra cómo crear y modificar el contenedor de bucles Foreach para utilizar una variable de paquete definida por el usuario y agregar la tarea de flujo de datos al bucle.</span><span class="sxs-lookup"><span data-stu-id="25fb7-113">The procedures in this task show you how to create and modify the Foreach Loop container to use a user-defined package variable and to add the data flow task to the loop.</span></span> <span data-ttu-id="25fb7-114">Aprenderá a modificar el administrador de conexiones de archivos planos para utilizar una variable definida por el usuario en la siguiente tarea.</span><span class="sxs-lookup"><span data-stu-id="25fb7-114">You will learn how to modify the Flat File connection manager to use a user-defined variable in the next task.</span></span>  
  
 <span data-ttu-id="25fb7-115">Una vez realizadas estas modificaciones en el paquete, cuando éste se ejecute, el contenedor de bucles Foreach se iterará en la colección de archivos de la carpeta Datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="25fb7-115">After you have made these modifications to the package, when the package is run, the Foreach Loop Container will iterate through the collection of files in the Sample Data folder.</span></span> <span data-ttu-id="25fb7-116">Cada vez que se encuentre un archivo que coincida con los criterios, el contenedor de bucles Foreach llenará la variable definida por el usuario con el nombre de archivo, asignará la variable definida por el usuario a la propiedad `ConnectionString` del administrador de conexiones de archivos planos Sample Currency Data y, a continuación, ejecutará el flujo de datos en dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="25fb7-116">Each time a file is found that matches the criteria, the Foreach Loop Container will populate the user-defined variable with the file name, map the user-defined variable to the `ConnectionString` property of the Sample Currency Data Flat File connection manager, and then run the data flow against that file.</span></span> <span data-ttu-id="25fb7-117">Por consiguiente, en cada iteración del bucle Foreach la tarea de flujo de datos utilizará un archivo plano distinto.</span><span class="sxs-lookup"><span data-stu-id="25fb7-117">Therefore, in each iteration of the Foreach Loop the Data Flow task will consume a different flat file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25fb7-118">Puesto que [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separa el flujo de control del flujo de datos, los bucles que agregue al flujo de control no precisarán ninguna modificación en el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="25fb7-118">Because [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates control flow from data flow, any looping that you add to the control flow will not require modification to the data flow.</span></span> <span data-ttu-id="25fb7-119">Por consiguiente, no es necesario modificar el flujo de datos creado en la lección 1.</span><span class="sxs-lookup"><span data-stu-id="25fb7-119">Therefore, the data flow that you created in Lesson 1 does not have to be changed.</span></span>  
  
### <a name="to-add-a-foreach-loop-container"></a><span data-ttu-id="25fb7-120">Para agregar un contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="25fb7-120">To add a Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="25fb7-121">En **SQL Server Data Tools**, haga clic en la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="25fb7-121">In **SQL Server Data Tools**, click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="25fb7-122">En el **Cuadro de herramientas de SSIS**, expanda **Contenedores**y arrastre un **Contenedor de bucles Foreach** a la superficie de diseño de la pestaña **Flujo de control** .</span><span class="sxs-lookup"><span data-stu-id="25fb7-122">In the **SSIS Toolbox**, expand **Containers**, and then drag a **Foreach Loop Container** onto the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="25fb7-123">Haga clic con el botón derecho en el **Contenedor de bucles Foreach** que acaba de agregar y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-123">Right-click the newly added **Foreach Loop Container** and select **Edit**.</span></span>  
  
4.  <span data-ttu-id="25fb7-124">En el cuadro de diálogo **Editor de bucles foreach** , en la página **General** , en **nombre**, escriba `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="25fb7-124">In the **Foreach Loop Editor** dialog box, on the **General** page, for **Name**, enter `Foreach File in Folder`.</span></span> <span data-ttu-id="25fb7-125">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="25fb7-126">Haga clic con el botón secundario en el contenedor de bucles foreach, haga clic en **propiedades**y, en el ventana Propiedades, compruebe que la `LocaleID` propiedad está establecida en **Inglés (Estados Unidos)**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-126">Right-click the Foreach Loop container, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
### <a name="to-configure-the-enumerator-for-the-foreach-loop-container"></a><span data-ttu-id="25fb7-127">Para configurar el enumerador para el contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="25fb7-127">To configure the enumerator for the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="25fb7-128">Haga doble clic en Foreach File in Folder para volver a abrir el **Editor de bucles Foreach**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-128">Double-click Foreach File in Folder to reopen the **Foreach Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="25fb7-129">Haga clic en **Colección**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-129">Click **Collection**.</span></span>  
  
3.  <span data-ttu-id="25fb7-130">En la página **Colección** , seleccione **Enumerador de archivos Foreach**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-130">On the **Collection** page, select **Foreach File Enumerator**.</span></span>  
  
4.  <span data-ttu-id="25fb7-131">En el grupo **Configuración de enumerador** , haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-131">In the **Enumerator configuration** group, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="25fb7-132">En el cuadro de diálogo **Buscar carpeta** , busque la carpeta del equipo que contenga los archivos Currency_\*.txt.</span><span class="sxs-lookup"><span data-stu-id="25fb7-132">In the **Browse for Folder** dialog box, locate the folder on your machine that contains the Currency_\*.txt files.</span></span>  
  
     <span data-ttu-id="25fb7-133">Estos datos de ejemplo se incluyen con los paquetes de lecciones de [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25fb7-133">This sample data is included with the [!INCLUDE[ssIS](../includes/ssis-md.md)] lesson packages.</span></span> <span data-ttu-id="25fb7-134">Para descargar los datos de ejemplo y los paquetes de lecciones, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="25fb7-134">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="25fb7-135">Navegue a los [ejemplos del producto Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="25fb7-135">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="25fb7-136">Haga clic en la pestaña **descargas** .</span><span class="sxs-lookup"><span data-stu-id="25fb7-136">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="25fb7-137">Haga clic en el hipervínculo " https://msftisprodsamples.codeplex.com/downloads/get/578097 " SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip archivo.</span><span class="sxs-lookup"><span data-stu-id="25fb7-137">Click the  HYPERLINK "https://msftisprodsamples.codeplex.com/downloads/get/578097" SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
6.  <span data-ttu-id="25fb7-138">En el cuadro **Archivos**, escriba **Currency_\*.txt**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-138">In the **Files** box, type **Currency_\*.txt**.</span></span>  
  
### <a name="to-map-the-enumerator-to-a-user-defined-variable"></a><span data-ttu-id="25fb7-139">Para asignar el enumerador a una variable definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="25fb7-139">To map the enumerator to a user-defined variable</span></span>  
  
1.  <span data-ttu-id="25fb7-140">Haga clic en **Asignaciones de variables**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-140">Click **Variable Mappings**.</span></span>  
  
2.  <span data-ttu-id="25fb7-141">En la página **asignaciones de variables** , en la columna **variable** , haga clic en la celda vacía y seleccione **\<New Variable...>** .</span><span class="sxs-lookup"><span data-stu-id="25fb7-141">On the **Variable Mappings** page, in the **Variable** column, click the empty cell and select **\<New Variable...>**.</span></span>  
  
3.  <span data-ttu-id="25fb7-142">En el cuadro de diálogo **Agregar variable** , en **nombre**, escriba `varFileName` .</span><span class="sxs-lookup"><span data-stu-id="25fb7-142">In the **Add Variable** dialog box, for **Name**, type `varFileName`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="25fb7-143">Los nombres de variables distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="25fb7-143">Variable names are case sensitive.</span></span>  
  
4.  <span data-ttu-id="25fb7-144">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="25fb7-144">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="25fb7-145">Haga clic de nuevo en **Aceptar** para salir del cuadro de diálogo **Editor de bucles Foreach** .</span><span class="sxs-lookup"><span data-stu-id="25fb7-145">Click **OK** again to exit the **Foreach Loop Editor** dialog box.</span></span>  
  
### <a name="to-add-the-data-flow-task-to-the-loop"></a><span data-ttu-id="25fb7-146">Para agregar la tarea de flujo de datos al bucle</span><span class="sxs-lookup"><span data-stu-id="25fb7-146">To add the data flow task to the loop</span></span>  
  
-   <span data-ttu-id="25fb7-147">Arrastre la tarea de flujo de datos **Extract Sample Currency Data** al contenedor de bucles foreach cuyo nombre ha cambiado `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="25fb7-147">Drag the **Extract Sample Currency Data** data flow task onto the Foreach Loop container now renamed `Foreach File in Folder`.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="25fb7-148">Tarea de la siguiente lección</span><span class="sxs-lookup"><span data-stu-id="25fb7-148">Next Lesson Task</span></span>  
 [<span data-ttu-id="25fb7-149">Paso 3: Modificación del Administrador de conexiones de archivos planos</span><span class="sxs-lookup"><span data-stu-id="25fb7-149">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
## <a name="see-also"></a><span data-ttu-id="25fb7-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25fb7-150">See Also</span></span>  
 <span data-ttu-id="25fb7-151">[Configurar un contenedor de bucles foreach](control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="25fb7-151">[Configure a Foreach Loop Container](control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="25fb7-152">Usar variables en paquetes</span><span class="sxs-lookup"><span data-stu-id="25fb7-152">Use Variables in Packages</span></span>](use-variables-in-packages.md)  
  
