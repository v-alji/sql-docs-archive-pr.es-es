---
title: Administrar roles mediante SSMS (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 652faac0-1cfc-438b-8119-2f4b090a2381
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4ee34d5e75d5d4ce3679d46d29af3215852d2bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744360"
---
# <a name="manage-roles-by-using-ssms-ssas-tabular"></a><span data-ttu-id="87b95-102">Administrar roles utilizando SSMS (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="87b95-102">Manage Roles by using SSMS (SSAS Tabular)</span></span>
  <span data-ttu-id="87b95-103">Puede crear, modificar, y administrar roles para un modelo tabular implementado mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87b95-103">You can create, edit, and manage roles for a deployed tabular model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="87b95-104">Tareas en este tema:</span><span class="sxs-lookup"><span data-stu-id="87b95-104">Tasks in this topic:</span></span>  
  
-   [<span data-ttu-id="87b95-105">Para crear un nuevo rol</span><span class="sxs-lookup"><span data-stu-id="87b95-105">To create a new role</span></span>](#bkmk_new_role)  
  
-   [<span data-ttu-id="87b95-106">Para copiar un rol</span><span class="sxs-lookup"><span data-stu-id="87b95-106">To copy a role</span></span>](#bkmk_copy_role)  
  
-   [<span data-ttu-id="87b95-107">Para editar un rol</span><span class="sxs-lookup"><span data-stu-id="87b95-107">To edit a role</span></span>](#bkmk_edit_role)  
  
-   [<span data-ttu-id="87b95-108">Para eliminar un rol</span><span class="sxs-lookup"><span data-stu-id="87b95-108">To delete a role</span></span>](#bkmk_deletet_role)  
  
> [!CAUTION]  
>  <span data-ttu-id="87b95-109">El nuevo despliegue de un proyecto de modelos tabular con roles definidos mediante el Administrador de roles de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] sobrescribirá los roles definidos en un modelo tabular implementado.</span><span class="sxs-lookup"><span data-stu-id="87b95-109">Re-deploying a tabular model project with roles defined by using Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] will overwrite roles defined in a deployed tabular model.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="87b95-110">Si se utiliza [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para administrar una base de datos del área de trabajo del modelo tabular mientras está abierto el proyecto de modelos en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , se puede dañar el archivo Model.bim.</span><span class="sxs-lookup"><span data-stu-id="87b95-110">Using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage a tabular model workspace database while the model project is open in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] may cause the Model.bim file to become corrupted.</span></span> <span data-ttu-id="87b95-111">Al crear y administrar roles para una base de datos del área de trabajo del modelo tabular, utilice el Administrador de roles de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87b95-111">When creating and managing roles for a tabular model workspace database, use Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a> <span data-ttu-id="87b95-112">Para crear un rol</span><span class="sxs-lookup"><span data-stu-id="87b95-112">To create a new role</span></span>  
  
1.  <span data-ttu-id="87b95-113">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda la base de datos de modelos tabulares en la que desee crear un rol, haga clic con el botón secundario en **Roles**y después en **Nuevo rol**.</span><span class="sxs-lookup"><span data-stu-id="87b95-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database for which you want to create a new role, then right click on **Roles**, and then click **New Role**.</span></span>  
  
2.  <span data-ttu-id="87b95-114">En el cuadro de diálogo **Crear rol** , en la ventana Seleccionar una página, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="87b95-114">In the **Create Role** dialog box, in the Select a page window, click **General**.</span></span>  
  
3.  <span data-ttu-id="87b95-115">En la ventana de las opciones generales, escriba un nombre para el rol en el campo **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="87b95-115">In the general settings window, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="87b95-116">De forma predeterminada, el nombre del rol predeterminado se incrementará numéricamente para cada nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="87b95-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="87b95-117">Se recomienda escribir un nombre que identifique claramente el tipo de miembro, por ejemplo, Administradores financieros o Especialistas en recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="87b95-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="87b95-118">En **Establezca los permisos de base de datos para este rol**, seleccione una de las siguientes opciones de permiso:</span><span class="sxs-lookup"><span data-stu-id="87b95-118">In **Set the database permissions for this role**, select one of the following permissions options:</span></span>  
  
    |<span data-ttu-id="87b95-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="87b95-119">Permission</span></span>|<span data-ttu-id="87b95-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="87b95-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="87b95-121">**Control total (administrador)**</span><span class="sxs-lookup"><span data-stu-id="87b95-121">**Full control (Administrator)**</span></span>|<span data-ttu-id="87b95-122">Los miembros pueden realizar modificaciones en el esquema del modelo y pueden ver todos los datos.</span><span class="sxs-lookup"><span data-stu-id="87b95-122">Members can make modifications to the model schema and can view all data.</span></span>|  
    |<span data-ttu-id="87b95-123">**Proceso de una base de datos**</span><span class="sxs-lookup"><span data-stu-id="87b95-123">**Process database**</span></span>|<span data-ttu-id="87b95-124">Los modelos pueden ejecutar las operaciones Procesar y Procesar todo.</span><span class="sxs-lookup"><span data-stu-id="87b95-124">Members can run Process and Process All operations.</span></span> <span data-ttu-id="87b95-125">No pueden modificar el esquema del modelo y no pueden ver los datos.</span><span class="sxs-lookup"><span data-stu-id="87b95-125">Cannot modify the model schema and cannot view data.</span></span>|  
    |<span data-ttu-id="87b95-126">**Lectura**</span><span class="sxs-lookup"><span data-stu-id="87b95-126">**Read**</span></span>|<span data-ttu-id="87b95-127">Los miembros pueden ver los datos (según los filtros de fila), pero no pueden realizar cambios en el esquema del modelo.</span><span class="sxs-lookup"><span data-stu-id="87b95-127">Members are allowed to view data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
  
5.  <span data-ttu-id="87b95-128">En el cuadro de diálogo **Crear rol** , en la ventana Seleccionar una página, haga clic en **Pertenencia**.</span><span class="sxs-lookup"><span data-stu-id="87b95-128">In the **Create Role** dialog box, in the Select a page window, click **Membership**.</span></span>  
  
6.  <span data-ttu-id="87b95-129">En la ventana de configuración de la pertenencia, haga clic en **Agregar**y en el cuadro de diálogo **Seleccionar usuarios o grupos** , agregue los usuarios o grupos de Windows que desee añadir como miembros.</span><span class="sxs-lookup"><span data-stu-id="87b95-129">In the membership settings window, click **Add**, and then in the **Select Users or Groups** dialog box, add the Windows users or groups you want to add as members.</span></span>  
  
7.  <span data-ttu-id="87b95-130">Si el rol que va a crear tiene permisos de lectura, puede agregar filtros de fila para las tablas utilizando una fórmula DAX.</span><span class="sxs-lookup"><span data-stu-id="87b95-130">If the role you are creating has Read permissions, you can add row filters for any table using a DAX formula.</span></span> <span data-ttu-id="87b95-131">Para agregar filtros de fila, en el cuadro de diálogo \*\*propiedades de rol- \<rolename> \*\* , en **seleccionar una página**, haga clic en **filtros de fila**.</span><span class="sxs-lookup"><span data-stu-id="87b95-131">To add row filters, in the **Role Properties - \<rolename>** dialog box, in **Select a page**, click on **Row Filters**.</span></span>  
  
8.  <span data-ttu-id="87b95-132">En la ventana filtros de fila, seleccione una tabla, haga clic en el campo **filtro Dax** y, a continuación, en el campo \*\*filtro Dax- \<tablename> \*\* , escriba una fórmula Dax.</span><span class="sxs-lookup"><span data-stu-id="87b95-132">In the row filters window, select a table, then click on the **DAX Filter** field, and then in the **DAX Filter - \<tablename>** field, type a DAX formula.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="87b95-133">El campo filtro DAX-no \<tablename> contiene una característica del editor de consultas de autocompletar o de la función Insert.</span><span class="sxs-lookup"><span data-stu-id="87b95-133">The DAX Filter - \<tablename> field does not contain an AutoComplete query editor or insert function feature.</span></span> <span data-ttu-id="87b95-134">Para usar Autocompletar al escribir una fórmula DAX, debe utilizar un editor de fórmulas DAX de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87b95-134">To use AutoComplete when writing a DAX formula, you must use a DAX formula editor in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
9. <span data-ttu-id="87b95-135">Haga clic en **Aceptar** para guardar el rol.</span><span class="sxs-lookup"><span data-stu-id="87b95-135">Click **Ok** to save the role.</span></span>  
  
###  <a name="to-copy-a-role"></a><a name="bkmk_copy_role"></a> <span data-ttu-id="87b95-136">Para copiar un rol</span><span class="sxs-lookup"><span data-stu-id="87b95-136">To copy a role</span></span>  
  
1.  <span data-ttu-id="87b95-137">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda la base de datos de modelos tabulares que contiene el rol que desea copiar, expanda **Roles**, haga clic con el botón secundario en el rol y después haga clic en **Duplicar**.</span><span class="sxs-lookup"><span data-stu-id="87b95-137">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to copy, then expand **Roles**, then right click on the role, and then click **Duplicate**.</span></span>  
  
###  <a name="to-edit-a-role"></a><a name="bkmk_edit_role"></a> <span data-ttu-id="87b95-138">Para modificar un rol</span><span class="sxs-lookup"><span data-stu-id="87b95-138">To edit a role</span></span>  
  
-   <span data-ttu-id="87b95-139">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda la base de datos de modelos tabulares que contiene el rol que desea modificar, expanda **Roles**, haga clic con el botón secundario en el rol y después haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="87b95-139">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to edit, then expand **Roles**, then right click on the role, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="87b95-140">En el cuadro de diálogo **propiedades de rol** \<rolename> , puede cambiar los permisos, agregar o quitar miembros y agregar o modificar filtros de fila.</span><span class="sxs-lookup"><span data-stu-id="87b95-140">In the **Role Properties** \<rolename> dialog box, you can change permissions, add or remove members, and add/edit row filters.</span></span>  
  
###  <a name="to-delete-a-role"></a><a name="bkmk_deletet_role"></a> <span data-ttu-id="87b95-141">Para eliminar un rol</span><span class="sxs-lookup"><span data-stu-id="87b95-141">To delete a role</span></span>  
  
-   <span data-ttu-id="87b95-142">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expanda la base de datos de modelos tabulares que contiene el rol que desea quitar, expanda **Roles**, haga clic con el botón secundario en el rol y después haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="87b95-142">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to delete, then expand **Roles**, then right click on the role, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b95-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87b95-143">See Also</span></span>  
 [<span data-ttu-id="87b95-144">Roles &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="87b95-144">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
