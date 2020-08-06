---
title: Crear un modelo mediante Administrador de informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report models [Reporting Services], creating
- Report Manager [Reporting Services], model creation
ms.assetid: 8e5d2bd3-48ec-45f3-afee-6d86797c8f28
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59ce278a22ec9797b001ca37a0bde576483cf5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747510"
---
# <a name="create-a-model-using-report-manager"></a><span data-ttu-id="d7b45-102">Crear un modelo con el Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="d7b45-102">Create a Model Using Report Manager</span></span>
  <span data-ttu-id="d7b45-103">Puede generar modelos a partir de un cubo de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o una base de datos de Oracle mediante el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="d7b45-103">You can generate models from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube, a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, or an Oracle database using Report Manager.</span></span> <span data-ttu-id="d7b45-104">Los modelos de informe se generan a partir de orígenes de datos compartidos que se han publicado en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d7b45-104">Report models are generated from shared data sources that are published on the report server.</span></span> <span data-ttu-id="d7b45-105">Si no tiene un origen de datos compartido, deberá crearlo.</span><span class="sxs-lookup"><span data-stu-id="d7b45-105">If you do not already have a shared data source, you must create one.</span></span>  
  
 <span data-ttu-id="d7b45-106">El modelo de informe que se genera se basa completamente en el esquema del origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="d7b45-106">The report model that you generate is based entirely on the schema of the shared data source.</span></span> <span data-ttu-id="d7b45-107">No puede elegir qué partes del origen de datos se incluyen en el modelo, ni puede editar las reglas o metadatos de un modelo generado.</span><span class="sxs-lookup"><span data-stu-id="d7b45-107">You cannot choose which parts of the data source are included in the model, nor can you edit the rules or metadata of a generated model.</span></span> <span data-ttu-id="d7b45-108">Sin embargo, puede establecer las propiedades del modelo después de que se haya generado y definir las asignaciones de roles que restrinjan el acceso a todo el modelo o parte de él.</span><span class="sxs-lookup"><span data-stu-id="d7b45-108">However, you can set properties on the model after it is generated and define role assignments that restrict access to all or part of the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7b45-109">Un modelo basado en Oracle generado mediante Administrador de informes o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] incluirá objetos de base de datos que forman parte del esquema de la cuenta de usuario utilizada para conectarse al origen de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="d7b45-109">An Oracle-based model generated using Report Manager or [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] will include database objects that are a part of the schema for the user account used to connect to the Oracle data source.</span></span> <span data-ttu-id="d7b45-110">El nombre de la cuenta de usuario está especificado en las credenciales de propiedades del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d7b45-110">The user account name is specified in the data source properties credentials.</span></span>  
  
### <a name="to-create-a-new-data-source-for-a-report-model-using-report-manager"></a><span data-ttu-id="d7b45-111">Para crear un nuevo origen de datos para un modelo de informe con el Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="d7b45-111">To create a new data source for a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="d7b45-112">En el explorador web, escriba la dirección URL del servidor de informes en la barra de direcciones.</span><span class="sxs-lookup"><span data-stu-id="d7b45-112">In your Web browser, type the URL for your report server in the address bar.</span></span>  
  
2.  <span data-ttu-id="d7b45-113">Haga clic en **Nuevo origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="d7b45-113">Click **New Data Source**.</span></span>  
  
3.  <span data-ttu-id="d7b45-114">En el cuadro **Nombre** , escriba un nombre para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d7b45-114">In the **Name** box, enter a name for the data source.</span></span>  
  
4.  <span data-ttu-id="d7b45-115">Opcionalmente, escriba una breve descripción del modo en el cuadro de texto **Descripción** .</span><span class="sxs-lookup"><span data-stu-id="d7b45-115">Optionally, enter a brief description of the mode in the **Description** text box.</span></span>  
  
5.  <span data-ttu-id="d7b45-116">Compruebe que la casilla **Habilitar este origen de datos** está activada.</span><span class="sxs-lookup"><span data-stu-id="d7b45-116">Verify that the **Enable this data source** check box is selected.</span></span>  
  
6.  <span data-ttu-id="d7b45-117">En la lista **Tipo de conexión** , seleccione el tipo de origen de datos al que desea conectarse.</span><span class="sxs-lookup"><span data-stu-id="d7b45-117">In the **Connection type** list, select the data source type to which you want to connect.</span></span> <span data-ttu-id="d7b45-118">El tipo de conexión debe ser uno de los siguientes: **Oracle**, **Microsoft SQL Server** o **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="d7b45-118">The connection type must be one of the following: **Oracle**, **Microsoft SQL Server** or **Microsoft SQL Server Analysis Services**.</span></span>  
  
7.  <span data-ttu-id="d7b45-119">En el cuadro **Cadena de conexión** , escriba la cadena de conexión que apunta a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d7b45-119">In the **Connection string** box, enter the connection string that points to the database.</span></span>  
  
8.  <span data-ttu-id="d7b45-120">Seleccione el método de conexión que utilizarán los usuarios del Generador de informes para conectarse a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d7b45-120">Select the connection method that Report Builder users will need to use to connect to the database.</span></span>  
  
    -   <span data-ttu-id="d7b45-121">Autenticación de Windows: seleccione esta opción cuando desee que el sistema operativo autentique a los usuarios de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7b45-121">Windows Authentication: Select this option when you want the operating system to authenticate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] users.</span></span> <span data-ttu-id="d7b45-122">Esta opción permite que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilice las características de seguridad de Windows, como el cifrado de contraseñas, para autenticar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d7b45-122">This option allows [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use Windows security features, such as password encryption, to authenticate users.</span></span> <span data-ttu-id="d7b45-123">Se recomienda encarecidamente seleccionar esta opción.</span><span class="sxs-lookup"><span data-stu-id="d7b45-123">It is strongly recommended that you select this option.</span></span>  
  
    -   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="d7b45-124">Autenticación: Seleccione esta opción si desea que los usuarios utilicen una [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cuenta de inicio de sesión que haya creado.</span><span class="sxs-lookup"><span data-stu-id="d7b45-124">Authentication: Select this option when you want users to use a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account that you created.</span></span> <span data-ttu-id="d7b45-125">Los usuarios deben proporcionar un nombre y una contraseña de inicio de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] válidos.</span><span class="sxs-lookup"><span data-stu-id="d7b45-125">Users must supply a valid [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login name and password.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="d7b45-126">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="d7b45-126">Whenever possible, use Windows Authentication.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-create-a-report-model-using-report-manager"></a><span data-ttu-id="d7b45-127">Para crear un modelo de informe mediante el Administrador de informes</span><span class="sxs-lookup"><span data-stu-id="d7b45-127">To create a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="d7b45-128">En el Administrador de informes, seleccione el origen de datos que desee usar para el modelo.</span><span class="sxs-lookup"><span data-stu-id="d7b45-128">In Report Manager, select the data source that you want to use for your model.</span></span>  
  
     <span data-ttu-id="d7b45-129">Se muestra la página Propiedades.</span><span class="sxs-lookup"><span data-stu-id="d7b45-129">The Properties page is displayed.</span></span>  
  
2.  <span data-ttu-id="d7b45-130">Compruebe que desea utilizar las opciones especificadas para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d7b45-130">Verify that you want to use the options specified for the data source.</span></span>  
  
3.  <span data-ttu-id="d7b45-131">Haga clic en **Generar modelo**.</span><span class="sxs-lookup"><span data-stu-id="d7b45-131">Click **Generate Model**.</span></span>  
  
     <span data-ttu-id="d7b45-132">Se muestra la página General para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d7b45-132">The General page is displayed for the data source.</span></span>  
  
4.  <span data-ttu-id="d7b45-133">En el cuadro **Nombre** , escriba un nombre para el modelo de informe.</span><span class="sxs-lookup"><span data-stu-id="d7b45-133">In the **Name** box, enter a name for the report model.</span></span>  
  
5.  <span data-ttu-id="d7b45-134">En el cuadro **Descripción** , escriba una breve descripción para el modelo.</span><span class="sxs-lookup"><span data-stu-id="d7b45-134">In the **Description** box, enter a brief description of the model.</span></span>  
  
6.  <span data-ttu-id="d7b45-135">Para especificar una nueva ubicación en la que guardar el modelo de informe, haga clic en **Cambiar ubicación**.</span><span class="sxs-lookup"><span data-stu-id="d7b45-135">To specify a new location to save the report model to, click **Change Location**.</span></span>  
  
     <span data-ttu-id="d7b45-136">De manera predeterminada, el modelo de informe se guarda en la página Inicio del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="d7b45-136">By default, the report model is saved to Report Manager Home.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="d7b45-137">El modelo de informe se crea y guarda en la ubicación que especificó.</span><span class="sxs-lookup"><span data-stu-id="d7b45-137">The report model is created and saved to the location that you specified.</span></span> <span data-ttu-id="d7b45-138">Puede asignar los permisos a este modelo con el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="d7b45-138">You can assign permissions to this model by using Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b45-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7b45-139">See Also</span></span>  
 <span data-ttu-id="d7b45-140">[Conceder permisos en un servidor de informes en modo nativo](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="d7b45-140">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="d7b45-141">[Conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="d7b45-141">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="d7b45-142">Nuevo origen de datos &#40;página del Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="d7b45-142">New Data Source Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/new-data-source-page-report-manager.md)  
  
  
