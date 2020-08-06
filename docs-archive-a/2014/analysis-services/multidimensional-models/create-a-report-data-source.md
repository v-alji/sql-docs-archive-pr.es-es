---
title: Crear un origen de datos de informe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bd6662c7-ffbe-479d-8944-3dc858340998
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9205eac497fc047b471f5b80becec36495474d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748345"
---
# <a name="create-a-report-data-source"></a><span data-ttu-id="92f0a-102">Crear un origen de datos de informe</span><span class="sxs-lookup"><span data-stu-id="92f0a-102">Create a Report Data Source</span></span>
  <span data-ttu-id="92f0a-103">Para que Power View se conecte con un modelo multidimensional, es necesario crear una definición de origen de datos de informe compartido, también conocida como un archivo .rsds, en una biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="92f0a-103">In order for Power View to connect to a multidimensional model, you must create a shared report data source definition, also known as an .rsds file, in a SharePoint library.</span></span> <span data-ttu-id="92f0a-104">El archivo .rsds especifica el nombre de una instancia de servidor de Analysis Services, el tipo de conexión, la cadena de conexión y las credenciales utilizadas para conectarse con el modelo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="92f0a-104">The .rsds file specifies the name of an Analysis Services server instance, connection type, connection string, and credentials used to connect to the multidimensional model.</span></span> <span data-ttu-id="92f0a-105">Cuando un usuario hace clic en el archivo .rsds, se abre un nuevo informe de Power View vacío (un archivo .rdlx) en el explorador.</span><span class="sxs-lookup"><span data-stu-id="92f0a-105">When a user clicks on the .rsds, a new blank Power View report (an .rdlx file) opens in the browser.</span></span>  
  
 <span data-ttu-id="92f0a-106">Para crear una conexión .rsds, es necesario tener instalado SQL Server 2012 (o posterior) Reporting Services y el complemento Reporting Services para SharePoint 2010 o SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="92f0a-106">In order to create an .rsds connection, you must have SQL Server 2012 (or later) Reporting Services and the Reporting Services add-in for SharePoint 2010 or SharePoint 2013 installed.</span></span>  
  
## <a name="create-a-report-data-source-rsds-connection-to-a-multidimensional-model"></a><span data-ttu-id="92f0a-107">Crear una conexión de origen de datos de informe (.rsds) con un modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="92f0a-107">Create a Report Data Source (.rsds) connection to a multidimensional model</span></span>  
 <span data-ttu-id="92f0a-108">Antes de empezar, debe conocer:</span><span class="sxs-lookup"><span data-stu-id="92f0a-108">Before you begin, you need to know:</span></span>  
  
-   <span data-ttu-id="92f0a-109">El nombre de la instancia de servidor de Analysis Services que se está ejecutando en modo multidimensional.</span><span class="sxs-lookup"><span data-stu-id="92f0a-109">The name of the Analysis Services server instance running in Multidimensional mode.</span></span>  
  
-   <span data-ttu-id="92f0a-110">El nombre de la base de datos multidimensional con la que desea conectarse.</span><span class="sxs-lookup"><span data-stu-id="92f0a-110">The name of the multidimensional database you want to connect to.</span></span>  
  
-   <span data-ttu-id="92f0a-111">El nombre del cubo, si hay más de uno.</span><span class="sxs-lookup"><span data-stu-id="92f0a-111">The name of the cube, if there is more than one.</span></span>  
  
-   <span data-ttu-id="92f0a-112">(Opcional) Nombre de la perspectiva.</span><span class="sxs-lookup"><span data-stu-id="92f0a-112">(Optional) Perspective name.</span></span>  
  
-   <span data-ttu-id="92f0a-113">(Opcional) Identificador de configuración regional.</span><span class="sxs-lookup"><span data-stu-id="92f0a-113">(Optional) Locale Identifier.</span></span>  
  
#### <a name="to-create-a-shared-report-data-source-rsds-file-sharepoint-2010"></a><span data-ttu-id="92f0a-114">Para crear un archivo de origen de datos compartido (.rsds) (SharePoint 2010)</span><span class="sxs-lookup"><span data-stu-id="92f0a-114">To create a shared Report Data Source (.rsds) file (SharePoint 2010)</span></span>  
  
1.  <span data-ttu-id="92f0a-115">Haga clic en la pestaña **Documentos** de la cinta de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="92f0a-115">Click the **Documents** tab on the library ribbon.</span></span>  
  
2.  <span data-ttu-id="92f0a-116">Haga clic en **nuevo documento**  >  **origen de datos de informe**.</span><span class="sxs-lookup"><span data-stu-id="92f0a-116">Click **New Document** > **Report Data Source**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92f0a-117">Si no ve el elemento **Origen de datos de informe** en el menú, significa que no se ha habilitado el tipo de contenido del origen de datos de informe para esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="92f0a-117">If you do not see the **Report Data Source** item on the menu, the report data source content type has not been enabled for this library.</span></span> <span data-ttu-id="92f0a-118">Para obtener más información, vea [agregar tipos de contenido del servidor de informes a una biblioteca &#40;Reporting Services en el modo integrado de SharePoint&#41;](../../reporting-services/add-reporting-services-content-types-to-a-sharepoint-library.md).</span><span class="sxs-lookup"><span data-stu-id="92f0a-118">For more information, see [Add Report Server Content Types to a Library &#40;Reporting Services in SharePoint Integrated Mode&#41;](../../reporting-services/add-reporting-services-content-types-to-a-sharepoint-library.md).</span></span>  
  
3.  <span data-ttu-id="92f0a-119">En la página **Propiedades del origen de datos** , en **Nombre**, escriba un nombre para el archivo de conexión .rsds.</span><span class="sxs-lookup"><span data-stu-id="92f0a-119">On the **Data Source Properties** page, in **Name**, type a name for the connection .rsds file.</span></span>  
  
4.  <span data-ttu-id="92f0a-120">En **Tipo de origen de datos**, seleccione **Microsoft BI Semantic Model para Power View**.</span><span class="sxs-lookup"><span data-stu-id="92f0a-120">In **Data Source Type**, select **Microsoft BI Semantic Model for Power View**.</span></span>  
  
5.  <span data-ttu-id="92f0a-121">En **Cadena de conexión**, especifique el nombre del servidor de Analysis Services, el nombre de la base de datos, el nombre del cubo y los valores opcionales.</span><span class="sxs-lookup"><span data-stu-id="92f0a-121">In **Connection String**, specify the Analysis Services server name, database name, cube name, and any optional settings.</span></span>  
  
     <span data-ttu-id="92f0a-122">Cadena de conexión: `Data source=<servername>;initial catalog=<multidimensionaldatabasename>-ee;cube='<cubename>'`</span><span class="sxs-lookup"><span data-stu-id="92f0a-122">Connection String: `Data source=<servername>;initial catalog=<multidimensionaldatabasename>-ee;cube='<cubename>'`</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="92f0a-123">Si hay más de un cubo, es necesario especificar un nombre de cubo.</span><span class="sxs-lookup"><span data-stu-id="92f0a-123">If there is more than one cube, you must specify a cube name.</span></span>  
  
     <span data-ttu-id="92f0a-124">(Opcional) Los cubos pueden tener perspectivas que proporcionan a los usuarios unas vistas especiales en las que únicamente están visibles ciertas dimensiones y/o grupos de medidas en el cliente.</span><span class="sxs-lookup"><span data-stu-id="92f0a-124">(Optional) Cubes can have perspectives that provide users a select view where only certain dimensions and/or measure groups are visible in the client.</span></span> <span data-ttu-id="92f0a-125">Para especificar una perspectiva, escriba el nombre de esta como un valor de la propiedad Cube: `Data source=<servername>;initial catalog=<multidimensionaldatabasename>-ee;cube='<perspectivename>'`</span><span class="sxs-lookup"><span data-stu-id="92f0a-125">To specify a perspective, enter the perspective name as a value to the Cube property: `Data source=<servername>;initial catalog=<multidimensionaldatabasename>-ee;cube='<perspectivename>'`</span></span>  
  
     <span data-ttu-id="92f0a-126">(Opcional) Los cubos pueden tener traducciones de datos y metadatos especificados para varios idiomas dentro del modelo.</span><span class="sxs-lookup"><span data-stu-id="92f0a-126">(Optional) Cubes can have metadata and data translations specified for various languages within the model.</span></span> <span data-ttu-id="92f0a-127">Para ver las traducciones (datos y metadatos), necesita agregar la propiedad "identificador regional" a la cadena de conexión:`Data source=<servername>;initial catalog=<multidimensionaldatabasename>-ee;cube='<cubename>'; Locale Identifier=<identifier number>`</span><span class="sxs-lookup"><span data-stu-id="92f0a-127">In order to see the translations (data and metadata) you need to add the "Locale Identifier" property to the connection string: `Data source=<servername>;initial catalog=<multidimensionaldatabasename>-ee;cube='<cubename>'; Locale Identifier=<identifier number>`</span></span>  
  
6.  <span data-ttu-id="92f0a-128">En **Credenciales**, especifique el modo en que el servidor de informes debe obtener las credenciales para obtener acceso al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="92f0a-128">In **Credentials**, specify how the report server obtains credentials to access the external data source.</span></span>  
  
    -   <span data-ttu-id="92f0a-129">Seleccione **Autenticación de Windows (integrada)** si quiere acceder a los datos con las credenciales del usuario que ha abierto el informe.</span><span class="sxs-lookup"><span data-stu-id="92f0a-129">Select **Windows authentication (integrated)** if you want to access the data using the credentials of the user who opened the report.</span></span> <span data-ttu-id="92f0a-130">No seleccione esta opción si el sitio o la granja de servidores de SharePoint usa la autenticación de formularios o se conecta al servidor de informes a través de una cuenta de confianza.</span><span class="sxs-lookup"><span data-stu-id="92f0a-130">Do not select this option if the SharePoint site or farm uses forms authentication or connects to the report server through a trusted account.</span></span> <span data-ttu-id="92f0a-131">No seleccione esta opción si desea programar el procesamiento de suscripciones o datos para este informe.</span><span class="sxs-lookup"><span data-stu-id="92f0a-131">Do not select this option if you want to schedule subscription or data processing for this report.</span></span> <span data-ttu-id="92f0a-132">Esta opción funciona de manera óptima cuando la autenticación Kerberos está habilitada para el dominio o cuando el origen de datos se encuentra en el mismo equipo que el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="92f0a-132">This option works best when Kerberos authentication is enabled for your domain, or when the data source is on the same computer as the report server.</span></span> <span data-ttu-id="92f0a-133">Si la autenticación Kerberos no está habilitada, las credenciales de Windows solo se pueden pasar a otro equipo.</span><span class="sxs-lookup"><span data-stu-id="92f0a-133">If Kerberos authentication is not enabled, Windows credentials can only be passed to one other computer.</span></span> <span data-ttu-id="92f0a-134">Esto significa que si el origen de datos externo es otro equipo, que requiere una conexión adicional, obtendrá un error en lugar de los datos esperados.</span><span class="sxs-lookup"><span data-stu-id="92f0a-134">This means that if the external data source is on another computer, requiring an additional connection, you will get an error instead of the data you expect.</span></span>  
  
    -   <span data-ttu-id="92f0a-135">Seleccione **Pedir credenciales** si desea que el usuario especifique sus credenciales cada vez que ejecute el informe.</span><span class="sxs-lookup"><span data-stu-id="92f0a-135">Select **Prompt for credentials** if you want the user to enter his or her credentials each time he or she runs the report.</span></span> <span data-ttu-id="92f0a-136">No seleccione esta opción si desea programar el procesamiento de suscripciones o datos para este informe.</span><span class="sxs-lookup"><span data-stu-id="92f0a-136">Do not select this option if you want to schedule subscription or data processing for this report.</span></span>  
  
    -   <span data-ttu-id="92f0a-137">Seleccione **Credenciales almacenadas** si desea obtener acceso a los datos mediante un único conjunto de credenciales.</span><span class="sxs-lookup"><span data-stu-id="92f0a-137">Select **Stored credentials** if you want to access the data using a single set of credentials.</span></span> <span data-ttu-id="92f0a-138">Las credenciales se cifran antes de guardarse.</span><span class="sxs-lookup"><span data-stu-id="92f0a-138">The credentials are encrypted before they are stored.</span></span> <span data-ttu-id="92f0a-139">Puede seleccionar opciones que determinan el modo en que se autentican las credenciales almacenadas.</span><span class="sxs-lookup"><span data-stu-id="92f0a-139">You can select options that determine how the stored credentials are authenticated.</span></span> <span data-ttu-id="92f0a-140">Seleccione Usar como credenciales de Windows si las credenciales almacenadas pertenecen a una cuenta de usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="92f0a-140">Select Use as Windows credentials if the stored credentials belong to a Windows user account.</span></span> <span data-ttu-id="92f0a-141">Seleccione **Establecer contexto de ejecución en esta cuenta** si desea establecer el contexto de ejecución en el servidor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="92f0a-141">Select **Set execution context to this account** if you want to set the execution context on the database server.</span></span>  
  
    -   <span data-ttu-id="92f0a-142">Seleccione **No se necesitan credenciales** si especifica las credenciales en la cadena de conexión o si quiere ejecutar el informe con una cuenta con privilegios mínimos.</span><span class="sxs-lookup"><span data-stu-id="92f0a-142">Select **Credentials are not required** if you specify credentials in the connection string, or if you want to run the report using a least-privilege account.</span></span>  
  
7.  <span data-ttu-id="92f0a-143">Haga clic en **Probar conexión** para validar la conexión.</span><span class="sxs-lookup"><span data-stu-id="92f0a-143">Click **Test Connection** to validate.</span></span>  
  
8.  <span data-ttu-id="92f0a-144">Seleccione **Habilitar este origen de datos** si desea que el origen de datos esté activo.</span><span class="sxs-lookup"><span data-stu-id="92f0a-144">Select **Enable this data source** if you want the data source to be active.</span></span> <span data-ttu-id="92f0a-145">Si el origen de datos está configurado pero no activo, los usuarios recibirán un mensaje de error si intentan crear un informe.</span><span class="sxs-lookup"><span data-stu-id="92f0a-145">If the data source is configured but not active, users will receive an error message when they attempt to create a report.</span></span>  
  
  