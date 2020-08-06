---
title: Importar valores de un proyecto de limpieza en un dominio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.importprojectvalues.f1
ms.assetid: f23e38e2-39e0-42d7-abd5-34d8fcca5d2a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 38616da5a0a8fb9c8f149d9f55a08b63dee5ff6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745979"
---
# <a name="import-cleansing-project-values-into-a-domain"></a><span data-ttu-id="dffee-102">Importar valores de un proyecto de limpieza en un dominio</span><span class="sxs-lookup"><span data-stu-id="dffee-102">Import Cleansing Project Values into a Domain</span></span>
  <span data-ttu-id="dffee-103">En [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), puede importar el conocimiento de calidad de los datos durante el proceso de limpieza en un proyecto de limpieza de calidad de datos o un paquete de Integration Services que contenga el componente Limpieza de DQS en un dominio.</span><span class="sxs-lookup"><span data-stu-id="dffee-103">In [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), you can import data quality knowledge gathered during the cleansing process in a data quality cleansing project or an Integration Services package containing the DQS Cleansing component into a domain.</span></span> <span data-ttu-id="dffee-104">De este modo, se garantiza la conservación del conocimiento de confianza y la continua mejora de la base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="dffee-104">This ensures that trusted knowledge is not lost, and that the knowledge base is continually improved.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dffee-105">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="dffee-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="dffee-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dffee-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="dffee-107">Para importar los valores del proyecto de limpieza en un dominio, el dominio debe haberse utilizado en el proyecto de limpieza en Data Quality Cliente o en el paquete de Integration Services que contiene un componente de Limpieza de DQS.</span><span class="sxs-lookup"><span data-stu-id="dffee-107">To import cleansing project values into a domain, the domain must have been used in the cleansing project in Data Quality Client or in the Integration Services package containing a DQS Cleansing component.</span></span>  
  
-   <span data-ttu-id="dffee-108">El proyecto de limpieza de Data Quality Client o el paquete de Integration Services que contiene el componente de Limpieza de DQS deben haberse completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="dffee-108">The cleansing project in Data Quality Client or the Integration Services package containing the DQS Cleansing component must have successfully completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dffee-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="dffee-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dffee-110">Permisos</span><span class="sxs-lookup"><span data-stu-id="dffee-110">Permissions</span></span>  
 <span data-ttu-id="dffee-111">Debe disponer del rol dqs_kb_editor o dqs_administrator en la base de datos DQS_MAIN para importar en un dominio el conocimiento de calidad de datos obtenido durante el proceso de limpieza.</span><span class="sxs-lookup"><span data-stu-id="dffee-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import data quality knowledge gathered during the cleansing process into a domain.</span></span>  
  
##  <a name="import-cleansing-project-values"></a><a name="Import"></a><span data-ttu-id="dffee-112">Importar valores de proyecto de limpieza</span><span class="sxs-lookup"><span data-stu-id="dffee-112">Import Cleansing Project Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="dffee-113">[Ejecute la aplicación Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="dffee-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="dffee-114">En la página de inicio de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , abra una base de conocimiento en la actividad Administración de dominios.</span><span class="sxs-lookup"><span data-stu-id="dffee-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="dffee-115">Si va a agregar valores a un dominio existente, selecciónelo en la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="dffee-115">If adding values to an existing domain, select the domain in the domain list.</span></span>  
  
4.  <span data-ttu-id="dffee-116">Haga clic en la pestaña **Valores del dominio** , haga clic en el icono **Importar valores** de la barra de iconos y, a continuación, haga clic en **Importar valores de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="dffee-116">Click the **Domain Values** tab, click the **Import Values** icon in the icon bar, and then click **Import project values**.</span></span> <span data-ttu-id="dffee-117">El cuadro de diálogo **Configuración de proyecto de importación** mostrará una lista de los proyectos de calidad de los datos y paquetes de Integration Services que fueron limpiados en el dominio.</span><span class="sxs-lookup"><span data-stu-id="dffee-117">The **Import Project Values** dialog box appears with a list of data quality projects and Integration Services packages that were cleansed using the domain.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dffee-118">Si no se ha creado ningún proyecto utilizando el dominio o alguno de sus dominios vinculados, o el proyecto no se ha finalizado, la opción **Importar valores de proyecto** no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="dffee-118">If no project has been created using the domain or any of its linked domains, or the project was not finished, the **Import project values** option will not be available.</span></span>  
  
5.  <span data-ttu-id="dffee-119">En el cuadro de diálogo **Configuración de proyecto de importación** :</span><span class="sxs-lookup"><span data-stu-id="dffee-119">In the **Import Project Values** dialog box:</span></span>  
  
    -   <span data-ttu-id="dffee-120">Seleccione **Todos** en la lista despegable **Importado** para mostrar todos los proyectos o **No** para mostrar solo los proyectos cuyos valores no se han importado todavía.</span><span class="sxs-lookup"><span data-stu-id="dffee-120">Select **All** in the **Imported** drop-down list to display all projects, or **No** to display only projects whose values have not been imported yet.</span></span>  
  
    -   <span data-ttu-id="dffee-121">Seleccione el proyecto del que desee importar los valores.</span><span class="sxs-lookup"><span data-stu-id="dffee-121">Select the project that you want to import values from.</span></span>  
  
    -   <span data-ttu-id="dffee-122">Seleccione **Agregar valores de la pestaña Nuevo** para importar los valores de la pestaña Nuevo, además de los valores de las pestañas **Correcto** y **Corregido** .</span><span class="sxs-lookup"><span data-stu-id="dffee-122">Select **Add values from New tab** to import values in the new tab, in addition to values in the **Correct** and **Corrected** tabs.</span></span>  
  
    -   <span data-ttu-id="dffee-123">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="dffee-123">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="dffee-124">Vuelve a la pestaña **Valores del dominio** y aparece un mensaje que indica que la importación de los valores fue correcta.</span><span class="sxs-lookup"><span data-stu-id="dffee-124">You return to the **Domain Values** tab, and a message is displayed on successful import of the values.</span></span> <span data-ttu-id="dffee-125">Los valores que se han importado y que, por lo tanto, son nuevos en el dominio, se mostrarán en la tabla **Valores** .</span><span class="sxs-lookup"><span data-stu-id="dffee-125">Values that have been imported, and so are new to the domain, will be displayed in the **Values** table.</span></span>  
  
7.  <span data-ttu-id="dffee-126">Anule la selección de la opción **Mostrar solo nuevo** para mostrar todos los valores del dominio.</span><span class="sxs-lookup"><span data-stu-id="dffee-126">Deselect **Show Only New** to display all values that are in the domain.</span></span>  
  
8.  <span data-ttu-id="dffee-127">Seleccione **Correcto**, **Error**o **No válido** para mostrar solo los valores del tipo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dffee-127">Select **Correct**, **Error**, or **Invalid** to display only those values of the selected type.</span></span>  
  
9. <span data-ttu-id="dffee-128">Para buscar una cadena específica, escríbala en el cuadro de texto **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="dffee-128">To search for a specific string, enter the string in the **Find** text box.</span></span> <span data-ttu-id="dffee-129">Haga clic en la flecha arriba o abajo para recorrer los valores que cumplen los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dffee-129">Click the up or down arrow to step through the values that meet the search criteria.</span></span> <span data-ttu-id="dffee-130">Aparecerán resaltados en amarillo.</span><span class="sxs-lookup"><span data-stu-id="dffee-130">They will be highlighted in yellow.</span></span>  
  
10. <span data-ttu-id="dffee-131">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="dffee-131">Click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dffee-132"> Para obtener más información sobre cómo trabajar con valores de la pestaña **Valores del dominio** , vea [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span><span class="sxs-lookup"><span data-stu-id="dffee-132">For more information on working with values in the **Domain Values** tab, see [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span></span>  
  
##  <a name="follow-up-after-importing-project-values-into-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="dffee-133">Seguimiento: después de importar valores de proyecto en un dominio</span><span class="sxs-lookup"><span data-stu-id="dffee-133">Follow Up: After Importing Project Values into a Domain</span></span>  
 <span data-ttu-id="dffee-134">Una vez importado en un dominio el conocimiento de calidad de datos obtenido durante el proceso de limpieza, puede realizar otras tareas de administración de dominios en el dominio y en los valores.</span><span class="sxs-lookup"><span data-stu-id="dffee-134">After you import data quality knowledge gathered during the cleansing process into a domain, you can perform other domain management tasks on the domain and the values.</span></span> <span data-ttu-id="dffee-135">Para más información, vea [Administrar un dominio](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="dffee-135">For more information, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
##  <a name="values-that-will-be-imported"></a><a name="Values"></a> <span data-ttu-id="dffee-136">Valores que se importarán</span><span class="sxs-lookup"><span data-stu-id="dffee-136">Values that Will Be Imported</span></span>  
 <span data-ttu-id="dffee-137">Se importarán los valores siguientes desde un proyecto a un dominio:</span><span class="sxs-lookup"><span data-stu-id="dffee-137">The following values will be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="dffee-138">Solo se importarán en el dominio los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="dffee-138">Only string values are imported to the domain.</span></span>  
  
-   <span data-ttu-id="dffee-139">Solamente se importarán los valores de las pestañas **Correcto**, **Corregido**y **Nuevo** de la página **Administrar y ver resultados** de la actividad **Limpieza** .</span><span class="sxs-lookup"><span data-stu-id="dffee-139">Only values from the **Correct**, **Corrected**, and **New** tabs on the **Manage and View results** page of the **Cleansing** activity will be imported.</span></span> <span data-ttu-id="dffee-140">Los valores de la pestaña **Nuevo** de la actividad **Limpieza** se importarán solamente si se ha activado la casilla del cuadro de diálogo **Importar valores de proyecto** .</span><span class="sxs-lookup"><span data-stu-id="dffee-140">Values from the **New** tab will be imported only if the **Add values from New tab** check box in the **Import Project Values** dialog box has been selected.</span></span>  
  
-   <span data-ttu-id="dffee-141">Los valores se importarán como correctos o como erróneos con sus correcciones.</span><span class="sxs-lookup"><span data-stu-id="dffee-141">Values will be imported as correct or as an error with its correction.</span></span> <span data-ttu-id="dffee-142">Solo se importarán los valores erróneos que tengan valores de corrección.</span><span class="sxs-lookup"><span data-stu-id="dffee-142">Only an error value with a correction value will be imported.</span></span>  
  
-   <span data-ttu-id="dffee-143">El valor de corrección deberá ser un nuevo valor que no exista en la base de conocimiento o un valor correcto ya existente.</span><span class="sxs-lookup"><span data-stu-id="dffee-143">The correction value will be either a new value that does not exist in the knowledge base or an existing correct value.</span></span>  
  
-   <span data-ttu-id="dffee-144">Solo se importarán en la base de conocimiento las correcciones realizadas en el nivel de valor, no en el de registro.</span><span class="sxs-lookup"><span data-stu-id="dffee-144">Only corrections performed on the value level, not the record level, will be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="dffee-145">Se crearán valores no válidos si el valor importado está en contradicción con una regla de dominio.</span><span class="sxs-lookup"><span data-stu-id="dffee-145">Invalid values will be created if the imported value contradicts a domain rule.</span></span>  
  
-   <span data-ttu-id="dffee-146">Si se importan valores de varios proyectos simultáneamente, la importación se realizará en orden secuencial.</span><span class="sxs-lookup"><span data-stu-id="dffee-146">If you import values from several projects at once, the values are imported in a sequential order.</span></span>  
  
-   <span data-ttu-id="dffee-147">Las correcciones realizadas como resultado de una relación basada en términos de un dominio se importan como valores correctos (no como errores).</span><span class="sxs-lookup"><span data-stu-id="dffee-147">A correction made as a result of a term-based relation in a domain is imported as a correct value (not as an error).</span></span>  
  
##  <a name="values-that-will-not-be-imported"></a><a name="ValuesNot"></a> <span data-ttu-id="dffee-148">Valores que no se importarán</span><span class="sxs-lookup"><span data-stu-id="dffee-148">Values that Will Not Be Imported</span></span>  
 <span data-ttu-id="dffee-149">No se importarán los valores siguientes desde un proyecto a un dominio:</span><span class="sxs-lookup"><span data-stu-id="dffee-149">The following values will not be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="dffee-150">Los valores de las pestañas **Sugerido** y **No válido** de la página **Administrar y ver resultados** de la actividad **Limpieza** no se importarán.</span><span class="sxs-lookup"><span data-stu-id="dffee-150">Values from the **Suggested** and **Invalid** tabs on the **Manage and View results** page of the **Cleansing** activity will not be imported.</span></span>  
  
-   <span data-ttu-id="dffee-151">Si un valor del proyecto de limpieza está en contradicción con un valor existente en el dominio, el primer valor se omite.</span><span class="sxs-lookup"><span data-stu-id="dffee-151">If a value found in the cleansing project contradicts an existing value in the domain, the value found in the project is skipped.</span></span> <span data-ttu-id="dffee-152">Esto incluirá los conflictos existentes entre los valores de la base de conocimiento y los de limpieza.</span><span class="sxs-lookup"><span data-stu-id="dffee-152">This will include conflicts between cleansing and knowledge base values.</span></span>  
  
-   <span data-ttu-id="dffee-153">Las correcciones realizadas en el nivel de registro no se importarán en la base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="dffee-153">Corrections performed on the record level will not be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="dffee-154">No se importará ningún valor en un dominio si el valor al que debe reemplazar lo corrigió o aprobó como correcto un servicio de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="dffee-154">No value will be imported to a domain if the value that it would replace was corrected or approved as correct by a reference data service.</span></span>  
  
-   <span data-ttu-id="dffee-155">Si un valor de corrección aparece en la base de conocimiento como no válido o erróneo, no se importarán ni el error ni el valor de corrección.</span><span class="sxs-lookup"><span data-stu-id="dffee-155">If a correction value appears in the knowledge base as an invalid or error value, neither the error nor the correction value will be imported.</span></span>  
  
-   <span data-ttu-id="dffee-156">Si el dominio forma parte de un dominio compuesto y se ha realizado la limpieza en este, no se importará ningún valor.</span><span class="sxs-lookup"><span data-stu-id="dffee-156">If the domain is part of a composite domain, and the cleansing was performed on the composite domain, no values will be imported.</span></span>  
  
-   <span data-ttu-id="dffee-157">Solo se podrán importar valores de un proyecto si la base de conocimiento se encuentra en el estado Trabajando y la ha bloqueado el usuario que realiza la importación.</span><span class="sxs-lookup"><span data-stu-id="dffee-157">You can import values from a project only when the knowledge base has a state of in-work and the knowledge base is locked by the user who is importing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dffee-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dffee-158">See Also</span></span>  
 <span data-ttu-id="dffee-159">[Limpieza de datos](../../2014/data-quality-services/data-cleansing.md) </span><span class="sxs-lookup"><span data-stu-id="dffee-159">[Data Cleansing](../../2014/data-quality-services/data-cleansing.md) </span></span>  
 [<span data-ttu-id="dffee-160">Transformación Limpieza de DQS</span><span class="sxs-lookup"><span data-stu-id="dffee-160">DQS Cleansing Transformation</span></span>](../integration-services/data-flow/transformations/dqs-cleansing-transformation.md)  
  
  
