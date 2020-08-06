---
title: Conectarse a los datos de origen (cliente de minería de datos para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- connections
ms.assetid: 548672ce-e403-4aca-b67a-c2c797f053dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4b4759d94043fdccacdf5b285de50697a18965e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669992"
---
# <a name="connect-to-source-data-data-mining-client-for-excel"></a><span data-ttu-id="5fb8b-102">Conectar con los datos de origen (Cliente de minería de datos para Excel)</span><span class="sxs-lookup"><span data-stu-id="5fb8b-102">Connect to Source Data (Data Mining Client for Excel)</span></span>
  <span data-ttu-id="5fb8b-103">En este tema se describe cómo crear y usar las conexiones utilizadas para almacenar modelos de minería de datos y para obtener acceso a datos externos almacenados en [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fb8b-103">This topic describes how to create and use connections used for storing data mining models, and for accessing external data stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5fb8b-104">**Conexiones de minería de datos.**</span><span class="sxs-lookup"><span data-stu-id="5fb8b-104">**Data mining connections.**</span></span> <span data-ttu-id="5fb8b-105">La conexión inicial que crea cuando inicia los complementos se usa para obtener acceso a los algoritmos, analizar los datos y almacenar modelos y estructuras de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-105">The initial connection that you create when you start the add-ins is used to access algorithms, analyze data, and store mining structure and models.</span></span>  
  
 <span data-ttu-id="5fb8b-106">Se requiere una conexión a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para usar las herramientas de modelado y de visualización en los complementos, ya que los complementos dependen de los algoritmos y estructuras de datos que proporciona [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fb8b-106">A connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is required to use the modeling and visualization tools in the add-ins, because the add-ins depend on algorithms and data structures that are provided by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5fb8b-107">**Conexiones a los orígenes de datos externos.**</span><span class="sxs-lookup"><span data-stu-id="5fb8b-107">**Connections to external data sources.**</span></span> <span data-ttu-id="5fb8b-108">También puede crear conexiones a datos externos mientras crea modelos o guarda resultados.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-108">You can also create connections to external data as you are building models or saving the results.</span></span> <span data-ttu-id="5fb8b-109">Por ejemplo, puede crear un modelo de minería de datos en un servidor y, a continuación, realizar una consulta de predicción a partir de ese modelo de minería de datos usando los datos almacenados en otra instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], en una tabla de datos de Excel o en un origen de datos externo, como [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-109">For example, you can create a data mining model on one server, and then perform a prediction query against the data mining model by using data stored in another instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], in an Excel data table, or in an external data source such as [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span></span> <span data-ttu-id="5fb8b-110">Cada vez que obtenga acceso al nuevo origen de datos, se le pedirá que cree una conexión mediante un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-110">Each time that you access a new data source, you will be prompted to create a connection by using a dialog box.</span></span>  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq2"></a> <span data-ttu-id="5fb8b-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5fb8b-111">Prerequisites</span></span>  
 <span data-ttu-id="5fb8b-112">Esta versión de los complementos requiere que la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sea SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-112">This version of the add-ins requires that your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] be SQL Server 2012.</span></span> <span data-ttu-id="5fb8b-113">Si desea conectarse a una versión anterior de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], tiene a su disposición otra versión de los complementos.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-113">A separate version of the add-ins is available if you want to connect to an earlier version of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="5fb8b-114">Existen versiones de los complementos que admiten SQL Server 2005, SQL Server 2008 y SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-114">There are versions of the add-ins that support SQL Server 2005, SQL Server 2008, and SQL Server 2008 R2.</span></span>  
  
 <span data-ttu-id="5fb8b-115">Para conectarse a una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], debe tener permisos para obtener acceso al servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-115">To connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, you must have permissions to access the database server.</span></span> <span data-ttu-id="5fb8b-116">Además, las sesiones de minería de datos deben estar habilitadas y se debe contar con permisos de lectura o de lectura y escritura en los objetos de base de datos almacenados en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-116">Moreover, data mining sessions must be enabled, and you must have read or read/write permissions on database objects stored on the server.</span></span>  
  
##  <a name="creating-data-mining-server-connections"></a><a name="bkmk_connect"></a><span data-ttu-id="5fb8b-117">Crear conexiones del servidor de minería de datos</span><span class="sxs-lookup"><span data-stu-id="5fb8b-117">Creating Data Mining Server Connections</span></span>  
 <span data-ttu-id="5fb8b-118">El grupo **conexiones** del cliente de minería de datos para Excel y las herramientas de análisis de tabla para Excel proporciona herramientas para administrar las conexiones a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fb8b-118">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel provides tools for managing connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="5fb8b-119">Puede crear la conexión cuando instale el complemento o agregar una conexión posteriormente.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-119">You can create the connection when you install the add-in, or you can add a connection later.</span></span>  
  
-   <span data-ttu-id="5fb8b-120">Puede crear varias conexiones y modificar las conexiones en cualquier momento, a menos que esté en el proceso de crear o consultar un modelo.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-120">You can create multiple connections, and change connections at any time, unless you are in the process of creating or querying a model.</span></span>  
  
     <span data-ttu-id="5fb8b-121">No cambie ni cierre una conexión cuando se esté procesando un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-121">Do not change or close a connection when a data mining model is being processed.</span></span> <span data-ttu-id="5fb8b-122">El modelo de minería de datos podría perder datos o quedar inutilizable.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-122">The data mining model might lose data, or the model might become unusable.</span></span>  
  
-   <span data-ttu-id="5fb8b-123">Solo puede haber una conexión activa de cada vez.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-123">Only one connection can be active at a particular time.</span></span>  
  
### <a name="connections-in-the-excel-add-ins"></a><span data-ttu-id="5fb8b-124">Conexiones en los complementos de Excel</span><span class="sxs-lookup"><span data-stu-id="5fb8b-124">Connections in the Excel Add-ins</span></span>  
 <span data-ttu-id="5fb8b-125">El grupo **conexiones** del cliente de minería de datos para Excel y las herramientas de análisis de tabla para Excel es donde se administran las conexiones a una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fb8b-125">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel is where you manage connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
##### <a name="create-a-new-server-connection-in-the-excel-add-ins"></a><span data-ttu-id="5fb8b-126">Crear una nueva conexión al servidor en los complementos de Excel</span><span class="sxs-lookup"><span data-stu-id="5fb8b-126">Create a new server connection in the Excel add-ins</span></span>  
  
1.  <span data-ttu-id="5fb8b-127">Haga clic en el botón **conexión** de la cinta de opciones **analizar** o **minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="5fb8b-127">Click the **Connection** button on the **Analyze** or **Data Mining** ribbon.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5fb8b-128">El texto del botón indica si existe una conexión.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-128">The text of the button indicates if a connection exists.</span></span> <span data-ttu-id="5fb8b-129">Cuando no se ha realizado ninguna conexión en la hoja de cálculo, el botón contiene el texto " \<No connection> ." Si anteriormente se realizó una conexión en el libro, el nombre de esa conexión aparece en el botón.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-129">When no connection has been made in the worksheet, the button contains the text "\<No connection>." If a connection was previously made in the workbook, the name of that connection appears in the button.</span></span>  
  
2.  <span data-ttu-id="5fb8b-130">En el cuadro de diálogo **Analysis Services conexiones** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-130">In the **Analysis Services Connections** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="5fb8b-131">En el cuadro de diálogo **nueva conexión de Analysis Services** , escriba el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-131">In the **New Analysis Services Connection** dialog box, type the name of the server.</span></span>  
  
4.  <span data-ttu-id="5fb8b-132">Especifique el método de autenticación.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-132">Specify the authentication method.</span></span>  
  
5.  <span data-ttu-id="5fb8b-133">Seleccione una base de datos en la lista desplegable **nombre del catálogo** .</span><span class="sxs-lookup"><span data-stu-id="5fb8b-133">Select a database from the **Catalog name** drop-down list.</span></span> <span data-ttu-id="5fb8b-134">Si no existe ninguna base de datos en la instancia, seleccione **(valor predeterminado)**.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-134">If no database exists on the instance, select **(default)**.</span></span>  
  
6.  <span data-ttu-id="5fb8b-135">Escriba un nombre descriptivo para la conexión.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-135">Type a friendly name for the connection.</span></span>  
  
7.  <span data-ttu-id="5fb8b-136">Haga clic en **probar conexión** para comprobar que el servidor y la base de datos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-136">Click **Test Connection** to verify that the server and database are available.</span></span>  
  
8.  <span data-ttu-id="5fb8b-137">Haga clic en **Aceptar**y, a continuación, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-137">Click **OK**, and then click **Close**.</span></span>  
  
### <a name="connections-using-a-web-service"></a><span data-ttu-id="5fb8b-138">Conexiones mediante un servicio web</span><span class="sxs-lookup"><span data-stu-id="5fb8b-138">Connections using a Web Service</span></span>  
 <span data-ttu-id="5fb8b-139">Si usa una arquitectura de cliente ligero para habilitar la exploración de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubos y datos, también puede configurar una conexión a un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] servidor a través de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-139">If you are using a thin-client architecture to enable browsing of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubes and data, you can also configure a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server through Web services.</span></span> <span data-ttu-id="5fb8b-140">Para obtener información acerca de cómo definir un cliente basado en web, vea los Libros en pantalla de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fb8b-140">For information about how to define a Web-based client, see [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="5fb8b-141">Si dispone de acceso a un servidor configurado para servicios Web, podrá especificar el tipo de conexión cuando la cree por primera vez.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-141">If you have access to a server that has been configured for Web services, you can specify the connection type when you first create the connection.</span></span>  
  
##### <a name="create-an-http-connection-to-analysis-services"></a><span data-ttu-id="5fb8b-142">Crear una conexión HTTP a Analysis Services</span><span class="sxs-lookup"><span data-stu-id="5fb8b-142">Create an HTTP connection to Analysis Services</span></span>  
  
1.  <span data-ttu-id="5fb8b-143">Abra el cuadro de diálogo **nueva conexión de Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="5fb8b-143">Open the **New Analysis Services Connection** dialog box.</span></span>  
  
2.  <span data-ttu-id="5fb8b-144">Para el nombre del servidor, escriba http:// seguido de la dirección URL asignada al servidor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fb8b-144">For the server name, type http:// followed by the URL assigned to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span>  
  
3.  <span data-ttu-id="5fb8b-145">Escriba el nombre de usuario y la contraseña necesarios para obtener acceso al servicio web.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-145">Type the user name and the password that is required to access the Web service.</span></span>  
  
### <a name="connections-in-the-visio-add-in"></a><span data-ttu-id="5fb8b-146">Conexiones en el complemento de Visio</span><span class="sxs-lookup"><span data-stu-id="5fb8b-146">Connections in the Visio Add-In</span></span>  
 <span data-ttu-id="5fb8b-147">A diferencia de Excel, Visio no dispone de una cinta de opciones de herramientas ni de botones específicos para crear o supervisar conexiones.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-147">Unlike Excel, Visio does not provide a tool ribbon, and there are no buttons specifically for creating or monitoring connections.</span></span> <span data-ttu-id="5fb8b-148">En su lugar, la conexión de datos se crea cuando se selecciona por vez primera una forma de minería de datos y se coloca en una página de Visio.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-148">Instead, the data connection is created when you first select a data mining shape and drop it onto a Visio page.</span></span> <span data-ttu-id="5fb8b-149">Un asistente le solicitará que seleccione el modelo para la forma y que establezca otras opciones.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-149">A wizard will prompt you to select the model for the shape and to set other options.</span></span>  
  
 <span data-ttu-id="5fb8b-150">Si ya ha usado conexiones a un origen de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en Excel con anterioridad, estas aparecen como posibles orígenes de datos entre los que puede elegir.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-150">If you have previously used a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source in Excel, these connections are listed as possible data sources from which to select.</span></span>  
  
##### <a name="create-a-connection-for-a-visio-shape"></a><span data-ttu-id="5fb8b-151">Crear una conexión para una forma de Visio</span><span class="sxs-lookup"><span data-stu-id="5fb8b-151">Create a connection for a Visio shape</span></span>  
  
1.  <span data-ttu-id="5fb8b-152">Abra la plantilla de minería de datos y seleccione una de las formas de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-152">Open the Data Mining Template, and select one of the data mining shapes.</span></span>  
  
2.  <span data-ttu-id="5fb8b-153">Arrastre la forma y colóquela en una página en blanco.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-153">Drag and drop the shape to a blank page.</span></span>  
  
3.  <span data-ttu-id="5fb8b-154">En el cuadro de diálogo **seleccionar un origen de datos** , seleccione un origen de datos de la lista o haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-154">In the **Select a data source** dialog box, select a data source from the list, or click **New**.</span></span>  
  
4.  <span data-ttu-id="5fb8b-155">Si selecciona **nuevo**, siga el procedimiento descrito anteriormente para especificar un nombre de servidor y de catálogo, o para conectarse a través de un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-155">If you select **New**, follow the procedure that is described earlier to specify a server and catalog name, or to connect through a Web service.</span></span>  
  
##  <a name="changing-connections"></a><a name="bkmk_change"></a><span data-ttu-id="5fb8b-156">Cambiar conexiones</span><span class="sxs-lookup"><span data-stu-id="5fb8b-156">Changing Connections</span></span>  
 <span data-ttu-id="5fb8b-157">Es posible crear varias conexiones en la misma hoja de cálculo, aunque sólo puede haber una activa en cada momento.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-157">You can create multiple connections in the same worksheet, but only one connection can be active at a time.</span></span> <span data-ttu-id="5fb8b-158">El nombre de la conexión actual se muestra en el botón **conexión** .</span><span class="sxs-lookup"><span data-stu-id="5fb8b-158">The name of the current connection is displayed in the **Connection** button.</span></span>  
  
 <span data-ttu-id="5fb8b-159">En el cliente de minería de datos para Excel, también puede comprobar la cadena de conexión y el estado de la conexión actual haciendo clic en **seguimiento** y, a continuación, haciendo clic en **conexión actual**.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-159">In the Data Mining Client for Excel, you can also verify the connection string and status for the current connection by clicking **Trace** and then clicking **Current Connection**.</span></span>  
  
#### <a name="use-a-different-server-connection"></a><span data-ttu-id="5fb8b-160">Usar una conexión al servidor diferente</span><span class="sxs-lookup"><span data-stu-id="5fb8b-160">Use a different server connection</span></span>  
  
1.  <span data-ttu-id="5fb8b-161">Haga clic en **conexión**.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-161">Click **Connection**.</span></span>  
  
2.  <span data-ttu-id="5fb8b-162">En el panel **Analysis Services conexiones** , seleccione una conexión de la lista **otras conexiones** y haga clic en **convertir en actual**.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-162">In the **Analysis Services Connections** pane, select a connection from the **Other Connections** list, and click **Make Current**.</span></span>  
  
3.  <span data-ttu-id="5fb8b-163">Haga clic en **probar conexión** para comprobar que la conexión está disponible.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-163">Click **Test Connection** to verify that the connection is available.</span></span>  
  
 <span data-ttu-id="5fb8b-164">Una vez que un modelo de minería de datos ha finalizado el procesamiento, los resultados se almacenan localmente; si se cierra la conexión con un servidor y se establece la conexión con otro, los datos no resultarán afectados.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-164">After a mining model has finished processing, the results are stored locally, and there is no effect on the data if you close the connection to one server and then connect to another server.</span></span> <span data-ttu-id="5fb8b-165">No obstante, se debe evitar el cambio de conexión o la pérdida de la misma mientras se está procesando un modelo de minería de datos, ya que los datos podrían resultar dañados.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-165">However, you should avoid changing connections or losing the connection when a data mining model is being processed, because this could corrupt data.</span></span>  
  
#### <a name="modify-an-existing-server-connection"></a><span data-ttu-id="5fb8b-166">Modificar una conexión al servidor existente</span><span class="sxs-lookup"><span data-stu-id="5fb8b-166">Modify an existing server connection</span></span>  
  
1.  <span data-ttu-id="5fb8b-167">No puede modificar una conexión existente; si desea conectarse a una base de datos o a un servidor diferente, debe crear una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-167">You cannot modify an existing connection; if you want to connect to a different database or a different server, you should create a new connection.</span></span>  
  
2.  <span data-ttu-id="5fb8b-168">Si debe modificar la cadena de conexión para aumentar el tiempo de espera de consulta o para agregar otros parámetros específicos para la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], una opción es modificar el archivo .dmc, donde se almacena la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-168">If you must modify the connection string to increase the query timeout or add other parameters specific to your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], one option is to edit the .dmc file, where the connection string is stored.</span></span>  
  
     <span data-ttu-id="5fb8b-169">\<drive:>\Users \\<\> el complemento de minería de datos \AppData\Local\Microsoft\Data</span><span class="sxs-lookup"><span data-stu-id="5fb8b-169">\<drive:>\Users\\<myusername\>\AppData\Local\Microsoft\Data Mining Add-in</span></span>  
  
##  <a name="connecting-to-external-data-sources"></a><a name="bkmk_extconnections"></a><span data-ttu-id="5fb8b-170">Conexión a orígenes de datos externos</span><span class="sxs-lookup"><span data-stu-id="5fb8b-170">Connecting to External Data Sources</span></span>  
 <span data-ttu-id="5fb8b-171">Mientras que las herramientas de la cinta de opciones **analizar** funcionan exclusivamente con los datos de Excel, las herramientas de la cinta de opciones **minería de datos** permiten conectarse directamente a orígenes de datos externos para usarlos como entradas para el modelo o para el muestreo.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-171">Whereas the tools in the **Analyze** ribbon work exclusively with data in Excel, the tools in the **Data Mining** ribbon let you connect directly to external data sources to use as inputs for your model, or for sampling.</span></span>  
  
 <span data-ttu-id="5fb8b-172">Las siguientes herramientas de estos complementos admiten el uso de datos externos para minería de datos:</span><span class="sxs-lookup"><span data-stu-id="5fb8b-172">The following tools in these add-ins support use of external data for data mining:</span></span>  
  
-   [<span data-ttu-id="5fb8b-173">&#40;de datos de ejemplo SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-173">Sample Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](sample-data-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="5fb8b-174">Asistente para clasificar &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-174">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="5fb8b-175">Asistente para estimación &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-175">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="5fb8b-176">Asistente para clúster &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-176">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="5fb8b-177">Asistente para previsión &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-177">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="5fb8b-178">Crear &#40;de estructura de minería de datos SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-178">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="5fb8b-179">Gráfico de precisión &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-179">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="5fb8b-180">Gráfico de beneficios &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-180">Profit Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](profit-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="5fb8b-181">Matriz de clasificación &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-181">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
### <a name="using-analysis-services-as-a-data-source"></a><span data-ttu-id="5fb8b-182">Usar Analysis Services como un origen de datos</span><span class="sxs-lookup"><span data-stu-id="5fb8b-182">Using Analysis Services as a Data Source</span></span>  
 <span data-ttu-id="5fb8b-183">No puede tener acceso directamente a los datos almacenados en un cubo o modelo tabular de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fb8b-183">You cannot directly access data stored in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube or tabular model.</span></span> <span data-ttu-id="5fb8b-184">En su lugar, cree una conexión en Excel al servidor de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y use los datos para crear un modelo.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-184">Instead, create a connection in Excel to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, and use the data to create a model.</span></span>  
  
### <a name="relational-data-sources"></a><span data-ttu-id="5fb8b-185">Orígenes de datos relacionales</span><span class="sxs-lookup"><span data-stu-id="5fb8b-185">Relational Data Sources</span></span>  
 <span data-ttu-id="5fb8b-186">Si desea usar los datos de un origen relacional como entrada para el modelo, puede conectarse a las versiones siguientes de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="5fb8b-186">If you want to use data from a relational source as input to your model, you can connect to the following versions of SQL Server:</span></span>  
  
-   <span data-ttu-id="5fb8b-187">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="5fb8b-187">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="5fb8b-188">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5fb8b-188">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="5fb8b-189">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="5fb8b-189">SQL Server 2012</span></span>  
  
 <span data-ttu-id="5fb8b-190">También puede obtener datos de cualquier otro origen de datos relacional que admita [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="5fb8b-190">You can also get data from any other relational data source that is supported as a data source by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="5fb8b-191">Para obtener información sobre los orígenes de datos admitidos, vea [orígenes de datos en modelos multidimensionales](multidimensional-models/data-sources-in-multidimensional-models.md) .</span><span class="sxs-lookup"><span data-stu-id="5fb8b-191">For information about supported data sources, see [Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md)</span></span>  
  
 <span data-ttu-id="5fb8b-192">Tenga en cuenta que los siguientes tipos de datos no se pueden usar para minería de datos y producirán un error si se incluyen al crear un modelo:</span><span class="sxs-lookup"><span data-stu-id="5fb8b-192">Note that the following data types cannot be used for data mining and will result in an error if included when you build a model:</span></span>  
  
-   <span data-ttu-id="5fb8b-193">ntext</span><span class="sxs-lookup"><span data-stu-id="5fb8b-193">ntext</span></span>  
  
-   <span data-ttu-id="5fb8b-194">binary</span><span class="sxs-lookup"><span data-stu-id="5fb8b-194">binary</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb8b-195">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fb8b-195">See Also</span></span>  
 [<span data-ttu-id="5fb8b-196">Seguimiento &#40;cliente de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb8b-196">Trace &#40;Data Mining Client for Excel&#41;</span></span>](trace-data-mining-client-for-excel.md)  
  
  
