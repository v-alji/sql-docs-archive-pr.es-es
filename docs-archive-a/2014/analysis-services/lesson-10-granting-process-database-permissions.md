---
title: Conceder permisos procesar base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 69ba952e-09ae-49a9-9297-00e32e8e89a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6ada30e3fb509bd1ffd210485ce0e34b7bf86fb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662308"
---
# <a name="granting-process-database-permissions"></a><span data-ttu-id="c231d-102">Conceder permisos Procesar base de datos</span><span class="sxs-lookup"><span data-stu-id="c231d-102">Granting Process Database Permissions</span></span>
  <span data-ttu-id="c231d-103">Después de instalar una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], todos los miembros del rol de administrador de servidor [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] de dicha instancia tienen permisos en el servidor para llevar a cabo cualquier tarea dentro de la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c231d-103">After you install an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], all members of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server administrator role in that instance have server-wide permissions to perform any task within the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c231d-104">De manera predeterminada, ningún otro usuario tiene permiso para administrar o ver objetos en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c231d-104">By default, no other users have any permission to administer or view any objects in the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>

 <span data-ttu-id="c231d-105">Un miembro del rol de administrador de servidor puede conceder a los usuarios acceso administrativo en un servidor si los convierte en miembros del rol.</span><span class="sxs-lookup"><span data-stu-id="c231d-105">A member of the server administrator role can grant users administrative access on a server-wide basis by making them members of the role.</span></span> <span data-ttu-id="c231d-106">Un miembro del rol de administrador de servidor puede conceder también a los usuarios acceso de forma más limitada concediéndoles permisos administrativos o de acceso limitados o completos en el nivel de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c231d-106">A member of the server administrator role can also grant users access on a more limited basis by granting them limited or complete administrative or access permissions at the database level.</span></span> <span data-ttu-id="c231d-107">Los permisos administrativos limitados incluyen permisos Procesar o Leer definición en el nivel de base de datos, cubo o dimensión.</span><span class="sxs-lookup"><span data-stu-id="c231d-107">Limited administrative permissions include process or read definition permissions at the database, cube, or dimension level.</span></span>

 <span data-ttu-id="c231d-108">En las tareas de este tema definirá un rol de seguridad Procesar objetos de base de datos que conceda a los miembros del rol permiso para procesar todos los objetos de la base de datos, pero ningún permiso para ver datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c231d-108">In the tasks in this topic, you will define a Process Database Objects security role that grants members of the role permission to process all database objects, but no permission to view data within the database.</span></span>

## <a name="defining-a-process-database-objects-security-role"></a><span data-ttu-id="c231d-109">Definir un rol de seguridad Procesar objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="c231d-109">Defining a Process Database Objects Security Role</span></span>

1.  <span data-ttu-id="c231d-110">En el Explorador de soluciones, haga clic con el botón derecho en **Roles** y, después, haga clic en **Nuevo rol** para abrir el Diseñador de roles.</span><span class="sxs-lookup"><span data-stu-id="c231d-110">In Solution Explorer, right-click **Roles** and then click **New Role** to open the Role Designer.</span></span>

2.  <span data-ttu-id="c231d-111">Haga clic en la casilla **Procesar base de datos** .</span><span class="sxs-lookup"><span data-stu-id="c231d-111">Click the **Process database** check box.</span></span>

3.  <span data-ttu-id="c231d-112">En el ventana Propiedades, cambie la propiedad **nombre** de este nuevo rol a `Process Database Objects Role` .</span><span class="sxs-lookup"><span data-stu-id="c231d-112">In the Properties window, change the **Name** property for this new role to `Process Database Objects Role`.</span></span>

     <span data-ttu-id="c231d-113">![Diseñador de roles](../../2014/tutorials/media/l10-security-1.png "Diseñador de roles")</span><span class="sxs-lookup"><span data-stu-id="c231d-113">![Role Designer](../../2014/tutorials/media/l10-security-1.png "Role Designer")</span></span>

4.  <span data-ttu-id="c231d-114">Vaya a la pestaña **Pertenencia** del Diseñador de roles y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c231d-114">Switch to the **Membership** tab of Role Designer and click **Add**.</span></span>

5.  <span data-ttu-id="c231d-115">Especifique las cuentas de los usuarios o grupos de dominios de Windows que sean miembros de este rol.</span><span class="sxs-lookup"><span data-stu-id="c231d-115">Enter the accounts of the Windows domain users or groups who will be members of this role.</span></span> <span data-ttu-id="c231d-116">Haga clic en **Comprobar nombres** para comprobar la información de la cuenta y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c231d-116">Click **Check Names** to verify the account information, and then click **OK**.</span></span>

6.  <span data-ttu-id="c231d-117">Vaya a la pestaña **Cubos** del Diseñador de roles.</span><span class="sxs-lookup"><span data-stu-id="c231d-117">Switch to the **Cubes** tab of Role Designer.</span></span>

     <span data-ttu-id="c231d-118">Observe que los miembros de este rol tienen permisos para procesar esta base de datos, pero no tienen permiso para obtener acceso a los datos del cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial y no tienen acceso a obtención de detalles o cubo local, como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="c231d-118">Notice that members of this role have permissions to process this database, but have no permission to access the data in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube and have no local cube/drillthrough access, as shown in the following image.</span></span>

     <span data-ttu-id="c231d-119">![Pestaña Cubos del Diseñador de roles](../../2014/tutorials/media/l10-security-2.png "Pestaña Cubos del Diseñador de roles")</span><span class="sxs-lookup"><span data-stu-id="c231d-119">![Cubes tab of Role Designer](../../2014/tutorials/media/l10-security-2.png "Cubes tab of Role Designer")</span></span>

7.  <span data-ttu-id="c231d-120">Vaya a la pestaña **Dimensiones** del Diseñador de roles.</span><span class="sxs-lookup"><span data-stu-id="c231d-120">Switch to the **Dimensions** tab of Role Designer.</span></span>

     <span data-ttu-id="c231d-121">Observe que los miembros de este rol tienen permisos para procesar todos los objetos de dimensión de esta base de datos y que, de manera predeterminada, tienen permisos de lectura para tener acceso a cada objeto de dimensión de la base de datos del Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c231d-121">Notice that members of this role have permissions to process all dimension objects in this database, and, by default, have read permissions to access each dimension object in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial database.</span></span>

8.  <span data-ttu-id="c231d-122">En el menú **Compilar** , haga clic en **Tutorial de Implementar Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="c231d-122">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

     <span data-ttu-id="c231d-123">Acaba de definir e implementar correctamente el rol de seguridad Procesar objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c231d-123">You have now successfully defined and deployed the Process Database Objects security role.</span></span> <span data-ttu-id="c231d-124">Después de que el cubo se implemente en el entorno de producción, los administradores del cubo implementado podrán agregar usuarios a este rol según vayan necesitando delegar responsabilidades de procesamiento en usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="c231d-124">After a cube is deployed to the production environment, the administrators of the deployed cube can add users to this role as required to delegate processing responsibilities to specific users.</span></span>

> [!NOTE]
>  <span data-ttu-id="c231d-125">Para disponer de un proyecto completado de la Lección 10, descargue e instale los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c231d-125">A completed project for Lesson 10 is available by downloading and installing the samples.</span></span> <span data-ttu-id="c231d-126">Para obtener más información, vea [instalar datos y proyectos de ejemplo para el tutorial de modelado multidimensional de Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="c231d-126">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c231d-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c231d-127">See Also</span></span>
 [<span data-ttu-id="c231d-128">Roles y permisos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c231d-128">Roles and Permissions &#40;Analysis Services&#41;</span></span>](multidimensional-models/roles-and-permissions-analysis-services.md)


