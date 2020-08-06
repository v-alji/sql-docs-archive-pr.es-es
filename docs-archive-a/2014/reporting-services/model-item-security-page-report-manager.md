---
title: Página seguridad de elemento de modelo (Administrador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.modelproperties.modelitemsecurity.f1
ms.assetid: 8c5b29ae-1f17-41f2-ab59-97899b8fb4fc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 928572437990c7f7fe1117c086c65c939aa9c999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662647"
---
# <a name="model-item-security-page-report-manager"></a><span data-ttu-id="b1338-102">Página Seguridad de elemento de modelo (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="b1338-102">Model Item Security Page (Report Manager)</span></span>
  <span data-ttu-id="b1338-103">Use esta página para proteger partes de un modelo concediendo o revocando permisos de solo lectura en elementos concretos.</span><span class="sxs-lookup"><span data-stu-id="b1338-103">Use this page to secure parts of a model by granting or revoking read-only permissions on particular items.</span></span> <span data-ttu-id="b1338-104">La seguridad del elemento de modelo afecta a la exploración de datos ad hoc en tiempo de ejecución y a la capacidad de usar partes de un modelo publicado cuando se crean informes en el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b1338-104">Model item security affects ad hoc data exploration at run time and the ability to use parts of a published model when creating reports in Report Builder.</span></span> <span data-ttu-id="b1338-105">Para usar esta característica, debe tener permisos de Administrador de contenido.</span><span class="sxs-lookup"><span data-stu-id="b1338-105">To use this feature, you must have Content Manager permissions.</span></span>  
  
 <span data-ttu-id="b1338-106">La seguridad del elemento de modelo se aplica a un modelo procesado en el servidor de informes y no afecta a los archivos .smdl que se modifican en el Diseñador de modelos o se usan en el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="b1338-106">Model item security is applied to a model that is processed on the report server and does not affect .smdl files that you edit in Model Designer or use in Report Designer.</span></span> <span data-ttu-id="b1338-107">Además, no tiene ningún efecto en los usuarios que tienen permiso para modificar una definición de modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-107">Furthermore, it has no effect on users who have permission to modify a model definition.</span></span> <span data-ttu-id="b1338-108">Los usuarios que tienen permisos de publicador o de administrador de contenido en un modelo pueden ver todas las partes del mismo, con independencia de que se aplique la seguridad del elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-108">Any user who has Content Manager or Publisher permissions on a model can see all parts of it, regardless of whether you apply model item security.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1338-109">Los elementos de modelo se pueden proteger más mediante el uso de filtros de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b1338-109">Model items can be further secured through the use of security filters.</span></span>  
  
 <span data-ttu-id="b1338-110">Puede definir la seguridad de elementos de modelo en las entidades, carpetas y campos individuales de un modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-110">You can define model item security on entities, folders, and individual fields within a model.</span></span> <span data-ttu-id="b1338-111">Dado que un modelo presenta este tipo de superficie grande de elementos protegibles, la herencia de permisos está integrada en el modelo de manera que pueda proteger un gran número de elementos a través de un número relativamente pequeño de asignaciones de roles.</span><span class="sxs-lookup"><span data-stu-id="b1338-111">Because a model presents such a large surface of securable items, permission inheritance is built into the model so that you can secure a large number of items through a relatively small number of role assignments.</span></span> <span data-ttu-id="b1338-112">La herencia de permisos se basa en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1338-112">Permission inheritance is based on the following:</span></span>  
  
-   <span data-ttu-id="b1338-113">Modelo</span><span class="sxs-lookup"><span data-stu-id="b1338-113">Model</span></span>  
  
-   <span data-ttu-id="b1338-114">Nodo raíz</span><span class="sxs-lookup"><span data-stu-id="b1338-114">Root node</span></span>  
  
-   <span data-ttu-id="b1338-115">Carpetas o entidades</span><span class="sxs-lookup"><span data-stu-id="b1338-115">Folders or entities</span></span>  
  
-   <span data-ttu-id="b1338-116">Fields</span><span class="sxs-lookup"><span data-stu-id="b1338-116">Fields</span></span>  
  
 <span data-ttu-id="b1338-117">Inicialmente, el permiso para tener acceso a los elementos de modelo se hereda a través de las asignaciones de roles que se establecen en el propio modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-117">Initially, permission to access to model items is inherited through role assignments that are set on the model itself.</span></span> <span data-ttu-id="b1338-118">Un usuario que tiene permiso para ver un modelo de una carpeta en el Administrador de informes puede ver todos los elementos del modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-118">A user who has permission to view a model in a folder in Report Manager can view all of the items in the model.</span></span>  
  
 <span data-ttu-id="b1338-119">Si aplica la seguridad de elemento de modelo, debe crear al menos una asignación de roles en el nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="b1338-119">If you apply model item security, you must create at least one role assignment on the root node.</span></span> <span data-ttu-id="b1338-120">Esta asignación de roles inicial en el nodo raíz se convierte en el nuevo origen de permisos heredados.</span><span class="sxs-lookup"><span data-stu-id="b1338-120">This initial role assignment on the root node becomes the new source of inherited permissions.</span></span> <span data-ttu-id="b1338-121">Todos los elementos de la jerarquía de modelo heredan automáticamente la asignación de roles en el nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="b1338-121">The role assignment on the root node is automatically inherited by all items in the model hierarchy.</span></span>  
  
 <span data-ttu-id="b1338-122">Para personalizar aún más los permisos en la exploración de datos, puede variar los permisos en las carpetas y entidades.</span><span class="sxs-lookup"><span data-stu-id="b1338-122">To further customize permissions on data exploration, you can vary permissions on folders and entities.</span></span> <span data-ttu-id="b1338-123">Finalmente, puede establecer permisos en campos individuales.</span><span class="sxs-lookup"><span data-stu-id="b1338-123">Finally, you can set permissions on individual fields.</span></span>  
  
 <span data-ttu-id="b1338-124">Para facilitar el mantenimiento de las asignaciones de roles, establezca solamente los permisos en carpetas o entidades en lugar de en campos individuales.</span><span class="sxs-lookup"><span data-stu-id="b1338-124">To make role assignments easier to maintain, set permissions only on folders or entities rather than individual fields.</span></span> <span data-ttu-id="b1338-125">No puede buscar las asignaciones de roles que crea.</span><span class="sxs-lookup"><span data-stu-id="b1338-125">You cannot search for role assignments that you create.</span></span> <span data-ttu-id="b1338-126">Si establece la seguridad en campos específicos y, posteriormente, desea actualizar la configuración de seguridad, debe hacer clic en el espacio de nombres del modelo para buscar los campos que ha protegido.</span><span class="sxs-lookup"><span data-stu-id="b1338-126">If you set security on specific fields and you want to update the security settings later, you must click through the model namespace to find the fields you secured.</span></span>  
  
 <span data-ttu-id="b1338-127">Para empezar, cree una asignación de roles en el nodo raíz y, a continuación, cree asignaciones de roles adicionales en las entidades y carpetas.</span><span class="sxs-lookup"><span data-stu-id="b1338-127">To get started, create a role assignment on the root node and then create additional role assignments on entities and folders.</span></span> <span data-ttu-id="b1338-128">Para borrar la seguridad de elemento de modelo, desactive la casilla **Proteger cada uno de los elementos de modelo de forma independiente para este modelo**.</span><span class="sxs-lookup"><span data-stu-id="b1338-128">To clear model item security, clear the check box for **Secure individual model items independently for this model**.</span></span> <span data-ttu-id="b1338-129">Al desactivar la casilla, se recuperan los permisos iniciales heredados del modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-129">Clearing the check box reverts back to the initial permissions that are inherited from the model.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="b1338-130">Navegación</span><span class="sxs-lookup"><span data-stu-id="b1338-130">Navigation</span></span>  
 <span data-ttu-id="b1338-131">Utilice el procedimiento siguiente para navegar hasta esta ubicación en la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="b1338-131">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-general-properties-page-for-a-report"></a><span data-ttu-id="b1338-132">Para abrir la página Propiedades generales de un informe</span><span class="sxs-lookup"><span data-stu-id="b1338-132">To open the General properties page for a report</span></span>  
  
1.  <span data-ttu-id="b1338-133">Abra el Administrador de informes y busque el modelo del que desea ver o configurar la seguridad para los elementos de modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-133">Open Report Manager, and locate the model for which you want to configure security for model items.</span></span>  
  
2.  <span data-ttu-id="b1338-134">Mantenga el mouse sobre el modelo y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b1338-134">Hover over the model, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="b1338-135">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="b1338-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="b1338-136">Se abrirá la página Propiedades generales correspondiente al modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-136">This opens the General properties page for the model.</span></span>  
  
4.  <span data-ttu-id="b1338-137">Seleccione la pestaña **Seguridad de elemento de modelo** .</span><span class="sxs-lookup"><span data-stu-id="b1338-137">Select the **Model Item Security** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b1338-138">Opciones</span><span class="sxs-lookup"><span data-stu-id="b1338-138">Options</span></span>  
 <span data-ttu-id="b1338-139">**Proteger cada uno de los elementos de modelo de forma independiente para este modelo**</span><span class="sxs-lookup"><span data-stu-id="b1338-139">**Secure individual model items independently for this model**</span></span>  
 <span data-ttu-id="b1338-140">Haga clic en esta casilla para habilitar la seguridad de elemento de modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-140">Click this check box to enable model item security.</span></span>  
  
 <span data-ttu-id="b1338-141">**Especifique la seguridad para los distintos elementos existentes en el modelo**</span><span class="sxs-lookup"><span data-stu-id="b1338-141">**Specify security for individual model items in the mode**</span></span>  
 <span data-ttu-id="b1338-142">Muestra todos los elementos de un modelo.</span><span class="sxs-lookup"><span data-stu-id="b1338-142">Shows all of the items in a model.</span></span> <span data-ttu-id="b1338-143">Puede navegar por el espacio de nombres del modelo para seleccionar el elemento que desea proteger.</span><span class="sxs-lookup"><span data-stu-id="b1338-143">You can navigate the model namespace to select the item you want to secure.</span></span> <span data-ttu-id="b1338-144">Solo puede seleccionar un elemento cada vez.</span><span class="sxs-lookup"><span data-stu-id="b1338-144">You can only select one item at a time.</span></span> <span data-ttu-id="b1338-145">Asegúrese de crear la primera asignación de roles en el nodo raíz antes de continuar con otras entidades y carpetas.</span><span class="sxs-lookup"><span data-stu-id="b1338-145">Be sure to create the first role assignment on the root node before proceeding to other entities and folders.</span></span>  
  
 <span data-ttu-id="b1338-146">**Heredar permisos del elemento primario**</span><span class="sxs-lookup"><span data-stu-id="b1338-146">**Inherit permissions from the parent item**</span></span>  
 <span data-ttu-id="b1338-147">Haga clic en esta opción para heredar la configuración de seguridad del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="b1338-147">Click this option to inherit the security settings of the parent item.</span></span>  
  
 <span data-ttu-id="b1338-148">**Asignar permiso de lectura a los usuarios y grupos siguientes (separados con puntos y coma)**</span><span class="sxs-lookup"><span data-stu-id="b1338-148">**Assign read permission to the following users and groups (semi-colon separated)**</span></span>  
 <span data-ttu-id="b1338-149">Haga clic en esta opción para especificar la cuenta de usuario o grupo para la que define el acceso.</span><span class="sxs-lookup"><span data-stu-id="b1338-149">Click this option to specify the user or group account for which you are defining access.</span></span> <span data-ttu-id="b1338-150">Si va a utilizar la seguridad predeterminada, las cuentas de usuario y grupo son las cuentas de dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="b1338-150">If you are using default security, the user and group accounts are Windows domain accounts.</span></span> <span data-ttu-id="b1338-151">Especifique las cuentas con este formato: \* \<domain> \\<cuenta \> \*.</span><span class="sxs-lookup"><span data-stu-id="b1338-151">Specify the accounts in this format: *\<domain>\\<account\>*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1338-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1338-152">See Also</span></span>  
 [<span data-ttu-id="b1338-153">Servidor de informes en Management Studio ayuda F1</span><span class="sxs-lookup"><span data-stu-id="b1338-153">Report Server in Management Studio F1 Help</span></span>](tools/report-server-in-management-studio-f1-help.md)  
  
  
