---
title: Conceder permisos para estructuras y modelos de minería de datos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.roledesignerdialog.miningmodels.f1
helpviewer_keywords:
- data mining [Analysis Services], security
- permissions [Analysis Services], mining models
- mining models [Analysis Services], security
- mining structures [Analysis Services], security
- permissions [Analysis Services], mining structures
- user access rights [Analysis Services], mining structures
- user access rights [Analysis Services], mining models
ms.assetid: a0008004-e2b7-47db-acad-5fe7e12b130f
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0db849551bdb38615f280b123c98f0e9d3053d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747212"
---
# <a name="grant-permissions-on-data-mining-structures-and-models-analysis-services"></a><span data-ttu-id="e88dc-102">Otorgar permisos para estructuras y modelos de minería de datos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="e88dc-102">Grant permissions on data mining structures and models (Analysis Services)</span></span>
  <span data-ttu-id="e88dc-103">De forma predeterminada, solamente el administrador de servidor dispone de permisos para ver las estructuras de minería de datos o modelos de minería de datos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e88dc-103">By default, only an Analysis Services server administrator has permissions to view data mining structures or mining models in the database.</span></span> <span data-ttu-id="e88dc-104">Siga las instrucciones de más abajo para conceder permisos a usuarios que no sean administradores.</span><span class="sxs-lookup"><span data-stu-id="e88dc-104">Follow the instructions below to grant permissions to non-administrator users.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-structure"></a><span data-ttu-id="e88dc-105">Establecer permisos para obtener acceso a una estructura de minería datos</span><span class="sxs-lookup"><span data-stu-id="e88dc-105">Set permissions to access a mining structure</span></span>  
  
1.  <span data-ttu-id="e88dc-106">En SSMS, conéctese a Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e88dc-106">In SSMS, connect to Analysis Services.</span></span> <span data-ttu-id="e88dc-107">Vea [Conectarse desde aplicaciones cliente &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md) si necesita ayuda con los pasos.</span><span class="sxs-lookup"><span data-stu-id="e88dc-107">See [Connect from client applications &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md) if you need help with the steps.</span></span>  
  
2.  <span data-ttu-id="e88dc-108">Abra la carpeta **Bases de datos** y seleccione una base de datos en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="e88dc-108">Open the **Databases** folder, and select a database in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="e88dc-109">Haga clic con el botón derecho en **Roles** y elija **Nuevo rol**.</span><span class="sxs-lookup"><span data-stu-id="e88dc-109">Right-click **Roles** and choose **New Role**.</span></span>  
  
4.  <span data-ttu-id="e88dc-110">En la página General, escriba un nombre y, si lo desea, una descripción.</span><span class="sxs-lookup"><span data-stu-id="e88dc-110">In the General page, enter a name, and optionally, a description.</span></span> <span data-ttu-id="e88dc-111">La página también contiene diversos permisos de base de datos, como Control total, Procesar base de datos y Leer definición.</span><span class="sxs-lookup"><span data-stu-id="e88dc-111">The page also contains several database permissions, such as Full Control, Process Database, and Read Definition.</span></span> <span data-ttu-id="e88dc-112">No se necesita ninguno de estos permisos para tener acceso a la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="e88dc-112">None of these permissions are needed for data mining access.</span></span> <span data-ttu-id="e88dc-113">Vea [Otorgar permisos de base de datos &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md) para obtener más información sobre los permisos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e88dc-113">See [Grant database permissions &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md) for more information about database permissions.</span></span>  
  
5.  <span data-ttu-id="e88dc-114">En el panel **Estructura de minería de datos** , seleccione **Lectura** o **Lectura y escritura**  para cada estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="e88dc-114">In the **Mining Structure** pane, select **Read** or **Read/Write**  for each data mining structure.</span></span>  
  
6.  <span data-ttu-id="e88dc-115">En el panel **Pertenencia** , especifique las cuentas de usuario y grupo de Windows que se conectan a Analysis Services con este rol.</span><span class="sxs-lookup"><span data-stu-id="e88dc-115">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
7.  <span data-ttu-id="e88dc-116">Haga clic en **Aceptar** para completar la creación del rol.</span><span class="sxs-lookup"><span data-stu-id="e88dc-116">Click **OK** to finish creating the role.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-model"></a><span data-ttu-id="e88dc-117">Establecer permisos para obtener acceso a un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e88dc-117">Set permissions to access a mining model</span></span>  
 <span data-ttu-id="e88dc-118">Para los modelos de minería de datos, los roles pueden tener permisos de **Lectura** o **Lectura y escritura** , así como permisos de **Obtención de detalles** y **Leer definición** que permiten ver y explorar los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="e88dc-118">For a data mining model, a role can have either **Read** or **Read/Write** permissions, as well as **Drillthrough** and **Read Definition** permissions that allow viewing and browsing the underlying data.</span></span>  
  
 <span data-ttu-id="e88dc-119">**Nota** : Si habilita la obtención de detalles en la estructura de minería de datos y el modelo de minería, cualquier usuario que sea miembro de un rol que tenga los permisos de obtención de detalles en el modelo de minería y la estructura de minería de datos también podrá ver las columnas en la estructura de minería de datos, aun cuando esas columnas no estén incluidas en el modelo de minería.</span><span class="sxs-lookup"><span data-stu-id="e88dc-119">**Note** If you enable drillthrough on both the mining structure and the mining model, any user who is a member of a role that has drillthrough permissions on the mining model and the mining structure can also view columns in the mining structure, even if those columns are not included in the mining model.</span></span> <span data-ttu-id="e88dc-120">Por consiguiente, para proteger información confidencial, debería preparar la vista del origen de datos de forma que enmascare datos personales y solo permita el acceso para la obtención de detalles en la estructura de minería de datos cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e88dc-120">Therefore, to protect sensitive information, you should set up the data source view to mask personal information, and allow drillthrough access on the mining structure only when necessary.</span></span>  
  
 <span data-ttu-id="e88dc-121">Para conceder permisos de lectura y escritura a un rol de base de datos, un usuario debe ser miembro del rol de servidor de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o de un rol de base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] con permisos de Control total (Administrador).</span><span class="sxs-lookup"><span data-stu-id="e88dc-121">To grant read or read/write permissions to a database role, a user must be a member of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server role or a member of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database role that has Full Control (Administrator) permissions.</span></span>  
  
1.  <span data-ttu-id="e88dc-122">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , conéctese a la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , expanda **roles** para la base de datos adecuada en explorador de objetos y, a continuación, haga clic en un rol de base de datos (o cree un nuevo rol de base de datos).</span><span class="sxs-lookup"><span data-stu-id="e88dc-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], expand **Roles** for the appropriate database in Object Explorer, and then click a database role (or create a new database role).</span></span>  
  
2.  <span data-ttu-id="e88dc-123">En el panel **Estructura de minería de datos** , busque el modelo de minería de datos en la lista **Modelos de minería de datos** y, después, seleccione **Lectura**, **Lectura y escritura**, **Obtención de detalles**o **Examinar** para ese modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="e88dc-123">In the **Mining Structure** pane, locate the mining model in the **Mining Models** list, and then select **Read**, **Read/Write**, **Drill Through**, or **Browse** for that mining model.</span></span>  
  
3.  <span data-ttu-id="e88dc-124">En el panel **Pertenencia** , especifique las cuentas de usuario y grupo de Windows que se conectan a Analysis Services con este rol.</span><span class="sxs-lookup"><span data-stu-id="e88dc-124">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
4.  <span data-ttu-id="e88dc-125">Haga clic en **Aceptar** para completar la creación del rol.</span><span class="sxs-lookup"><span data-stu-id="e88dc-125">Click **OK** to finish creating the role.</span></span>  
  
 <span data-ttu-id="e88dc-126">Para usar un origen de datos en una consulta de obtención de detalles que usa la cláusula (DMX) OPENQUERY de Extensiones de minería de datos (DMX), el rol de base de datos también requiere permiso de lectura y escritura sobre el objeto de origen de datos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e88dc-126">To use a data source in a drillthrough query that uses the Data Mining Extensions (DMX) OPENQUERY clause, the database role also needs read/write permission on the appropriate data source object.</span></span> <span data-ttu-id="e88dc-127">Para obtener más información, vea [Otorgar permisos para un objeto de origen de datos &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) y [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span><span class="sxs-lookup"><span data-stu-id="e88dc-127">For more information, see [Grant permissions on a data source object &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) and [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e88dc-128">De forma predeterminada, el envío de consultas DMX al usar OPENROWSET está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="e88dc-128">By default, the submission of DMX queries by using OPENROWSET is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e88dc-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e88dc-129">See Also</span></span>  
 <span data-ttu-id="e88dc-130">[Conceder permisos de administrador de servidor &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="e88dc-130">[Grant Server Administrator Permissions &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="e88dc-131">[Conceder permisos de cubo o de modelo &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e88dc-131">[Grant cube or model permissions &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span></span>  
 <span data-ttu-id="e88dc-132">[Conceder acceso personalizado a datos de dimensión &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e88dc-132">[Grant custom access to dimension data &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span></span>  
 [<span data-ttu-id="e88dc-133">Otorgar acceso personalizado a los datos de las celdas &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e88dc-133">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
  
