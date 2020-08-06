---
title: Ejecutar el Asistente para importación y exportación de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Import and Export Wizard
- starting SQL Server Import and Export Wizard
- Import and Export Wizard
- starting Import and Export Wizard
ms.assetid: 5fc4f6d1-1f6f-444e-9aeb-827f85e1c405
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 008c541b1f1a295057b0ee7cc384982627b9689a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674911"
---
# <a name="run-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="a8171-102">Ejecutar el Asistente para importación y exportación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8171-102">Run the SQL Server Import and Export Wizard</span></span>
  <span data-ttu-id="a8171-103">El Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona el método más sencillo para copiar datos entre orígenes de datos y crear paquetes básicos.</span><span class="sxs-lookup"><span data-stu-id="a8171-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard provides the simplest method of copying data between data sources and of constructing basic packages.</span></span> <span data-ttu-id="a8171-104">Para obtener más información sobre el asistente, vea [SQL Server Asistente para importación y exportación](import-and-export-data-with-the-sql-server-import-and-export-wizard.md)de.</span><span class="sxs-lookup"><span data-stu-id="a8171-104">For more information about the wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="a8171-105">Para ver un vídeo en el que se muestra cómo usar el Asistente para importación y exportación de SQL Server para crear un paquete que exporta datos de una base de datos de SQL Server a una hoja de cálculo de Microsoft Excel, vea [exportar datos de SQL Server a Excel (SQL Server vídeo)](https://go.microsoft.com/fwlink/?LinkId=131024).</span><span class="sxs-lookup"><span data-stu-id="a8171-105">For a video that demonstrates how to use the SQL Server Import and Export Wizard to create a package that exports data from a SQL Server database to a Microsoft Excel spreadsheet, see [Exporting SQL Server Data to Excel (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131024).</span></span>  
  
### <a name="to-start-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="a8171-106">Para iniciar el Asistente para importación y exportación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8171-106">To start the SQL Server Import and Export Wizard</span></span>  
  
-   <span data-ttu-id="a8171-107">En el menú **Inicio** , seleccione **todos los programas**,**Microsoft SQL Server** y, a continuación, haga clic en **importar y exportar datos**.</span><span class="sxs-lookup"><span data-stu-id="a8171-107">On the **Start** menu, point to **All Programs**, point to**Microsoft SQL Server** , and then click **Import and Export Data**.</span></span>  
  
     <span data-ttu-id="a8171-108">O bien</span><span class="sxs-lookup"><span data-stu-id="a8171-108">-or-</span></span>  
  
     <span data-ttu-id="a8171-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , haga clic con el botón secundario en la carpeta **paquetes SSIS** y, a continuación, haga clic en **Asistente para SSISImport y exportar**.</span><span class="sxs-lookup"><span data-stu-id="a8171-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the **SSIS Packages** folder, and then click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="a8171-110">O bien</span><span class="sxs-lookup"><span data-stu-id="a8171-110">-or-</span></span>  
  
     <span data-ttu-id="a8171-111">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , en el menú **proyecto** , haga clic en **Asistente para SSISImport y exportar**.</span><span class="sxs-lookup"><span data-stu-id="a8171-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Project** menu, click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="a8171-112">O bien</span><span class="sxs-lookup"><span data-stu-id="a8171-112">-or-</span></span>  
  
     <span data-ttu-id="a8171-113">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , conéctese al [!INCLUDE[ssDE](../../includes/ssde-md.md)] tipo de servidor, expanda bases de datos, haga clic con el botón secundario en una base de datos, seleccione **tareas**y, a continuación, haga clic en **importar datos** o **exportar datos**.</span><span class="sxs-lookup"><span data-stu-id="a8171-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] server type, expand Databases, right-click a database, point to **Tasks**, and then click **Import Data** or **Export data**.</span></span>  
  
     <span data-ttu-id="a8171-114">O bien</span><span class="sxs-lookup"><span data-stu-id="a8171-114">-or-</span></span>  
  
     <span data-ttu-id="a8171-115">En una ventana de símbolo del sistema, ejecute DTSWizard.exe, ubicado en C:\Archivos de programa\Microsoft SQL Server\100\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="a8171-115">In a command prompt window, run DTSWizard.exe, located in C:\Program Files\Microsoft SQL Server\100\DTS\Binn.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8171-116">En un equipo de 64 bits, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instala la versión de 64 bits del Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (DTSWizard.exe).</span><span class="sxs-lookup"><span data-stu-id="a8171-116">On a 64-bit computer, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs the 64-bit version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard (DTSWizard.exe).</span></span> <span data-ttu-id="a8171-117">Sin embargo, algunos orígenes de datos, como Access o Excel, solo tienen un proveedor de 32 bits disponible.</span><span class="sxs-lookup"><span data-stu-id="a8171-117">However, some data sources, such as Access or Excel, only have a 32-bit provider available.</span></span> <span data-ttu-id="a8171-118">Para trabajar con estos orígenes de datos, podría tener que instalar y ejecutar la versión de 32 bits del asistente.</span><span class="sxs-lookup"><span data-stu-id="a8171-118">To work with these data sources, you might have to install and run the 32-bit version of the wizard.</span></span> <span data-ttu-id="a8171-119">Para instalar la versión de 32 bits del asistente, seleccione Herramientas cliente o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="a8171-119">To install the 32-bit version of the wizard, select either Client Tools or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] during setup.</span></span>  
  
### <a name="to-import-or-export-data-by-using-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="a8171-120">Para importar o exportar datos con el Asistente para importación y exportación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8171-120">To import or export data by using the SQL Server Import and Export Wizard</span></span>  
  
1.  <span data-ttu-id="a8171-121">Inicie el Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8171-121">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard.</span></span>  
  
2.  <span data-ttu-id="a8171-122">En las páginas del asistente correspondientes, seleccione un origen y un destino para los datos.</span><span class="sxs-lookup"><span data-stu-id="a8171-122">On the corresponding wizard pages, select a data source and a data destination.</span></span>  
  
     <span data-ttu-id="a8171-123">Los orígenes de datos disponibles incluyen proveedores de datos [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], proveedores OLE DB, proveedores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, proveedores de [!INCLUDE[vstecado](../../includes/vstecado-md.md)], Microsoft Office Excel, Microsoft Office Access y el origen de archivo plano.</span><span class="sxs-lookup"><span data-stu-id="a8171-123">The available data sources include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client providers, [!INCLUDE[vstecado](../../includes/vstecado-md.md)] providers, Microsoft Office Excel, Microsoft Office Access, and the Flat File source.</span></span> <span data-ttu-id="a8171-124">Dependiendo del origen, se establecen opciones tales como el modo de autenticación, el nombre de servidor, el nombre de base de datos y el formato de archivos.</span><span class="sxs-lookup"><span data-stu-id="a8171-124">Depending on the source, you set options such as the authentication mode, server name, database name, and file format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8171-125">El Proveedor OLE DB de [!INCLUDE[msCoName](../../includes/msconame-md.md)] para Oracle no admite los siguientes tipos de datos de Oracle: BLOB, CLOB, NCLOB, BFILE y UROWID.</span><span class="sxs-lookup"><span data-stu-id="a8171-125">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Oracle does not support the Oracle BLOB, CLOB, NCLOB, BFILE, and UROWID data types.</span></span> <span data-ttu-id="a8171-126">Por consiguiente, el origen OLE DB no puede extraer datos de tablas que contengan columnas con estos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="a8171-126">Therefore, the OLE DB source cannot extract data from tables that contain columns with these data types.</span></span>  
  
     <span data-ttu-id="a8171-127">Los destinos de datos disponibles incluyen los proveedores de datos [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], proveedores OLE DB, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access y el destino de archivo plano.</span><span class="sxs-lookup"><span data-stu-id="a8171-127">The available data destinations include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access, and the Flat File destination.</span></span>  
  
3.  <span data-ttu-id="a8171-128">Establezca las opciones para el tipo de destino que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a8171-128">Set the options for the type of destination that you selected.</span></span>  
  
     <span data-ttu-id="a8171-129">Si el destino es una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8171-129">If the destination is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database you can specify the following:</span></span>  
  
    -   <span data-ttu-id="a8171-130">Indicar si se debe crear una nueva base de datos y establecer las propiedades de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a8171-130">Indicate whether to create a new database and set the database properties.</span></span> <span data-ttu-id="a8171-131">Las siguientes propiedades no pueden configurarse y el asistente usa los valores predeterminados especificados:</span><span class="sxs-lookup"><span data-stu-id="a8171-131">The following properties cannot be configured and the wizard uses the specified default values:</span></span>  
  
        |<span data-ttu-id="a8171-132">Propiedad</span><span class="sxs-lookup"><span data-stu-id="a8171-132">Property</span></span>|<span data-ttu-id="a8171-133">Value</span><span class="sxs-lookup"><span data-stu-id="a8171-133">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="a8171-134">Intercalación</span><span class="sxs-lookup"><span data-stu-id="a8171-134">Collation</span></span>|<span data-ttu-id="a8171-135">Latin1_General_CS_AS_KS_WS</span><span class="sxs-lookup"><span data-stu-id="a8171-135">Latin1_General_CS_AS_KS_WS</span></span>|  
        |<span data-ttu-id="a8171-136">modelo de recuperación</span><span class="sxs-lookup"><span data-stu-id="a8171-136">Recovery model</span></span>|<span data-ttu-id="a8171-137">Completo</span><span class="sxs-lookup"><span data-stu-id="a8171-137">Full</span></span>|  
        |<span data-ttu-id="a8171-138">Usar indización de texto completo</span><span class="sxs-lookup"><span data-stu-id="a8171-138">Use full-text indexing</span></span>|<span data-ttu-id="a8171-139">True</span><span class="sxs-lookup"><span data-stu-id="a8171-139">True</span></span>|  
  
    -   <span data-ttu-id="a8171-140">Seleccionar si se deben copiar datos desde tablas o vistas, o copiar los resultados de las consultas.</span><span class="sxs-lookup"><span data-stu-id="a8171-140">Select whether to copy data from tables or views, or to copy query results.</span></span>  
  
         <span data-ttu-id="a8171-141">Si desea hacer una consulta en los datos de origen y copiar los resultados, puede generar una consulta Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a8171-141">If you want to query the source data and copy the results, you can construct a Transact-SQL query.</span></span> <span data-ttu-id="a8171-142">Puede ingresar la consulta Transact-SQL manualmente o usar una consulta guardada en un archivo.</span><span class="sxs-lookup"><span data-stu-id="a8171-142">You can enter the Transact-SQL query manually or use a query saved to a file.</span></span> <span data-ttu-id="a8171-143">El asistente incluye una característica de exploración para buscar el archivo, y el asistente abre automáticamente el archivo y pega su contenido en la página del asistente al seleccionar el archivo.</span><span class="sxs-lookup"><span data-stu-id="a8171-143">The wizard includes a browse feature for locating the file, and the wizard automatically opens the file and pastes its content into the wizard page when you select the file.</span></span>  
  
         <span data-ttu-id="a8171-144">Si el origen es un proveedor [!INCLUDE[vstecado](../../includes/vstecado-md.md)], debe usar también la opción para copiar los resultados de las consultas, proporcionando la cadena DBCommand como consulta.</span><span class="sxs-lookup"><span data-stu-id="a8171-144">If the source is an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] provider you can also use the option to copy query results, providing the DBCommand string as the query.</span></span>  
  
         <span data-ttu-id="a8171-145">Si la información de origen es una vista, el Asistente para importación/exportación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] convierte automáticamente la vista en una tabla en el destino.</span><span class="sxs-lookup"><span data-stu-id="a8171-145">If the source data is a view, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically converts the view to a table in the destination.</span></span>  
  
    -   <span data-ttu-id="a8171-146">Indicar si la tabla de destino debe quitarse y volver a crearse posteriormente, y si se deben habilitar las inserciones de identidad.</span><span class="sxs-lookup"><span data-stu-id="a8171-146">Indicate whether the destination table is dropped and then re-created, and whether to enable identity inserts.</span></span>  
  
    -   <span data-ttu-id="a8171-147">Indicar si se deben eliminar filas o anexar filas en una tabla de destino existente.</span><span class="sxs-lookup"><span data-stu-id="a8171-147">Indicate whether to delete rows or append rows in an existing destination table.</span></span> <span data-ttu-id="a8171-148">Si la tabla no existe, el Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la crea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a8171-148">If the table does not exist, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically creates it.</span></span>  
  
     <span data-ttu-id="a8171-149">Si el destino es un destino de archivo plano, puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8171-149">If the destination is a Flat File destination you can specify the following:</span></span>  
  
    -   <span data-ttu-id="a8171-150">Especificar el delimitador de fila en el archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="a8171-150">Specify the row delimiter in the destination file.</span></span>  
  
    -   <span data-ttu-id="a8171-151">Especificar el delimitador de columna en el archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="a8171-151">Specify the column delimiter in the destination file.</span></span>  
  
4.  <span data-ttu-id="a8171-152">Si se desea, seleccionar una tabla y cambiar las asignaciones entre las columnas de origen y de destino, o cambiar los metadatos de las columnas de destino:</span><span class="sxs-lookup"><span data-stu-id="a8171-152">(Optional) Select one table and change the mappings between source and destination columns, or change the metadata of destination columns:</span></span>  
  
    -   <span data-ttu-id="a8171-153">Asignar las columnas de origen a diferentes columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="a8171-153">Map source columns to different destination columns.</span></span>  
  
    -   <span data-ttu-id="a8171-154">Cambiar el tipo de datos en la columna de destino.</span><span class="sxs-lookup"><span data-stu-id="a8171-154">Change the data type in the destination column.</span></span>  
  
    -   <span data-ttu-id="a8171-155">Establecer la longitud de las columnas con tipos de datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a8171-155">Set the length of columns with character data types.</span></span>  
  
    -   <span data-ttu-id="a8171-156">Establecer la precisión y la escala de las columnas con tipos de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="a8171-156">Set the precision and scale of columns with numeric data types.</span></span>  
  
    -   <span data-ttu-id="a8171-157">Especifique si la columna puede contener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a8171-157">Specify whether the column can contain null values.</span></span>  
  
5.  <span data-ttu-id="a8171-158">Si se desea, seleccionar varias tablas y actualizar los metadatos y las opciones para aplicar a esas tablas:</span><span class="sxs-lookup"><span data-stu-id="a8171-158">(Optional) Select multiple tables, and update the metadata and options to apply to those tables:</span></span>  
  
    -   <span data-ttu-id="a8171-159">Seleccionar un esquema de destino existente o proporcionar un esquema nuevo al que asignar tablas.</span><span class="sxs-lookup"><span data-stu-id="a8171-159">Select an existing destination schema or provide a new schema to which to assign tables.</span></span>  
  
    -   <span data-ttu-id="a8171-160">Especificar si se habilitan las inserciones de identidades en las tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="a8171-160">Specify whether to enable identity inserts in destination tables.</span></span>  
  
    -   <span data-ttu-id="a8171-161">Especificar si se quitan y vuelven a crear las tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="a8171-161">Specify whether to drop and re-create destination tables.</span></span>  
  
    -   <span data-ttu-id="a8171-162">Especificar si se truncan las tablas de destino existentes.</span><span class="sxs-lookup"><span data-stu-id="a8171-162">Specify whether to truncate existing destination tables.</span></span>  
  
6.  <span data-ttu-id="a8171-163">Guardar y ejecutar un paquete.</span><span class="sxs-lookup"><span data-stu-id="a8171-163">Save and run a package.</span></span>  
  
     <span data-ttu-id="a8171-164">Si se inicia el asistente desde [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o desde el símbolo del sistema, el paquete se puede ejecutar de inmediato.</span><span class="sxs-lookup"><span data-stu-id="a8171-164">If the wizard is started from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the command prompt, the package can run immediately.</span></span> <span data-ttu-id="a8171-165">Opcionalmente, puede guardar el paquete en la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de datos **msdb** o en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="a8171-165">You can optionally save the package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** database or to the file system.</span></span> <span data-ttu-id="a8171-166">Para obtener más información acerca de la base de datos **msdb** , vea [Administración de paquetes &#40;servicio SSIS&#41;](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="a8171-166">For more information about the **msdb** database, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
     <span data-ttu-id="a8171-167">Al guardar el paquete, puede establecer su nivel de protección y, si el nivel utiliza una contraseña, proporcionarla.</span><span class="sxs-lookup"><span data-stu-id="a8171-167">When you save the package you can set the package protection level, and if the protection level uses a password, provide the password.</span></span> <span data-ttu-id="a8171-168">Para obtener más información acerca de los niveles de protección de paquetes, consulte [Access Control de datos confidenciales en paquetes](../security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="a8171-168">For more information about package protection levels, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
     <span data-ttu-id="a8171-169">Si se inicia el asistente desde un proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], el paquete no se puede ejecutar desde el asistente.</span><span class="sxs-lookup"><span data-stu-id="a8171-169">If the wizard is started from an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you cannot run the package from the wizard.</span></span> <span data-ttu-id="a8171-170">En lugar de ello, el paquete se agrega al proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] desde el cual se inició el asistente.</span><span class="sxs-lookup"><span data-stu-id="a8171-170">Instead, the package is added to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project from which you started the wizard.</span></span> <span data-ttu-id="a8171-171">En ese caso, se puede ejecutar el paquete en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8171-171">You can then run the package in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a8171-172">En [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , la opción para guardar el paquete creado por el asistente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="a8171-172">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8171-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8171-173">See Also</span></span>  
 <span data-ttu-id="a8171-174">[Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="a8171-174">[SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span></span>  
 [<span data-ttu-id="a8171-175">Crear paquetes en herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8171-175">Create Packages in SQL Server Data Tools</span></span>](../create-packages-in-sql-server-data-tools.md)  
  
  
