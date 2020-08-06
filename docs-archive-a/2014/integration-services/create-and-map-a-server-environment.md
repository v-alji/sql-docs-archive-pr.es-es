---
title: Crear y asignar un entorno de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isenvprop.variables.f1
- sql12.ssis.ssms.iscreateenv.f1
- sql12.ssis.ssms.isenvprop.permissions.f1
- sql12.ssis.ssms.isenvprop.general.f1
ms.assetid: b1cbb697-713f-48e4-b234-b23724d87451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9331b5078effb562931f45c48bd8ff975c1d1998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671606"
---
# <a name="create-and-map-a-server-environment"></a><span data-ttu-id="daa1f-102">Crear y asignar un entorno de servidor</span><span class="sxs-lookup"><span data-stu-id="daa1f-102">Create and Map a Server Environment</span></span>
  <span data-ttu-id="daa1f-103">Los entornos de servidor se crean con el fin de especificar valores en tiempo de ejecución para los paquetes contenidos en un proyecto implementado en el servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daa1f-103">You create a server environment to specify runtime values for packages contained in a project you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="daa1f-104">Después puede asignar las variables de entorno a parámetros para un paquete concreto, para los paquetes de punto de entrada o para todos los paquetes de un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="daa1f-104">You can then map the environment variables to parameters, for a specific package, for entry-point packages, or for all the packages in a given project.</span></span> <span data-ttu-id="daa1f-105">Un paquete de punto de entrada suele ser un paquete primario que ejecuta un paquete secundario.</span><span class="sxs-lookup"><span data-stu-id="daa1f-105">An entry-point package is typically a parent package that executes a child package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="daa1f-106">Para una ejecución determinada, un paquete solo puede ejecutarse con los valores contenidos en un único entorno de servidor.</span><span class="sxs-lookup"><span data-stu-id="daa1f-106">For a given execution, a package can execute only with the values contained in a single server environment.</span></span>  
  
 <span data-ttu-id="daa1f-107">Puede consultar las vistas para obtener una lista de entornos de servidor, referencias de entorno y variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="daa1f-107">You can query views for a list of server environments, environment references, and environment variables.</span></span> <span data-ttu-id="daa1f-108">También puede llamar a procedimientos almacenados para agregar, eliminar y modificar entornos, referencias de entorno y variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="daa1f-108">You can also call stored to add, delete, and modify environments, environment references, and environment variables.</span></span> <span data-ttu-id="daa1f-109">Para obtener más información, vea la sección **Entornos de servidor, variables de servidor y referencias del entorno de servidor** en [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="daa1f-109">For more information, see the **Server Environments, Server Variables and Server Environment References** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
### <a name="to-create-and-use-a-server-environment"></a><span data-ttu-id="daa1f-110">Para crear y utilizar un entorno de servidor</span><span class="sxs-lookup"><span data-stu-id="daa1f-110">To create and use a server environment</span></span>  
  
1.  <span data-ttu-id="daa1f-111">En [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , expanda el [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nodo catálogos> **SSISDB** en explorador de objetos y busque la carpeta **entornos** del proyecto para el que desea crear un entorno.</span><span class="sxs-lookup"><span data-stu-id="daa1f-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], expand the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Catalogs> **SSISDB** node in Object Explorer, and locate the **Environments** folder of the project for which you want to create an environment.</span></span>  
  
2.  <span data-ttu-id="daa1f-112">Haga clic con el botón derecho en la carpeta **Entornos** y, después, haga clic en **Crear entorno**.</span><span class="sxs-lookup"><span data-stu-id="daa1f-112">Right-click the **Environments** folder, and then click **Create Environment**.</span></span>  
  
3.  <span data-ttu-id="daa1f-113">Escriba un nombre para el entorno y opcionalmente una descripción y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="daa1f-113">Type a name for the environment and optionally a description, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="daa1f-114">Haga clic con el botón derecho en el nuevo entorno y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="daa1f-114">Right-click the new environment and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="daa1f-115">En la página **Variables** , haga lo siguiente para agregar una variable.</span><span class="sxs-lookup"><span data-stu-id="daa1f-115">On the **Variables** page, do the following to add a variable.</span></span>  
  
    1.  <span data-ttu-id="daa1f-116">Seleccione **Tipo** para la variable.</span><span class="sxs-lookup"><span data-stu-id="daa1f-116">Select the **Type** for the variable.</span></span> <span data-ttu-id="daa1f-117">**No** es necesario que el nombre de la variable coincida con el nombre del parámetro del proyecto al que asignará la variable.</span><span class="sxs-lookup"><span data-stu-id="daa1f-117">The name of the variable **does not** need to match the name of the project parameter that you map to the variable.</span></span>  
  
    2.  <span data-ttu-id="daa1f-118">Escriba la **Descripción** opcional para la variable.</span><span class="sxs-lookup"><span data-stu-id="daa1f-118">Enter an optional **Description** for the variable.</span></span>  
  
    3.  <span data-ttu-id="daa1f-119">Escriba el **Valor** para la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="daa1f-119">Enter the **Value** for the environment variable.</span></span>  
  
         <span data-ttu-id="daa1f-120">Para obtener información sobre las reglas para los nombres de las variables de entorno, vea la sección **Variable de entorno** en [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="daa1f-120">For information about the rules for environment variable names, see the **Environment Variable** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
    4.  <span data-ttu-id="daa1f-121">Indique si la variable contiene un valor confidencial; para ello, active o desactive la casilla **Confidencial** .</span><span class="sxs-lookup"><span data-stu-id="daa1f-121">Indicate whether the variable contains sensitive value, by selecting or clearing the **Sensitive** checkbox.</span></span>  
  
         <span data-ttu-id="daa1f-122">Si selecciona **Confidencial**, el valor de la variable no aparece en el campo **Valor** .</span><span class="sxs-lookup"><span data-stu-id="daa1f-122">If you select **Sensitive**, the variable value does not display in the **Value** field.</span></span>  
  
         <span data-ttu-id="daa1f-123">Los valores confidenciales se cifran en el catálogo de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="daa1f-123">Sensitive values are encrypted in the SSISDB catalog.</span></span> <span data-ttu-id="daa1f-124">Para obtener más información acerca del cifrado, vea [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="daa1f-124">For more information about the encryption, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
6.  <span data-ttu-id="daa1f-125">En la página **Permisos** , haga lo siguiente para conceder o denegar permisos para los usuarios y roles seleccionados.</span><span class="sxs-lookup"><span data-stu-id="daa1f-125">On the **Permissions** page, grant or deny permissions for selected users and roles by doing the following.</span></span>  
  
    1.  <span data-ttu-id="daa1f-126">Haga clic en **Examinar**y, a continuación, seleccione uno o más usuarios y roles en el cuadro de diálogo **Examinar todas las entidades** .</span><span class="sxs-lookup"><span data-stu-id="daa1f-126">Click **Browse**, and then select one or more users and roles in the **Browse All Principals** dialog box.</span></span>  
  
    2.  <span data-ttu-id="daa1f-127">En el área **Inicios de sesión o roles** , seleccione el usuario o el rol al que desea conceder o denegar permisos.</span><span class="sxs-lookup"><span data-stu-id="daa1f-127">In the **Logins or roles** area, select the user or role that you want to grant or deny permissions for.</span></span>  
  
    3.  <span data-ttu-id="daa1f-128">En el área **Explícito** , haga clic en **Conceder** o **Denegar** junto a cada permiso.</span><span class="sxs-lookup"><span data-stu-id="daa1f-128">In the **Explicit** area, click **Grant** or **Deny** next to each permission.</span></span>  
  
7.  <span data-ttu-id="daa1f-129">Para incluir el entorno en el script, haga clic en **Script**.</span><span class="sxs-lookup"><span data-stu-id="daa1f-129">To script the environment, click **Script**.</span></span> <span data-ttu-id="daa1f-130">De forma predeterminada, el script aparece en una nueva ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="daa1f-130">By default, the script displays in a new Query Editor window.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="daa1f-131">Tiene que hacer clic en **Script** después de realizar cambios en las propiedades del entorno (como agregar una variable) y antes de hacer clic en **Aceptar** en el cuadro de diálogo **Propiedades del entorno**.</span><span class="sxs-lookup"><span data-stu-id="daa1f-131">You need to click **Script** after you've made one or changes to the environment properties, such as adding a variable, and before you click **OK** in the **Environment Properties** dialog box.</span></span> <span data-ttu-id="daa1f-132">De lo contrario, no se generará un script.</span><span class="sxs-lookup"><span data-stu-id="daa1f-132">Otherwise, a script is not generated.</span></span>  
  
8.  <span data-ttu-id="daa1f-133">Haga clic en **Aceptar** para guardar los cambios realizados en las propiedades de entorno.</span><span class="sxs-lookup"><span data-stu-id="daa1f-133">Click **OK** to save your changes to the environment properties.</span></span>  
  
9. <span data-ttu-id="daa1f-134">En el nodo **SSISDB** del Explorador de objetos, expanda la carpeta **Proyectos** , haga clic con el botón derecho en el proyecto y, después, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="daa1f-134">Under the **SSISDB** node in Object Explorer, expand the **Projects** folder, right-click the project, and then click **Configure**.</span></span>  
  
10. <span data-ttu-id="daa1f-135">En la página **Referencias** , haga clic en **Agregar** para agregar un entorno y, a continuación, haga clic en **Aceptar** para guardar la referencia al entorno.</span><span class="sxs-lookup"><span data-stu-id="daa1f-135">On the **References** page, click **Add** to add an environment, and then click **OK** to save the reference to the environment.</span></span>  
  
11. <span data-ttu-id="daa1f-136">Vuelva a hacer clic con el botón derecho en el proyecto y, después, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="daa1f-136">Right-click the project again, and then click **Configure**.</span></span>  
  
12. <span data-ttu-id="daa1f-137">Para asignar la variable de entorno a un parámetro que agregó al paquete en tiempo de diseño o a un parámetro que se generó cuando convirtió el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] al modelo de implementación del proyecto, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="daa1f-137">To map the environment variable to a parameter that you added to the package at design-time or to a parameter that was generated when you converted the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the project deployment model, do the following.,</span></span>  
  
    1.  <span data-ttu-id="daa1f-138">En la pestaña **Parámetros** de la página **Parámetros** , haga clic en el botón Examinar situado junto al campo **Valor** .</span><span class="sxs-lookup"><span data-stu-id="daa1f-138">In the **Parameters** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="daa1f-139">Haga clic en **Usar variable de entorno**y seleccione la variable de entorno que creó.</span><span class="sxs-lookup"><span data-stu-id="daa1f-139">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
13. <span data-ttu-id="daa1f-140">Para asignar la variable de entorno a una propiedad del administrador de conexiones, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="daa1f-140">To map the environment variable to a connection manager property, do the following.</span></span> <span data-ttu-id="daa1f-141">Se generan automáticamente parámetros en el servidor SSIS para las propiedades del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="daa1f-141">Parameters are automatically generated on the SSIS server for the connection manager properties.</span></span>  
  
    1.  <span data-ttu-id="daa1f-142">En la pestaña **Administradores de conexiones** de la página **Parámetros** , haga clic en el botón Examinar situado junto al campo **Valor** .</span><span class="sxs-lookup"><span data-stu-id="daa1f-142">In the **Connection Managers** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="daa1f-143">Haga clic en **Usar variable de entorno**y seleccione la variable de entorno que creó.</span><span class="sxs-lookup"><span data-stu-id="daa1f-143">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
14. <span data-ttu-id="daa1f-144">Haga clic en **Aceptar** dos veces para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="daa1f-144">Click **OK** twice to save your changes.</span></span>  
  
  
