---
title: Establecer permisos para elementos del servidor de informes en un sitio de SharePoint (Reporting Services en el modo integrado de SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- permissions [Reporting Services], SharePoint integrated mode
- SharePoint integration [Reporting Services], permissions
ms.assetid: 2467c657-a3bf-4ec3-a88c-8877df19823d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f38497843ca99342f13952153d7fed957564e006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744997"
---
# <a name="set-permissions-for-report-server-items-on-a-sharepoint-site-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="e2551-102">Establecer permisos para elementos del servidor de informes en un sitio de SharePoint (Reporting Services en el modo integrado de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="e2551-102">Set Permissions for Report Server Items on a SharePoint Site (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="e2551-103">Si la configuración de seguridad predeterminada no proporciona el nivel de acceso necesario, puede crear nuevos niveles de permisos para proporcionar acceso a elementos u operaciones específicos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="e2551-103">If default security settings do not provide the level of access that you require, you can create new permission levels to provide access to specific report server items or operations.</span></span> <span data-ttu-id="e2551-104">La configuración de seguridad personalizada puede ser útil si desea restringir el acceso a un informe determinado.</span><span class="sxs-lookup"><span data-stu-id="e2551-104">Custom security settings can be useful if you want to restrict access to a particular report.</span></span>  
  
 <span data-ttu-id="e2551-105">Debe ser el propietario del sitio para crear niveles de permiso y grupos.</span><span class="sxs-lookup"><span data-stu-id="e2551-105">You must be a site owner to create permission levels and groups.</span></span> <span data-ttu-id="e2551-106">Los niveles de permiso se usan de forma global en el sitio.</span><span class="sxs-lookup"><span data-stu-id="e2551-106">Permission levels are used globally throughout a site.</span></span> <span data-ttu-id="e2551-107">Si crea un nivel de permiso nuevo, estará disponible para otros propietarios de sitios.</span><span class="sxs-lookup"><span data-stu-id="e2551-107">If you create a new permission level, it will be available to other site owners.</span></span>  
  
 <span data-ttu-id="e2551-108">La mayoría de los permisos se heredan de un sitio primario.</span><span class="sxs-lookup"><span data-stu-id="e2551-108">Most permissions are inherited from a parent site.</span></span> <span data-ttu-id="e2551-109">Si asigna permisos en una biblioteca o elemento específicos, anula la herencia de permisos y genera una sobrecarga adicional en el modo de administrar los permisos para dicha rama de la jerarquía de sitios.</span><span class="sxs-lookup"><span data-stu-id="e2551-109">If you assign permissions on a specific library or item, you break permission inheritance and incur additional overhead in how manage permissions for that branch of your site hierarchy.</span></span>  
  
 <span data-ttu-id="e2551-110">Puede establecer permisos en archivos de definición de informe (.rdl), modelos (.smdl) y orígenes de datos compartidos (.rsds).</span><span class="sxs-lookup"><span data-stu-id="e2551-110">You can set permissions on report definition (.rdl), model (.smdl), and shared data source (.rsds) files.</span></span> <span data-ttu-id="e2551-111">No se pueden combinar permisos heredados y administrados en el mismo elemento.</span><span class="sxs-lookup"><span data-stu-id="e2551-111">You cannot combine inherited and managed permissions on the same item.</span></span> <span data-ttu-id="e2551-112">Si elige administrar permisos directamente, los permisos heredados no tendrán ningún efecto sobre el elemento actual.</span><span class="sxs-lookup"><span data-stu-id="e2551-112">If you choose to manage permissions directly, inherited permissions will have no effect on the current item.</span></span> <span data-ttu-id="e2551-113">Si desea reanudar la herencia de permisos más adelante, puede seleccionar **Heredar permisos** en el menú **Acciones** .</span><span class="sxs-lookup"><span data-stu-id="e2551-113">If you want to resume permission inheritance later, you can select **Inherit Permissions** on the **Actions** menu.</span></span>  
  
 <span data-ttu-id="e2551-114">Para establecer permisos en las entidades y perspectivas de un modelo, debe tener el nivel de permiso Control total para el modelo.</span><span class="sxs-lookup"><span data-stu-id="e2551-114">To set permissions on entities and perspectives in a model, you must have Full Control level of permission for the model.</span></span> <span data-ttu-id="e2551-115">Control total incluye "Administrar permisos", que es un permiso de nivel de sitio que se concede a los propietarios del sitio y a otros grupos de SharePoint con el nivel de permiso Control total.</span><span class="sxs-lookup"><span data-stu-id="e2551-115">Full Control includes "Manage Permissions", which is a site level permission that is granted to site owners and other SharePoint groups who have Full Control level of permission.</span></span> <span data-ttu-id="e2551-116">Si desea conceder a usuarios específicos la capacidad de establecer la seguridad de elementos de modelo, debe anular la herencia de permisos y conceder permisos elevados (como Control total) al usuario o grupo del archivo del modelo.</span><span class="sxs-lookup"><span data-stu-id="e2551-116">If you want to offer specific users the ability to set model item security, you must break permission inheritance and grant elevated permissions (such as Full Control) to the user or group on the model file.</span></span> <span data-ttu-id="e2551-117">Cuando concede el control total sobre un elemento como un archivo de una biblioteca, los permisos se centran en ese elemento y no se extienden al elemento primario ni a otros elementos de la misma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e2551-117">When you grant Full Control on an item such as a file in the library, the permissions are scoped to that item and do not extend to the parent or to other items within the same library.</span></span> <span data-ttu-id="e2551-118">Una vez que el usuario posee el permiso Administrar permisos para el modelo, podrá usar la seguridad de los elementos del modelo establecida a través del sitio de SharePoint o el Diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="e2551-118">After the user has Manage Permissions permission on the model, he or she can use set model item security via the SharePoint site or Model Designer.</span></span>  
  
### <a name="to-set-permissions-on-an-individual-report-model-or-data-source"></a><span data-ttu-id="e2551-119">Para establecer permisos en un informe, modelo u origen de datos individual</span><span class="sxs-lookup"><span data-stu-id="e2551-119">To set permissions on an individual report, model, or data source</span></span>  
  
1.  <span data-ttu-id="e2551-120">Si la biblioteca no está abierta todavía, haga clic en su nombre en Inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="e2551-120">If the library is not already open, click its name on the Quick Launch.</span></span> <span data-ttu-id="e2551-121">Si no aparece el nombre de la biblioteca, haga clic en **Ver todo el contenido del sitio**y, a continuación, haga clic en el nombre de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e2551-121">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="e2551-122">Seleccione el archivo de informe, modelo de informe u origen de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="e2551-122">Point to the report, report model, or shared data source file.</span></span>  
  
3.  <span data-ttu-id="e2551-123">Haga clic en la flecha hacia abajo y, en el menú, haga clic en **Administrar permisos**.</span><span class="sxs-lookup"><span data-stu-id="e2551-123">Click the down arrow, and on the menu, click **Manage Permissions**.</span></span>  
  
4.  <span data-ttu-id="e2551-124">En el menú **Acciones** , haga clic en **Editar permisos**y, a continuación, haga clic en **Aceptar** para confirmar la acción.</span><span class="sxs-lookup"><span data-stu-id="e2551-124">On the **Actions** menu, click **Edit Permissions**, and then click **OK** to confirm the action.</span></span>  
  
5.  <span data-ttu-id="e2551-125">Para conceder permisos a un usuario o un grupo que aún no tenga permisos para usar el archivo, haga clic en **Nuevo**y, a continuación, haga clic en **Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e2551-125">To give permissions to a user or group that does not yet have permissions to use the file, click **New**, and then click **Add Users**.</span></span>  
  
6.  <span data-ttu-id="e2551-126">Para quitar o modificar permisos para un usuario o grupo existente, haga clic en la casilla junto al usuario o grupo, haga clic en **Acciones**y, a continuación, haga clic en **Quitar permisos de usuario** o **Editar permisos de usuario**.</span><span class="sxs-lookup"><span data-stu-id="e2551-126">To remove or modify permissions for an existing user or group, click the check box next to the user or group, click **Actions**, and then click **Remove User Permissions** or **Edit User Permissions**.</span></span>  
  
### <a name="to-set-permissions-that-enable-model-item-security"></a><span data-ttu-id="e2551-127">Para establecer permisos que habiliten la seguridad de elementos de modelo</span><span class="sxs-lookup"><span data-stu-id="e2551-127">To set permissions that enable model item security</span></span>  
  
1.  <span data-ttu-id="e2551-128">Inicie sesión en el sitio de SharePoint mediante una cuenta con el permiso Administrar permisos para el sitio.</span><span class="sxs-lookup"><span data-stu-id="e2551-128">Log in to the SharePoint site using an account that has Manage Permissions permission on the site.</span></span>  
  
2.  <span data-ttu-id="e2551-129">Abra la biblioteca que contiene el modelo.</span><span class="sxs-lookup"><span data-stu-id="e2551-129">Open the library that contains the model.</span></span>  
  
3.  <span data-ttu-id="e2551-130">Elija el modelo.</span><span class="sxs-lookup"><span data-stu-id="e2551-130">Point to the model.</span></span>  
  
4.  <span data-ttu-id="e2551-131">Haga clic en la flecha hacia abajo situada junto al modelo y seleccione **Administrar permisos**.</span><span class="sxs-lookup"><span data-stu-id="e2551-131">Click the down arrow next to the model, and click **Manage Permissions**.</span></span>  
  
5.  <span data-ttu-id="e2551-132">Haga clic en **Acciones**.</span><span class="sxs-lookup"><span data-stu-id="e2551-132">Click **Actions**.</span></span>  
  
6.  <span data-ttu-id="e2551-133">Haga clic en **Editar permisos**.</span><span class="sxs-lookup"><span data-stu-id="e2551-133">Click **Edit Permissions**.</span></span> <span data-ttu-id="e2551-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2551-134">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="e2551-135">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="e2551-135">Click **New**.</span></span>  
  
8.  <span data-ttu-id="e2551-136">Haga clic en **Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e2551-136">Click **Add Users**.</span></span>  
  
9. <span data-ttu-id="e2551-137">En Usuarios/Grupos, especifique la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e2551-137">In Users/Groups, enter the user account.</span></span>  
  
10. <span data-ttu-id="e2551-138">Seleccione **Conceder permisos a los usuarios directamente**.</span><span class="sxs-lookup"><span data-stu-id="e2551-138">Select **Give users permission directly**.</span></span>  
  
11. <span data-ttu-id="e2551-139">Haga clic en **Control total**.</span><span class="sxs-lookup"><span data-stu-id="e2551-139">Click **Full Control**.</span></span>  
  
12. <span data-ttu-id="e2551-140">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2551-140">Click **OK**.</span></span> <span data-ttu-id="e2551-141">Una vez que el usuario pueda administrar permisos para un modelo específico, dicho usuario podrá abrir el modelo para editar los permisos de dicho modelo.</span><span class="sxs-lookup"><span data-stu-id="e2551-141">Once a user has the ability to manage permissions for a specific model, he or she can open the model to edit permissions within the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2551-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2551-142">See Also</span></span>  
 <span data-ttu-id="e2551-143">[Usar la seguridad integrada de Windows SharePoint Services para los elementos del servidor de informes](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="e2551-143">[Use Built-in Security in Windows SharePoint Services for Report Server Items](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span></span>  
 <span data-ttu-id="e2551-144">[Establecimiento de permisos para las operaciones del servidor de informes en una aplicación web de SharePoint](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span><span class="sxs-lookup"><span data-stu-id="e2551-144">[Set Permissions for Report Server Operations in a SharePoint Web Application](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span></span>  
 <span data-ttu-id="e2551-145">[Comparar roles y tareas de Reporting Services con grupos y permisos de SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="e2551-145">[Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span></span>  
 <span data-ttu-id="e2551-146">[Referencia de permisos de sitio y lista de SharePoint para los elementos del servidor de informes](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="e2551-146">[SharePoint Site and List Permission Reference for Report Server Items](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="e2551-147">Concesión de permisos sobre elementos del servidor de informes en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e2551-147">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
  
  
