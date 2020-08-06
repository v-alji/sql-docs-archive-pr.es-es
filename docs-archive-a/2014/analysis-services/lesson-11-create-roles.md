---
title: 'Lección 12: crear roles | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 984face4-00fc-46d3-8ae1-9755bf737bdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 962cd19726a5404de81e20a2209b25b9cc277e21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662303"
---
# <a name="lesson-12-create-roles"></a><span data-ttu-id="36650-102">Lección 12: Crear roles</span><span class="sxs-lookup"><span data-stu-id="36650-102">Lesson 12: Create Roles</span></span>
  <span data-ttu-id="36650-103">En esta lección, creará roles.</span><span class="sxs-lookup"><span data-stu-id="36650-103">In this lesson, you will create roles.</span></span> <span data-ttu-id="36650-104">Los roles proporcionan seguridad a los objetos y datos de la base de datos del modelo limitando el acceso únicamente a los usuarios de Windows que sean miembros del rol.</span><span class="sxs-lookup"><span data-stu-id="36650-104">Roles provide model database object and data security by limiting access to only those Windows users which are role members.</span></span> <span data-ttu-id="36650-105">Cada rol se define con un permiso único: Ninguno, Lectura, Lectura y procesamiento, Procesamiento o Administrador.</span><span class="sxs-lookup"><span data-stu-id="36650-105">Each role is defined with a single permission: None, Read, Read and Process, Process, or Administrator.</span></span> <span data-ttu-id="36650-106">Los roles se pueden definir durante la creación del modelo mediante el cuadro de diálogo Administrador de roles de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36650-106">Roles can be defined during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="36650-107">Una vez implementado un modelo, los roles se pueden administrar con [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36650-107">After a model has been deployed, you can manage roles by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="36650-108">Para obtener más información, consulte [Roles &#40;SSAS tabular&#41;](tabular-models/roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="36650-108">To learn more, see [Roles &#40;SSAS Tabular&#41;](tabular-models/roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36650-109">No es necesario crear roles para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="36650-109">Creating roles is not necessary to complete this tutorial.</span></span> <span data-ttu-id="36650-110">De forma predeterminada, la cuenta en la que ha iniciado sesión actualmente tendrá privilegios de administrador en el modelo.</span><span class="sxs-lookup"><span data-stu-id="36650-110">By default, the account you are currently logged in with will have Administrator privileges on the model.</span></span> <span data-ttu-id="36650-111">Sin embargo, para permitir que otros usuarios de su organización examinen el modelo utilizando una aplicación cliente de informes, debe crear al menos un rol con permisos de lectura y agregar esos usuarios como miembros.</span><span class="sxs-lookup"><span data-stu-id="36650-111">However, to allow other users in your organization to browse the model by using a reporting client application, you must create at least one role with Read permissions and add those users as members.</span></span>  
  
 <span data-ttu-id="36650-112">Creará tres roles:</span><span class="sxs-lookup"><span data-stu-id="36650-112">You will create three roles:</span></span>  
  
-   <span data-ttu-id="36650-113">Jefe de ventas: este rol puede incluir a los usuarios de la organización para los que desea tener permiso de lectura para todos los objetos y datos del modelo.</span><span class="sxs-lookup"><span data-stu-id="36650-113">Sales Manager - This role can include users in your organization for which you want to have Read permission to all model objects and data.</span></span>  
  
-   <span data-ttu-id="36650-114">Analista de ventas EE. UU.: este rol puede incluir a los usuarios de su organización para los que desea que solo puedan examinar los datos relacionados con las ventas en EE. UU. (Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="36650-114">Sales Analyst US - This role can include users in your organization for which you want only to be able to browse data related to sales in the US (United States).</span></span> <span data-ttu-id="36650-115">Para este rol, usará una fórmula DAX para definir un *Filtro de fila*, que restringe los miembros para que solo examinen los datos correspondientes a Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="36650-115">For this role, you will use a DAX formula to define a *Row Filter*, which restricts members to browse data only for the United States.</span></span>  
  
-   <span data-ttu-id="36650-116">Administrador: este rol puede incluir a los usuarios para los que desea tener permiso de administrador, lo que permite el acceso ilimitado y permisos para realizar tareas administrativas en la base de datos modelo.</span><span class="sxs-lookup"><span data-stu-id="36650-116">Administrator - This role can include users for which you want to have Administrator permission, which allows unlimited access and permissions to perform administrative tasks on the model database.</span></span>  
  
 <span data-ttu-id="36650-117">Dado que las cuentas de usuario y grupo de Windows de su organización son únicas, puede agregar cuentas de su propia organización a los miembros.</span><span class="sxs-lookup"><span data-stu-id="36650-117">Because Windows user and group accounts in your organization are unique, you can add accounts from your particular organization to members.</span></span> <span data-ttu-id="36650-118">Sin embargo, para este tutorial, también puede dejar los miembros en blanco.</span><span class="sxs-lookup"><span data-stu-id="36650-118">However, for this tutorial, you can also leave the members blank.</span></span> <span data-ttu-id="36650-119">Todavía podrá probar el efecto de cada rol más adelante en la lección 12: Analizar en Excel.</span><span class="sxs-lookup"><span data-stu-id="36650-119">You will still be able to test the effect of each role later in Lesson 12: Analyze in Excel.</span></span>  
  
 <span data-ttu-id="36650-120">Tiempo estimado para completar esta lección: **15 minutos**</span><span class="sxs-lookup"><span data-stu-id="36650-120">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="36650-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="36650-121">Prerequisites</span></span>  
 <span data-ttu-id="36650-122">Este tema forma parte de un tutorial de modelado tabular, que se debe completar en orden.</span><span class="sxs-lookup"><span data-stu-id="36650-122">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="36650-123">Antes de realizar las tareas de esta lección, debe haber completado la lección anterior: [Lección 11: Crear particiones](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="36650-123">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
## <a name="create-roles"></a><span data-ttu-id="36650-124">Crear roles</span><span class="sxs-lookup"><span data-stu-id="36650-124">Create Roles</span></span>  
  
#### <a name="to-create-a-sales-manager-user-role"></a><span data-ttu-id="36650-125">Para crear el rol de usuario Director de ventas</span><span class="sxs-lookup"><span data-stu-id="36650-125">To create a Sales Manager user role</span></span>  
  
1.  <span data-ttu-id="36650-126">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** y, luego, en **Roles**.</span><span class="sxs-lookup"><span data-stu-id="36650-126">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="36650-127">En el cuadro de diálogo **Administrador de roles** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="36650-127">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="36650-128">Se agrega a la lista un nuevo rol con el permiso Ninguno.</span><span class="sxs-lookup"><span data-stu-id="36650-128">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="36650-129">Haga clic en el nuevo rol y, a continuación, en la columna **nombre** , cambie el nombre del rol a `Internet Sales Manager` .</span><span class="sxs-lookup"><span data-stu-id="36650-129">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Manager`.</span></span>  
  
4.  <span data-ttu-id="36650-130">En la columna **Permisos**, haga clic en la lista desplegable y, luego, seleccione el permiso **Lectura**.</span><span class="sxs-lookup"><span data-stu-id="36650-130">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="36650-131">Opcional: Haga clic en la pestaña **Miembros** y, luego, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="36650-131">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="36650-132">En el cuadro de diálogo **Seleccionar usuarios o grupos**, escriba los usuarios o grupos de Windows de la organización que quiere incluir en el rol.</span><span class="sxs-lookup"><span data-stu-id="36650-132">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
7.  <span data-ttu-id="36650-133">Compruebe las selecciones y, a continuación, haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="36650-133">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-a-sales-analyst-us-user-role"></a><span data-ttu-id="36650-134">Para crear un rol de usuario Analista de ventas EE. UU.</span><span class="sxs-lookup"><span data-stu-id="36650-134">To create a Sales Analyst US user role</span></span>  
  
1.  <span data-ttu-id="36650-135">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** y, luego, en **Roles**.</span><span class="sxs-lookup"><span data-stu-id="36650-135">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="36650-136">En el cuadro de diálogo **Administrador de roles** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="36650-136">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="36650-137">Se agrega a la lista un nuevo rol con el permiso Ninguno.</span><span class="sxs-lookup"><span data-stu-id="36650-137">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="36650-138">Haga clic en el nuevo rol y, a continuación, en la columna **nombre** , cambie el nombre del rol a `Internet Sales US` .</span><span class="sxs-lookup"><span data-stu-id="36650-138">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales US`.</span></span>  
  
4.  <span data-ttu-id="36650-139">En la columna **Permisos**, haga clic en la lista desplegable y, luego, seleccione el permiso **Lectura**.</span><span class="sxs-lookup"><span data-stu-id="36650-139">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="36650-140">Haga clic en la pestaña Filtros de fila y, después, solo para la tabla **Geografía** , en la columna de Filtro DAX, escriba la siguiente fórmula:</span><span class="sxs-lookup"><span data-stu-id="36650-140">Click on the Row Filters tab, and then for the **Geography** table only, in the DAX Filter column, type the following formula:</span></span>  
  
     `=Geography[Country Region Code] = "US"`  
  
     <span data-ttu-id="36650-141">Una fórmula de filtro de fila debe resolverse en un valor booleano (TRUE/FALSE).</span><span class="sxs-lookup"><span data-stu-id="36650-141">A Row Filter formula must resolve to a Boolean (TRUE/FALSE) value.</span></span> <span data-ttu-id="36650-142">Con esta fórmula, está especificando que solo las filas con el valor de código de región del país "EE. UU." estarán visibles para el usuario.</span><span class="sxs-lookup"><span data-stu-id="36650-142">With this formula, you are specifying that only rows with the Country Region Code value of "US" be visible to the user.</span></span>  
  
     <span data-ttu-id="36650-143">Cuando termine de crear la fórmula, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="36650-143">When you have finished building the formula, press ENTER.</span></span>  
  
6.  <span data-ttu-id="36650-144">Opcional: Haga clic en la pestaña **Miembros** y, luego, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="36650-144">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="36650-145">En el cuadro de diálogo **Seleccionar usuarios o grupos**, escriba los usuarios o grupos de Windows de la organización que quiere incluir en el rol.</span><span class="sxs-lookup"><span data-stu-id="36650-145">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
8.  <span data-ttu-id="36650-146">Compruebe las selecciones y, a continuación, haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="36650-146">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-an-administrator-role"></a><span data-ttu-id="36650-147">Para crear un rol Administrador</span><span class="sxs-lookup"><span data-stu-id="36650-147">To create an Administrator role</span></span>  
  
1.  <span data-ttu-id="36650-148">En el cuadro de diálogo **Administrador de roles** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="36650-148">In the **Role Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="36650-149">Haga clic en el nuevo rol y, a continuación, en la columna **nombre** , cambie el nombre del rol a `Internet Sales Administrator` .</span><span class="sxs-lookup"><span data-stu-id="36650-149">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Administrator`.</span></span>  
  
3.  <span data-ttu-id="36650-150">En la columna **Permisos** , haga clic en la lista desplegable y luego seleccione el permiso **Administrador** .</span><span class="sxs-lookup"><span data-stu-id="36650-150">In the **Permissions** column, click the dropdown list, and then select the **Administrator** permission.</span></span>  
  
4.  <span data-ttu-id="36650-151">Haga clic en la pestaña **Miembros** y luego en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="36650-151">Click on the **Members** tab, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="36650-152">Opcional: En el cuadro de diálogo **Seleccionar usuario o grupo** , especifique los usuarios o grupos de Windows de su organización que quiera incluir en el rol.</span><span class="sxs-lookup"><span data-stu-id="36650-152">Optional: In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
6.  <span data-ttu-id="36650-153">Compruebe las selecciones y, a continuación, haga clic en **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="36650-153">Verify your selections, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="36650-154">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="36650-154">Next Steps</span></span>  
 <span data-ttu-id="36650-155">Para continuar este tutorial, vaya a la lección siguiente: [Lección 13: Analizar en Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="36650-155">To continue this tutorial, go to the next lesson: Lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
  
