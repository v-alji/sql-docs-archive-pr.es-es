---
title: Roles de seguridad (Analysis Services de datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- storage [Analysis Services], roles
- Analysis Services objects, roles
- security [Analysis Services], roles
- roles [Analysis Services], about roles
- server roles [Analysis Services]
- database roles [Analysis Services]
- roles [Analysis Services]
- storing data [Analysis Services], roles
- access rights [Analysis Services], roles
ms.assetid: 5b7e9cef-ff68-4d8e-99bc-e0094ced1baa
author: minewiskan
ms.author: owend
ms.openlocfilehash: e62abaab5a8f74dfee7d51962f2fb243dc6eb20a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748322"
---
# <a name="security-roles--analysis-services---multidimensional-data"></a><span data-ttu-id="bdd4a-102">Roles de seguridad (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="bdd4a-102">Security Roles  (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="bdd4a-103">Los roles se usan en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] para administrar la seguridad de los [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objetos y los datos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-103">Roles are used in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] to manage security for [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objects and data.</span></span> <span data-ttu-id="bdd4a-104">En términos simples, un rol asocia los identificadores de seguridad (SID) de usuarios y grupos de Microsoft Windows que tienen derechos y permisos de acceso específicos a los objetos administrados por una instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdd4a-104">In basic terms, a role associates the security identifiers (SIDs) of Microsoft Windows users and groups that have specific access rights and permissions defined for objects managed by an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="bdd4a-105">En [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]se incluyen dos tipos de roles:</span><span class="sxs-lookup"><span data-stu-id="bdd4a-105">Two types of roles are provided in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="bdd4a-106">El rol del servidor, que es un rol fijo que proporciona acceso de administrador a una instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdd4a-106">The server role, a fixed role that provides administrator access to an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="bdd4a-107">Los roles de base de datos, que son roles definidos por los administradores para controlar el acceso a los objetos y datos de los usuarios que no son administradores.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-107">Database roles, roles defined by administrators to control access to objects and data for non-administrator users.</span></span>  
  
 <span data-ttu-id="bdd4a-108">La seguridad en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] seguridad se administra mediante roles y permisos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-108">Security in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] security is managed by using roles and permissions.</span></span> <span data-ttu-id="bdd4a-109">Los roles son grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-109">Roles are groups of users.</span></span> <span data-ttu-id="bdd4a-110">Los usuarios, también denominados miembros, se pueden agregar o quitar de los roles.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-110">Users, also called members, can be added or removed from roles.</span></span> <span data-ttu-id="bdd4a-111">Los permisos de los objetos se especifican mediante los roles y todos los miembros de un rol pueden usar los objetos para los que este dispone de permiso.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-111">Permissions for objects are specified by roles, and all members in a role can use the objects for which the role has permissions.</span></span> <span data-ttu-id="bdd4a-112">Todos los miembros de un rol disponen de los mismos permisos en los objetos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-112">All members in a role have equal permissions to the objects.</span></span> <span data-ttu-id="bdd4a-113">Los permisos son específicos de los objetos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-113">Permissions are particular to objects.</span></span> <span data-ttu-id="bdd4a-114">Cada objeto cuenta con una colección de permisos que incluye los permisos concedidos en ese objeto; en un objeto se pueden conceder diferentes conjuntos de permisos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-114">Each object has a permissions collection with the permissions granted on that object, different sets of permissions can be granted on an object.</span></span> <span data-ttu-id="bdd4a-115">Cada permiso, de la colección de permisos del objeto, tiene un rol único asignado.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-115">Each permission, from the permissions collection of the object, has a single role assigned to it.</span></span>  
  
## <a name="role-and-role-member-objects"></a><span data-ttu-id="bdd4a-116">Objetos de rol y miembro de rol</span><span class="sxs-lookup"><span data-stu-id="bdd4a-116">Role and Role Member Objects</span></span>  
 <span data-ttu-id="bdd4a-117">Un rol es un objeto que contiene una colección de usuarios (miembros).</span><span class="sxs-lookup"><span data-stu-id="bdd4a-117">A role is a containing object for a collection of users (members).</span></span> <span data-ttu-id="bdd4a-118">La definición de roles establece la pertenencia de los usuarios en [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdd4a-118">A Role definition establishes the membership of the users in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="bdd4a-119">Dado que los permisos se asignan por rol, un usuario debe ser miembro de un rol para tener acceso a un objeto.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-119">Because permissions are assigned by role, a user must be a member of a role before the user has access to any object.</span></span>  
  
 <span data-ttu-id="bdd4a-120">Un objeto <xref:Microsoft.AnalysisServices.Role> se compone del nombre, el identificador y los miembros de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-120">A <xref:Microsoft.AnalysisServices.Role> object is composed of the parameters Name, Id, and Members.</span></span> <span data-ttu-id="bdd4a-121">Los miembros son una colección de cadenas.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-121">Members is a collection of strings.</span></span> <span data-ttu-id="bdd4a-122">Cada miembro contiene el nombre de usuario con el formato "dominio\nombre de usuario".</span><span class="sxs-lookup"><span data-stu-id="bdd4a-122">Each member contains the user name in the form of "domain\username".</span></span> <span data-ttu-id="bdd4a-123">El nombre es una cadena que contiene el nombre del rol.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-123">Name is a string that contains the name of the role.</span></span> <span data-ttu-id="bdd4a-124">El identificador es una cadena que contiene el identificador único del rol.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-124">ID is a string that contains the unique identifier of the role.</span></span>  
  
### <a name="server-role"></a><span data-ttu-id="bdd4a-125">Rol del servidor</span><span class="sxs-lookup"><span data-stu-id="bdd4a-125">Server Role</span></span>  
 <span data-ttu-id="bdd4a-126">El rol del servidor de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] define el acceso administrativo de los usuarios y grupos de Windows a una instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdd4a-126">The [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] server role defines administrative access of Windows users and groups to an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="bdd4a-127">Los miembros de este rol tienen acceso a todas las bases de datos y objetos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en una instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]y pueden realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="bdd4a-127">Members of this role have access to all [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] databases and objects on an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], and can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="bdd4a-128">Realizar funciones administrativas de nivel de servidor con SQL Server Management Studio o [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], incluida la creación de bases de datos y el establecimiento de propiedades de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-128">Perform server-level administrative functions using SQL Server Management Studio or [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], including creating databases and setting server-level properties.</span></span>  
  
-   <span data-ttu-id="bdd4a-129">Realizar funciones administrativas mediante programación con Objetos de administración de Análisis (AMO).</span><span class="sxs-lookup"><span data-stu-id="bdd4a-129">Perform administrative functions programmatically with Analysis Management Objects (AMO).</span></span>  
  
-   <span data-ttu-id="bdd4a-130">Mantener los roles de base de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bdd4a-130">Maintain [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database roles.</span></span>  
  
-   <span data-ttu-id="bdd4a-131">Iniciar seguimientos (distintas de eventos de procesamiento, que puede realizar un rol de base de datos con acceso de proceso).</span><span class="sxs-lookup"><span data-stu-id="bdd4a-131">Start traces (other than for processing events, which can be performed by a database role with Process access).</span></span>  
  
 <span data-ttu-id="bdd4a-132">Cada instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] tiene un rol de servidor que define qué usuarios pueden administrar la instancia.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-132">Every instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] has a server role that defines which users can administer that instance.</span></span> <span data-ttu-id="bdd4a-133">El nombre e Id. de este rol es Administradores y, a diferencia de los roles de base de datos, no puede eliminarse el rol del servidor ni pueden agregarse ni quitarse permisos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-133">The name and ID of this role is Administrators, and unlike database roles, the server role cannot be deleted, nor can permissions be added or removed.</span></span> <span data-ttu-id="bdd4a-134">En otras palabras, un usuario puede o no ser un administrador para una instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], según esté incluido en el rol del servidor de la instancia de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdd4a-134">In other words, a user either is or is not an administrator for an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], depending on whether he or she is included in the server role for that instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
### <a name="database-roles"></a><span data-ttu-id="bdd4a-135">Roles de base de datos</span><span class="sxs-lookup"><span data-stu-id="bdd4a-135">Database Roles</span></span>  
 <span data-ttu-id="bdd4a-136">Un rol de base de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] define el acceso de usuario a los objetos y datos de una base de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bdd4a-136">An [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database role defines user access to objects and data in an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="bdd4a-137">Un rol de base de datos se crea como objeto independiente en una base de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] y solo se aplica a la base de datos en la que se crea el rol.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-137">A database role is created as a separate object in an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database, and applies only to the database in which that role is created.</span></span> <span data-ttu-id="bdd4a-138">El administrador incluye los usuarios y grupos de Windows en el rol y también define los permisos del rol.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-138">Windows users and groups are included in the role by an administrator, who also defines permissions within the role.</span></span>  
  
 <span data-ttu-id="bdd4a-139">Los permisos de un rol pueden permitir a los miembros obtener acceso y administrar la base de datos, además de los objetos y los datos de la misma.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-139">The permissions of a role may allow members to access and administer the database, in addition to the objects and data within the database.</span></span> <span data-ttu-id="bdd4a-140">Cada permiso tiene uno o más derechos de acceso asociados, que a su vez proporcionan al permiso más control sobre el acceso a un objeto específico de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-140">Each permission has one or more access rights associated with it, which in turn give the permission finer control over access to a particular object in the database.</span></span>  
  
## <a name="permission-objects"></a><span data-ttu-id="bdd4a-141">Objetos de permiso</span><span class="sxs-lookup"><span data-stu-id="bdd4a-141">Permission Objects</span></span>  
 <span data-ttu-id="bdd4a-142">Los permisos se asocian a un objeto (cubo, dimensión, otros) para un rol determinado.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-142">Permissions are associated with an object (cube, dimension, others) for a particular role.</span></span> <span data-ttu-id="bdd4a-143">Los permisos especifican qué operaciones puede realizar el miembro de dicho rol en el objeto.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-143">Permissions specify what operations the member of that role can perform on that object.</span></span>  
  
 <span data-ttu-id="bdd4a-144">La clase <xref:Microsoft.AnalysisServices.Permission> es una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-144">The <xref:Microsoft.AnalysisServices.Permission> class is an abstract class.</span></span> <span data-ttu-id="bdd4a-145">Por consiguiente, debe usar las clases derivadas para definir los permisos en los objetos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-145">Therefore, you must use the derived classes to define permissions on the corresponding objects.</span></span> <span data-ttu-id="bdd4a-146">Para cada objeto se define una clase derivada de permiso.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-146">For each object, a permission derived class is defined.</span></span>  
  
|<span data-ttu-id="bdd4a-147">Object</span><span class="sxs-lookup"><span data-stu-id="bdd4a-147">Object</span></span>|<span data-ttu-id="bdd4a-148">Clase</span><span class="sxs-lookup"><span data-stu-id="bdd4a-148">Class</span></span>|  
|------------|-----------|  
|<xref:Microsoft.AnalysisServices.Database>|<xref:Microsoft.AnalysisServices.DatabasePermission>|  
|<xref:Microsoft.AnalysisServices.DataSource>|<xref:Microsoft.AnalysisServices.DataSourcePermission>|  
|<xref:Microsoft.AnalysisServices.Dimension>|<xref:Microsoft.AnalysisServices.DimensionPermission>|  
|<xref:Microsoft.AnalysisServices.Cube>|<xref:Microsoft.AnalysisServices.CubePermission>|  
|<xref:Microsoft.AnalysisServices.MiningStructure>|<xref:Microsoft.AnalysisServices.MiningStructurePermission>|  
|<xref:Microsoft.AnalysisServices.MiningModel>|<xref:Microsoft.AnalysisServices.MiningModelPermission>|  
  
 <span data-ttu-id="bdd4a-149">En la lista se muestran las posibles acciones habilitadas por permisos:</span><span class="sxs-lookup"><span data-stu-id="bdd4a-149">Possible actions enabled by permissions are shown in the list:</span></span>  
  
|<span data-ttu-id="bdd4a-150">Acción</span><span class="sxs-lookup"><span data-stu-id="bdd4a-150">Action</span></span>|<span data-ttu-id="bdd4a-151">Valores</span><span class="sxs-lookup"><span data-stu-id="bdd4a-151">Values</span></span>|<span data-ttu-id="bdd4a-152">Explicación</span><span class="sxs-lookup"><span data-stu-id="bdd4a-152">Explanation</span></span>|  
|------------|------------|-----------------|  
|<span data-ttu-id="bdd4a-153">Proceso</span><span class="sxs-lookup"><span data-stu-id="bdd4a-153">Process</span></span>|<span data-ttu-id="bdd4a-154">{`true`, `false`}</span><span class="sxs-lookup"><span data-stu-id="bdd4a-154">{`true`, `false`}</span></span><br /><br /> <span data-ttu-id="bdd4a-155">Valor predeterminado = `false`</span><span class="sxs-lookup"><span data-stu-id="bdd4a-155">Default=`false`</span></span>|<span data-ttu-id="bdd4a-156">Si es `true`, los miembros pueden procesar el objeto y cualquier objeto contenido en él.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-156">If `true`, members can process the object and any object that is contained in the object.</span></span><br /><br /> <span data-ttu-id="bdd4a-157">Los permisos de proceso no se aplican a los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-157">Process permissions do not apply to mining models.</span></span> <span data-ttu-id="bdd4a-158">Los permisos de <xref:Microsoft.AnalysisServices.MiningModel> siempre se heredan de <xref:Microsoft.AnalysisServices.MiningStructure>.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-158"><xref:Microsoft.AnalysisServices.MiningModel> permissions are always inherited from <xref:Microsoft.AnalysisServices.MiningStructure>.</span></span>|  
|<span data-ttu-id="bdd4a-159">Leer definición</span><span class="sxs-lookup"><span data-stu-id="bdd4a-159">ReadDefinition</span></span>|<span data-ttu-id="bdd4a-160">{`None`, `Basic`, `Allowed`}</span><span class="sxs-lookup"><span data-stu-id="bdd4a-160">{`None`, `Basic`, `Allowed`}</span></span><br /><br /> <span data-ttu-id="bdd4a-161">Valor predeterminado = `None`</span><span class="sxs-lookup"><span data-stu-id="bdd4a-161">Default=`None`</span></span>|<span data-ttu-id="bdd4a-162">Especifica si los miembros pueden leer la definición de datos (ASSL) asociada al objeto.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-162">Specifies whether members can read the data definition (ASSL) associated with the object.</span></span><br /><br /> <span data-ttu-id="bdd4a-163">Si el valor es `Allowed`, los miembros pueden leer el ASSL asociado al objeto.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-163">If `Allowed`, members can read the ASSL associated with the object.</span></span><br /><br /> <span data-ttu-id="bdd4a-164">Los objetos incluidos en el objeto heredan `Basic` y `Allowed`.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-164">`Basic` and `Allowed` are inherited by objects that are contained in the object.</span></span> <span data-ttu-id="bdd4a-165">`Allowed` invalida `Basic` y `None`.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-165">`Allowed` overrides `Basic` and `None`.</span></span><br /><br /> <span data-ttu-id="bdd4a-166">`Allowed` se requiere para usar DISCOVER_XML_METADATA en un objeto.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-166">`Allowed` is required for DISCOVER_XML_METADATA on an object.</span></span> <span data-ttu-id="bdd4a-167">`Basic` se requiere para crear objetos vinculados y cubos locales.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-167">`Basic` is required to create linked objects and local cubes.</span></span>|  
|<span data-ttu-id="bdd4a-168">Lectura</span><span class="sxs-lookup"><span data-stu-id="bdd4a-168">Read</span></span>|<span data-ttu-id="bdd4a-169">{`None`, `Allowed`}</span><span class="sxs-lookup"><span data-stu-id="bdd4a-169">{`None`, `Allowed`}</span></span><br /><br /> <span data-ttu-id="bdd4a-170">Valor predeterminado =`None` (excepto en permisos de dimensión, donde el valor predeterminado =`Allowed`)</span><span class="sxs-lookup"><span data-stu-id="bdd4a-170">Default=`None` (Except for DimensionPermission, where default=`Allowed`)</span></span>|<span data-ttu-id="bdd4a-171">Especifica si los miembros disponen de acceso de lectura a los conjuntos de filas de esquema y contenido de datos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-171">Specifies whether members have read access to schema rowsets and data content.</span></span><br /><br /> <span data-ttu-id="bdd4a-172">`Allowed`proporciona acceso de lectura a una base de datos, lo que permite detectar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-172">`Allowed` gives read access on a database, which lets you discover a database.</span></span><br /><br /> <span data-ttu-id="bdd4a-173">`Allowed` en un cubo proporciona acceso de lectura a conjuntos de filas de esquema y acceso al contenido del cubo (a menos que se restrinja mediante <xref:Microsoft.AnalysisServices.CellPermission> y <xref:Microsoft.AnalysisServices.CubeDimensionPermission>).</span><span class="sxs-lookup"><span data-stu-id="bdd4a-173">`Allowed` on a cube gives read access in schema rowsets and access to cube content (unless constrained by <xref:Microsoft.AnalysisServices.CellPermission> and <xref:Microsoft.AnalysisServices.CubeDimensionPermission>).</span></span><br /><br /> <span data-ttu-id="bdd4a-174">`Allowed` en una dimensión concede permiso de lectura en todos los atributos de la dimensión (a menos que se restrinja mediante <xref:Microsoft.AnalysisServices.CubeDimensionPermission>).</span><span class="sxs-lookup"><span data-stu-id="bdd4a-174">`Allowed` on a dimension grants that read permission on all attributes in the dimension (unless constrained by <xref:Microsoft.AnalysisServices.CubeDimensionPermission>).</span></span> <span data-ttu-id="bdd4a-175">El permiso de lectura solamente se usa para la herencia estática a <xref:Microsoft.AnalysisServices.CubeDimensionPermission>.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-175">Read permission is used for static inheritance to the <xref:Microsoft.AnalysisServices.CubeDimensionPermission> only.</span></span> <span data-ttu-id="bdd4a-176">`None` en una dimensión oculta la dimensión y solo proporciona acceso al miembro predeterminado para los atributos agregables; se produce un error si la dimensión contiene un atributo no agregable.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-176">`None` on a dimension hides the dimension and gives access to the default member only for aggregatable attributes; an error is raised if the dimension contains a non-aggregatable attribute.</span></span><br /><br /> <span data-ttu-id="bdd4a-177">`Allowed` en <xref:Microsoft.AnalysisServices.MiningModelPermission> concede permisos para ver los objetos en conjuntos de filas de esquema y para realizar combinaciones de predicciones.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-177">`Allowed` on a <xref:Microsoft.AnalysisServices.MiningModelPermission> grants permissions to see objects in schema rowsets and to perform predict joins.</span></span><br /><br /> <span data-ttu-id="bdd4a-178">**NoteAllowed** es necesario para leer o escribir en cualquier objeto de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-178">**NoteAllowed** is required to read or write to any object in the database.</span></span>|  
|<span data-ttu-id="bdd4a-179">Escritura</span><span class="sxs-lookup"><span data-stu-id="bdd4a-179">Write</span></span>|<span data-ttu-id="bdd4a-180">{`None`, `Allowed`}</span><span class="sxs-lookup"><span data-stu-id="bdd4a-180">{`None`, `Allowed`}</span></span><br /><br /> <span data-ttu-id="bdd4a-181">Valor predeterminado = `None`</span><span class="sxs-lookup"><span data-stu-id="bdd4a-181">Default=`None`</span></span>|<span data-ttu-id="bdd4a-182">Especifica si los miembros tienen acceso de escritura a los datos del objeto primario.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-182">Specifies whether members have write access to data of the parent object.</span></span><br /><br /> <span data-ttu-id="bdd4a-183">El acceso se aplica a las subclases <xref:Microsoft.AnalysisServices.Dimension>, <xref:Microsoft.AnalysisServices.Cube> y <xref:Microsoft.AnalysisServices.MiningModel>.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-183">Access applies to <xref:Microsoft.AnalysisServices.Dimension>, <xref:Microsoft.AnalysisServices.Cube>, and <xref:Microsoft.AnalysisServices.MiningModel> subclasses.</span></span> <span data-ttu-id="bdd4a-184">No se aplica a las subclases <xref:Microsoft.AnalysisServices.MiningStructure> de base de datos, que generan un error de validación.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-184">It does not apply to database <xref:Microsoft.AnalysisServices.MiningStructure> subclasses, which generates a validation error.</span></span><br /><br /> <span data-ttu-id="bdd4a-185">`Allowed` en <xref:Microsoft.AnalysisServices.Dimension> concede permiso de escritura en todos los atributos de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-185">`Allowed` on a <xref:Microsoft.AnalysisServices.Dimension> grants write permission on all attributes in the dimension.</span></span><br /><br /> <span data-ttu-id="bdd4a-186">`Allowed` en <xref:Microsoft.AnalysisServices.Cube> concede permiso de escritura en las celdas del cubo de particiones definidas con el tipo de reescritura.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-186">`Allowed` on a <xref:Microsoft.AnalysisServices.Cube> grants write permission on the cells of the cube for partitions defined as Type=writeback.</span></span><br /><br /> <span data-ttu-id="bdd4a-187">`Allowed` en <xref:Microsoft.AnalysisServices.MiningModel> concede permiso para modificar el contenido del modelo.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-187">`Allowed` on a <xref:Microsoft.AnalysisServices.MiningModel> grants permission to modify model content.</span></span><br /><br /> <span data-ttu-id="bdd4a-188">`Allowed` en <xref:Microsoft.AnalysisServices.MiningStructure> no tiene ningún significado concreto en [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdd4a-188">`Allowed` on a <xref:Microsoft.AnalysisServices.MiningStructure> has no specific meaning in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="bdd4a-189">**Nota:**  La escritura no se puede establecer en a menos que la `Allowed` lectura también esté establecida en`Allowed`</span><span class="sxs-lookup"><span data-stu-id="bdd4a-189">**Note:**  Write cannot be set to `Allowed` unless read is also set to `Allowed`</span></span>|  
|<span data-ttu-id="bdd4a-190">Administrar **Nota:** solo en permisos de base de datos</span><span class="sxs-lookup"><span data-stu-id="bdd4a-190">Administer **Note:**  Only in Database permissions</span></span>|<span data-ttu-id="bdd4a-191">{`true`, `false`}</span><span class="sxs-lookup"><span data-stu-id="bdd4a-191">{`true`, `false`}</span></span><br /><br /> <span data-ttu-id="bdd4a-192">Valor predeterminado = `false`</span><span class="sxs-lookup"><span data-stu-id="bdd4a-192">Default=`false`</span></span>|<span data-ttu-id="bdd4a-193">Especifica si los miembros pueden administrar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-193">Specifies whether members can administer a database.</span></span><br /><br /> <span data-ttu-id="bdd4a-194">`true` permite el acceso de los miembros a todos los objetos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-194">`true` grants members access to all objects in a database.</span></span><br /><br /> <span data-ttu-id="bdd4a-195">Un miembro puede tener permisos para administrar una base de datos concreta, pero no otras.</span><span class="sxs-lookup"><span data-stu-id="bdd4a-195">A member can have Administer permissions for a specific database, but not for others.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdd4a-196">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdd4a-196">See Also</span></span>  
 [<span data-ttu-id="bdd4a-197">Cómo autorizar el acceso a objetos y operaciones &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bdd4a-197">Authorizing access to objects and operations &#40;Analysis Services&#41;</span></span>](../authorizing-access-to-objects-and-operations-analysis-services.md)  
  
  