---
title: Opciones (entorno-página general) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.SQLEnvironmentOptions
ms.assetid: c32ccdb8-2cf8-4c78-b474-a3abd3dbbd13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7712c568b478bd2ba958237ba3204246657b3a72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678005"
---
# <a name="options-environment-general-page"></a><span data-ttu-id="b7f30-102">Opciones (Entorno - Página General)</span><span class="sxs-lookup"><span data-stu-id="b7f30-102">Options (Environment-General Page)</span></span>
  <span data-ttu-id="b7f30-103">Use el cuadro de diálogo **Opciones** para configurar las acciones de inicio de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], opciones generales de administración de ventanas y otros valores de configuración generales.</span><span class="sxs-lookup"><span data-stu-id="b7f30-103">Use the **Options** dialog box to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] startup actions, general window management options, and other general settings.</span></span> <span data-ttu-id="b7f30-104">En el menú **Herramientas** , haga clic en **Opciones**, expanda la carpeta **Entorno** y haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="b7f30-104">On the **Tools** menu, click **Options**, expand the **Environment** folder, and then click **General**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b7f30-105">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b7f30-105">UI element list</span></span>  
 <span data-ttu-id="b7f30-106">**Al iniciar**</span><span class="sxs-lookup"><span data-stu-id="b7f30-106">**At startup**</span></span>  
 <span data-ttu-id="b7f30-107">Seleccione la acción que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] debe llevar a cabo una vez que se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="b7f30-107">Select the action for [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to perform when it is started.</span></span> <span data-ttu-id="b7f30-108">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="b7f30-108">The options are:</span></span>  
  
-   <span data-ttu-id="b7f30-109">**Abrir el Explorador de objetos** : solicita una conexión y abre el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="b7f30-109">**Open Object Explorer** prompts for a connection and then opens Object Explorer.</span></span>  
  
-   <span data-ttu-id="b7f30-110">**Abrir nueva ventana de consulta** : solicita una conexión y abre el Editor de consultas de SQL.</span><span class="sxs-lookup"><span data-stu-id="b7f30-110">**Open new query window** prompts for a connection and then opens SQL Query Editor.</span></span>  
  
-   <span data-ttu-id="b7f30-111">**Abrir el Explorador de objetos y una nueva ventana de consulta** : solicita una conexión y abre el Explorador de objetos y el Editor de consultas de SQL con dicha conexión.</span><span class="sxs-lookup"><span data-stu-id="b7f30-111">**Open Object Explorer and new query** prompts for a connection, then opens both Object Explorer and SQL Query Editor with that connection.</span></span>  
  
-   <span data-ttu-id="b7f30-112">**Abrir entorno vacío** : abre [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sin ninguna ventana del Editor de consultas de SQL y sin conectar el Explorador de objetos a un servidor.</span><span class="sxs-lookup"><span data-stu-id="b7f30-112">**Open empty environment** opens [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] without a SQL Query editor window and without connecting Object Explorer to a server.</span></span>  
  
 <span data-ttu-id="b7f30-113">**Ocultar objetos del sistema en el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="b7f30-113">**Hide system objects in Object Explorer**</span></span>  
 <span data-ttu-id="b7f30-114">Seleccione esta casilla para eliminar de la vista de árbol del Explorador de objetos las bases de datos del sistema, las tablas del sistema, las vistas del sistema y los procedimientos almacenados del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7f30-114">Select this check box to remove the system databases, system tables, system views, and system stored procedures from tree view in Object Explorer.</span></span> <span data-ttu-id="b7f30-115">Las funciones del sistema y los tipos de datos del sistema no se ocultan.</span><span class="sxs-lookup"><span data-stu-id="b7f30-115">System functions and system data types are not hidden.</span></span> <span data-ttu-id="b7f30-116">Esta opción solo se aplica a instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y no afecta a los servidores que ya están conectados en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="b7f30-116">This option only applies to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and does not affect servers already connected in Object Explorer.</span></span>  
  
## <a name="environment-layout"></a><span data-ttu-id="b7f30-117">Diseño del entorno</span><span class="sxs-lookup"><span data-stu-id="b7f30-117">Environment Layout</span></span>  
 <span data-ttu-id="b7f30-118">Para poder pasar del modo organizado por pestañas al modo de interfaz de múltiples documentos (MDI), debe cerrar y volver a abrir [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7f30-118">You must close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change between tabbed document and multiple-document interface (MDI) environment mode.</span></span>  
  
 <span data-ttu-id="b7f30-119">**Organización por pestañas**</span><span class="sxs-lookup"><span data-stu-id="b7f30-119">**Tabbed documents**</span></span>  
 <span data-ttu-id="b7f30-120">Seleccione esta opción para mostrar ventanas de documentos que estén agrupadas por pestañas en los editores.</span><span class="sxs-lookup"><span data-stu-id="b7f30-120">Select this option to display document windows that are tabbed together within editors.</span></span> <span data-ttu-id="b7f30-121">Las ventanas organizadas por pestañas son de gran utilidad para organizar los documentos y pasar de un documento abierto a otro.</span><span class="sxs-lookup"><span data-stu-id="b7f30-121">Tabbed document windows are useful for organizing and switching between multiple open documents.</span></span>  
  
 <span data-ttu-id="b7f30-122">**Entorno MDI**</span><span class="sxs-lookup"><span data-stu-id="b7f30-122">**MDI environment**</span></span>  
 <span data-ttu-id="b7f30-123">Seleccione esta opción para abrir documentos en un entorno MDI.</span><span class="sxs-lookup"><span data-stu-id="b7f30-123">Select this option to open documents in a MDI environment.</span></span> <span data-ttu-id="b7f30-124">Las ventanas de documento MDI son útiles para ganar espacio en la pantalla; de lo contrario, dicho espacio está ocupado por las pestañas del entorno organizado por pestañas.</span><span class="sxs-lookup"><span data-stu-id="b7f30-124">MDI document windows are useful for gaining the screen space that is otherwise taken up by the tabs in the tabbed documents environment.</span></span> <span data-ttu-id="b7f30-125">Si trabaja en modo MDI, para pasar de un documento a otro, presione las teclas CTRL+TAB, o utilice las opciones de organización del menú **Ventana** .</span><span class="sxs-lookup"><span data-stu-id="b7f30-125">When working in MDI mode, you can switch between documents by pressing CTRL+TAB, or you can use the tile options located on the **Window** menu.</span></span>  
  
## <a name="docked-tool-window-behavior"></a><span data-ttu-id="b7f30-126">Comportamiento de la ventana de herramientas acoplada</span><span class="sxs-lookup"><span data-stu-id="b7f30-126">Docked Tool Window Behavior</span></span>  
 <span data-ttu-id="b7f30-127">**El botón Cerrar afecta solo a la pestaña activa**</span><span class="sxs-lookup"><span data-stu-id="b7f30-127">**Close button affects active tab only**</span></span>  
 <span data-ttu-id="b7f30-128">Si esta casilla está seleccionada, solo se cierra la ventana de herramientas activa, no todas las ventanas del conjunto de ventanas acopladas.</span><span class="sxs-lookup"><span data-stu-id="b7f30-128">Specifies that when this check box is selected, only the tool window that has focus currently is closed and not all of the tool windows in the docked set.</span></span> <span data-ttu-id="b7f30-129">De forma predeterminada, esta casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="b7f30-129">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="b7f30-130">**El botón Ocultar automáticamente afecta solo a la pestaña activa**</span><span class="sxs-lookup"><span data-stu-id="b7f30-130">**Auto Hide button affects active tab only**</span></span>  
 <span data-ttu-id="b7f30-131">Si esta casilla está seleccionada, solo se oculta automáticamente la ventana de herramientas activa, no todas las ventanas del conjunto de ventanas acopladas.</span><span class="sxs-lookup"><span data-stu-id="b7f30-131">Specifies that when this check box is selected, only the tool window that has focus currently is hidden automatically, not all of the tool windows in the docked set.</span></span> <span data-ttu-id="b7f30-132">De forma predeterminada, esta casilla no está activada.</span><span class="sxs-lookup"><span data-stu-id="b7f30-132">By default, this check box is cleared.</span></span>  
  
## <a name="display"></a><span data-ttu-id="b7f30-133">Pantalla</span><span class="sxs-lookup"><span data-stu-id="b7f30-133">Display</span></span>  
 <span data-ttu-id="b7f30-134">**Mostrar n archivos de la lista de archivos recientes**</span><span class="sxs-lookup"><span data-stu-id="b7f30-134">**Display n files in recently used list**</span></span>  
 <span data-ttu-id="b7f30-135">Personaliza el número de proyectos y archivos recientes que aparecen en el menú **Archivo** .</span><span class="sxs-lookup"><span data-stu-id="b7f30-135">Customizes the number of recent projects and recent files that appear on the **File** menu.</span></span> <span data-ttu-id="b7f30-136">Escriba un número entre 1 y 24.</span><span class="sxs-lookup"><span data-stu-id="b7f30-136">Type a number between 1 and 24.</span></span> <span data-ttu-id="b7f30-137">El valor predeterminado es 4.</span><span class="sxs-lookup"><span data-stu-id="b7f30-137">The default is 4.</span></span> <span data-ttu-id="b7f30-138">Esta es una manera fácil de recuperar los proyectos de script y los proyectos de archivos y script usados recientemente.</span><span class="sxs-lookup"><span data-stu-id="b7f30-138">This is an easy way to retrieve recently used script projects and files and script projects.</span></span>  
  
  
