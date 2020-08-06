---
title: Crear nuevo InfoObject | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3587a633-1c0b-4d63-a22a-6b2b93923c3a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 022f2d1e3fe10ae037ea379a02a18845b3a36107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676608"
---
# <a name="create-new-infoobject"></a><span data-ttu-id="a436f-102">Crear nuevo InfoObject</span><span class="sxs-lookup"><span data-stu-id="a436f-102">Create New InfoObject</span></span>
  <span data-ttu-id="a436f-103">Use el cuadro de diálogo **Crear nuevo InfoObject** para crear un nuevo InfoObject en el sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a436f-103">Use the **Create New InfoObject** dialog box to create a new InfoObject in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="a436f-104">Puede abrir el cuadro de diálogo **Crear InfoObject** desde la página **Administrador de conexiones** del **Editor de destino de SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="a436f-104">You can open the **Create InfoObject** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="a436f-105">Para más información acerca del destino de SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a436f-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a436f-106">La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="a436f-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a436f-107">Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.</span><span class="sxs-lookup"><span data-stu-id="a436f-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a436f-108">**Para abrir el cuadro de diálogo Crear nuevo InfoObject**</span><span class="sxs-lookup"><span data-stu-id="a436f-108">**To open the Create New InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="a436f-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a436f-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="a436f-110">En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a436f-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="a436f-111">En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.</span><span class="sxs-lookup"><span data-stu-id="a436f-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="a436f-112">En la página **Administrador de conexiones** , en el cuadro del grupo **Crear objetos de SAP BW** , lleve a cabo uno de los siguientes pasos para crear un InfoObject:</span><span class="sxs-lookup"><span data-stu-id="a436f-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, do one of the following steps to create an InfoObject:</span></span>  
  
    1.  <span data-ttu-id="a436f-113">Para crear un InfoObject directamente, seleccione **InfoObject**y haga clic en **Crear** para abrir el cuadro de diálogo **Crear nuevo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a436f-113">To create an InfoObject directly, select **InfoObject**, and then click **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
    2.  <span data-ttu-id="a436f-114">Para crear un InfoObject mientras crea un InfoCube, seleccione **InfoCube**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a436f-114">To create an InfoObject while creating an InfoCube, select **InfoCube**, and then click **Create**.</span></span> <span data-ttu-id="a436f-115">En el cuadro de diálogo **Crear InfoCube para los datos de transacción** , en la columna **IObject** para una de las filas en la lista, seleccione **Crear** para abrir el cuadro de diálogo **Crear nuevo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a436f-115">In the **Create InfoCube for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a436f-116">Cada fila de la tabla representa una columna en el flujo de datos del paquete.</span><span class="sxs-lookup"><span data-stu-id="a436f-116">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="a436f-117">Para crear un InfoObject mientras crea un InfoSource para los datos de transacción, seleccione **InfoSource**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a436f-117">To create an InfoObject while creating an InfoSouce for transactional data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="a436f-118">En el cuadro de diálogo **Crear InfoSource** , seleccione **Datos transaccionales**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a436f-118">In the **Create InfoSource** dialog box, select **Transaction Data**, and then click **OK**.</span></span> <span data-ttu-id="a436f-119">En el cuadro de diálogo **Crear InfoSource para los datos de transacción** , en la columna **IObject** para una de las filas en la lista, seleccione **Crear** para abrir el cuadro de diálogo **Crear nuevo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a436f-119">In the **Create InfoSource for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a436f-120">Cada fila de la tabla representa una columna en el flujo de datos del paquete.</span><span class="sxs-lookup"><span data-stu-id="a436f-120">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    4.  <span data-ttu-id="a436f-121">Para crear un InfoObject mientras crea un InfoSource para los datos maestros, seleccione **InfoSource**y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a436f-121">To create an InfoObject while creating an InfoSource for master data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="a436f-122">En el cuadro de diálogo **Crear InfoSource** , seleccione **Datos maestros**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a436f-122">In the **Create InfoSource** dialog box, select **Master Data**, and then click **OK**.</span></span> <span data-ttu-id="a436f-123">En el cuadro de diálogo **Crear InfoSource para datos maestros** , haga clic en **Nuevo** para abrir el cuadro de diálogo **Crear nuevo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a436f-123">In the **Create InfoSource for Master Data** dialog box, click **New** to open the **Create New InfoObject** dialog box.</span></span>  
  
 <span data-ttu-id="a436f-124">También puede abrir el cuadro de diálogo **Crear nuevo InfoObject** si hace clic en **Nuevo** en la sección **Atributos** del cuadro de diálogo **Crear nuevo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="a436f-124">You can also open the **Create New InfoObject** dialog box by clicking **New** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="a436f-125">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="a436f-125">General Options</span></span>  
 <span data-ttu-id="a436f-126">**Característica**</span><span class="sxs-lookup"><span data-stu-id="a436f-126">**Characteristic**</span></span>  
 <span data-ttu-id="a436f-127">Cree un InfoObject que represente datos de dimensión.</span><span class="sxs-lookup"><span data-stu-id="a436f-127">Create an InfoObject that represents dimension data.</span></span>  
  
 <span data-ttu-id="a436f-128">**Cifra clave**</span><span class="sxs-lookup"><span data-stu-id="a436f-128">**Key figure**</span></span>  
 <span data-ttu-id="a436f-129">Permite crear un InfoObject que represente datos de hechos.</span><span class="sxs-lookup"><span data-stu-id="a436f-129">Create an InfoObject that represents fact data.</span></span>  
  
 <span data-ttu-id="a436f-130">**Nombre de InfoObject**</span><span class="sxs-lookup"><span data-stu-id="a436f-130">**InfoObject name**</span></span>  
 <span data-ttu-id="a436f-131">Permite escribir un nombre para el InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a436f-131">Enter a name for the InfoObject.</span></span>  
  
 <span data-ttu-id="a436f-132">**Descripción breve**</span><span class="sxs-lookup"><span data-stu-id="a436f-132">**Short description**</span></span>  
 <span data-ttu-id="a436f-133">Permite escribir una descripción breve para el InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a436f-133">Enter a short description for the InfoObject.</span></span>  
  
 <span data-ttu-id="a436f-134">**Descripción larga**</span><span class="sxs-lookup"><span data-stu-id="a436f-134">**Long description**</span></span>  
 <span data-ttu-id="a436f-135">Permite escribir una descripción larga para el InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a436f-135">Enter a long description for the InfoObject.</span></span>  
  
 <span data-ttu-id="a436f-136">**Tiene datos maestros**</span><span class="sxs-lookup"><span data-stu-id="a436f-136">**Has master data**</span></span>  
 <span data-ttu-id="a436f-137">Permite indicar que el InfoObject contiene datos maestros en forma de atributos, texto o jerarquías.</span><span class="sxs-lookup"><span data-stu-id="a436f-137">Indicate that the InfoObject contains master data in the form of attributes, texts, or hierarchies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a436f-138">Seleccione esta opción si el InfoObject representa datos dimensionales y ha seleccionado la opción **Característica** .</span><span class="sxs-lookup"><span data-stu-id="a436f-138">Select this option if the InfoObject represents dimensional data and you have selected the **Characteristic** option.</span></span>  
  
 <span data-ttu-id="a436f-139">**Permitir caracteres en minúscula**</span><span class="sxs-lookup"><span data-stu-id="a436f-139">**Allow lower-case characters**</span></span>  
 <span data-ttu-id="a436f-140">Permite aceptar caracteres en minúsculas en los datos del InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a436f-140">Allow lower-case characters in the InfoObject data.</span></span>  
  
 <span data-ttu-id="a436f-141">**Guardar y activar**</span><span class="sxs-lookup"><span data-stu-id="a436f-141">**Save & Activate**</span></span>  
 <span data-ttu-id="a436f-142">Permite guardar y activar el nuevo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a436f-142">Save and active the new InfoObject.</span></span>  
  
## <a name="data-type-options"></a><span data-ttu-id="a436f-143">Opciones de tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a436f-143">Data Type Options</span></span>  
 <span data-ttu-id="a436f-144">**CHAR - Cadena de caracteres**</span><span class="sxs-lookup"><span data-stu-id="a436f-144">**CHAR - Character String**</span></span>  
 <span data-ttu-id="a436f-145">Permite indicar que el InfoObject no contiene datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a436f-145">Indicates that the InfoObject contains character data.</span></span>  
  
 <span data-ttu-id="a436f-146">**NUMC - Cadena numérica**</span><span class="sxs-lookup"><span data-stu-id="a436f-146">**NUMC - Numeric String**</span></span>  
 <span data-ttu-id="a436f-147">Permite indicar que el InfoObject no contiene datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="a436f-147">Indicates that the InfoObject contains numeric data.</span></span>  
  
 <span data-ttu-id="a436f-148">**DATS - Fecha (AAAAMMDD)**</span><span class="sxs-lookup"><span data-stu-id="a436f-148">**DATS - Date (YYYYMMDD)**</span></span>  
 <span data-ttu-id="a436f-149">Permite indicar que el InfoObject no contiene datos de fecha.</span><span class="sxs-lookup"><span data-stu-id="a436f-149">Indicates that the InfoObject contains date data.</span></span>  
  
 <span data-ttu-id="a436f-150">**TIMS - Hora (HHMMSS)**</span><span class="sxs-lookup"><span data-stu-id="a436f-150">**TIMS - Time (HHMMSS)**</span></span>  
 <span data-ttu-id="a436f-151">Permite indicar que InfoObject no contiene datos de hora.</span><span class="sxs-lookup"><span data-stu-id="a436f-151">Indicates that the InfoObject contains time data.</span></span>  
  
 <span data-ttu-id="a436f-152">**Longitud**</span><span class="sxs-lookup"><span data-stu-id="a436f-152">**Length**</span></span>  
 <span data-ttu-id="a436f-153">Permite escribir la longitud de los datos.</span><span class="sxs-lookup"><span data-stu-id="a436f-153">Enter the length of the data.</span></span>  
  
## <a name="text-options"></a><span data-ttu-id="a436f-154">Opciones de texto</span><span class="sxs-lookup"><span data-stu-id="a436f-154">Text Options</span></span>  
 <span data-ttu-id="a436f-155">**Con textos**</span><span class="sxs-lookup"><span data-stu-id="a436f-155">**With Texts**</span></span>  
 <span data-ttu-id="a436f-156">Permite indicar que el InfoObject no contiene datos de texto.</span><span class="sxs-lookup"><span data-stu-id="a436f-156">Indicate that the InfoObject contains texts.</span></span>  
  
 <span data-ttu-id="a436f-157">**Texto breve**</span><span class="sxs-lookup"><span data-stu-id="a436f-157">**Short Text**</span></span>  
 <span data-ttu-id="a436f-158">Permite indicar que el InfoObject no contiene textos breves.</span><span class="sxs-lookup"><span data-stu-id="a436f-158">Indicates that the InfoObject contains short texts.</span></span>  
  
 <span data-ttu-id="a436f-159">**Texto intermedio**</span><span class="sxs-lookup"><span data-stu-id="a436f-159">**Medium Text**</span></span>  
 <span data-ttu-id="a436f-160">Permite indicar que el InfoObject no contiene textos intermedios.</span><span class="sxs-lookup"><span data-stu-id="a436f-160">Indicates that the InfoObject contains medium texts.</span></span>  
  
 <span data-ttu-id="a436f-161">**Texto largo**</span><span class="sxs-lookup"><span data-stu-id="a436f-161">**Long Text**</span></span>  
 <span data-ttu-id="a436f-162">permite indicar que el InfoObject no contiene textos largos.</span><span class="sxs-lookup"><span data-stu-id="a436f-162">Indicates that the InfoObject contains long texts.</span></span>  
  
 <span data-ttu-id="a436f-163">**Dependiente del idioma del texto**</span><span class="sxs-lookup"><span data-stu-id="a436f-163">**Text Language-Dependent**</span></span>  
 <span data-ttu-id="a436f-164">Permite indicar que los textos dependen del idioma.</span><span class="sxs-lookup"><span data-stu-id="a436f-164">Indicates that the texts are language-dependent.</span></span>  
  
 <span data-ttu-id="a436f-165">**Dependiente de la hora del texto**</span><span class="sxs-lookup"><span data-stu-id="a436f-165">**Text Time-Dependent**</span></span>  
 <span data-ttu-id="a436f-166">Permite indicar que los textos dependen de la hora.</span><span class="sxs-lookup"><span data-stu-id="a436f-166">Indicates that the texts are time-dependent.</span></span>  
  
## <a name="attributes-section"></a><span data-ttu-id="a436f-167">Sección Atributos</span><span class="sxs-lookup"><span data-stu-id="a436f-167">Attributes Section</span></span>  
 <span data-ttu-id="a436f-168">La sección **Atributos** consta de una lista de atributos para InfoObject y de las opciones que permiten agregar y quitar atributos de la lista.</span><span class="sxs-lookup"><span data-stu-id="a436f-168">The **Attributes** section consists of a list of attributes for the InfoObject, and the options that let you add and remove attributes from the list.</span></span>  
  
### <a name="attributes-list"></a><span data-ttu-id="a436f-169">Lista de atributos</span><span class="sxs-lookup"><span data-stu-id="a436f-169">Attributes List</span></span>  
 <span data-ttu-id="a436f-170">La lista **Atributos** muestra los atributos del InfoObject que está creando.</span><span class="sxs-lookup"><span data-stu-id="a436f-170">The **Attributes** list displays the attributes of the InfoObject that you are creating.</span></span> <span data-ttu-id="a436f-171">La lista **Atributos** tiene los siguientes encabezados de columna:</span><span class="sxs-lookup"><span data-stu-id="a436f-171">The **Attributes** list has the following column headings:</span></span>  
  
 <span data-ttu-id="a436f-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="a436f-172">**InfoObject**</span></span>  
 <span data-ttu-id="a436f-173">Permite ver el nombre del InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a436f-173">View the name of the InfoObject.</span></span>  
  
 <span data-ttu-id="a436f-174">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a436f-174">**Description**</span></span>  
 <span data-ttu-id="a436f-175">Permite ver la descripción del InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a436f-175">View the description of the InfoObject.</span></span>  
  
 <span data-ttu-id="a436f-176">**Tipo de InfoObject**</span><span class="sxs-lookup"><span data-stu-id="a436f-176">**InfoObject Type**</span></span>  
 <span data-ttu-id="a436f-177">Permite ver el tipo de InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a436f-177">View the type of the InfoObject.</span></span> <span data-ttu-id="a436f-178">En la siguiente tabla se muestran los posibles valores para el tipo.</span><span class="sxs-lookup"><span data-stu-id="a436f-178">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="a436f-179">Value</span><span class="sxs-lookup"><span data-stu-id="a436f-179">Value</span></span>|<span data-ttu-id="a436f-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="a436f-180">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a436f-181">CHA</span><span class="sxs-lookup"><span data-stu-id="a436f-181">CHA</span></span>|<span data-ttu-id="a436f-182">Características</span><span class="sxs-lookup"><span data-stu-id="a436f-182">Characteristics</span></span>|  
|<span data-ttu-id="a436f-183">KYF</span><span class="sxs-lookup"><span data-stu-id="a436f-183">KYF</span></span>|<span data-ttu-id="a436f-184">Cifras clave</span><span class="sxs-lookup"><span data-stu-id="a436f-184">Key figures</span></span>|  
|<span data-ttu-id="a436f-185">UNI</span><span class="sxs-lookup"><span data-stu-id="a436f-185">UNI</span></span>|<span data-ttu-id="a436f-186">Unidades</span><span class="sxs-lookup"><span data-stu-id="a436f-186">Units</span></span>|  
|<span data-ttu-id="a436f-187">TIM</span><span class="sxs-lookup"><span data-stu-id="a436f-187">TIM</span></span>|<span data-ttu-id="a436f-188">Características de tiempo</span><span class="sxs-lookup"><span data-stu-id="a436f-188">Time characteristics</span></span>|  
  
### <a name="attributes-options"></a><span data-ttu-id="a436f-189">Opciones de Atributos</span><span class="sxs-lookup"><span data-stu-id="a436f-189">Attributes Options</span></span>  
 <span data-ttu-id="a436f-190">Use las opciones siguientes para agregar y quitar los atributos para el InfoObject que está creando:</span><span class="sxs-lookup"><span data-stu-id="a436f-190">Use the following options to add and remove attributes for the InfoObject that you are creating:</span></span>  
  
 <span data-ttu-id="a436f-191">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="a436f-191">**Add**</span></span>  
 <span data-ttu-id="a436f-192">Permite agregar un InfoObject existente como atributo.</span><span class="sxs-lookup"><span data-stu-id="a436f-192">Add an existing InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="a436f-193">Para agregar un InfoObject existente, haga clic en Agregar y, a continuación, use el cuadro de diálogo **Buscar InfoObject** para buscar el InfoObject.</span><span class="sxs-lookup"><span data-stu-id="a436f-193">To add an existing InfoObject, click Add, and then use the **Look Up InfoObject** dialog box to find the InfoObject.</span></span> <span data-ttu-id="a436f-194">Para obtener más información sobre este cuadro de diálogo, vea [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="a436f-194">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="a436f-195">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="a436f-195">**New**</span></span>  
 <span data-ttu-id="a436f-196">Permite agregar un InfoObject nuevo como atributo.</span><span class="sxs-lookup"><span data-stu-id="a436f-196">Add a new InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="a436f-197">Para crear y agregar un InfoObject nuevo, haga clic en Nuevo y, a continuación, use una nueva instancia del cuadro de diálogo crear **Crear nuevo InfoObject** para crear el InfoObject nuevo.</span><span class="sxs-lookup"><span data-stu-id="a436f-197">To create and add a new InfoObject, click New, and then use a new instance of the **Create New InfoObject** dialog box to create the new InfoObject.</span></span>  
  
 <span data-ttu-id="a436f-198">**Remove**</span><span class="sxs-lookup"><span data-stu-id="a436f-198">**Remove**</span></span>  
 <span data-ttu-id="a436f-199">Quita el InfoObject seleccionado de la lista **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="a436f-199">Remove the selected InfoObject from the **Attributes** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a436f-200">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a436f-200">See Also</span></span>  
 <span data-ttu-id="a436f-201">[Crear InfoCube para datos de transacción](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="a436f-201">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="a436f-202">[Crear InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="a436f-202">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="a436f-203">[Crear InfoSource para datos de transacción](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="a436f-203">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="a436f-204">[Crear InfoSource para datos maestros](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="a436f-204">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 [<span data-ttu-id="a436f-205">Ayuda F1 de Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a436f-205">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
