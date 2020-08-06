---
title: Cómo trabajar con CDC Service | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db5c718a-6e7f-48ec-82a3-9d5b131716e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cfb5a0ed0e9ded8e0be118deb3c819626448896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671632"
---
# <a name="how-to-work-with-cdc-services"></a><span data-ttu-id="246ed-102">Cómo trabajar con servicios CDC</span><span class="sxs-lookup"><span data-stu-id="246ed-102">How to Work with CDC Services</span></span>
  <span data-ttu-id="246ed-103">En este procedimiento se describe cómo usar la Consola de configuración del servicio CDC para preparar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de manera que funcione con servicios CDC de Oracle y para crear un nuevo servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="246ed-103">This procedure describes how to use the CDC Service Configuration Console to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to work with Oracle CDC Services and to create a new CDC service.</span></span>  
  
### <a name="to-work-with-cdc-services"></a><span data-ttu-id="246ed-104">Para trabajar con servicios CDC</span><span class="sxs-lookup"><span data-stu-id="246ed-104">To work with CDC services</span></span>  
  
1.  <span data-ttu-id="246ed-105">En el menú **Inicio** , seleccione **Configuración del servicio CDC para Oracle**.</span><span class="sxs-lookup"><span data-stu-id="246ed-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="246ed-106">En el panel izquierdo, seleccione **Local CDC Services** (Servicios CDC locales), el nivel raíz.</span><span class="sxs-lookup"><span data-stu-id="246ed-106">From the left pane, select **Local CDC Services** (the root level).</span></span>  
  
3.  <span data-ttu-id="246ed-107">Realice una o ambas de las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="246ed-107">You carry out the one or both of the following tasks:</span></span>  
  
    -   <span data-ttu-id="246ed-108">**Preparar SQL Server**</span><span class="sxs-lookup"><span data-stu-id="246ed-108">**Prepare SQL Server**</span></span>  
  
         <span data-ttu-id="246ed-109">Seleccione esta opción en el panel **Acciones** del lado derecho de la Consola de configuración del servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="246ed-109">Select this option from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="246ed-110">También puede hacer clic con el botón derecho en **Local CDC Services** (Servicios CDC locales) y seleccionar **Prepare SQL Server**(Preparar SQL Server).</span><span class="sxs-lookup"><span data-stu-id="246ed-110">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
         <span data-ttu-id="246ed-111">Se abrirá el cuadro de diálogo Preparando instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="246ed-111">The Preparing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance for Oracle CDC dialog box opens.</span></span>  
  
         <span data-ttu-id="246ed-112">Para preparar la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para los servicios CDC de Oracle, el inicio de sesión debe tener un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el rol fijo de servidor `dbcreator` .</span><span class="sxs-lookup"><span data-stu-id="246ed-112">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC services, the login must have a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with the `dbcreator` fixed server role.</span></span> <span data-ttu-id="246ed-113">Este inicio de sesión se emplea para crear la base de datos MSXDBCDC necesaria para agregar servicios CDC de Oracle y, después, instancias CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="246ed-113">This login is used to create the MSXDBCDC database that is required for adding Oracle CDC Services and, later on, Oracle CDC Instances.</span></span>  
  
         <span data-ttu-id="246ed-114">Para obtener información acerca de cómo usar este cuadro de diálogo, vea [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="246ed-114">For information on how to use this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span> <span data-ttu-id="246ed-115">Para obtener información sobre cómo habilitar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para CDC, vea [Cómo preparar SQL Server para CDC](how-to-prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="246ed-115">For information on how to enable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for CDC, see [How to Prepare SQL Server for CDC](how-to-prepare-sql-server-for-cdc.md).</span></span>  
  
    -   <span data-ttu-id="246ed-116">**Crear un nuevo servicio CDC**</span><span class="sxs-lookup"><span data-stu-id="246ed-116">**Create a new CDC service**</span></span>  
  
         <span data-ttu-id="246ed-117">Haga clic en **Nuevo servicio** en el panel **Acciones** del lado derecho de la Consola de configuración del servicio CDC.</span><span class="sxs-lookup"><span data-stu-id="246ed-117">Click **New Service** from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="246ed-118">También puede hacer clic con el botón derecho en **Local CDC Services** (Servicios CDC locales) y seleccionar **Nuevo servicio**.</span><span class="sxs-lookup"><span data-stu-id="246ed-118">You can also right-Click **Local CDC Services** and select **New Service**.</span></span>  
  
         <span data-ttu-id="246ed-119">Se abrirá el cuadro de diálogo Nuevo servicio CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="246ed-119">The New Oracle CDC Service dialog box opens.</span></span>  
  
         <span data-ttu-id="246ed-120">Para obtener información acerca de cómo usar este cuadro de diálogo, vea [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="246ed-120">For information on how to use this dialog box, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span></span> <span data-ttu-id="246ed-121">Para obtener información acerca de cómo crear o editar un servicio CDC, vea [Cómo crear y editar un servicio CDC](how-to-create-and-edit-a-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="246ed-121">For information on how to create or edit a CDC service, see [How to Create and Edit a CDC Service](how-to-create-and-edit-a-cdc-service.md).</span></span>  
  
         <span data-ttu-id="246ed-122">El inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usado por el servicio CDC de Oracle solo necesita ser miembro del rol fijo de servidor `public` ; no se necesita ningún otro privilegio.</span><span class="sxs-lookup"><span data-stu-id="246ed-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Oracle CDC Service only needs to be a member of the `public` fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="246ed-123">Pero, para crear el servicio CDC de Oracle, el inicio de sesión necesita tener permiso de escritura en la base de datos MSXDBCDC (por ejemplo, es necesario asignar el rol de base de datos **db_owner** al inicio de sesión).</span><span class="sxs-lookup"><span data-stu-id="246ed-123">However, to create the Oracle CDC Service, the login must have write permission to the MSXDBCDC database, for example the **db_owner** database role must be assigned to the login.</span></span> <span data-ttu-id="246ed-124">Cuando un inicio de sesión sin permiso de escritura para la base de datos MSXDBDCDC intenta crear una nueva instancia CDC de Oracle, se muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="246ed-124">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="246ed-125">Haga clic en **Aceptar** en ese cuadro de diálogo para mostrar el cuadro de diálogo Conectar con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="246ed-125">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span>  
  
         <span data-ttu-id="246ed-126">Para más información sobre cómo especificar las credenciales de un inicio de sesión que tenga permisos de escritura en la base de datos MSXDBCDC, como el rol de base de datos **db_owner** , vea [Crear y editar un servicio CDC de Oracle](create-and-edit-an-oracle-cdc-service.md) y [Conexión con SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="246ed-126">For information on how to enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) and [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246ed-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="246ed-127">See Also</span></span>  
 [<span data-ttu-id="246ed-128">Trabajar con servicios CDC</span><span class="sxs-lookup"><span data-stu-id="246ed-128">Work with CDC Services</span></span>](work-with-cdc-services.md)  
  
  
