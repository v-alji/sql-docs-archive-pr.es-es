---
title: Administrar objetos mediante el Explorador de objetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SQLSERVEROBJECTEXPLORER.DHELP
helpviewer_keywords:
- Object Explorer F1 Help
- OE F1 Help
- OE Help
ms.assetid: e60367a7-3fdd-40b8-82bb-9e819d78de5a
author: stevestein
ms.author: sstein
ms.openlocfilehash: dc510c40cf98a1f08660bcafda8854281b70d9f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750438"
---
# <a name="manage-objects-by-using-object-explorer"></a><span data-ttu-id="bd7c7-102">Administrar objetos mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="bd7c7-102">Manage Objects by Using Object Explorer</span></span>
  <span data-ttu-id="bd7c7-103">Puede utilizar el Explorador de objetos para administrar objetos, como bases de datos, tablas y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-103">You can use Object Explorer to manage objects such as databases, tables and stored procedures.</span></span>  
  
## <a name="viewing-objects-in-object-explorer"></a><span data-ttu-id="bd7c7-104">Ver objetos en el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="bd7c7-104">Viewing Objects in Object Explorer</span></span>  
 <span data-ttu-id="bd7c7-105">El Explorador de objetos utiliza una estructura de árbol para agrupar la información en carpetas.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-105">Object Explorer uses a tree structure to group information into folders.</span></span> <span data-ttu-id="bd7c7-106">Para expandir las carpetas, haga clic en el signo más (+) o haga doble clic en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-106">To expand folders, click the plus sign (+) or double-click the folder.</span></span> <span data-ttu-id="bd7c7-107">Expanda las carpetas para obtener información más detallada.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-107">Expand folders to show more detailed information.</span></span> <span data-ttu-id="bd7c7-108">Haga clic con el botón secundario en las carpetas o en los objetos para realizar tareas comunes.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-108">Right-click folders or objects to perform common tasks.</span></span> <span data-ttu-id="bd7c7-109">Haga doble clic en los objetos para realizar las tareas más comunes.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-109">Double-click objects to perform the most common task.</span></span>  
  
 <span data-ttu-id="bd7c7-110">La primera vez que expanda una carpeta, el Explorador de objetos pedirá al servidor información para rellenar el árbol.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-110">The first time you expand a folder, Object Explorer will query the server for information to populate the tree.</span></span> <span data-ttu-id="bd7c7-111">Mientras el árbol se rellena, puede realizar otras funciones.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-111">You can perform other functions while the tree is populating.</span></span> <span data-ttu-id="bd7c7-112">Mientras el Explorador de objetos rellena el árbol, puede hacer clic en **Detener** para interrumpir el proceso.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-112">While Object Explorer is populating the tree, you can click **Stop** to halt the process.</span></span> <span data-ttu-id="bd7c7-113">Otras acciones, como el filtrado de la lista, solo actuarán sobre la parte de la carpeta que esté rellena, a menos que se actualice la carpeta para volver a empezar a rellenar.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-113">Further actions, such as filtering the list, will only act upon the portion of the folder that was populated, unless you refresh the folder to start population again.</span></span>  
  
 <span data-ttu-id="bd7c7-114">Para conservar recursos cuando hay muchos objetos, las carpetas del árbol del Explorador de objetos no actualizan automáticamente su lista de contenido.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-114">To conserve resources when there are many objects, the folders in the Object Explorer tree do not automatically refresh their list of contents.</span></span> <span data-ttu-id="bd7c7-115">Para actualizar la lista de objetos de una carpeta, haga clic con el botón derecho en esa carpeta y, a continuación, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-115">To refresh the list of objects within a folder, right-click the folder, and then click **Refresh**.</span></span>  
  
 <span data-ttu-id="bd7c7-116">El Explorador de objetos solamente puede mostrar hasta 65536 objetos.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-116">Object Explorer can only display up to 65,536 objects.</span></span> <span data-ttu-id="bd7c7-117">Una vez superada esta cifra, no es posible desplazarse por otros objetos en el árbol del Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-117">After you have exceeded 65,536 visible objects, you cannot scroll through additional objects in the Object Explorer tree view.</span></span> <span data-ttu-id="bd7c7-118">Para ver objetos adicionales en el Explorador de objetos, cierre aquellos nodos que no esté utilizando o aplique filtros para reducir el número de objetos.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-118">To view additional objects in Object Explorer, close nodes that you are not using or apply filtering to reduce the number of objects.</span></span>  
  
## <a name="filtering-the-list-of-objects-in-object-explorer"></a><span data-ttu-id="bd7c7-119">Filtrar la lista de objetos en el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="bd7c7-119">Filtering the List of Objects in Object Explorer</span></span>  
 <span data-ttu-id="bd7c7-120">Cuando una carpeta contiene un gran número de objetos, puede ser difícil encontrar el que se busca.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-120">When a folder contains a large number of objects, it may be difficult to find the object you are looking for.</span></span> <span data-ttu-id="bd7c7-121">En estos casos, utilice la característica de filtro del Explorador de objetos a fin de reducir la lista.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-121">In such cases, use the filter feature of Object Explorer to reduce the list to a smaller size.</span></span> <span data-ttu-id="bd7c7-122">Por ejemplo, quizás desee buscar un usuario de una base de datos concreta o la última tabla creada en listas que contienen cientos de objetos.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-122">For example, you may want to find a specific database user or the most recently created table in lists that contain hundreds of objects.</span></span> <span data-ttu-id="bd7c7-123">Haga clic en la carpeta que desea filtrar y, a continuación, en el botón de filtro para abrir el cuadro de diálogo **Configuración del filtro** .</span><span class="sxs-lookup"><span data-stu-id="bd7c7-123">Click on the folder that you want to filter, and then click the filter button to open the **Filter Settings** dialog box.</span></span> <span data-ttu-id="bd7c7-124">Es posible filtrar la lista por nombre, fecha de creación y, algunas veces, por esquema, así como proporcionar operadores de filtrado adicionales como **Empieza por**, **Contiene**y **Entre**.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-124">You can filter the list by name, create date, and sometimes schema, and provide additional filtering operators like **Starts with**, **Contains**, and **Between**.</span></span>  
  
## <a name="multi-select"></a><span data-ttu-id="bd7c7-125">Selección múltiple</span><span class="sxs-lookup"><span data-stu-id="bd7c7-125">Multi-select</span></span>  
 <span data-ttu-id="bd7c7-126">El Explorador de objetos solamente permite seleccionar un objeto cada vez.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-126">Only one object can be selected at a time in Object Explorer.</span></span> <span data-ttu-id="bd7c7-127">Para seleccionar varios elementos, presione **F7** para abrir la página **Detalles del Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-127">To select multiple items, press **F7** to open the **Object Explorer Details Page**.</span></span> <span data-ttu-id="bd7c7-128">La página **Detalles del Explorador de objetos** admite la selección múltiple.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-128">The **Object Explorer Details Page** supports multi-select.</span></span>  
  
## <a name="register-a-server-from-object-explorer"></a><span data-ttu-id="bd7c7-129">Registrar un servidor del Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="bd7c7-129">Register a Server from Object Explorer</span></span>  
 <span data-ttu-id="bd7c7-130">Una vez conectado a un servidor, es muy sencillo registrar ese servidor para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-130">When connected to a server, you can easily register the server for future use.</span></span> <span data-ttu-id="bd7c7-131">En el Explorador de objetos, haga clic con el botón derecho en el nombre del servidor y, a continuación, haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-131">In Object Explorer, right-click the server name, and then click **Register**.</span></span> <span data-ttu-id="bd7c7-132">En el cuadro de diálogo **Registrar servidor** , especifique en qué lugar del árbol del grupo de servidores desea colocar ese servidor.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-132">In the **Register Server** dialog box, specify where in the server group tree you want to place the server.</span></span> <span data-ttu-id="bd7c7-133">En el cuadro **Nombre del servidor** , puede sustituir el nombre del servidor por otro más explicativo.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-133">In the **Server name** box, you can replace the server name with a more meaningful server name.</span></span> <span data-ttu-id="bd7c7-134">Por ejemplo, puede registrar el servidor **APSQL02** con un nombre más descriptivo, como "**Cuentas por pagar**".</span><span class="sxs-lookup"><span data-stu-id="bd7c7-134">For example, you could register server **APSQL02** with a more meaningful name such as "**Accounts Payable**".</span></span>  
  
## <a name="performing-actions-on-object-explorer-nodes"></a><span data-ttu-id="bd7c7-135">Ejecutar acciones en nodos del Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="bd7c7-135">Performing Actions on Object Explorer Nodes</span></span>  
 <span data-ttu-id="bd7c7-136">Las acciones se llevan a cabo en los objetos haciendo clic con el botón secundario en el nodo del Explorador de objetos que representa el objeto.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-136">You perform actions on objects by right clicking the Object Explorer node representing the object.</span></span> <span data-ttu-id="bd7c7-137">Cada tipo de objeto admite un conjunto único de acciones del botón secundario.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-137">Each type of object supports a unique set of right-click actions.</span></span> <span data-ttu-id="bd7c7-138">Algunos de los tipos de acciones que puede realizar con los menús del botón secundario son:</span><span class="sxs-lookup"><span data-stu-id="bd7c7-138">Some of the types of actions you can perform by using the right-click menus include:</span></span>  
  
### <a name="open-a-connected-query-editor"></a><span data-ttu-id="bd7c7-139">Abrir un Editor de consultas conectado</span><span class="sxs-lookup"><span data-stu-id="bd7c7-139">Open a Connected Query Editor</span></span>  
 <span data-ttu-id="bd7c7-140">Cuando el Explorador de objetos está conectado a un servidor, es posible abrir una ventana nueva del Editor de código mediante los valores de conexión del Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-140">When Object Explorer is connected to a server, you can open a new Code Editor window using the connection settings of Object Explorer.</span></span> <span data-ttu-id="bd7c7-141">Para abrir una ventana nueva del Editor de código, haga clic con el botón derecho en el nombre del servidor en el Explorador de objetos y, a continuación, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-141">To open a new Code Editor window, right-click the server name in Object Explorer, and then click **New Query**.</span></span> <span data-ttu-id="bd7c7-142">Para abrir una ventana del Editor de código mediante una base de datos concreta, haga clic con el botón derecho en el nombre del servidor y, a continuación, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-142">To open a Code Editor window using a particular database, right-click the database name, and then click **New Query**.</span></span> <span data-ttu-id="bd7c7-143">Al abrir una consulta nueva para un servidor de Analysis Services, puede seleccionar consultas DMX, MDX o XMLA.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-143">When opening a new query for an Analysis Services server, you can select DMX, MDX, or XMLA queries.</span></span>  
  
### <a name="start-powershell"></a><span data-ttu-id="bd7c7-144">Iniciar PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd7c7-144">Start PowerShell</span></span>  
 <span data-ttu-id="bd7c7-145">Puede iniciar una sesión de PowerShell haciendo clic con el botón derecho en la mayoría de las carpetas y objetos en el árbol del Explorador de objetos y seleccionando **Iniciar PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-145">You can start a PowerShell session by right-clicking most folders and objects in the Object Explorer tree and selecting **Start PowerShell**.</span></span> <span data-ttu-id="bd7c7-146">De este modo se inicia una sesión de PowerShell que tiene habilitada la compatibilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell, y tiene establecida la ruta de acceso al objeto en el que hizo clic con el botón secundario en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-146">This starts a PowerShell session that has the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell support enabled, and the path set to the object you right-clicked in Object Explorer.</span></span> <span data-ttu-id="bd7c7-147">A continuación, puede escribir comandos de PowerShell en un entorno interactivo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd7c7-147">You can then enter PowerShell commands in an interactive PowerShell environment.</span></span> <span data-ttu-id="bd7c7-148">Para más información, consulte el artículo sobre [SQL Server PowerShell](../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="bd7c7-148">For more information, see [SQL Server PowerShell](../../powershell/sql-server-powershell.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7c7-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd7c7-149">See Also</span></span>  
 <span data-ttu-id="bd7c7-150">[Explorador de objetos](object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="bd7c7-150">[Object Explorer](object-explorer.md) </span></span>  
 <span data-ttu-id="bd7c7-151">[Abra y configure Explorador de objetos](open-and-configure-object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="bd7c7-151">[Open and Configure Object Explorer](open-and-configure-object-explorer.md) </span></span>  
 <span data-ttu-id="bd7c7-152">[Conectarse a una instancia desde Explorador de objetos](connect-to-an-instance-from-object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="bd7c7-152">[Connect to an Instance From Object Explorer](connect-to-an-instance-from-object-explorer.md) </span></span>  
 <span data-ttu-id="bd7c7-153">[Explorador de objetos panel de detalles](object-explorer-details-pane.md) </span><span class="sxs-lookup"><span data-stu-id="bd7c7-153">[Object Explorer Details Pane](object-explorer-details-pane.md) </span></span>  
 [<span data-ttu-id="bd7c7-154">Informes personalizados en Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd7c7-154">Custom Reports in Management Studio</span></span>](custom-reports-in-management-studio.md)  
  
  