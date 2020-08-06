---
title: Origen CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.f1
ms.assetid: 99775608-e177-44ed-bb44-aaccb0f4f327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 064c25b129364dfcd813d71a462586303dd4ff60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676617"
---
# <a name="cdc-source"></a><span data-ttu-id="7f309-102">origen de CDC</span><span class="sxs-lookup"><span data-stu-id="7f309-102">CDC Source</span></span>
  <span data-ttu-id="7f309-103">El origen CDC lee un intervalo de datos modificados de las tablas de cambios de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] y entrega los cambios de nivel inferior a otros componentes de SSIS.</span><span class="sxs-lookup"><span data-stu-id="7f309-103">The CDC source reads a range of change data from [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables and delivers the changes downstream to other SSIS components.</span></span>  
  
 <span data-ttu-id="7f309-104">El intervalo de lectura de los datos modificados por el origen CDC se denomina intervalo de procesamiento CDC y se determina con la tarea Control CDC que se ejecuta antes de que el flujo de datos actual se inicie.</span><span class="sxs-lookup"><span data-stu-id="7f309-104">The range of change data read by the CDC source is called the CDC Processing Range and is determine by the CDC Control task that is executed before the current data flow starts.</span></span> <span data-ttu-id="7f309-105">El intervalo de procesamiento CDC se deriva del valor de una variable de paquete que mantiene el estado del procesamiento CDC para un grupo de tablas.</span><span class="sxs-lookup"><span data-stu-id="7f309-105">The CDC Processing Range is derived from the value of a package variable that maintains the state of the CDC processing for a group of tables.</span></span>  
  
 <span data-ttu-id="7f309-106">El origen CDC extrae los datos de una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante una tabla de base de datos, una vista o una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="7f309-106">The CDC source extracts data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="7f309-107">El origen CDC utiliza las configuraciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f309-107">The CDC source uses the following configurations:</span></span>  
  
-   <span data-ttu-id="7f309-108">Administrador de conexiones ADO.NET de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para tener acceso a la base de datos CDC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f309-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ADO.NET connection manager to access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database.</span></span> <span data-ttu-id="7f309-109">Para más información sobre cómo configurar la conexión de origen CDC, vea [Editor de origen de CDC &#40;página Administrador de conexiones&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="7f309-109">For more information about configuring the CDC source connection, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
-   <span data-ttu-id="7f309-110">Tabla habilitada para CDC.</span><span class="sxs-lookup"><span data-stu-id="7f309-110">A table enabled for CDC.</span></span>  
  
-   <span data-ttu-id="7f309-111">Nombre de la instancia de captura de la tabla seleccionada (si existe más de una).</span><span class="sxs-lookup"><span data-stu-id="7f309-111">The name of the capture instance of the selected table (if more-than-one exists).</span></span>  
  
-   <span data-ttu-id="7f309-112">Modo del procesamiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="7f309-112">The change processing mode.</span></span>  
  
-   <span data-ttu-id="7f309-113">Nombre de la variable de paquete de estado CDC basado en lo que determina el intervalo de procesamiento CDC.</span><span class="sxs-lookup"><span data-stu-id="7f309-113">The name of the CDC state package variable based on which the CDC Processing range is determined.</span></span> <span data-ttu-id="7f309-114">El origen CDC no modifica esa variable.</span><span class="sxs-lookup"><span data-stu-id="7f309-114">The CDC source does not modify that variable.</span></span>  
  
 <span data-ttu-id="7f309-115">Los datos devueltos por el origen CDC son los mismos que los devueltos por las funciones CDC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** o **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (si está disponible).</span><span class="sxs-lookup"><span data-stu-id="7f309-115">The data returned by the CDC Source is the same as that returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC functions **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** or **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (when available).</span></span> <span data-ttu-id="7f309-116">La única adición opcional es la columna **__$initial_processing** , que indica si el intervalo de procesamiento actual puede solaparse con una carga inicial de la tabla.</span><span class="sxs-lookup"><span data-stu-id="7f309-116">The only optional addition is the column, **__$initial_processing** that indicates whether the current processing range can overlap with an initial load of the table.</span></span> <span data-ttu-id="7f309-117">Para obtener más información acerca del procesamiento inicial, vea [CDC Control Task](../control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="7f309-117">For more information about initial processing, see [CDC Control Task](../control-flow/cdc-control-task.md).</span></span>  
  
 <span data-ttu-id="7f309-118">El origen de CDC tiene una salida normal y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="7f309-118">The CDC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="7f309-119">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="7f309-119">Error Handling</span></span>  
 <span data-ttu-id="7f309-120">El origen de CDC tiene una salida de error.</span><span class="sxs-lookup"><span data-stu-id="7f309-120">The CDC source has an error output.</span></span> <span data-ttu-id="7f309-121">La salida de error del componente incluye las columnas de salida siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f309-121">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="7f309-122">**Código de error**: el valor es siempre -1.</span><span class="sxs-lookup"><span data-stu-id="7f309-122">**Error Code**: The value is always -1.</span></span>  
  
-   <span data-ttu-id="7f309-123">**Columna de error**: columna de origen que produce el error (para los errores de conversión).</span><span class="sxs-lookup"><span data-stu-id="7f309-123">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="7f309-124">**Columnas de fila de error**: datos de registro que ocasionan el error.</span><span class="sxs-lookup"><span data-stu-id="7f309-124">**Error Row Columns**: The record data that causes the error.</span></span>  
  
 <span data-ttu-id="7f309-125">Según la configuración del comportamiento de los errores, el origen CDC permite devolver los errores (conversión de datos, truncamiento) que aparecerán durante el proceso de extracción en la salida de error.</span><span class="sxs-lookup"><span data-stu-id="7f309-125">Depending on the error behavior setting, the CDC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="7f309-126">Para más información, vea [Editor de origen de CDC &#40;página Salida de error&#41;](../cdc-source-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="7f309-126">For more information, see [CDC Source Editor &#40;Error Output Page&#41;](../cdc-source-editor-error-output-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="7f309-127">Compatibilidad con tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7f309-127">Data Type Support</span></span>  
 <span data-ttu-id="7f309-128">El componente de origen CDC para Microsoft admite todos los tipos de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , que se asignan a los tipos de datos de SSIS correctos.</span><span class="sxs-lookup"><span data-stu-id="7f309-128">The CDC source component for Microsoft supports all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, which are mapped to the correct SSIS data types.</span></span>  
  
## <a name="troubleshooting-the-cdc-source"></a><span data-ttu-id="7f309-129">Solucionar problemas del origen de CDC</span><span class="sxs-lookup"><span data-stu-id="7f309-129">Troubleshooting the CDC Source</span></span>  
 <span data-ttu-id="7f309-130">A continuación se muestra información para solucionar problemas del origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="7f309-130">The following contains information on troubleshooting the CDC source.</span></span>  
  
### <a name="use-this-script-to-isolate-problems-and-reproduce-them-in-sql-server-management-studio"></a><span data-ttu-id="7f309-131">Use este script para aislar los problemas y reproducirlos en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f309-131">Use this script to isolate problems and reproduce them in SQL Server Management Studio</span></span>  
 <span data-ttu-id="7f309-132">La operación de origen de CDC se rige por la operación de la tarea Control CDC ejecutada antes de invocar al origen de CDC.</span><span class="sxs-lookup"><span data-stu-id="7f309-132">The CDC source operation is governed by the operation of the CDC Control task executed before invoking the CDC source.</span></span> <span data-ttu-id="7f309-133">La tarea Control CDC prepara el valor de la variable de paquete de estado CDC para contener los LSN inicial y final.</span><span class="sxs-lookup"><span data-stu-id="7f309-133">The CDC Control task prepares the value of the CDC state package variable to contain the start and end LSNs.</span></span> <span data-ttu-id="7f309-134">Realiza la función equivalente a la del script siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f309-134">It performs function equivalent to the following script:</span></span>  
  
```  
use <cdc-enabled-database-name>  
               declare @start_lsn binary(10), @end_lsn binary(10)  
               set @start_lsn = sys.fn_cdc_increment_lsn(  
                       convert(binary(10),'0x' + '<value-from-state-cs>', 1))  
               set @end_lsn =   
                       convert(binary(10),'0x' + '<value-from-state-ce>', 1)  
               select * from cdc.fn_cdc_get_net_changes_dbo_Table1(@start_lsn,  
@end_lsn, '<mode>')  
```  
  
 <span data-ttu-id="7f309-135">donde:</span><span class="sxs-lookup"><span data-stu-id="7f309-135">where:</span></span>  
  
-   <span data-ttu-id="7f309-136">\<cdc-enabled-database-name> es el nombre de la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contiene las tablas de cambios.</span><span class="sxs-lookup"><span data-stu-id="7f309-136">\<cdc-enabled-database-name> is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database containing the change tables.</span></span>  
  
-   <span data-ttu-id="7f309-137">\<value-from-state-cs> es el valor que aparece en la variable de estado CDC como CS/\<value-from-state-cs>/ (CS representa el inicio del intervalo de procesamiento actual [Current-processing-range-Start]).</span><span class="sxs-lookup"><span data-stu-id="7f309-137">\<value-from-state-cs> is the value that appears in the CDC state variable as CS/\<value-from-state-cs>/ (CS stands for Current-processing-range-Start).</span></span>  
  
-   <span data-ttu-id="7f309-138">\<value-from-state-ce> es el valor que aparece en la variable de estado CDC como CE/\<value-from-state-cs>/ (CE representa el final del intervalo de procesamiento actual [Current-processing-range-End]).</span><span class="sxs-lookup"><span data-stu-id="7f309-138">\<value-from-state-ce> is the value that appears in the CDC state variable as CE/\<value-from-state-cs>/ (CE stands for Current-processing-range-End).</span></span>  
  
-   <span data-ttu-id="7f309-139">\<mode> son los modos de procesamiento de CDC.</span><span class="sxs-lookup"><span data-stu-id="7f309-139">\<mode> are the CDC processing modes.</span></span> <span data-ttu-id="7f309-140">Los modos de procesamiento tienen uno de los siguientes valores **Todo**, **Todo con valores antiguos**, **Neto**, **Neto con máscara de actualización**, **Neto con combinación**.</span><span class="sxs-lookup"><span data-stu-id="7f309-140">The processing modes have one of the following values **All**, **All with Old Values**, **Net**, **Net with Update Mask**, **Net with Merge**.</span></span>  
  
 <span data-ttu-id="7f309-141">Este script ayuda a aislar los problemas reproduciéndolos en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], donde resulta sencillo reproducir e identificar los errores.</span><span class="sxs-lookup"><span data-stu-id="7f309-141">This script helps isolate problems by reproducing them in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], where it is easy to reproduce and identify errors.</span></span>  
  
#### <a name="sql-server-error-message"></a><span data-ttu-id="7f309-142">Mensaje de error de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7f309-142">SQL Server Error Message</span></span>  
 <span data-ttu-id="7f309-143">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]podría devolver el mensaje siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f309-143">The following message may be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="7f309-144">**Se ha especificado un número insuficiente de argumentos para el procedimiento o función cdc.fn_cdc_get_net_changes_ \<..>.**</span><span class="sxs-lookup"><span data-stu-id="7f309-144">**An insufficient number of arguments were supplied for the procedure or function cdc.fn_cdc_get_net_changes_\<..>.**</span></span>  
  
 <span data-ttu-id="7f309-145">Este error indica que falta un argumento.</span><span class="sxs-lookup"><span data-stu-id="7f309-145">This error does not indicate that an argument is missing.</span></span> <span data-ttu-id="7f309-146">Indica que los valores de LSN inicial o final de la variable de estado CDC no son válidos.</span><span class="sxs-lookup"><span data-stu-id="7f309-146">It means that the start or end LSN values in the CDC state variable are invalid.</span></span>  
  
## <a name="configuring-the-cdc-source"></a><span data-ttu-id="7f309-147">Configurar el origen de CDC</span><span class="sxs-lookup"><span data-stu-id="7f309-147">Configuring the CDC Source</span></span>  
 <span data-ttu-id="7f309-148">Puede configurar el origen de CDC mediante programación o través del Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="7f309-148">You can configure the CDC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="7f309-149">Para obtener más información, vea uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="7f309-149">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7f309-150">Editor de origen de CDC &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="7f309-150">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="7f309-151">Editor de origen de CDC &#40;página Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="7f309-151">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="7f309-152">Editor de origen de CDC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="7f309-152">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="7f309-153">El cuadro de diálogo **Editor avanzado** contiene las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7f309-153">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="7f309-154">Para abrir el cuadro de diálogo **Editor avanzado** :</span><span class="sxs-lookup"><span data-stu-id="7f309-154">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="7f309-155">En la pantalla **Flujo de datos** del proyecto de [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , haga clic con el botón secundario en el origen CDC y seleccione **Mostrar editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="7f309-155">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="7f309-156">Para obtener más información acerca de las propiedades que se pueden establecer en el cuadro de diálogo **Editor avanzado** , vea [CDC Source Custom Properties](cdc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7f309-156">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [CDC Source Custom Properties](cdc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f309-157">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7f309-157">In This Section</span></span>  
  
-   [<span data-ttu-id="7f309-158">Editor de origen de CDC &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="7f309-158">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="7f309-159">Editor de origen de CDC &#40;página Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="7f309-159">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="7f309-160">Editor de origen de CDC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="7f309-160">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="7f309-161">Propiedades personalizadas del origen de CDC</span><span class="sxs-lookup"><span data-stu-id="7f309-161">CDC Source Custom Properties</span></span>](cdc-source-custom-properties.md)  
  
-   [<span data-ttu-id="7f309-162">Extraer datos de modificaciones mediante el origen de CDC</span><span class="sxs-lookup"><span data-stu-id="7f309-162">Extract Change Data Using the CDC Source</span></span>](cdc-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="7f309-163">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="7f309-163">Related Content</span></span>  
  
-   <span data-ttu-id="7f309-164">Entrada del blog, sobre [Modos de procesamiento para el origen CDC](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/), en mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="7f309-164">Blog entry, [Processing Modes for the CDC Source](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/), on mattmasson.com.</span></span>  
  
  
