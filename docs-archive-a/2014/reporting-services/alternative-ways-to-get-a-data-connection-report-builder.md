---
title: Maneras alternativas de obtener una conexión de datos (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aebc5f3d-97d5-4d54-b525-753fed073a9a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2be693469318172b2a55fbcb17b33e1deaaed3df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669538"
---
# <a name="alternative-ways-to-get-a-data-connection-report-builder"></a><span data-ttu-id="6805b-102">Maneras alternativas de obtener una conexión de datos (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="6805b-102">Alternative Ways to Get a Data Connection (Report Builder)</span></span>
  <span data-ttu-id="6805b-103">Una conexión de datos contiene la información para conectarse a un origen de datos externo, por ejemplo una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6805b-103">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="6805b-104">Normalmente, la información de conexión y el tipo de credenciales que se debe usar utilizar se obtienen del propietario del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6805b-104">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span>  
  
 <span data-ttu-id="6805b-105">Para especificar una conexión de datos, puede utilizar un origen de datos compartido del servidor de informes o crear un origen de datos incrustado que solo se utilice en un informe específico.</span><span class="sxs-lookup"><span data-stu-id="6805b-105">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in a specific report.</span></span>  
  
 <span data-ttu-id="6805b-106">En la mayoría de los tutoriales se utilizan orígenes de datos incrustados, pero si tiene acceso a orígenes de datos compartidos, puede utilizarlos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6805b-106">In most tutorials you use embedded data sources, but if you have access to shared data sources, then you can use them instead.</span></span>  
  
## <a name="getting-a-data-connection-from-a-shared-data-source"></a><span data-ttu-id="6805b-107">Recibir una conexión de datos desde un origen de datos compartido</span><span class="sxs-lookup"><span data-stu-id="6805b-107">Getting a Data Connection From a Shared Data Source</span></span>  
 <span data-ttu-id="6805b-108">Si el servidor de informes dispone de orígenes de datos compartidos para los que tiene permisos de uso, puede utilizarlos en lugar de los orígenes de datos incrustados.</span><span class="sxs-lookup"><span data-stu-id="6805b-108">If the report server has available shared data source that you have permissions to use, you can use them instead of an embedded data source.</span></span> <span data-ttu-id="6805b-109">Los siguientes procedimientos indican cómo buscar los orígenes de datos compartidos y proporcionar las credenciales necesarias para usarlos.</span><span class="sxs-lookup"><span data-stu-id="6805b-109">The following procedures tell how to locate the shared data sources and provide any credentials needed to use them.</span></span>  
  
 <span data-ttu-id="6805b-110">Para usar un origen de datos compartido, debe desplazarse a un servidor de informes y seleccionar uno.</span><span class="sxs-lookup"><span data-stu-id="6805b-110">To use a shared data source, you must browse to a report server and select one.</span></span> <span data-ttu-id="6805b-111">Normalmente, obtendrá la dirección URL del servidor de informes del administrador del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6805b-111">Usually, you get the report server URL from the report server administrator.</span></span>  
  
#### <a name="to-specify-a-data-connection-from-a-list-of-shared-data-sources"></a><span data-ttu-id="6805b-112">Especificar una conexión de datos de una lista de orígenes de datos compartidos</span><span class="sxs-lookup"><span data-stu-id="6805b-112">To specify a data connection from a list of shared data sources</span></span>  
  
1.  <span data-ttu-id="6805b-113">En la página **Elegir un conjunto de datos** , seleccione **Crear un conjunto de datos**y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6805b-113">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="6805b-114">Se abre la página **Elegir una conexión a un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="6805b-114">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="6805b-115">De la lista de orígenes de datos, seleccione un origen de datos para el que tenga permiso de acceso.</span><span class="sxs-lookup"><span data-stu-id="6805b-115">From the list of data sources, select a data source that you have permission to access.</span></span>  
  
3.  <span data-ttu-id="6805b-116">Para comprobar que se puede conectar al origen de datos, haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="6805b-116">To verify that you can connect to the data source, click **Test Connection**.</span></span> <span data-ttu-id="6805b-117">Aparece un mensaje que indica que la conexión se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6805b-117">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="6805b-118">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="6805b-118">Click **Next**.</span></span>  
  
     <span data-ttu-id="6805b-119">Si es necesario, escriba sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="6805b-119">If necessary, enter your credentials.</span></span> <span data-ttu-id="6805b-120">Para guardar las credenciales de forma local, seleccione **Guardar contraseña con conexión**.</span><span class="sxs-lookup"><span data-stu-id="6805b-120">To save the credentials locally, select **Save password with connection**.</span></span> <span data-ttu-id="6805b-121">Si no selecciona esta opción, se le pedirán las credenciales cada vez que ejecute el informe</span><span class="sxs-lookup"><span data-stu-id="6805b-121">If you not select this option, you will be prompted for credentials every time that you run the report</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-specify-a-data-connection-by-browsing-to-a-shared-data-source-on-a-report-server"></a><span data-ttu-id="6805b-122">Especificar una conexión de datos desplazándose a un origen de datos compartido en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="6805b-122">To specify a data connection by browsing to a shared data source on a report server</span></span>  
  
1.  <span data-ttu-id="6805b-123">En la página **Elegir un conjunto de datos** , seleccione **Crear un conjunto de datos**y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6805b-123">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="6805b-124">Se abre la página **Elegir una conexión a un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="6805b-124">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="6805b-125">Haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="6805b-125">Click **Browse**.</span></span> <span data-ttu-id="6805b-126">Se abre el cuadro de diálogo **Seleccionar origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="6805b-126">The **Select Data Source** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="6805b-127">En la lista desplegable **Buscar en** , seleccione **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="6805b-127">From the **Look in** drop-down list, select **Recent Sites and Servers**.</span></span> <span data-ttu-id="6805b-128">En el panel de origen de datos, haga clic en la dirección URL del servidor y, después, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6805b-128">In the data source pane, click the URL for your server, and then click **Open**.</span></span>  
  
     <span data-ttu-id="6805b-129">Se muestra la lista de orígenes o modelos de datos.</span><span class="sxs-lookup"><span data-stu-id="6805b-129">The list of data sources or models appears.</span></span>  
  
4.  <span data-ttu-id="6805b-130">Alternativamente, en **Name**, escriba la dirección URL del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="6805b-130">Alternatively, in **Name**, type the URL to the report server.</span></span> <span data-ttu-id="6805b-131">Haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6805b-131">Click **Open**.</span></span>  
  
     <span data-ttu-id="6805b-132">El Generador de informes se conecta al servidor de informes y carga los orígenes de datos que están disponibles en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="6805b-132">Report Builder connects to the report server and loads the data sources that are available at the root folder.</span></span>  
  
5.  <span data-ttu-id="6805b-133">Vaya hasta una carpeta que contenga un origen de datos para el que disponga de los permisos de conexión necesarios, seleccione el origen de datos y luego haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6805b-133">Navigate to a folder that contains a data source that you have sufficient permissions to connect to, select the data source, and then click **Open**.</span></span>  
  
     <span data-ttu-id="6805b-134">Volverá a encontrarse en la página **Elegir una conexión a un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="6805b-134">You are back on the **Choose a connection to a data source** page.</span></span>  
  
6.  <span data-ttu-id="6805b-135">Para comprobar que se puede conectar al origen de datos, haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="6805b-135">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="6805b-136">Aparece un mensaje que indica que la conexión se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6805b-136">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="6805b-137">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="6805b-137">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="6805b-138">Si se le solicita un nombre de usuario y contraseña, escriba sus credenciales.</span><span class="sxs-lookup"><span data-stu-id="6805b-138">If you are prompted for a user name and password, enter your credentials.</span></span> <span data-ttu-id="6805b-139">Para guardar las credenciales de forma local, seleccione **Guardar contraseña con conexión**.</span><span class="sxs-lookup"><span data-stu-id="6805b-139">To save the credentials locally, select **Save password with connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6805b-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6805b-140">See Also</span></span>  
 <span data-ttu-id="6805b-141">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6805b-141">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="6805b-142">Tutoriales &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="6805b-142">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
