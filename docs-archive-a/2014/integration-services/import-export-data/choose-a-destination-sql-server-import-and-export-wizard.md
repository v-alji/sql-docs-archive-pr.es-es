---
title: Elegir un destino (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.chooseadestination.f1
ms.assetid: 1898be15-3e69-42d3-8ecb-3733c9f6c8e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf9b717ef9de20d84d32c18eb3caa4c54cad87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674940"
---
# <a name="choose-a-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="c3595-102">Elegir un destino (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c3595-102">Choose a Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="c3595-103">Use la página **elegir un destino** para especificar el destino de los datos que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="c3595-103">Use the **Choose a Destination** page to specify the destination of the data that you want to copy.</span></span>  
  
 <span data-ttu-id="c3595-104">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c3595-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="c3595-105">Para obtener información sobre las opciones para iniciar el asistente, así como los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c3595-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="c3595-106">La finalidad del Asistente para importación y exportación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="c3595-106">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="c3595-107">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="c3595-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="c3595-108">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="c3595-109">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c3595-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="c3595-110">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="c3595-110">Static Options</span></span>  
 <span data-ttu-id="c3595-111">**Destino**</span><span class="sxs-lookup"><span data-stu-id="c3595-111">**Destination**</span></span>  
 <span data-ttu-id="c3595-112">Elija el proveedor de datos que coincide con el formato de almacenamiento de datos del destino.</span><span class="sxs-lookup"><span data-stu-id="c3595-112">Choose the data provider that matches the data storage format of the destination.</span></span> <span data-ttu-id="c3595-113">Es posible que haya más de un proveedor disponible para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-113">There may be more than one provider available for your data source.</span></span> <span data-ttu-id="c3595-114">Por ejemplo, con puede [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, el proveedor de datos de .NET Framework para SQL Server o el proveedor de OLE DB de Microsoft para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c3595-114">For example, with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, the .NET Framework Data Provider for SQL Server, or the Microsoft OLE DB Provider for SQL Server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3595-115">Para guardar datos en un destino ODBC, seleccione el proveedor de datos de .NET Framework para ODBC.</span><span class="sxs-lookup"><span data-stu-id="c3595-115">To save data to an ODBC destination, select the .NET Framework Data Provider for ODBC.</span></span>  
  
 <span data-ttu-id="c3595-116">La propiedad **origen de datos** tiene un número variable de opciones, que cambian en función de los proveedores instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c3595-116">The **Data Source** property has a variable number of options, which change depending on the providers installed on the computer.</span></span> <span data-ttu-id="c3595-117">Las siguientes tablas enumeran las opciones que se aplican a algunos destinos frecuentemente utilizados.</span><span class="sxs-lookup"><span data-stu-id="c3595-117">The following tables list the options for some commonly used destinations.</span></span> <span data-ttu-id="c3595-118">Para otros proveedores, vea la documentación específica del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c3595-118">For other providers, see the provider-specific documentation.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="c3595-119">Opciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="c3595-119">Dynamic Options</span></span>  
 <span data-ttu-id="c3595-120">En las secciones siguientes se muestran las opciones disponibles para varios orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-120">The following sections show the options available for several data sources.</span></span> <span data-ttu-id="c3595-121">Aquí no encontrará todos los destinos disponibles en la lista desplegable Destino.</span><span class="sxs-lookup"><span data-stu-id="c3595-121">Not all the destinations that are available in the Destination drop-down are listed here.</span></span>  
  
### <a name="destination--sql-server-native-client-or-microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="c3595-122">Destino = Proveedor OLE DB de Microsoft para SQL Server o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c3595-122">Destination = SQL Server Native Client or Microsoft OLE DB Provider for SQL Server</span></span>  
 <span data-ttu-id="c3595-123">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="c3595-123">**Server name**</span></span>  
 <span data-ttu-id="c3595-124">Escriba el nombre del servidor que recibirá los datos o elija un servidor de la lista.</span><span class="sxs-lookup"><span data-stu-id="c3595-124">Type the name of the server to receive the data, or choose a server from the list.</span></span>  
  
 <span data-ttu-id="c3595-125">**Utilizar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="c3595-125">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="c3595-126">Especifique si el paquete debe utilizar la autenticación de Microsoft Windows para iniciar una sesión en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-126">Specify whether the package should use Microsoft Windows Authentication to log in to the database.</span></span> <span data-ttu-id="c3595-127">Para obtener una mayor seguridad, es recomendable utilizar la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c3595-127">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="c3595-128">**Utilizar autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="c3595-128">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="c3595-129">Especifique si el paquete debe usar la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticación de para iniciar sesión en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-129">Specify whether the package should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to log in to the database.</span></span> <span data-ttu-id="c3595-130">Si usa la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , debe proporcionar un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="c3595-130">If you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="c3595-131">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="c3595-131">**User name**</span></span>  
 <span data-ttu-id="c3595-132">Especifique un nombre de usuario para la conexión de la base de datos cuando utilice la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3595-132">Specify a user name for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="c3595-133">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="c3595-133">**Password**</span></span>  
 <span data-ttu-id="c3595-134">Proporcione la contraseña para la conexión de la base de datos cuando use la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3595-134">Provide the password for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="c3595-135">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="c3595-135">**Database**</span></span>  
 <span data-ttu-id="c3595-136">Seleccione en la lista de bases de datos de la instancia especificada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o cree una nueva base de datos haciendo clic en **nueva**.</span><span class="sxs-lookup"><span data-stu-id="c3595-136">Select from the list of databases on the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or create a new database by clicking **New**.</span></span>  
  
 <span data-ttu-id="c3595-137">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="c3595-137">**Refresh**</span></span>  
 <span data-ttu-id="c3595-138">Para restaurar la lista de bases de datos disponibles, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="c3595-138">Restore the list of available databases by clicking **Refresh**.</span></span>  
  
 <span data-ttu-id="c3595-139">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="c3595-139">**New**</span></span>  
 <span data-ttu-id="c3595-140">Cree una nueva base de datos de destino mediante el cuadro de diálogo **crear base de datos** .</span><span class="sxs-lookup"><span data-stu-id="c3595-140">Create a new destination database by using the **Create Database** dialog box.</span></span>  
  
### <a name="destination--flat-file-destination"></a><span data-ttu-id="c3595-141">Destino = Destino de archivo plano</span><span class="sxs-lookup"><span data-stu-id="c3595-141">Destination = Flat File Destination</span></span>  
 <span data-ttu-id="c3595-142">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="c3595-142">**File name**</span></span>  
 <span data-ttu-id="c3595-143">Especifique la ruta de acceso y el nombre de archivo correspondiente al archivo en el que almacenará los datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-143">Specify the path and file name for the file in which to store the data.</span></span> <span data-ttu-id="c3595-144">O bien, haga clic en **Examinar** para buscar un archivo.</span><span class="sxs-lookup"><span data-stu-id="c3595-144">Or, click **Browse** to locate a file.</span></span>  
  
 <span data-ttu-id="c3595-145">**Browse**</span><span class="sxs-lookup"><span data-stu-id="c3595-145">**Browse**</span></span>  
 <span data-ttu-id="c3595-146">Busque un archivo mediante el cuadro de diálogo **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c3595-146">Locate a file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="c3595-147">**Configuración regional**</span><span class="sxs-lookup"><span data-stu-id="c3595-147">**Locale**</span></span>  
 <span data-ttu-id="c3595-148">Especifique el Id. de configuración regional (LCID) que define el criterio de ordenación de los caracteres y el formato de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="c3595-148">Specify the locale ID (LCID) that defines character sort orders and date and time formatting.</span></span>  
  
 <span data-ttu-id="c3595-149">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="c3595-149">**Unicode**</span></span>  
 <span data-ttu-id="c3595-150">Indique si se va a utilizar Unicode.</span><span class="sxs-lookup"><span data-stu-id="c3595-150">Indicate whether to use Unicode.</span></span> <span data-ttu-id="c3595-151">Si utiliza Unicode, no es necesario que especifique una página de códigos.</span><span class="sxs-lookup"><span data-stu-id="c3595-151">If you use Unicode, you do not have to specify a code page.</span></span>  
  
 <span data-ttu-id="c3595-152">**Página de códigos**</span><span class="sxs-lookup"><span data-stu-id="c3595-152">**Code page**</span></span>  
 <span data-ttu-id="c3595-153">Especifique la página de códigos correspondiente al idioma que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="c3595-153">Specify the code page for the language you want to use.</span></span>  
  
 <span data-ttu-id="c3595-154">**Formato**</span><span class="sxs-lookup"><span data-stu-id="c3595-154">**Format**</span></span>  
 <span data-ttu-id="c3595-155">Indique si se utiliza formato delimitado, de ancho fijo o derecho irregular.</span><span class="sxs-lookup"><span data-stu-id="c3595-155">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="c3595-156">Value</span><span class="sxs-lookup"><span data-stu-id="c3595-156">Value</span></span>|<span data-ttu-id="c3595-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3595-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c3595-158">Delimitado</span><span class="sxs-lookup"><span data-stu-id="c3595-158">Delimited</span></span>|<span data-ttu-id="c3595-159">Las columnas se separan mediante un delimitador, que se especifica en la página **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="c3595-159">Columns are separated by a delimiter, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="c3595-160">Ancho fijo</span><span class="sxs-lookup"><span data-stu-id="c3595-160">Fixed width</span></span>|<span data-ttu-id="c3595-161">Las columnas tienen un ancho fijo.</span><span class="sxs-lookup"><span data-stu-id="c3595-161">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="c3595-162">Derecho irregular</span><span class="sxs-lookup"><span data-stu-id="c3595-162">Ragged right</span></span>|<span data-ttu-id="c3595-163">Los archivos de derecho irregular son archivos en los que todas las columnas tienen un ancho fijo, a excepción de la última, que está delimitada por el delimitador de filas.</span><span class="sxs-lookup"><span data-stu-id="c3595-163">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="c3595-164">**Calificador de texto**</span><span class="sxs-lookup"><span data-stu-id="c3595-164">**Text qualifier**</span></span>  
 <span data-ttu-id="c3595-165">Escriba el calificador de texto que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="c3595-165">Type the text qualifier to use.</span></span> <span data-ttu-id="c3595-166">Puede, por ejemplo, especificar que el texto de cada columna se encierre entre comillas.</span><span class="sxs-lookup"><span data-stu-id="c3595-166">For example, you can specify that each text column be surrounded with quotation marks.</span></span>  
  
 <span data-ttu-id="c3595-167">**Nombres de columna de la primera fila de datos**</span><span class="sxs-lookup"><span data-stu-id="c3595-167">**Column names in first data row**</span></span>  
 <span data-ttu-id="c3595-168">Indique si desea mostrar los nombres de las columnas de la primera fila de datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-168">Indicate whether you want to display column names in the first data row.</span></span>  
  
### <a name="destination--microsoft-excel"></a><span data-ttu-id="c3595-169">Destino = Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="c3595-169">Destination = Microsoft Excel</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3595-170">Seleccione **Microsoft Excel** solo si desea conectarse a un origen de datos que use Excel 2003 o una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="c3595-170">Select **Microsoft Excel** only if you want to connect to a data source that uses Excel 2003 or earlier.</span></span> <span data-ttu-id="c3595-171">Para conectarse a un origen de datos que usa Excel 2007, seleccione **Microsoft Office 12,0 acceso motor de base de datos proveedor de OLE DB**, haga clic en **propiedades**y, a continuación, en la pestaña **todo** del cuadro de diálogo Propiedades de **vínculo de datos** , para **propiedades extendidas**, escriba `Excel 12.0` .</span><span class="sxs-lookup"><span data-stu-id="c3595-171">To connect to a data source that uses Excel 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**, click **Properties**, and then on the **All** tab of the **Data Link Properties** dialog box, for **Extended Properties**, enter `Excel 12.0`.</span></span>  
  
 <span data-ttu-id="c3595-172">**Ruta de acceso del archivo Excel**</span><span class="sxs-lookup"><span data-stu-id="c3595-172">**Excel file path**</span></span>  
 <span data-ttu-id="c3595-173">Especifique la ruta de acceso y el nombre de archivo del libro en el que desea almacenar los datos (por ejemplo, C:\MyData.xls, \\\Sales\Database\Northwind.xls).</span><span class="sxs-lookup"><span data-stu-id="c3595-173">Specify the path and file name for the workbook in which to store the data (for example, C:\MyData.xls, \\\Sales\Database\Northwind.xls).</span></span> <span data-ttu-id="c3595-174">O bien, haga clic en **Examinar** para buscar un libro.</span><span class="sxs-lookup"><span data-stu-id="c3595-174">Or, click **Browse** to locate a workbook.</span></span>  
  
 <span data-ttu-id="c3595-175">**Browse**</span><span class="sxs-lookup"><span data-stu-id="c3595-175">**Browse**</span></span>  
 <span data-ttu-id="c3595-176">Busque un libro de Excel mediante el cuadro de diálogo **abrir** .</span><span class="sxs-lookup"><span data-stu-id="c3595-176">Locate an Excel workbook by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="c3595-177">**Versión de Excel**</span><span class="sxs-lookup"><span data-stu-id="c3595-177">**Excel version**</span></span>  
 <span data-ttu-id="c3595-178">Seleccione la versión de Excel que utiliza el libro de destino.</span><span class="sxs-lookup"><span data-stu-id="c3595-178">Select the version of Excel that is used by the destination workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3595-179">Al exportar datos a un destino de [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] , el asistente utiliza el componente Destino de Excel de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3595-179">When you export data to a [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] destination, the wizard uses the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Excel Destination component.</span></span> <span data-ttu-id="c3595-180">Para obtener información sobre algunas consideraciones de uso y problemas conocidos, vea [Excel Destination](../data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c3595-180">For information on some usage considerations and known issues, see [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
### <a name="destination--microsoft-access"></a><span data-ttu-id="c3595-181">Destino = Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="c3595-181">Destination = Microsoft Access</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3595-182">Seleccione **Microsoft Access** solo si desea conectarse a una base de datos que use Access 2003 o una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="c3595-182">Select **Microsoft Access** only if you want to connect to a database that uses Access 2003 or earlier.</span></span> <span data-ttu-id="c3595-183">Para conectarse a una base de datos que usa Access 2007, seleccione **Microsoft Office 12,0 Access motor de base de datos proveedor de OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="c3595-183">To connect to a database that uses Access 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**.</span></span>  
  
 <span data-ttu-id="c3595-184">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="c3595-184">**File name**</span></span>  
 <span data-ttu-id="c3595-185">Especifique la ruta de acceso y el nombre de archivo del archivo de base de datos en el que se almacenarán los datos (por ejemplo, C:\MyData.mdb, \\ \Sales\Database\Northwind.mdb).</span><span class="sxs-lookup"><span data-stu-id="c3595-185">Specify the path and file name for the database file in which to store the data (for example, C:\MyData.mdb, \\\Sales\Database\Northwind.mdb).</span></span> <span data-ttu-id="c3595-186">O bien, haga clic en **Examinar** para buscar un archivo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-186">Or, click **Browse** to locate a database file.</span></span>  
  
 <span data-ttu-id="c3595-187">**Browse**</span><span class="sxs-lookup"><span data-stu-id="c3595-187">**Browse**</span></span>  
 <span data-ttu-id="c3595-188">Busque el archivo de base de datos mediante el cuadro de diálogo **abrir** .</span><span class="sxs-lookup"><span data-stu-id="c3595-188">Browse to the database file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="c3595-189">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="c3595-189">**User name**</span></span>  
 <span data-ttu-id="c3595-190">Especifique un nombre de usuario válido para la conexión de base de datos si hay un archivo de información de grupo de trabajo asociado a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-190">Specify a valid user name for the database connection when a workgroup information file is associated with the database.</span></span>  
  
 <span data-ttu-id="c3595-191">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="c3595-191">**Password**</span></span>  
 <span data-ttu-id="c3595-192">Especifique una contraseña de usuario para la conexión de base de datos si hay un archivo de información de grupo de trabajo asociado a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3595-192">Provide the user's password for the database connection when a workgroup information file is associated with the database.</span></span> <span data-ttu-id="c3595-193">Sin embargo, si la base de datos está protegida con una misma contraseña para todos los usuarios, debe proporcionar este valor en el cuadro de diálogo **Propiedades del vínculo de datos** , al que se obtiene acceso desde el botón **Avanzadas** .</span><span class="sxs-lookup"><span data-stu-id="c3595-193">However, if the database is protected with a single password for all users, you must provide this value in the **Data Link Properties** dialog box, which is accessed from the **Advanced** button.</span></span>  
  
 <span data-ttu-id="c3595-194">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="c3595-194">**Advanced**</span></span>  
 <span data-ttu-id="c3595-195">Especifique las opciones avanzadas, como la contraseña de la base de datos o un archivo de información del grupo de trabajo no predeterminado, mediante el cuadro de diálogo **Propiedades de vínculo de datos**.</span><span class="sxs-lookup"><span data-stu-id="c3595-195">Specify advanced options, such as the database password or a non-default workgroup information file, by using the **Data Link Properties** dialog box.</span></span> <span data-ttu-id="c3595-196">Para obtener más información sobre las propiedades de proveedor OLE DB, busque en la sección sobre acceso a datos de [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="c3595-196">For more information about OLE DB provider properties, search in the Data Access section of the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
  
