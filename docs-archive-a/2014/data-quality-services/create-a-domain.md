---
title: Crear un dominio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.createdomain.f1
ms.assetid: 5c4828f5-bd51-4c29-b3de-87b7d2f2d3e5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fad6abd795aa9412bb71d251623d92d3e13b889c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663734"
---
# <a name="create-a-domain"></a><span data-ttu-id="a05da-102">Crear un dominio</span><span class="sxs-lookup"><span data-stu-id="a05da-102">Create a Domain</span></span>
  <span data-ttu-id="a05da-103">En este tema se describe cómo crear un dominio en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="a05da-103">This topic describes how to create a domain in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="a05da-104">Los valores del dominio son una representación semántica de los datos de un campo.</span><span class="sxs-lookup"><span data-stu-id="a05da-104">The values in the domain are a semantic representation of the data in a field.</span></span> <span data-ttu-id="a05da-105">Para más información sobre los dominios, vea [Administrar un dominio](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="a05da-105">For more information on domains, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
 <span data-ttu-id="a05da-106">Hay dos maneras de crear un nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="a05da-106">There are two ways to create a new domain.</span></span> <span data-ttu-id="a05da-107">La primera es durante el paso de asignación de la actividad de detección de conocimiento, cuando se analiza una muestra de los datos para agregar conocimiento a una base de conocimiento nueva o a una ya existente.</span><span class="sxs-lookup"><span data-stu-id="a05da-107">The first is during the Map step of the knowledge discovery activity, when you are in the process of analyzing a data sample to add knowledge to a new or existing knowledge base.</span></span> <span data-ttu-id="a05da-108">La segunda es durante la actividad de administración de dominios, cuando se crea un nuevo dominio en lugar de modificar uno ya existente.</span><span class="sxs-lookup"><span data-stu-id="a05da-108">The second is during the domain management activity, when instead of changing an existing domain, you create a new one.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a05da-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a05da-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="a05da-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a05da-110">Prerequisites</span></span>  
 <span data-ttu-id="a05da-111">Para crear un dominio, debe haber creado y abierto una base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="a05da-111">To create a domain, you must have created and opened a knowledge base.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a05da-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a05da-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a05da-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="a05da-113">Permissions</span></span>  
 <span data-ttu-id="a05da-114">Debe disponer del rol dqs_kb_editor o dqs_administrator en la base de datos DQS_MAIN para crear un dominio.</span><span class="sxs-lookup"><span data-stu-id="a05da-114">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to create a domain.</span></span>  
  
##  <a name="create-a-domain-in-the-knowledge-discovery-activity"></a><a name="Discovery"></a> <span data-ttu-id="a05da-115">Crear un dominio en la actividad Detección de conocimiento</span><span class="sxs-lookup"><span data-stu-id="a05da-115">Create a Domain in the Knowledge Discovery Activity</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="a05da-116">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="a05da-116">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="a05da-117">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Abrir base de conocimiento** y seleccione una base de conocimiento, o haga clic en **Nueva base de conocimiento** y especifique las propiedades para la nueva base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="a05da-117">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
3.  <span data-ttu-id="a05da-118">Seleccione **Detección de conocimiento** como actividad y, a continuación, haga clic en **Crear** para crear la nueva base de conocimiento o en **Abrir** para abrir una ya existente.</span><span class="sxs-lookup"><span data-stu-id="a05da-118">Select **Knowledge Discovery** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
4.  <span data-ttu-id="a05da-119">En la página **Asignación** , especifique una conexión con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a05da-119">On the **Map** page, specify a connection to the data source.</span></span> <span data-ttu-id="a05da-120">Para obtener más información, vea [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="a05da-120">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span></span>  
  
5.  <span data-ttu-id="a05da-121">En la tabla **Asignaciones** , seleccione una columna de origen en la lista desplegable para la columna **Columna de origen** de una fila vacía.</span><span class="sxs-lookup"><span data-stu-id="a05da-121">In the **Mappings** table, select a source column from the drop-down list for the **Source Column** column of an empty row.</span></span> <span data-ttu-id="a05da-122">Si no existe ningún dominio correspondiente, haga clic en el icono **Crear un dominio** .</span><span class="sxs-lookup"><span data-stu-id="a05da-122">If no corresponding domain exists, click the **Create a Domain** icon.</span></span>  
  
##  <a name="create-a-domain-in-the-domain-management-activity"></a><a name="DomainManagement"></a><span data-ttu-id="a05da-123">Crear un dominio en la actividad administración de dominios</span><span class="sxs-lookup"><span data-stu-id="a05da-123">Create a Domain in the Domain Management Activity</span></span>  
  
1.  <span data-ttu-id="a05da-124">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , haga clic en **Abrir base de conocimiento** y seleccione una base de conocimiento, o haga clic en **Nueva base de conocimiento** y especifique las propiedades para la nueva base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="a05da-124">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
2.  <span data-ttu-id="a05da-125">Seleccione **Administración de dominios** como actividad y, a continuación, haga clic en **Crear** para crear la nueva base de conocimiento o en **Abrir** para abrir una ya existente.</span><span class="sxs-lookup"><span data-stu-id="a05da-125">Select **Domain Management** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
3.  <span data-ttu-id="a05da-126">En la página **Administración de dominios** , haga clic en el icono **Crear un dominio** situado sobre la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="a05da-126">On the **Domain Management** page, click the **Create a Domain** icon above the Domain list.</span></span>  
  
##  <a name="set-domain-properties"></a><a name="Properties"></a><span data-ttu-id="a05da-127">Establecer propiedades de dominio</span><span class="sxs-lookup"><span data-stu-id="a05da-127">Set Domain Properties</span></span>  
  
1.  <span data-ttu-id="a05da-128">En el cuadro de diálogo **Crear dominio** , escriba un nombre que sea único en la base de conocimiento y una descripción con una longitud máxima de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a05da-128">In the **Create Domain** dialog box, enter a name that is unique to the knowledge base and a description up to 256 characters.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a05da-129"> Para obtener más información acerca de las propiedades de dominio, vea [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a05da-129">For more information about domain properties, see [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span></span>  
  
2.  <span data-ttu-id="a05da-130">En la lista **Tipo de datos** , seleccione un tipo de datos para los valores del dominio.</span><span class="sxs-lookup"><span data-stu-id="a05da-130">From the **Data Type** list, select a data type for the values in the domain.</span></span> <span data-ttu-id="a05da-131">El tipo de datos puede ser **Cadena** (el valor predeterminado), **Fecha**, **Entero**o **Decimal**.</span><span class="sxs-lookup"><span data-stu-id="a05da-131">The data type can be **String** (the default), **Date**, **Integer**, or **Decimal**.</span></span>  
  
3.  <span data-ttu-id="a05da-132">Seleccione **Usar valores iniciales** para especificar que se mostrará el valor inicial de un grupo de sinónimos en lugar de un valor que sea un sinónimo.</span><span class="sxs-lookup"><span data-stu-id="a05da-132">Select **Use Leading Values** to specify that the leading value in a group of synonyms will be output instead of a value that is a synonym to it.</span></span> <span data-ttu-id="a05da-133">Anule la selección **Usar valores iniciales** para especificar que cada valor de sinónimo se mostrará en su forma correcta o corregida, y que no será reemplazado por el valor inicial de su grupo.</span><span class="sxs-lookup"><span data-stu-id="a05da-133">Deselect **Use Leading Values** to specify that each synonym value is output in its correct or corrected form, and is not replaced by the leading value for its group.</span></span>  
  
4.  <span data-ttu-id="a05da-134">Si el tipo de datos es **Cadena**, seleccione **Normalizar cadena** para quitar caracteres especiales de los valores de dominio, lo que puede aumentar las probabilidades de que se produzcan coincidencias.</span><span class="sxs-lookup"><span data-stu-id="a05da-134">If the data type is **String**, select **Normalize String** to remove special characters in the domain values, which may improve the likelihood of matches.</span></span>  
  
5.  <span data-ttu-id="a05da-135">En la lista desplegable **Dar formato a la salida para** , seleccione el formato que se aplicará al mostrar los valores de los datos del dominio.</span><span class="sxs-lookup"><span data-stu-id="a05da-135">From the **Format Output to** drop-down list, select the formatting that will be applied when the data values in the domain are output.</span></span> <span data-ttu-id="a05da-136">El formato es específico del tipo de datos seleccionado en el paso 2, tal como se muestra en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="a05da-136">The formatting is specific to the data type selected in step 2, as shown in the following list:</span></span>  
  
    -   <span data-ttu-id="a05da-137">Para un valor de cadena, puede especificar que esta se genere en mayúsculas, en minúsculas o con la inicial en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="a05da-137">For a string value, you can specify that the string be output as upper case, lower case, or capitalized.</span></span>  
  
    -   <span data-ttu-id="a05da-138">Para un valor de fecha, puede especificar el formato del día, del mes y del año.</span><span class="sxs-lookup"><span data-stu-id="a05da-138">For a date value, you can specify the format of the day, month, and year.</span></span>  
  
    -   <span data-ttu-id="a05da-139">Para un valor entero, puede especificar el tipo de máscara de formato que se aplicará.</span><span class="sxs-lookup"><span data-stu-id="a05da-139">For an integer value, you can specify the type of format mask to be applied.</span></span>  
  
    -   <span data-ttu-id="a05da-140">Para un valor decimal, puede especificar la precisión y el tipo de máscara de formato que se aplicará.</span><span class="sxs-lookup"><span data-stu-id="a05da-140">For a decimal value, you can specify the accuracy and the type of format mask to be applied.</span></span>  
  
     <span data-ttu-id="a05da-141">Si se selecciona **Ninguno** en la lista desplegable **Dar formato a la salida para** , significa que no se aplicará ninguno de los formatos de la lista.</span><span class="sxs-lookup"><span data-stu-id="a05da-141">Selecting **None** in the **Format Output to** drop-down list means none of the formats in the list will be applied.</span></span>  
  
6.  <span data-ttu-id="a05da-142">Si el tipo de datos es **Cadena**, en la lista desplegable **Idioma** , seleccione la versión de idioma del corrector ortográfico que desea aplicar si se habilita este.</span><span class="sxs-lookup"><span data-stu-id="a05da-142">If the data type is **String**, in the **Language** drop-down list, select which language version of the speller you want to apply if you enable the speller.</span></span>  
  
7.  <span data-ttu-id="a05da-143">Si el tipo de datos es **Cadena**, seleccione **Habilitar corrector ortográfico** para ejecutar el corrector ortográfico en todos los valores de cadena al rellenar el dominio.</span><span class="sxs-lookup"><span data-stu-id="a05da-143">If the data type is **String**, select **Enable Speller** to run the Speller on all string values when populating the domain.</span></span>  
  
8.  <span data-ttu-id="a05da-144">Si el tipo de datos es **Cadena**, seleccione **Deshabilitar algoritmos de error de sintaxis** para rellenar el dominio sin comprobar la existencia de errores de sintaxis en los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="a05da-144">If the data type is **String**, select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span>  
  
9. <span data-ttu-id="a05da-145">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a05da-145">Click **OK**.</span></span>  
  
10. <span data-ttu-id="a05da-146">Haga clic en **Finalizar** para finalizar la actividad de administración de dominios, tal como se describe en [Finalizar la actividad Administración de dominios](../../2014/data-quality-services/end-the-domain-management-activity.md).</span><span class="sxs-lookup"><span data-stu-id="a05da-146">Click **Finish** to complete the domain management activity, as described in [End the Domain Management Activity](../../2014/data-quality-services/end-the-domain-management-activity.md).</span></span>  
  
##  <a name="follow-up-after-creating-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="a05da-147">Seguimiento: después de crear un dominio</span><span class="sxs-lookup"><span data-stu-id="a05da-147">Follow Up: After Creating a Domain</span></span>  
 <span data-ttu-id="a05da-148">Una vez creado el dominio, puede realizar otras tareas de administración en el dominio, ejecutar la detección de conocimiento para agregar conocimiento al dominio o agregar a este una directiva de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="a05da-148">After you create a domain, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="a05da-149">Para más información, vea [Realizar la detección de conocimiento](../../2014/data-quality-services/perform-knowledge-discovery.md), [Administrar un dominio](../../2014/data-quality-services/managing-a-domain.md) o [Crear una directiva de coincidencia](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="a05da-149">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
