---
title: Configurar propiedades de origen de datos para un informe (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
ms.assetid: 27af5195-c845-40e0-9a9c-efe569424022
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 42969b4667dd71e4c6413f38e4deadb96491169c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663924"
---
# <a name="configure-data-source-properties-for-a-report--report-manager"></a><span data-ttu-id="e9692-102">Configurar propiedades de origen de datos para un informe (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="e9692-102">Configure Data Source Properties for a Report  (Report Manager)</span></span>
  <span data-ttu-id="e9692-103">Al ejecutar un informe, el servidor de informes recupera información de propiedad para determinar la manera de conectarse a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e9692-103">When you run a report, the report server retrieves property information to determine how to connect to a data source.</span></span> <span data-ttu-id="e9692-104">El tipo de origen de datos, la cadena de conexión y la información de credenciales se especifican en las páginas de propiedades Origen de datos del informe publicado.</span><span class="sxs-lookup"><span data-stu-id="e9692-104">The data source type, connection string, and credential information are specified in the Data Source property pages of the published report.</span></span> <span data-ttu-id="e9692-105">Puede establecer las propiedades para variar la información de conexión a un origen de datos de los valores originales que se especificaron cuando se creó el informe.</span><span class="sxs-lookup"><span data-stu-id="e9692-105">You can set the properties to vary the data source connection information from the original values that were specified when the report was created.</span></span>  
  
 <span data-ttu-id="e9692-106">Como alternativa, si tiene un origen de datos compartido predefinido que ya especifica la información de conexión que desear usar, puede especificar un origen de datos compartido en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e9692-106">Alternatively, if you have a predefined shared data source that already specifies the connection information you want to use, you can specify a shared data source instead.</span></span> <span data-ttu-id="e9692-107">Para usar un origen de datos compartido, haga clic en **Un origen de datos compartido** en la página de propiedades Origen de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="e9692-107">To use a shared data source, click **A shared data source** on the Data Source properties page of the report.</span></span>  
  
### <a name="to-configure-an-embedded-data-source"></a><span data-ttu-id="e9692-108">Para configurar un origen de datos incrustado</span><span class="sxs-lookup"><span data-stu-id="e9692-108">To configure an embedded data source</span></span>  
  
1.  <span data-ttu-id="e9692-109">Inicie el [Administrador de informes &#40;Modo nativo de SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e9692-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="e9692-110">En Administrador de informes, vaya a la página **contenido** .</span><span class="sxs-lookup"><span data-stu-id="e9692-110">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="e9692-111">Navegue al informe para el que desee configurar un origen de datos específico y abra el informe.</span><span class="sxs-lookup"><span data-stu-id="e9692-111">Navigate to the report that you want to configure a report-specific data source for, and open the report.</span></span>  
  
3.  <span data-ttu-id="e9692-112">Haga clic en la pestaña **propiedades** . Se abre la página de propiedades **General** .</span><span class="sxs-lookup"><span data-stu-id="e9692-112">Click the **Properties** tab. The **General** properties page opens.</span></span>  
  
4.  <span data-ttu-id="e9692-113">Haga clic en la pestaña **orígenes de datos** . Se abrirá la página Propiedades del origen de datos del informe.</span><span class="sxs-lookup"><span data-stu-id="e9692-113">Click the **Data Sources** tab. This opens the Data Source properties page of the report.</span></span>  
  
5.  <span data-ttu-id="e9692-114">Haga clic en **Un origen de datos personalizado** para especificar información de conexión a un origen de datos dentro del informe.</span><span class="sxs-lookup"><span data-stu-id="e9692-114">Click **A custom data source** to specify data source connection information within the report.</span></span>  
  
6.  <span data-ttu-id="e9692-115">En la lista **Tipo de conexión** , especifique la extensión de procesamiento de datos que se utiliza para procesar datos desde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e9692-115">In the **Connection Type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="e9692-116">En **cadena de conexión**, especifique la cadena de conexión que utiliza el servidor de informes para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e9692-116">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="e9692-117">Se recomienda que no especifique credenciales en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="e9692-117">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="e9692-118">En el ejemplo siguiente se muestra una cadena de conexión para conectarse a la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] base de datos local:</span><span class="sxs-lookup"><span data-stu-id="e9692-118">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="e9692-119">En **Conectar utilizando**, especifique cómo se obtienen las credenciales cuando se ejecuta el informe:</span><span class="sxs-lookup"><span data-stu-id="e9692-119">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="e9692-120">Si desea solicitar al usuario un nombre de inicio de sesión y una contraseña, haga clic en **Credenciales suministradas por el usuario que ejecuta el informe**.</span><span class="sxs-lookup"><span data-stu-id="e9692-120">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span>  
  
    -   <span data-ttu-id="e9692-121">Si va a usar el origen de datos con informes que son compatibles con suscripciones u otras operaciones programadas (por ejemplo, la generación automatizada de historiales de informes), haga clic en **Credenciales almacenadas de forma segura en el servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="e9692-121">If you intend to use the data source with reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span>  
  
    -   <span data-ttu-id="e9692-122">Si desea que el servidor de informes envíe las credenciales del usuario que tiene acceso al informe al servidor que hospeda el origen de datos externo, haga clic en **Seguridad integrada de Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="e9692-122">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="e9692-123">En este caso, no se solicita al usuario que escriba un nombre de usuario ni una contraseña.</span><span class="sxs-lookup"><span data-stu-id="e9692-123">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="e9692-124">Si el origen de datos no usa credenciales (por ejemplo, si el origen de datos es un archivo XML al que se tiene acceso desde el sistema de archivos), haga clic en **No se necesitan credenciales**.</span><span class="sxs-lookup"><span data-stu-id="e9692-124">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="e9692-125">Solo debería especificar este tipo de credencial si es válido para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e9692-125">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="e9692-126">Si selecciona esta opción para un origen de datos que requiere autenticación, se producirá un error en la conexión.</span><span class="sxs-lookup"><span data-stu-id="e9692-126">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="e9692-127">Si selecciona esta opción, asegúrese de que configura la cuenta de ejecución desatendida que permite al servidor de informes conectar a otros equipos para recuperar datos o archivos cuando las credenciales del usuario no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="e9692-127">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
 <span data-ttu-id="e9692-128">Para obtener más información sobre cómo configurar credenciales, vea [Especificar información de credenciales y conexión para los orígenes de datos de informes](specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="e9692-128">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="e9692-129">Para más información sobre la cuenta de ejecución desatendida, vea [Configurar la cuenta de ejecución desatendida &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e9692-129">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9692-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9692-130">See Also</span></span>  
 <span data-ttu-id="e9692-131">[Administrador de informes de &#40;de página de contenido&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e9692-131">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="e9692-132">[Nueva página de origen de datos &#40;Administrador de informes&#41;](../new-data-source-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e9692-132">[New Data Source Page &#40;Report Manager&#41;](../new-data-source-page-report-manager.md) </span></span>  
 <span data-ttu-id="e9692-133">[Crear, modificar y eliminar orígenes de datos compartidos &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e9692-133">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="e9692-134">[Administrar orígenes de datos de informe](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="e9692-134">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="e9692-135">[Crear, eliminar o modificar un origen de datos compartido &#40;Administrador de informes&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e9692-135">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 [<span data-ttu-id="e9692-136">Orígenes de datos &#40;página de propiedades del Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="e9692-136">Data Sources Properties Page &#40;Report Manager&#41;</span></span>](../data-sources-properties-page-report-manager.md)  
  
  
