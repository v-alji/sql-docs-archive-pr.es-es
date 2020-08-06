---
title: Cambiar control de código fuente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- IDD_SCC_CONNECTION_DIALOG
helpviewer_keywords:
- Change Source Control dialog box
ms.assetid: e6a5d83c-5809-4c56-907a-73d0c7ccdd7a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 55831529243608e8c71972a31009e5672fb0234f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674361"
---
# <a name="change-source-control"></a><span data-ttu-id="13ea8-102">Cambiar el control de código fuente</span><span class="sxs-lookup"><span data-stu-id="13ea8-102">Change Source Control</span></span>
  <span data-ttu-id="13ea8-103">Crea y administra las conexiones y los enlaces que vinculan una solución o un proyecto guardados localmente con una carpeta de la base de datos de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="13ea8-103">Creates and manages the connections and bindings that link a locally saved solution or project to a source control database folder.</span></span>  
  
## <a name="dialog-box-access"></a><span data-ttu-id="13ea8-104">Acceso al cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="13ea8-104">Dialog Box Access</span></span>  
 <span data-ttu-id="13ea8-105">En [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], seleccione un elemento en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="13ea8-105">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], select an item in Solution Explorer.</span></span> <span data-ttu-id="13ea8-106">En el menú **Archivo** , haga clic en **Control de código fuente**y en **Cambiar control de código fuente**.</span><span class="sxs-lookup"><span data-stu-id="13ea8-106">On the **File** menu, click **Source Control**, and then **Change Source Control**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13ea8-107">También se puede obtener acceso a este cuadro de diálogo haciendo clic con el botón secundario en el elemento, en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="13ea8-107">This dialog box is also available by right-clicking the item in Solution Explorer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="13ea8-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="13ea8-108">Options</span></span>  
 <span data-ttu-id="13ea8-109">**Volver**</span><span class="sxs-lookup"><span data-stu-id="13ea8-109">**Bind**</span></span>  
 <span data-ttu-id="13ea8-110">Asocie elementos seleccionados con una ubicación del servidor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="13ea8-110">Associate selected items with a specified source control server location.</span></span> <span data-ttu-id="13ea8-111">Por ejemplo, puede utilizar este botón para enlazar con las últimas carpetas y bases de datos conocidas del servidor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="13ea8-111">For example, you can use this button to bind to the last known source control server folder and database.</span></span> <span data-ttu-id="13ea8-112">Si no encuentra una base de datos o una carpeta del servidor recientes, se le indicará que especifique otras.</span><span class="sxs-lookup"><span data-stu-id="13ea8-112">If a recent server folder or database cannot be found, you are prompted to specify another.</span></span>  
  
 <span data-ttu-id="13ea8-113">**Browse**</span><span class="sxs-lookup"><span data-stu-id="13ea8-113">**Browse**</span></span>  
 <span data-ttu-id="13ea8-114">Navegue a una nueva ubicación del servidor de control de código fuente del elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="13ea8-114">Navigate to a new source control server location for the specified item.</span></span>  
  
 <span data-ttu-id="13ea8-115">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="13ea8-115">**Columns**</span></span>  
 <span data-ttu-id="13ea8-116">Identifique las columnas que se mostrarán y el orden en el que deben aparecer.</span><span class="sxs-lookup"><span data-stu-id="13ea8-116">Identify columns to display and the order in which they are displayed.</span></span>  
  
 <span data-ttu-id="13ea8-117">**Conexión**</span><span class="sxs-lookup"><span data-stu-id="13ea8-117">**Connect**</span></span>  
 <span data-ttu-id="13ea8-118">Cree una conexión entre los elementos seleccionados y el servidor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="13ea8-118">Create a connection between selected items and the source control server.</span></span>  
  
 <span data-ttu-id="13ea8-119">**Conectada**</span><span class="sxs-lookup"><span data-stu-id="13ea8-119">**Connected**</span></span>  
 <span data-ttu-id="13ea8-120">Muestra el estado de conexión de una solución o un proyecto seleccionados.</span><span class="sxs-lookup"><span data-stu-id="13ea8-120">Displays the connection status of a selected solution or project.</span></span>  
  
 <span data-ttu-id="13ea8-121">**Desconexión**</span><span class="sxs-lookup"><span data-stu-id="13ea8-121">**Disconnect**</span></span>  
 <span data-ttu-id="13ea8-122">Desconecte la copia local de una solución o un proyecto del equipo de su copia maestra en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="13ea8-122">Disconnect the local copy of a solution or project on your computer from its master copy in the database.</span></span> <span data-ttu-id="13ea8-123">Utilice este comando antes de dejar sin conexión el equipo del servidor de control de código fuente, por ejemplo, al trabajar sin conexión en su equipo portátil.</span><span class="sxs-lookup"><span data-stu-id="13ea8-123">Use this command before disconnecting your computer from the source control server, for example, when working offline on your laptop.</span></span>  
  
 <span data-ttu-id="13ea8-124">**OK (CORRECTO)**</span><span class="sxs-lookup"><span data-stu-id="13ea8-124">**OK**</span></span>  
 <span data-ttu-id="13ea8-125">Acepta los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="13ea8-125">Accept changes made in the dialog box.</span></span>  
  
 <span data-ttu-id="13ea8-126">**Proveedor**</span><span class="sxs-lookup"><span data-stu-id="13ea8-126">**Provider**</span></span>  
 <span data-ttu-id="13ea8-127">Muestra el nombre del complemento de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="13ea8-127">Displays the name of your source control plug-in.</span></span>  
  
 <span data-ttu-id="13ea8-128">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="13ea8-128">**Refresh**</span></span>  
 <span data-ttu-id="13ea8-129">Actualiza la información de conexión de todos los proyectos que aparecen en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="13ea8-129">Refreshes the connection information for all projects listed in this dialog box.</span></span>  
  
 <span data-ttu-id="13ea8-130">**Enlace del servidor**</span><span class="sxs-lookup"><span data-stu-id="13ea8-130">**Server Binding**</span></span>  
 <span data-ttu-id="13ea8-131">Indica el enlace del elemento con un servidor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="13ea8-131">Indicates the item's binding to a source control server.</span></span>  
  
 <span data-ttu-id="13ea8-132">**Nombre de servidor**</span><span class="sxs-lookup"><span data-stu-id="13ea8-132">**Server Name**</span></span>  
 <span data-ttu-id="13ea8-133">Muestra el nombre del servidor de control de código fuente con el que están enlazados el proyecto o la solución correspondientes.</span><span class="sxs-lookup"><span data-stu-id="13ea8-133">Displays the name of the source control server to which the corresponding solution or project is bound.</span></span>  
  
 <span data-ttu-id="13ea8-134">**Solución/Proyecto**</span><span class="sxs-lookup"><span data-stu-id="13ea8-134">**Solution/Project**</span></span>  
 <span data-ttu-id="13ea8-135">Muestra el nombre de cada solución y proyecto de la selección actual.</span><span class="sxs-lookup"><span data-stu-id="13ea8-135">Displays the name of each solution and project in the current selection.</span></span>  
  
 <span data-ttu-id="13ea8-136">**Sort**</span><span class="sxs-lookup"><span data-stu-id="13ea8-136">**Sort**</span></span>  
 <span data-ttu-id="13ea8-137">Ordena las columnas mostradas.</span><span class="sxs-lookup"><span data-stu-id="13ea8-137">Sort the order of displayed columns.</span></span>  
  
 <span data-ttu-id="13ea8-138">**Estado**</span><span class="sxs-lookup"><span data-stu-id="13ea8-138">**Status**</span></span>  
 <span data-ttu-id="13ea8-139">Identifica el estado de conexión y enlace de un elemento.</span><span class="sxs-lookup"><span data-stu-id="13ea8-139">Identifies the binding and connection status of an item.</span></span> <span data-ttu-id="13ea8-140">Las opciones posibles son:</span><span class="sxs-lookup"><span data-stu-id="13ea8-140">Possible options are:</span></span>  
  
|<span data-ttu-id="13ea8-141">**Opción**</span><span class="sxs-lookup"><span data-stu-id="13ea8-141">**Option**</span></span>|<span data-ttu-id="13ea8-142">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="13ea8-142">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="13ea8-143">Válido</span><span class="sxs-lookup"><span data-stu-id="13ea8-143">Valid</span></span>|<span data-ttu-id="13ea8-144">El elemento está correctamente enlazado y conectado con la carpeta de servidor a la que pertenece.</span><span class="sxs-lookup"><span data-stu-id="13ea8-144">The item is correctly bound and connected to the server folder to which it belongs.</span></span>|  
|<span data-ttu-id="13ea8-145">No válida</span><span class="sxs-lookup"><span data-stu-id="13ea8-145">Invalid</span></span>|<span data-ttu-id="13ea8-146">El elemento no está correctamente enlazado o está desconectado de la carpeta a la que pertenece.</span><span class="sxs-lookup"><span data-stu-id="13ea8-146">The item is incorrectly bound to or disconnected from the folder to which it belongs.</span></span> <span data-ttu-id="13ea8-147">Utilice el comando **Agregar a control de código fuente** en lugar de **Enlazar** para este elemento.</span><span class="sxs-lookup"><span data-stu-id="13ea8-147">Use the **Add to Source Control** command instead of **Bind** for this item.</span></span>|  
|<span data-ttu-id="13ea8-148">Desconocido</span><span class="sxs-lookup"><span data-stu-id="13ea8-148">Unknown</span></span>|<span data-ttu-id="13ea8-149">El estado del elemento en el control de código fuente no se ha determinado todavía.</span><span class="sxs-lookup"><span data-stu-id="13ea8-149">The status of the item under source control has not yet been determined.</span></span>|  
|<span data-ttu-id="13ea8-150">No controlado</span><span class="sxs-lookup"><span data-stu-id="13ea8-150">Not Controlled</span></span>|<span data-ttu-id="13ea8-151">El elemento no se ha colocado en el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="13ea8-151">The item has not been placed under source control.</span></span>|  
  
 <span data-ttu-id="13ea8-152">**Desenlace**</span><span class="sxs-lookup"><span data-stu-id="13ea8-152">**Unbind**</span></span>  
 <span data-ttu-id="13ea8-153">Muestra el cuadro de diálogo **Control de código fuente** para permitirle eliminar los elementos seleccionados del control de código fuente y anular definitivamente la asociación de los elementos con sus carpetas actuales.</span><span class="sxs-lookup"><span data-stu-id="13ea8-153">Display the **Source Control** dialog box to allow you to remove selected items from source control and permanently disassociate the items from their present folders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ea8-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13ea8-154">See Also</span></span>  
 [<span data-ttu-id="13ea8-155">Control de código fuente del Explorador de soluciones</span><span class="sxs-lookup"><span data-stu-id="13ea8-155">Solution Explorer Source Control</span></span>](../../2014/database-engine/solution-explorer-source-control.md)  
  
  
