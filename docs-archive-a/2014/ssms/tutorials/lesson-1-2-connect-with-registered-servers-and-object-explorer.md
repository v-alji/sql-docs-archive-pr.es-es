---
title: Conectar con el Explorador de objetos y Servidores registrados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: d6b3911f-68b4-4483-831b-df89d6400add
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4bc75ad7f3682765dc102064a5621cd541ccd12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743869"
---
# <a name="connect-with-registered-servers-and-object-explorer"></a><span data-ttu-id="8161b-102">Conectar con el Explorador de objetos y Servidores registrados</span><span class="sxs-lookup"><span data-stu-id="8161b-102">Connect with Registered Servers and Object Explorer</span></span>
  <span data-ttu-id="8161b-103">Este tutorial muestra el uso de Servidores registrados y del Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="8161b-103">This tutorial demonstrates the use of Registered Servers and Object Explorer.</span></span>  
  
 <span data-ttu-id="8161b-104">En este tutorial se usa la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8161b-104">This tutorial uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="8161b-105">Con el objeto de mejorar la seguridad, las bases de datos de ejemplo no se instalan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8161b-105">To help enhance security, by default, the sample databases are not installed.</span></span> <span data-ttu-id="8161b-106">Para obtener más información, vea la página sobre [cómo instalar ejemplos y bases de datos de ejemplo de SQL Server](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="8161b-106">For more information, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="connecting-to-servers"></a><span data-ttu-id="8161b-107">Conectar con servidores</span><span class="sxs-lookup"><span data-stu-id="8161b-107">Connecting to Servers</span></span>  
 <span data-ttu-id="8161b-108">La barra de herramientas del componente Servidores registrados contiene botones para [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]e [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8161b-108">The toolbar of the Registered Servers component has buttons for the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="8161b-109">Puede registrar uno o más de estos tipos de servidor para una administración práctica.</span><span class="sxs-lookup"><span data-stu-id="8161b-109">You can register one or more of these server types for convenient management.</span></span> <span data-ttu-id="8161b-110">Realice el siguiente ejercicio para registrar la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8161b-110">Try the following exercise to register the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
#### <a name="to-register-the-database"></a><span data-ttu-id="8161b-111">Para registrar la base de datos</span><span class="sxs-lookup"><span data-stu-id="8161b-111">To register the database</span></span>  
  
1.  <span data-ttu-id="8161b-112">En la barra de herramientas de Servidores registrados, haga clic en **Motor de base de datos** , si es necesario.</span><span class="sxs-lookup"><span data-stu-id="8161b-112">On the Registered Servers toolbar, click **Database Engine** if you have to.</span></span> <span data-ttu-id="8161b-113">Es posible que ya esté seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8161b-113">(It may already be selected.)</span></span>  
  
2.  <span data-ttu-id="8161b-114">Expanda **Motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="8161b-114">Expand **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="8161b-115">Haga clic con el botón secundario en **Grupos de servidores locales**y, después, haga clic en **Nuevo registro de servidor**.</span><span class="sxs-lookup"><span data-stu-id="8161b-115">Right-click **Local Server Groups**, and then click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="8161b-116">En el cuadro de diálogo **Nuevo registro de servidor** , en el cuadro de texto **Nombre del servidor** , escriba el nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8161b-116">In the **New Server Registration** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="8161b-117">En el cuadro **Nombre del servidor registrado** , escriba [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8161b-117">In the **Registered server name** box, type [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
6.  <span data-ttu-id="8161b-118">En la pestaña **propiedades de conexión** , en la lista **conectar con base de datos** , seleccione **\<Browse server...>** .</span><span class="sxs-lookup"><span data-stu-id="8161b-118">On the **Connection Properties** tab, in the **Connect to database** list, select **\<Browse server...>**.</span></span>  
  
7.  <span data-ttu-id="8161b-119">En el cuadro de diálogo **Buscar bases de datos** , haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="8161b-119">In the **Browse for Databases** dialog box, click **Yes**.</span></span>  
  
8.  <span data-ttu-id="8161b-120">En el cuadro de diálogo **Buscar base de datos en el servidor** , seleccione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8161b-120">In the **Browse Server for Database** dialog box, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
9. <span data-ttu-id="8161b-121">Para comprobar que el servidor se ha registrado correctamente, haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="8161b-121">To verify that the server has been registered correctly, click **Test**.</span></span>  
  
10. <span data-ttu-id="8161b-122">En el cuadro de diálogo **Nuevo registro de servidor** , haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8161b-122">In the **New Server Registration** dialog box, click **Save**.</span></span>  
  
## <a name="connecting-with-object-explorer"></a><span data-ttu-id="8161b-123">Conectar con el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="8161b-123">Connecting with Object Explorer</span></span>  
 <span data-ttu-id="8161b-124">Al igual que Servidores registrados, el Explorador de objetos puede conectarse a [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]y [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8161b-124">Like Registered Servers, Object Explorer can connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
#### <a name="to-connect-with-object-explorer"></a><span data-ttu-id="8161b-125">Para conectar con el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="8161b-125">To connect with Object Explorer</span></span>  
  
1.  <span data-ttu-id="8161b-126">En la barra de herramientas del Explorador de objetos, haga clic en **Conectar** para obtener la lista de tipos de conexión posibles y, a continuación, seleccione **Motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="8161b-126">On the toolbar of Object Explorer, click **Connect** for a list of possible connection types, and then select **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="8161b-127">En el cuadro de diálogo **Conectar al servidor** , en el cuadro de texto **Nombre del servidor** , escriba el nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8161b-127">In the **Connect to Server** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="8161b-128">Haga clic en **Opciones** para explorar las opciones elegidas.</span><span class="sxs-lookup"><span data-stu-id="8161b-128">Click **Options** and explore the choices.</span></span>  
  
4.  <span data-ttu-id="8161b-129">Para conectar con el servidor, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="8161b-129">To connect to the server, click **Connect**.</span></span> <span data-ttu-id="8161b-130">Si ya estaba conectado, volverá al Explorador de objetos y el foco se establecerá en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="8161b-130">If you are already connected, this action just returns you to Object Explorer and sets the focus on that server.</span></span>  
  
     <span data-ttu-id="8161b-131">El Explorador de objetos permite administrar la seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la replicación y el correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8161b-131">With Object Explorer you can administer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Security, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, Replication, and Database Mail.</span></span> <span data-ttu-id="8161b-132">El Explorador de objetos solamente puede administrar algunas características de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]y [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8161b-132">Object Explorer can only manage some of the features of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span></span> <span data-ttu-id="8161b-133">Cada uno de estos componentes cuenta con herramientas especializadas adicionales.</span><span class="sxs-lookup"><span data-stu-id="8161b-133">Each of those components has additional specialized tools.</span></span>  
  
5.  <span data-ttu-id="8161b-134">En el Explorador de objetos, expanda la carpeta **Bases de datos** y seleccione [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8161b-134">In Object Explorer, expand the **Databases** folder and select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
     <span data-ttu-id="8161b-135">Observe que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] incluye las bases de datos del sistema en una carpeta separada.</span><span class="sxs-lookup"><span data-stu-id="8161b-135">Notice that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] presents the system databases in a separate folder.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8161b-136">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="8161b-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8161b-137">Cambiar el diseño del entorno</span><span class="sxs-lookup"><span data-stu-id="8161b-137">Change the Environment Layout</span></span>](lesson-1-3-change-the-environment-layout.md)  
  
  
