---
title: Barra de estado (Editor de consultas del motor de base de datos)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7f2d6f4-bb94-4cf5-a096-c34397e679af
author: rothja
ms.author: jroth
ms.openlocfilehash: 743ae0a4152daee19aa67f85337ae4077a3ed7f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675799"
---
# <a name="status-bar-database-engine-query-editor"></a><span data-ttu-id="5d83e-102">Barra de estado (Editor de consultas del motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="5d83e-102">Status Bar (Database Engine Query Editor)</span></span>
  <span data-ttu-id="5d83e-103">La barra de estado de las ventanas del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] puede codificarse por colores para indicar la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] a la que está conectada cada ventana.</span><span class="sxs-lookup"><span data-stu-id="5d83e-103">The status bar of [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor windows can be color coded to indicate which instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] each window is connected to.</span></span>  
  
1.  <span data-ttu-id="5d83e-104">**Antes de empezar:**  [Colores de la barra de estado](#StatusBarColors)</span><span class="sxs-lookup"><span data-stu-id="5d83e-104">**Before you begin:**  [Status Bar Colors](#StatusBarColors)</span></span>  
  
2.  <span data-ttu-id="5d83e-105">**Para establecer un color de estado del servidor en:**  [Explorador de objetos](#SetOEServerColor), [Servidor registrado](#SetRegServerColor)</span><span class="sxs-lookup"><span data-stu-id="5d83e-105">**To set a server status color in:**  [Object Explorer](#SetOEServerColor), [Registered Server](#SetRegServerColor)</span></span>  
  
3.  <span data-ttu-id="5d83e-106">**Para usar un color de estado:**  [Abrir el editor de consultas usando un color de servidor](#OpenServerColor), [Abrir un editor de consultas especificando un color de estado](#OpenSpecColor)</span><span class="sxs-lookup"><span data-stu-id="5d83e-106">**To use a status color:**  [Open Query Editor Using a Server Color](#OpenServerColor), [Open a Query Editor Specifying a Status Color](#OpenSpecColor)</span></span>  
  
##  <a name="status-bar-colors"></a><a name="StatusBarColors"></a> <span data-ttu-id="5d83e-107">Colores de la barra de estado</span><span class="sxs-lookup"><span data-stu-id="5d83e-107">Status Bar Colors</span></span>  
 <span data-ttu-id="5d83e-108">Puede asociar el color de una barra de estado con un determinado nodo del servidor en el **Explorador de objetos** o en los **Servidores registrados**.</span><span class="sxs-lookup"><span data-stu-id="5d83e-108">You can associate a status bar color with a specific server node in either **Object Explorer** or **Registered Servers**.</span></span> <span data-ttu-id="5d83e-109">Los colores solo se pueden especificar en los nodos del servidor conectados a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)], no en los nodos del servidor de otras tecnologías de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5d83e-109">The colors can only be specified for server nodes connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], not server nodes for other SQL Server technologies.</span></span> <span data-ttu-id="5d83e-110">También puede especificar un color personalizado para la barra de estado cada vez que conecte una nueva ventana del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d83e-110">You can also specify a custom status bar color each time you connect a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="5d83e-111">Puede abrir una ventana del Editor de consultas mediante el color de estado definido en el nodo de servidor o especificar un color único para la ventana del editor.</span><span class="sxs-lookup"><span data-stu-id="5d83e-111">You can then open a query editor window using either the status color defined for the server node, or specify a unique color for that editor window.</span></span>  
  
 <span data-ttu-id="5d83e-112">Si desea establecer un color de barra de estado personalizado para un nodo de servidor en el Explorador de objetos, deberá hacerlo al realizar la conexión.</span><span class="sxs-lookup"><span data-stu-id="5d83e-112">Setting a custom status bar color for a server node in Object Explorer must be done when making the connection.</span></span> <span data-ttu-id="5d83e-113">Para cambiar el color asociado a un nodo de servidor existente, deberá desconectar y conectarse de nuevo especificando el nuevo color.</span><span class="sxs-lookup"><span data-stu-id="5d83e-113">To change the color associated with an existing server node, you must disconnect and then reconnect specifying the new color.</span></span>  
  
##  <a name="set-the-status-color-for-a-server-in-object-explorer"></a><a name="SetOEServerColor"></a> <span data-ttu-id="5d83e-114">Establecer el color de estado de un servidor en el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="5d83e-114">Set the Status Color for a Server in Object Explorer</span></span>  
 <span data-ttu-id="5d83e-115">**Para establecer el color de estado del servidor en el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="5d83e-115">**To set a server status color in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="5d83e-116">En el **Explorador de objetos**, haga clic en el botón **Conectar** y después seleccione **Motor de base de datos...** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-116">In **Object Explorer**, select the **Connect** button and then select **Database Engine...**.</span></span>  
  
2.  <span data-ttu-id="5d83e-117">En el cuadro de diálogo **Conectar con el servidor**, seleccione **Options >>** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-117">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
3.  <span data-ttu-id="5d83e-118">Active la casilla **Usar color personalizado** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-118">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="5d83e-119">Para elegir el color, haga clic en el botón **Seleccionar…** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-119">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="5d83e-120">Seleccione un color básico o personalizado y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="5d83e-120">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="5d83e-121">Complete el resto de la información de conexión y, a continuación, haga clic en el botón **Conectar** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-121">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
##  <a name="set-the-status-color-for-a-registered-server"></a><a name="SetRegServerColor"></a> <span data-ttu-id="5d83e-122">Establecer el color de estado en un servidor registrado</span><span class="sxs-lookup"><span data-stu-id="5d83e-122">Set the Status Color For a Registered Server</span></span>  
 <span data-ttu-id="5d83e-123">**Para establecer el color de estado en un servidor registrado**</span><span class="sxs-lookup"><span data-stu-id="5d83e-123">**To set a server color For a Registered Server**</span></span>  
  
1.  <span data-ttu-id="5d83e-124">En **Servidores registrados**, haga clic con el botón derecho en el nodo de servidor y después haga clic en **Propiedades...** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-124">In **Registered Servers**, right click the server node and then select **Properties...**.</span></span>  
  
2.  <span data-ttu-id="5d83e-125">En el cuadro de diálogo **Editar propiedades de registro de servidor** , seleccione la pestaña **Propiedades de conexión** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-125">On the **Edit Server Registration Properties** dialog, select the **Connection Properties** tab.</span></span>  
  
3.  <span data-ttu-id="5d83e-126">Active la casilla **Usar color personalizado** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-126">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="5d83e-127">Para elegir el color, haga clic en el botón **Seleccionar…** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-127">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="5d83e-128">Seleccione un color básico o personalizado y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="5d83e-128">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="5d83e-129">Haga clic en el botón **Guardar** del cuadro de diálogo **Editar propiedades de registro de servidor** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-129">Select the **Save** button on the **Edit Server Registration Properties** dialog.</span></span>  
  
##  <a name="open-an-editor-using-a-server-color"></a><a name="OpenServerColor"></a> <span data-ttu-id="5d83e-130">Abrir un editor mediante un color de servidor</span><span class="sxs-lookup"><span data-stu-id="5d83e-130">Open An Editor Using a Server Color</span></span>  
 <span data-ttu-id="5d83e-131">**Para abrir una ventana del editor mediante un color de servidor**</span><span class="sxs-lookup"><span data-stu-id="5d83e-131">**To open an editor window using a server color**</span></span>  
  
-   <span data-ttu-id="5d83e-132">Haga clic con el botón derecho en un nodo del servidor en el **Explorador de objetos** o en **Servidores registrados**y seleccione **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5d83e-132">Right-click a server node in either **Object Explorer** or **Registered Servers**, and select **New Query**.</span></span>  
  
-   <span data-ttu-id="5d83e-133">O bien, resalte un nodo servidor y, a continuación, haga clic en el botón de la barra de herramientas **Nueva consulta** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-133">Alternatively, highlight a server node, and then select the **New Query** toolbar button.</span></span>  
  
-   <span data-ttu-id="5d83e-134">La barra de estado de la ventana del editor usará el color definido para el servidor asociado.</span><span class="sxs-lookup"><span data-stu-id="5d83e-134">The status bar in the editor window will use the color defined for the associated server.</span></span>  
  
##  <a name="open-an-editor-specifying-a-status-color"></a><a name="OpenSpecColor"></a> <span data-ttu-id="5d83e-135">Abrir un editor especificando un color de estado</span><span class="sxs-lookup"><span data-stu-id="5d83e-135">Open an Editor Specifying a Status Color</span></span>  
 <span data-ttu-id="5d83e-136">**Para abrir una ventana del editor especificando un color de estado**</span><span class="sxs-lookup"><span data-stu-id="5d83e-136">**To open an editor window specifying a status color**</span></span>  
  
-   <span data-ttu-id="5d83e-137">Abra el menú **Archivo** , seleccione **Nuevo**y, a continuación, seleccione **Consulta de motor de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="5d83e-137">Open the **File** menu, select **New**, and then select **Database Engine Query**.</span></span>  
  
-   <span data-ttu-id="5d83e-138">En el cuadro de diálogo **Conectar con el servidor**, seleccione **Options >>** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-138">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
-   <span data-ttu-id="5d83e-139">Active la casilla **Usar color personalizado** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-139">Select the **Use custom color** check box.</span></span>  
  
-   <span data-ttu-id="5d83e-140">Para elegir el color, haga clic en el botón **Seleccionar…** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-140">To select the color, select the **Select...** button.</span></span>  
  
-   <span data-ttu-id="5d83e-141">Seleccione un color básico o personalizado y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="5d83e-141">Select either a basic or custom color, then select OK.</span></span>  
  
-   <span data-ttu-id="5d83e-142">Complete el resto de la información de conexión y, a continuación, haga clic en el botón **Conectar** .</span><span class="sxs-lookup"><span data-stu-id="5d83e-142">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d83e-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d83e-143">See Also</span></span>  
 [<span data-ttu-id="5d83e-144">Editores de consultas y texto &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="5d83e-144">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](../scripting/query-and-text-editors-sql-server-management-studio.md)  
  
  
