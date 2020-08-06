---
title: Crear, eliminar o modificar un origen de datos compartido (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- removing shared data sources
- data sources [Reporting Services], shared
- deleting shared data sources
- modifying shared data sources
ms.assetid: cd7bace3-f8ec-4ee3-8a9f-2f217cdca9f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6f4ff658e656b159995087df3121806b462e687
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673546"
---
# <a name="create-delete-or-modify-a-shared-data-source-report-manager"></a><span data-ttu-id="42263-102">Crear, eliminar o modificar un origen de datos compartido (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="42263-102">Create, Delete, or Modify a Shared Data Source (Report Manager)</span></span>
  <span data-ttu-id="42263-103">Un origen de datos compartido especifica las propiedades de conexión para un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="42263-103">A shared data source specifies connection properties for a data source.</span></span> <span data-ttu-id="42263-104">Si tiene un origen de datos usado por un gran número de informes, modelos o suscripciones controladas por datos, piense en crear un origen de datos compartido para eliminar la sobrecarga de tener que mantener la misma información de conexión en varios lugares.</span><span class="sxs-lookup"><span data-stu-id="42263-104">If you have a data source that is used by a large number of reports, models, or data-driven subscriptions, consider creating a shared data source to eliminate the overhead of having to maintain the same connection information in multiple places.</span></span>  
  
 <span data-ttu-id="42263-105">El siguiente icono indica que existe un origen de datos compartido en la jerarquía de carpetas del Administrador de informes:</span><span class="sxs-lookup"><span data-stu-id="42263-105">The following icon indicates a shared data source in the Report Manager folder hierarchy:</span></span>  
  
 <span data-ttu-id="42263-106">![Icono de origen de datos compartido](media/hlp-16datasource.png "Icono de origen de datos compartido")</span><span class="sxs-lookup"><span data-stu-id="42263-106">![Shared data source icon](media/hlp-16datasource.png "Shared data source icon")</span></span>  
<span data-ttu-id="42263-107">Icono de origen de datos compartido</span><span class="sxs-lookup"><span data-stu-id="42263-107">shared data source icon</span></span>  
  
### <a name="to-create-a-shared-data-source"></a><span data-ttu-id="42263-108">Para crear un origen de datos compartido</span><span class="sxs-lookup"><span data-stu-id="42263-108">To create a shared data source</span></span>  
  
1.  <span data-ttu-id="42263-109">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="42263-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="42263-110">En Administrador de informes, vaya a la página **contenido** .</span><span class="sxs-lookup"><span data-stu-id="42263-110">In Report Manager, navigate to the **Contents** page.</span></span>  
  
3.  <span data-ttu-id="42263-111">Haga clic en **Nuevo origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="42263-111">Click **New Data Source**.</span></span> <span data-ttu-id="42263-112">Se abre la página **Nuevo origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="42263-112">The **New Data Source** page opens.</span></span>  
  
4.  <span data-ttu-id="42263-113">Escriba el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="42263-113">Type a name for the item.</span></span> <span data-ttu-id="42263-114">El nombre debe incluir al menos un carácter y debe empezar con una letra.</span><span class="sxs-lookup"><span data-stu-id="42263-114">A name must contain at least one character and it must start with a letter.</span></span> <span data-ttu-id="42263-115">También puede incluir determinados símbolos, pero no espacios en blanco o los caracteres ; ?</span><span class="sxs-lookup"><span data-stu-id="42263-115">It can also include certain symbols, but not spaces or the characters ; ?</span></span> <span data-ttu-id="42263-116">: \@ & = +, $/\* \< > | " /.</span><span class="sxs-lookup"><span data-stu-id="42263-116">: \@ & = + , $ / \* \< > | " /.</span></span>  
  
5.  <span data-ttu-id="42263-117">Si lo desea, escriba una descripción que ofrezca a los usuarios información sobre la conexión.</span><span class="sxs-lookup"><span data-stu-id="42263-117">Optionally type a description to provide users with information about the connection.</span></span> <span data-ttu-id="42263-118">Esta descripción aparecerá en la página **Contenido** del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="42263-118">This description will appear on the **Contents** page in Report Manager.</span></span>  
  
6.  <span data-ttu-id="42263-119">En la lista **Tipo de origen de datos** , especifique la extensión de procesamiento de datos que se utiliza para procesar datos desde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="42263-119">In the **Data source type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="42263-120">En **Cadena de conexión**, especifique la cadena de conexión que utiliza el servidor de informes para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="42263-120">For **Connection string**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="42263-121">Se recomienda que no especifique credenciales en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="42263-121">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="42263-122">En el ejemplo siguiente se muestra una cadena de conexión para conectarse a la [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] base de datos local:</span><span class="sxs-lookup"><span data-stu-id="42263-122">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="42263-123">En **Conectar utilizando**, especifique cómo se obtienen las credenciales cuando se ejecuta el informe:</span><span class="sxs-lookup"><span data-stu-id="42263-123">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="42263-124">Si desea solicitar al usuario un nombre de inicio de sesión y una contraseña, haga clic en **Credenciales suministradas por el usuario que ejecuta el informe**.</span><span class="sxs-lookup"><span data-stu-id="42263-124">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span> <span data-ttu-id="42263-125">Para utilizar las credenciales que el usuario especifica como credenciales de Windows, active la casilla **Utilizar como credenciales de Windows para la conexión al origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="42263-125">To use the credentials that the user enters as Windows credentials, click **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="42263-126">Si el nombre de usuario y la contraseña son las credenciales de la base de datos, no active esta opción.</span><span class="sxs-lookup"><span data-stu-id="42263-126">If the user name and password are database credentials, do not select this option.</span></span>  
  
    -   <span data-ttu-id="42263-127">Si va a usar el origen de datos para que se comparta con credenciales guardadas administradas por el propietario del origen de datos, o con informes que admitan suscripciones u otras operaciones programadas (por ejemplo, la generación automatizada de historiales de informes), haga clic en **Credenciales almacenadas de forma segura en el servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="42263-127">If you intend to use the data source as a shared data source with saved credentials that are managed by the owner of the data source, or for reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span> <span data-ttu-id="42263-128">Si el servidor de bases de datos admite la suplantación o la delegación, puede seleccionar **Suplantar al usuario autenticado después de realizar una conexión al origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="42263-128">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>  
  
    -   <span data-ttu-id="42263-129">Si desea que el servidor de informes envíe las credenciales del usuario que tiene acceso al informe al servidor que hospeda el origen de datos externo, haga clic en **Seguridad integrada de Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="42263-129">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="42263-130">En este caso, no se solicita al usuario que escriba un nombre de usuario ni una contraseña.</span><span class="sxs-lookup"><span data-stu-id="42263-130">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="42263-131">Si el origen de datos no usa credenciales (por ejemplo, si el origen de datos es un archivo XML al que se tiene acceso desde el sistema de archivos), haga clic en **No se necesitan credenciales**.</span><span class="sxs-lookup"><span data-stu-id="42263-131">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="42263-132">Solo debería especificar este tipo de credencial si es válido para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="42263-132">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="42263-133">Si selecciona esta opción para un origen de datos que requiere autenticación, se producirá un error en la conexión.</span><span class="sxs-lookup"><span data-stu-id="42263-133">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="42263-134">Si selecciona esta opción, asegúrese de que configura la cuenta de ejecución desatendida que permite al servidor de informes conectar a otros equipos para recuperar datos o archivos cuando las credenciales del usuario no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="42263-134">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
     <span data-ttu-id="42263-135">Para obtener más información sobre cómo configurar credenciales, vea [Especificar información de credenciales y conexión para los orígenes de datos de informes](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="42263-135">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="42263-136">Para más información sobre la cuenta de ejecución desatendida, vea [Configurar la cuenta de ejecución desatendida &#40;Administrador de configuración de SSRS&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="42263-136">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
9. <span data-ttu-id="42263-137">Haga clic en el botón **Probar conexión** para validar la configuración del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="42263-137">Click the **Test Connection** button to validate the data source configuration.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="42263-138">El botón Probar conexión no se admite para el tipo de origen de datos XML.</span><span class="sxs-lookup"><span data-stu-id="42263-138">The Test Connection button is not supported for the XML data source type.</span></span>  
  
10. <span data-ttu-id="42263-139">Haga clic en **Aceptar**</span><span class="sxs-lookup"><span data-stu-id="42263-139">Click **OK**</span></span>  
  
### <a name="to-modify-a-shared-data-source"></a><span data-ttu-id="42263-140">Para modificar un origen de datos compartido</span><span class="sxs-lookup"><span data-stu-id="42263-140">To modify a shared data source</span></span>  
  
1.  <span data-ttu-id="42263-141">En el Administrador de informes, navegue a la página Contenido.</span><span class="sxs-lookup"><span data-stu-id="42263-141">In Report Manager, navigate to the Contents page.</span></span>  
  
2.  <span data-ttu-id="42263-142">Navegue al elemento de orígenes de datos compartidos, mantenga el mouse sobre el elemento, haga clic en la lista desplegable y seleccione **Administrar**en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="42263-142">Navigate to the shared data source item, hover over the item, click the drop-down list, and from the context menu, click **Manage**.</span></span> <span data-ttu-id="42263-143">Se abre la página **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="42263-143">The **Properties** page opens.</span></span>  
  
3.  <span data-ttu-id="42263-144">Modifique el origen de datos y, a continuación, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="42263-144">Modify the data source, and then click **Apply**.</span></span>  
  
### <a name="to-delete-a-shared-data-source"></a><span data-ttu-id="42263-145">Para eliminar un origen de datos compartido</span><span class="sxs-lookup"><span data-stu-id="42263-145">To delete a shared data source</span></span>  
  
-   <span data-ttu-id="42263-146">En el Administrador de informes, navegue a la página **Contenido** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="42263-146">In Report Manager, navigate to the **Contents** page and do one of the following:</span></span>  
  
    -   <span data-ttu-id="42263-147">Navegue al elemento de origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="42263-147">Navigate to the shared data source item.</span></span>  
  
         <span data-ttu-id="42263-148">Haga clic en el elemento para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="42263-148">Click the item to open it.</span></span> <span data-ttu-id="42263-149">Se abre la página de propiedades General.</span><span class="sxs-lookup"><span data-stu-id="42263-149">The General Properties page opens.</span></span>  
  
         <span data-ttu-id="42263-150">Haga clic en **Eliminar** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="42263-150">Click **Delete**, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="42263-151">En la página **Contenido** , navegue a la carpeta que contiene el origen de datos que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="42263-151">In the **Contents** page, navigate to the folder that contains the data source you want to delete.</span></span>  
  
         <span data-ttu-id="42263-152">Mantenga el mouse sobre el elemento, haga clic en la lista desplegable y seleccione **Eliminar**en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="42263-152">Hover over the item, click the drop-down list, and from the context menu, click **Delete**.</span></span>  
  
         [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="42263-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42263-153">See Also</span></span>  
 <span data-ttu-id="42263-154">[Conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="42263-154">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="42263-155">[Administrador de informes de &#40;de página de contenido&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="42263-155">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="42263-156">[Crear, modificar y eliminar orígenes de datos compartidos &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="42263-156">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="42263-157">[Administrar orígenes de datos de informe](report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="42263-157">[Manage Report Data Sources](report-data/manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="42263-158">Configurar propiedades de origen de datos para un informe &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="42263-158">Configure Data Source Properties for a Report  &#40;Report Manager&#41;</span></span>](report-data/configure-data-source-properties-for-a-report-report-manager.md)  
  
  
