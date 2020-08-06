---
title: Crear y administrar roles (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.rolemanager.f1
- sql12.asvs.bidtoolset.roledb.f1
ms.assetid: e23d27a8-e968-4082-9dbe-963fc724b5d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 335e0e311d97ea452449cd0c5d6550f6dbcca4f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663761"
---
# <a name="create-and-manage-roles-ssas-tabular"></a><span data-ttu-id="ada4e-102">Crear y administrar roles (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="ada4e-102">Create and Manage Roles (SSAS Tabular)</span></span>
  <span data-ttu-id="ada4e-103">Los roles, en los modelos tabulares, definen los permisos de los miembros para un modelo.</span><span class="sxs-lookup"><span data-stu-id="ada4e-103">Roles, in tabular models, define member permissions for a model.</span></span> <span data-ttu-id="ada4e-104">Los roles se definen para un proyecto de modelos mediante el cuadro de diálogo Administrador de roles de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ada4e-104">Roles are defined for a model project by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ada4e-105">Al implementar un modelo, los administradores de bases de datos pueden administrar los roles mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ada4e-105">When a model is deployed, database administrators can manage roles by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ada4e-106">Las tareas de este tema explican cómo crear y administrar roles durante la creación de modelos mediante el cuadro de diálogo Administrador de roles en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ada4e-106">The tasks in this topic describe how to create and manage roles during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ada4e-107">Para obtener información sobre cómo administrar roles en una base de datos modelo implementada, vea [Roles de modelos tabulares &#40;SSAS tabular&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="ada4e-107">For information about managing roles in a deployed model database, see [Tabular Model Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="ada4e-108">Tareas</span><span class="sxs-lookup"><span data-stu-id="ada4e-108">Tasks</span></span>  
 <span data-ttu-id="ada4e-109">Para crear, modificar, copiar y eliminar roles, utilice el cuadro de diálogo **Administrador de roles** .</span><span class="sxs-lookup"><span data-stu-id="ada4e-109">To create, edit, copy, and delete roles, you will use the **Role Manager** dialog box.</span></span> <span data-ttu-id="ada4e-110">Para ver el cuadro de diálogo **Administrador de roles** , en [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** y en **Administrador de roles**.</span><span class="sxs-lookup"><span data-stu-id="ada4e-110">To view the **Role Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a> <span data-ttu-id="ada4e-111">Para crear un rol</span><span class="sxs-lookup"><span data-stu-id="ada4e-111">To create a new role</span></span>  
  
1.  <span data-ttu-id="ada4e-112">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** y en **Administrador de roles**.</span><span class="sxs-lookup"><span data-stu-id="ada4e-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
2.  <span data-ttu-id="ada4e-113">En el cuadro de diálogo **Administrador de roles** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ada4e-113">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="ada4e-114">Se agregará un nuevo rol resaltado a la lista de roles.</span><span class="sxs-lookup"><span data-stu-id="ada4e-114">A new highlighted role is added to the Roles list.</span></span>  
  
3.  <span data-ttu-id="ada4e-115">En la lista **Roles** , en el campo **Nombre** , escriba un nombre para el rol.</span><span class="sxs-lookup"><span data-stu-id="ada4e-115">In the **Roles** list, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="ada4e-116">De forma predeterminada, el nombre del rol predeterminado se incrementará numéricamente para cada nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="ada4e-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="ada4e-117">Se recomienda escribir un nombre que identifique claramente el tipo de miembro, por ejemplo, Administradores financieros o Especialistas en recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="ada4e-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="ada4e-118">En el campo **Permisos** , haga clic en la flecha abajo y seleccione uno de los tipos de permisos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ada4e-118">In the **Permissions** field, click the down arrow and then select one of the following permission types:</span></span>  
  
    |<span data-ttu-id="ada4e-119">Permiso</span><span class="sxs-lookup"><span data-stu-id="ada4e-119">Permission</span></span>|<span data-ttu-id="ada4e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="ada4e-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="ada4e-121">**None**</span><span class="sxs-lookup"><span data-stu-id="ada4e-121">**None**</span></span>|<span data-ttu-id="ada4e-122">Los miembros no pueden realizar ninguna modificación en el esquema del modelo y no pueden consultar los datos.</span><span class="sxs-lookup"><span data-stu-id="ada4e-122">Members cannot make any modifications to the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="ada4e-123">**Lectura**</span><span class="sxs-lookup"><span data-stu-id="ada4e-123">**Read**</span></span>|<span data-ttu-id="ada4e-124">Los miembros pueden consultar los datos (según los filtros de fila), pero no pueden realizar cambios en el esquema del modelo.</span><span class="sxs-lookup"><span data-stu-id="ada4e-124">Members are allowed to query data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="ada4e-125">**Lectura y proceso**</span><span class="sxs-lookup"><span data-stu-id="ada4e-125">**Read and Process**</span></span>|<span data-ttu-id="ada4e-126">Los miembros pueden actualizar los datos (según los filtros de fila) y ejecutar las operaciones Procesar y Procesar todo, pero no pueden realizar cambios en el esquema del modelo.</span><span class="sxs-lookup"><span data-stu-id="ada4e-126">Members are allowed to query data (based on row-level filters) and run Process and Process All operations, but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="ada4e-127">**Proceso**</span><span class="sxs-lookup"><span data-stu-id="ada4e-127">**Process**</span></span>|<span data-ttu-id="ada4e-128">Los modelos pueden ejecutar las operaciones Procesar y Procesar todo.</span><span class="sxs-lookup"><span data-stu-id="ada4e-128">Members can run Process and Process All operations.</span></span> <span data-ttu-id="ada4e-129">No pueden modificar el esquema de modelo ni pueden consultar datos.</span><span class="sxs-lookup"><span data-stu-id="ada4e-129">Cannot modify the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="ada4e-130">**Administrador**</span><span class="sxs-lookup"><span data-stu-id="ada4e-130">**Administrator**</span></span>|<span data-ttu-id="ada4e-131">Los miembros pueden realizar modificaciones en el esquema del modelo y pueden consultar todos los datos.</span><span class="sxs-lookup"><span data-stu-id="ada4e-131">Members can make modifications to the model schema and can query all data.</span></span>|  
  
5.  <span data-ttu-id="ada4e-132">Para especificar una descripción para el rol, haga clic en el campo **Descripción** y escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="ada4e-132">To enter a description for the role, click the **Description** field, and then type a description.</span></span>  
  
6.  <span data-ttu-id="ada4e-133">Si el rol que está creando tiene permiso de lectura o de lectura y procesamiento, puede agregar filtros de fila mediante una fórmula de DAX.</span><span class="sxs-lookup"><span data-stu-id="ada4e-133">If the role you are creating has Read or Read and Process permission, you can add row filters using a DAX formula.</span></span> <span data-ttu-id="ada4e-134">Para agregar filtros de fila, haga clic en la pestaña **Filtros de fila** , seleccione una tabla, haga clic en el campo **Filtro DAX** y, a continuación, escriba una fórmula de DAX.</span><span class="sxs-lookup"><span data-stu-id="ada4e-134">To add row filters, click the **Row Filters** tab, then select a table, then click the **DAX Filter** field, and then type a DAX formula.</span></span>  
  
7.  <span data-ttu-id="ada4e-135">Para agregar miembros al rol, haga clic en la pestaña **Miembros** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ada4e-135">To add members to the role, click the **Members** tab, and then click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ada4e-136">También se pueden agregar miembros de rol a un modelo implementado mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ada4e-136">Role members can also be added to a deployed model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ada4e-137">Para más información, vea [Administrar roles usando SSMS &#40;SSAS tabular&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="ada4e-137">For more information, see [Manage Roles by using SSMS &#40;SSAS Tabular&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span></span>  
  
8.  <span data-ttu-id="ada4e-138">En el cuadro de diálogo **Seleccionar usuarios o grupos** , especifique el usuario de Windows o los objetos de grupo de Windows como miembros.</span><span class="sxs-lookup"><span data-stu-id="ada4e-138">In the **Select Users or Groups** dialog box, enter Windows user or Windows group objects as members.</span></span>  
  
9. <span data-ttu-id="ada4e-139">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ada4e-139">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ada4e-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ada4e-140">See Also</span></span>  
 <span data-ttu-id="ada4e-141">[Roles &#40;SSAS tabular&#41;](roles-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ada4e-141">[Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md) </span></span>  
 <span data-ttu-id="ada4e-142">[Perspectivas &#40;SSAS tabular&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ada4e-142">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 <span data-ttu-id="ada4e-143">[Analizar en Excel &#40;SSAS tabular&#41;](analyze-in-excel-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ada4e-143">[Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md) </span></span>  
 <span data-ttu-id="ada4e-144">[Función USERNAME &#40;&#41;DAX](/dax/username-function-dax) </span><span class="sxs-lookup"><span data-stu-id="ada4e-144">[USERNAME Function &#40;DAX&#41;](/dax/username-function-dax) </span></span>  
 [<span data-ttu-id="ada4e-145">Función CUSTOMDATA &#40;DAX&#41;</span><span class="sxs-lookup"><span data-stu-id="ada4e-145">CUSTOMDATA Function &#40;DAX&#41;</span></span>](/dax/customdata-function-dax)  
  
  
