---
title: Cómo crear y editar CDC Service | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1b3d47a5-dc89-482d-bbc7-fff04f194c43
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d90534b475901b08fcd2e09acdc0f7976f0fb6e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744267"
---
# <a name="how-to-create-and-edit-a-cdc-service"></a><span data-ttu-id="61fa9-102">Cómo crear y editar un servicio CDC</span><span class="sxs-lookup"><span data-stu-id="61fa9-102">How to Create and Edit a CDC Service</span></span>
  <span data-ttu-id="61fa9-103">En estos procedimientos se describe cómo crear y editar un nuevo servicio CDC de Oracle desde la Consola de configuración del servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="61fa9-103">These procedures describe how to create and edit a new Oracle CDC Service from the CDC Service Configuration Console.</span></span>  
  
 <span data-ttu-id="61fa9-104">Para poder realizar este procedimiento, un usuario de Windows debe tener privilegios de administrador en el equipo donde está configurado el servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="61fa9-104">This procedure requires a Windows user with administrator privileges on the computer where the Oracle CDC service is configured.</span></span>  
  
### <a name="to-create-a-new-cdc-service"></a><span data-ttu-id="61fa9-105">Para crear un nuevo servicio CDC</span><span class="sxs-lookup"><span data-stu-id="61fa9-105">To create a new CDC service</span></span>  
  
1.  <span data-ttu-id="61fa9-106">En el menú **Inicio** , seleccione **Configuración del servicio CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="61fa9-106">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="61fa9-107">En el panel izquierdo, haga clic con el botón secundario en Servicios CDC locales y seleccione Nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="61fa9-107">From the left pane, right click Local CDC Services and select New Service</span></span>  
  
     <span data-ttu-id="61fa9-108">También puede hacer clic en **Nuevo servicio** en el panel **Acciones** .</span><span class="sxs-lookup"><span data-stu-id="61fa9-108">You can also click **New Service** from the **Actions** pane.</span></span>  
  
3.  <span data-ttu-id="61fa9-109">Escriba la información necesaria en el cuadro de diálogo Nuevo servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="61fa9-109">Type or enter the required information in the New Oracle CDC Service dialog box.</span></span> <span data-ttu-id="61fa9-110">Vea [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) para obtener información acerca de cómo especificar información en el cuadro de diálogo Nuevo servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="61fa9-110">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the New Oracle CDC Service dialog box.</span></span>  
  
     <span data-ttu-id="61fa9-111">El servicio CDC de Oracle emplea el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporcionado en el cuadro de diálogo Nuevo servicio CDC de Oracle cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="61fa9-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login provided in the New Oracle CDC Service dialog box is used by the Oracle CDC Service when the service runs.</span></span> <span data-ttu-id="61fa9-112">Este inicio de sesión solo necesita ser miembro del rol fijo de servidor public; no se necesita ningún otro privilegio.</span><span class="sxs-lookup"><span data-stu-id="61fa9-112">This login only needs to be a member of the public fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="61fa9-113">Una vez agregadas nuevas instancias CDC de Oracle, ese inicio de sesión recibe acceso **db_owner** a las bases de datos CDC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asociadas.</span><span class="sxs-lookup"><span data-stu-id="61fa9-113">Once new Oracle CDC Instances are added, that login receives **db_owner** access to the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC databases.</span></span>  
  
4.  <span data-ttu-id="61fa9-114">Cuando termine de especificar la información necesaria, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61fa9-114">When you finish entering the required information, click **OK**.</span></span>  
  
     <span data-ttu-id="61fa9-115">Para crear la definición del servicio de Windows CDC de Oracle, el programa necesita acceso de actualización a la base de datos MSXDBCDC en la instancia asociada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61fa9-115">To create the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="61fa9-116">Al hacer clic en **Aceptar**, un cuadro de diálogo pide al usuario que especifique un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con un acceso de actualización para la base de datos MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="61fa9-116">When you click **OK**, a dialog box prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
     <span data-ttu-id="61fa9-117">Para obtener información acerca de los datos que debe escribir en el cuadro de diálogo Conectar con SQL Server, vea [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="61fa9-117">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="61fa9-118">Haga clic en **Aceptar** para cerrar el cuadro de diálogo Nuevo servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="61fa9-118">Click **OK** to close the New Oracle CDC Service dialog box.</span></span>  
  
### <a name="to-edit-a-cdc-service"></a><span data-ttu-id="61fa9-119">Para editar un servicio CDC</span><span class="sxs-lookup"><span data-stu-id="61fa9-119">To edit a CDC service</span></span>  
  
1.  <span data-ttu-id="61fa9-120">En el menú **Inicio** , seleccione **Configuración del servicio CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="61fa9-120">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="61fa9-121">En el panel izquierdo, seleccione **Servicios CDC locales** , haga clic con el botón derecho en el servicio local que quiera editar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="61fa9-121">From the left pane, select **Local CDC Services** then right-click the local service you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="61fa9-122">También puede seleccionar el servicio con el que está trabajando en la parte central y a continuación, en el panel **Acciones** , hacer clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="61fa9-122">You can also select the service you are working with in the middle and then from the **Actions** pane, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="61fa9-123">Escriba la información necesaria en el cuadro de diálogo Propiedades del servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="61fa9-123">Type or enter the required information in the CDC Service Properties dialog box.</span></span> <span data-ttu-id="61fa9-124">Vea [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) para obtener información acerca de cómo especificar información en el cuadro de diálogo Propiedades del servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="61fa9-124">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the CDC Service Properties dialog box.</span></span>  
  
4.  <span data-ttu-id="61fa9-125">Cuando termine de escribir la información necesaria, haga clic en **Aceptar**; se abrirá el cuadro de diálogo Conectar con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61fa9-125">When you finish entering the required information, Click **OK**, the Connect to SQL Server dialog box opens.</span></span>  
  
     <span data-ttu-id="61fa9-126">Cuando un inicio de sesión sin permiso de escritura para la base de datos MSXDBDCDC intenta crear una nueva instancia CDC de Oracle, se muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="61fa9-126">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="61fa9-127">Haga clic en **Aceptar** en ese cuadro de diálogo para mostrar el cuadro de diálogo Conectar con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61fa9-127">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span> <span data-ttu-id="61fa9-128">En este cuadro de diálogo debe especificar las credenciales para un inicio de sesión que tenga permiso de escritura para la base de datos MSXDBCDC, como el rol de base de datos **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="61fa9-128">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role.</span></span>  
  
     <span data-ttu-id="61fa9-129">Para obtener información acerca de los datos que debe escribir en el cuadro de diálogo Conectar con SQL Server, vea [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="61fa9-129">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="61fa9-130">Haga clic en **Aceptar** en el cuadro de diálogo Conectar con Oracle.</span><span class="sxs-lookup"><span data-stu-id="61fa9-130">Click **OK** in the Connect to Oracle dialog box.</span></span> <span data-ttu-id="61fa9-131">Se cerrarán ambos cuadros de diálogo, y se actualizará y registrará el servicio.</span><span class="sxs-lookup"><span data-stu-id="61fa9-131">Both dialog boxes close and the service is updated and registered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61fa9-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="61fa9-132">See Also</span></span>  
 <span data-ttu-id="61fa9-133">[Diseñador de captura de datos modificados para Oracle de Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="61fa9-133">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="61fa9-134">Crear y editar un servicio CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="61fa9-134">Create and Edit an Oracle CDC Service</span></span>](create-and-edit-an-oracle-cdc-service.md)  
  
  
