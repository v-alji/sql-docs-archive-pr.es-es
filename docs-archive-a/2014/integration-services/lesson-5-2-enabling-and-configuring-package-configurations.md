---
title: 'Paso 2: Habilitar y configurar las configuraciones de paquetes | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 005218ab-8dd5-48e9-a185-6bc60cd43a7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a804efcd84ebe563a13f61443fe19096788ca809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670431"
---
# <a name="step-2-enabling-and-configuring-package-configurations"></a><span data-ttu-id="ee4e3-102">Paso 2: Habilitación y configuración de configuraciones de paquete</span><span class="sxs-lookup"><span data-stu-id="ee4e3-102">Step 2: Enabling and Configuring Package Configurations</span></span>
  <span data-ttu-id="ee4e3-103">En esta tarea, convertirá el proyecto al modelo de implementación de paquetes y habilitará las configuraciones de paquetes mediante el Asistente para configuración de paquetes.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-103">In this task, you will convert the project to the Package Deployment Model and enable package configurations using the Package Configuration Wizard.</span></span> <span data-ttu-id="ee4e3-104">Utilizará este asistente para generar un archivo de configuración XML que contiene parámetros de configuración para la propiedad `Directory` del contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-104">You will use this wizard to generate an XML configuration file that contains configuration settings for the `Directory` property of the Foreach Loop container.</span></span> <span data-ttu-id="ee4e3-105">El valor de la propiedad Directory se proporciona a través de una variable nueva de nivel de paquete que puede actualizarse durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-105">The value of the Directory property is supplied by a new package-level variable that you can update at run time.</span></span> <span data-ttu-id="ee4e3-106">Además, rellenará una carpeta nueva de datos de ejemplo que utilizará durante las pruebas.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-106">Additionally, you will populate a new sample data folder to use during testing.</span></span>  
  
### <a name="to-create-a-new-package-level-variable-mapped-to-the-directory-property"></a><span data-ttu-id="ee4e3-107">Para crear una variable nueva de nivel de paquete asignada a la propiedad Directory</span><span class="sxs-lookup"><span data-stu-id="ee4e3-107">To create a new package-level variable mapped to the Directory property</span></span>  
  
1.  <span data-ttu-id="ee4e3-108">Haga clic en el fondo de la pestaña **Flujo de control** del Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee4e3-108">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="ee4e3-109">De este modo se establece en el paquete el ámbito de la variable que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-109">This sets the scope for the variable you will create to the package.</span></span>  
  
2.  <span data-ttu-id="ee4e3-110">En el menú [!INCLUDE[ssIS](../includes/ssis-md.md)] , seleccione **Variables**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-110">On the [!INCLUDE[ssIS](../includes/ssis-md.md)] menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="ee4e3-111">En la ventana **Variables** , haga clic en el icono Agregar variable.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-111">In the **Variables** window, click the Add Variable icon.</span></span>  
  
4.  <span data-ttu-id="ee4e3-112">En el cuadro **Nombre** , escriba **varFolderName**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-112">In the **Name** box, type **varFolderName**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ee4e3-113">Los nombres de variables distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-113">Variable names are case sensitive.</span></span>  
  
5.  <span data-ttu-id="ee4e3-114">Compruebe que en el cuadro **ámbito** se muestra el nombre del paquete, Lección 5.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-114">Verify that the **Scope** box shows the name of the package, Lesson 5.</span></span>  
  
6.  <span data-ttu-id="ee4e3-115">Establezca el valor del cuadro **Tipo de datos** de la variable `varFolderName` en **String**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-115">Set the value of the **Data Type** box of the `varFolderName` variable to **String**.</span></span>  
  
7.  <span data-ttu-id="ee4e3-116">Vuelva a la pestaña **Flujo de control** y haga doble clic en el contenedor **Foreach File in Folder** .</span><span class="sxs-lookup"><span data-stu-id="ee4e3-116">Return to the **Control Flow** tab and double-click the **Foreach File in Folder** container.</span></span>  
  
8.  <span data-ttu-id="ee4e3-117">En la página **Colección** del **Editor de bucles Foreach**, haga clic en **Expresiones** y, después, haga clic en el botón de puntos suspensivos **(…)**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-117">On the **Collection** page of the **Foreach Loop Editor**, click **Expressions**, and then click the ellipsis button **(...)**.</span></span>  
  
9. <span data-ttu-id="ee4e3-118">En el **Editor de expresiones de propiedad**, haga clic en la lista de **propiedades** y seleccione `Directory` .</span><span class="sxs-lookup"><span data-stu-id="ee4e3-118">In the **Property Expressions Editor**, click in the **Property** list, and select `Directory`.</span></span>  
  
10. <span data-ttu-id="ee4e3-119">En el cuadro **expresión** , haga clic en el botón de puntos suspensivos **(...)**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-119">In the **Expression** box, click the ellipsis button **(...)**.</span></span>  
  
11. <span data-ttu-id="ee4e3-120">En el **Generador de expresiones**, expanda la carpeta Variables y arrastre la variable **User:varFolderName** al cuadro **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="ee4e3-120">In the **Expression Builder**, expand the Variables folder, and drag the variable **User::varFolderName** to the **Expression** box.</span></span>  
  
12. <span data-ttu-id="ee4e3-121">Haga clic en **Aceptar** para salir del **Generador de expresiones**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-121">Click **OK** to exit the **Expression Builder**.</span></span>  
  
13. <span data-ttu-id="ee4e3-122">Haga clic en **Aceptar** para salir del **Editor de expresiones de propiedad**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-122">Click **OK** to exit the **Property Expressions Editor**.</span></span>  
  
14. <span data-ttu-id="ee4e3-123">Haga clic en **Aceptar** para salir del **Editor de bucles Foreach**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-123">Click **OK** to exit the **Foreach Loop Editor**.</span></span>  
  
### <a name="to-enable-package-configurations"></a><span data-ttu-id="ee4e3-124">Para habilitar las configuraciones de paquetes</span><span class="sxs-lookup"><span data-stu-id="ee4e3-124">To enable package configurations</span></span>  
  
1.  <span data-ttu-id="ee4e3-125">En el **menú proyecto**, haga clic en **convertir al modelo de implementación de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-125">On the **Project Menu**, click **Convert to Package Deployment Model**.</span></span>  
  
2.  <span data-ttu-id="ee4e3-126">Haga clic en **Aceptar** en el mensaje de advertencia y, una vez completada la conversión, haga clic en **Aceptar** en el cuadro de diálogo **Convertir al modelo de implementación de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="ee4e3-126">Click **OK** on the warning prompt and, once the conversion is complete, click **OK** on the **Convert to Package Deployment Model** dialog.</span></span>  
  
3.  <span data-ttu-id="ee4e3-127">Haga clic en el fondo de la pestaña **Flujo de control** del Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee4e3-127">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
4.  <span data-ttu-id="ee4e3-128">En el menú **SSIS** , haga clic en **Configuraciones de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-128">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="ee4e3-129">En el cuadro de diálogo **Organizador de configuraciones de paquetes** , seleccione **Habilitar configuraciones de paquetes**y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-129">In the **Package Configurations Organizer** dialog box, select **Enable Package Configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="ee4e3-130">En la página de bienvenida del Asistente para la configuración de paquetes, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-130">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
7.  <span data-ttu-id="ee4e3-131">En la página **Seleccionar tipo de configuración** , compruebe que el **Tipo de configuración** está establecido en **Archivo de configuración XML**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-131">On the **Select Configuration Type** page, verify that the **Configuration type** is set to **XML configuration file**.</span></span>  
  
8.  <span data-ttu-id="ee4e3-132">En la página **Seleccionar tipo de configuración** , haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-132">On the **Select Configuration Type** page, click **Browse**.</span></span>  
  
9. <span data-ttu-id="ee4e3-133">De forma predeterminada, el cuadro de diálogo **Seleccionar ubicación del archivo de configuración** se abrirá en la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-133">By default, the **Select Configuration File Location** dialog box will open to the project folder.</span></span>  
  
10. <span data-ttu-id="ee4e3-134">En el cuadro de diálogo **Seleccionar ubicación del archivo de configuración** , escriba **SSISTutorial** en **Nombre de archivo**y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-134">In the **Select Configuration File Location** dialog box, for **File name** type **SSISTutorial**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="ee4e3-135">En la página **Seleccionar tipo de configuración** , haga clic en **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="ee4e3-135">On the **Select Configuration Type** page, click **Next.**</span></span>  
  
12. <span data-ttu-id="ee4e3-136">En la página **seleccionar Propiedades para la exportación** , en el panel **objetos** , expanda **variables**, expanda **varFolderName**, expanda **propiedades**y, a continuación, seleccione **valor**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-136">On the **Select Properties to Export** page, in the **Objects** pane, expand **Variables**, expand **varFolderName**, expand **Properties**, and then select **Value**.</span></span>  
  
13. <span data-ttu-id="ee4e3-137">En la página **Seleccionar propiedades para la exportación** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-137">On the **Select Properties to Export** page, click **Next**.</span></span>  
  
14. <span data-ttu-id="ee4e3-138">En la página **Finalización del asistente** , escriba un nombre para la configuración, por ejemplo, **Configuración del directorio del Tutorial de SSIS**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-138">On the **Completing the Wizard** page, type a configuration name for the configuration, such as **SSIS Tutorial Directory configuration**.</span></span> <span data-ttu-id="ee4e3-139">Este es el nombre de configuración que se muestra en el cuadro de diálogo **Organizador de configuraciones de paquetes** .</span><span class="sxs-lookup"><span data-stu-id="ee4e3-139">This is the configuration name that is displayed in the **Package Configuration Organizer** dialog box.</span></span>  
  
15. <span data-ttu-id="ee4e3-140">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="ee4e3-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="ee4e3-141">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-141">Click **Close**.</span></span>  
  
17. <span data-ttu-id="ee4e3-142">El asistente crea un archivo de configuración denominado SSISTutorial. dtsConfig, que contiene los valores de configuración para el `value` de la variable que, a su vez, establece la `Directory` propiedad del enumerador.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-142">The wizard creates a configuration file, named SSISTutorial.dtsConfig, that contains configuration settings for the `value` of the variable that in turn sets the `Directory` property of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ee4e3-143">Generalmente, un archivo de configuración contiene información compleja sobre las propiedades de un paquete, pero en este tutorial la única información de configuración debería ser</span><span class="sxs-lookup"><span data-stu-id="ee4e3-143">A configuration file typically contains complex information about the package properties, but for this tutorial the only configuration information should be</span></span>  
    > <span data-ttu-id="ee4e3-144"><Configuration ConfiguredType="Property"</span><span class="sxs-lookup"><span data-stu-id="ee4e3-144"><Configuration ConfiguredType="Property"</span></span>  
    > <span data-ttu-id="ee4e3-145">Path = "\Package.Variables [usuario:: varFolderName]. Properties [valor] "ValueType =" cadena "\></span><span class="sxs-lookup"><span data-stu-id="ee4e3-145">Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"\></span></span>  
    >  \<ConfiguredValue>\</ConfiguredValue>  
    > <span data-ttu-id="ee4e3-146">\</Configuration>.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-146">\</Configuration>.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="ee4e3-147">Para crear y rellenar una carpeta nueva de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee4e3-147">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="ee4e3-148">En el explorador de Windows, en el nivel raíz de la unidad (por ejemplo, C: \\ ), cree una nueva carpeta denominada `New Sample Data` .</span><span class="sxs-lookup"><span data-stu-id="ee4e3-148">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named `New Sample Data`.</span></span>  
  
2.  <span data-ttu-id="ee4e3-149">Busque los archivos de ejemplo en su equipo y copie tres de los archivos de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-149">Locate the sample files on your computer and copy three of the files from the folder.</span></span>  
  
3.  <span data-ttu-id="ee4e3-150">En la `New Sample Data` carpeta, pegue los archivos copiados.</span><span class="sxs-lookup"><span data-stu-id="ee4e3-150">In the `New Sample Data` folder, paste the copied files.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ee4e3-151">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="ee4e3-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ee4e3-152">Paso 3: Modificación del valor de configuración de la propiedad Directory</span><span class="sxs-lookup"><span data-stu-id="ee4e3-152">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
  
