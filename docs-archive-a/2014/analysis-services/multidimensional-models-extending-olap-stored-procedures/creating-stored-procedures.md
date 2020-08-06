---
title: Crear procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- registering assemblies
- database assemblies [Analysis Services]
- server assemblies [Analysis Services]
- stored procedures [Analysis Services], creating
- assemblies [Analysis Services]
ms.assetid: a12ff02f-6d0b-4488-9846-3609fc0d0554
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9a997244a2d54cca8732196107dd21927b5f9e2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746041"
---
# <a name="creating-stored-procedures"></a><span data-ttu-id="79d0f-102">Creación de procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="79d0f-102">Creating Stored Procedures</span></span>
  <span data-ttu-id="79d0f-103">Todos los procedimientos almacenados deben asociarse a una clase de Common Language Runtime (CLR) o Modelo de objetos componentes (COM) para poder usarse.</span><span class="sxs-lookup"><span data-stu-id="79d0f-103">All stored procedures must be associated with a common language runtime (CLR) or Component Object Model (COM) class in order to be used.</span></span> <span data-ttu-id="79d0f-104">La clase debe instalarse en el servidor (normalmente en forma de una [!INCLUDE[msCoName](../../includes/msconame-md.md)] biblioteca de vínculos dinámicos (dll) de ActiveX® y registrada como un ensamblado en el servidor o en una [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="79d0f-104">The class must be installed on the server - usually in the form of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® dynamic link library (DLL) - and registered as an assembly on the server or in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="79d0f-105">Los procedimientos almacenados se registran en un servidor o en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="79d0f-105">Stored procedures are registered on a server or on a database.</span></span> <span data-ttu-id="79d0f-106">Se puede llamar a los procedimientos almacenados del servidor desde cualquier contexto de consulta.</span><span class="sxs-lookup"><span data-stu-id="79d0f-106">Server stored procedures can be called from any query context.</span></span> <span data-ttu-id="79d0f-107">Solo se puede tener acceso a los procedimientos almacenados de base de datos si el contexto de base de datos es la base de datos bajo la cual se define el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="79d0f-107">Database stored procedures can only be accessed if the database context is the database under which the stored procedure is defined.</span></span> <span data-ttu-id="79d0f-108">Si las funciones de un ensamblado llaman a las funciones en otro ensamblado, debe registrar ambos ensamblados en el mismo contexto (servidor o base de datos).</span><span class="sxs-lookup"><span data-stu-id="79d0f-108">If functions in one assembly call functions in a different assembly, you must register both assemblies in the same context (server or database).</span></span> <span data-ttu-id="79d0f-109">Para un servidor o una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de datos implementada en un servidor, puede usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para registrar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="79d0f-109">For a server or a deployed [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database on a server, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to register an assembly.</span></span> <span data-ttu-id="79d0f-110">Para un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], puede usar el Diseñador de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para registrar un ensamblado en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="79d0f-110">For an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you can use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Designer to register an assembly in the project.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="79d0f-111">Los ensamblados COM pueden suponer un riesgo para la seguridad.</span><span class="sxs-lookup"><span data-stu-id="79d0f-111">COM assemblies might pose a security risk.</span></span> <span data-ttu-id="79d0f-112">Debido a esto y a otras consideraciones, los ensamblados COM están en desuso en [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79d0f-112">Due to this risk and other considerations, COM assemblies were deprecated in [!INCLUDE[ssASversion10](../../includes/ssasversion10-md.md)].</span></span> <span data-ttu-id="79d0f-113">Es posible que este tipo de ensamblados no esté disponible en versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="79d0f-113">COM assemblies might not be supported in future releases.</span></span>  
  
## <a name="registering-a-server-assembly"></a><span data-ttu-id="79d0f-114">Registro de un ensamblado de servidor</span><span class="sxs-lookup"><span data-stu-id="79d0f-114">Registering a Server Assembly</span></span>  
 <span data-ttu-id="79d0f-115">En el Explorador de objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], los ensamblados de servidor aparecen en la carpeta Ensamblados bajo una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79d0f-115">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], server assemblies are listed in the Assemblies folder under an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="79d0f-116">Los ensamblados de servidor pueden contener ensamblados .NET (CLR) y bibliotecas COM.</span><span class="sxs-lookup"><span data-stu-id="79d0f-116">Server assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-server-assembly"></a><span data-ttu-id="79d0f-117">Para crear un ensamblado de servidor</span><span class="sxs-lookup"><span data-stu-id="79d0f-117">To create a server assembly</span></span>  
  
1.  <span data-ttu-id="79d0f-118">Expanda la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en explorador de objetos, haga clic con el botón secundario en la carpeta **ensamblados** y, a continuación, haga clic en **nuevo ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="79d0f-118">Expand the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="79d0f-119">Esto muestra el cuadro de diálogo **registrar ensamblado de servidor** .</span><span class="sxs-lookup"><span data-stu-id="79d0f-119">This displays the **Register Server Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="79d0f-120">En **tipo** , especifique el tipo de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="79d0f-120">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="79d0f-121">Para una DLL de código administrado (CLR), especifique Ensamblado .NET.</span><span class="sxs-lookup"><span data-stu-id="79d0f-121">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="79d0f-122">Para un archivo DLL de código nativo (COM), especifique DLL de COM.</span><span class="sxs-lookup"><span data-stu-id="79d0f-122">For a native code (COM) DLL, specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="79d0f-123">En **nombre de archivo**, especifique el archivo DLL que contiene los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="79d0f-123">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="79d0f-124">En **nombre de ensamblado**, especifique un nombre para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="79d0f-124">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="79d0f-125">Si se trata de una compilación de depuración de la biblioteca que va a usar para depurar procedimientos almacenados, active la casilla **incluir información de depuración** .</span><span class="sxs-lookup"><span data-stu-id="79d0f-125">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="79d0f-126">Para obtener más información sobre la depuración de procedimientos almacenados, vea [depurar procedimientos almacenados](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="79d0f-126">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="79d0f-127">Puede hacer clic en **Aceptar** para registrar el ensamblado inmediatamente, o bien, en la barra de herramientas del cuadro de diálogo, puede hacer clic en un comando del menú **script** para incluir en el script la acción de registro en una ventana de consulta, un archivo o el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="79d0f-127">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="79d0f-128">Después de registrar un ensamblado de servidor, puede configurarlo haciendo clic con el botón secundario en el ensamblado en Explorador de objetos y, a continuación, haciendo clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="79d0f-128">After you register a server assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-on-the-server"></a><span data-ttu-id="79d0f-129">Registrar un ensamblado de base de datos en el servidor</span><span class="sxs-lookup"><span data-stu-id="79d0f-129">Registering a Database Assembly on the Server</span></span>  
 <span data-ttu-id="79d0f-130">En el Explorador de objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], los ensamblados de base de datos aparecen en la carpeta Ensamblados bajo una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79d0f-130">In Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="79d0f-131">Los ensamblados de base de datos pueden contener ensamblados .NET (CLR) y bibliotecas COM.</span><span class="sxs-lookup"><span data-stu-id="79d0f-131">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-on-a-server"></a><span data-ttu-id="79d0f-132">Para crear un ensamblado de base de datos en un servidor</span><span class="sxs-lookup"><span data-stu-id="79d0f-132">To create a database assembly on a server</span></span>  
  
1.  <span data-ttu-id="79d0f-133">Expanda la instancia [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de la base de datos en explorador de objetos, haga clic con el botón secundario en la carpeta **ensamblados** y, a continuación, haga clic en **nuevo ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="79d0f-133">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly**.</span></span> <span data-ttu-id="79d0f-134">Esto muestra el cuadro de diálogo **registrar ensamblado de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="79d0f-134">This displays the **Register Database Assembly** dialog box.</span></span>  
  
2.  <span data-ttu-id="79d0f-135">En **tipo** , especifique el tipo de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="79d0f-135">For **Type** specify the type of assembly:</span></span>  
  
    -   <span data-ttu-id="79d0f-136">Para una DLL de código administrado (CLR), especifique Ensamblado .NET.</span><span class="sxs-lookup"><span data-stu-id="79d0f-136">For a managed code (CLR) DLL, specify .NET Assembly.</span></span>  
  
    -   <span data-ttu-id="79d0f-137">Para una DLL de código nativo (COM), especifique DLL COM.</span><span class="sxs-lookup"><span data-stu-id="79d0f-137">For a native code (COM) DLL), specify COM DLL.</span></span>  
  
3.  <span data-ttu-id="79d0f-138">En **nombre de archivo**, especifique el archivo DLL que contiene los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="79d0f-138">For **File name**, specify the DLL containing the stored procedures.</span></span>  
  
4.  <span data-ttu-id="79d0f-139">En **nombre de ensamblado**, especifique un nombre para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="79d0f-139">For **Assembly name**, specify a name for the assembly.</span></span>  
  
5.  <span data-ttu-id="79d0f-140">Si se trata de una compilación de depuración de la biblioteca que va a usar para depurar procedimientos almacenados, active la casilla **incluir información de depuración** .</span><span class="sxs-lookup"><span data-stu-id="79d0f-140">If this is a debug build of the library that you are going to use to debug stored procedures, select the **Include debug information** check box.</span></span> <span data-ttu-id="79d0f-141">Para obtener más información sobre la depuración de procedimientos almacenados, vea [depurar procedimientos almacenados](debugging-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="79d0f-141">For more information about debugging stored procedures, see [Debugging Stored Procedures](debugging-stored-procedures.md).</span></span>  
  
6.  <span data-ttu-id="79d0f-142">Puede hacer clic en **Aceptar** para registrar el ensamblado inmediatamente, o bien, en la barra de herramientas del cuadro de diálogo, puede hacer clic en un comando del menú **script** para incluir en el script la acción de registro en una ventana de consulta, un archivo o el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="79d0f-142">You can click **OK** to register the assembly immediately, or on the dialog box toolbar, you can click a command on the **Script** menu to script the registration action to a query window, a file, or the Clipboard.</span></span>  
  
 <span data-ttu-id="79d0f-143">Después de registrar un ensamblado de base de datos, puede configurarlo haciendo clic con el botón secundario en el ensamblado en Explorador de objetos y, a continuación, haciendo clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="79d0f-143">After you register a database assembly, you can configure it by right-clicking the assembly in Object Explorer and then clicking **Properties**.</span></span>  
  
## <a name="registering-a-database-assembly-in-a-project"></a><span data-ttu-id="79d0f-144">Registrar un ensamblado de base de datos en un proyecto</span><span class="sxs-lookup"><span data-stu-id="79d0f-144">Registering a Database Assembly in a Project</span></span>  
 <span data-ttu-id="79d0f-145">En el Explorador de soluciones de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], los ensamblados de base de datos aparecen en la carpeta Ensamblados bajo un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79d0f-145">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], database assemblies are listed in the Assemblies folder under an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="79d0f-146">Los ensamblados de base de datos pueden contener ensamblados .NET (CLR) y bibliotecas COM.</span><span class="sxs-lookup"><span data-stu-id="79d0f-146">Database assemblies can contain both .NET (CLR) assemblies and COM libraries.</span></span>  
  
### <a name="to-create-a-database-assembly-in-an-analysis-service-project"></a><span data-ttu-id="79d0f-147">Para crear un ensamblado de base de datos en un proyecto de Analysis Service</span><span class="sxs-lookup"><span data-stu-id="79d0f-147">To create a database assembly in an Analysis Service project</span></span>  
  
1.  <span data-ttu-id="79d0f-148">Expanda la instancia [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de la base de datos en explorador de objetos, haga clic con el botón secundario en la carpeta **ensamblados** y haga clic en **nueva referencia de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="79d0f-148">Expand the instance the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in Object Explorer, right-click the **Assemblies** folder, and then click **New Assembly Reference**.</span></span> <span data-ttu-id="79d0f-149">Esto muestra el cuadro de diálogo **Agregar referencia** .</span><span class="sxs-lookup"><span data-stu-id="79d0f-149">This displays the **Add Reference** dialog box.</span></span> <span data-ttu-id="79d0f-150">En la pestaña **.net** del cuadro de diálogo **Agregar referencia se** enumeran los ensamblados .net (CLR) existentes, mientras que la pestaña **proyectos** enumera los proyectos.</span><span class="sxs-lookup"><span data-stu-id="79d0f-150">The **.NET** tab of the **Add Reference** dialog box lists existing .NET (CLR) assemblies, while the **Projects** tab lists projects.</span></span>  
  
2.  <span data-ttu-id="79d0f-151">Puede hacer clic en un componente o proyecto existente y, a continuación, hacer clic en **Agregar** para agregarlo al [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="79d0f-151">You can click an existing component or project and then click **Add** to add it to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="79d0f-152">Para agregar una referencia a una DLL COM, haga clic en la pestaña **examinar** para buscar el archivo.</span><span class="sxs-lookup"><span data-stu-id="79d0f-152">To add a reference to a COM DLL, click the **Browse** tab to find the file.</span></span> <span data-ttu-id="79d0f-153">La lista **proyectos y componentes seleccionados** muestra el nombre, el tipo, la versión y la ubicación de cada componente que se va a agregar al proyecto.</span><span class="sxs-lookup"><span data-stu-id="79d0f-153">The **Selected projects and components** list shows the name, type, version, and location for each component that you are adding to the project.</span></span>  
  
3.  <span data-ttu-id="79d0f-154">Cuando haya terminado de seleccionar los componentes que desea agregar, haga clic en **Aceptar** para agregarlos al [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="79d0f-154">When you are finished selecting components to add, click **OK** to add them to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
## <a name="script-format-for-an-assembly"></a><span data-ttu-id="79d0f-155">Formato de script para un ensamblado</span><span class="sxs-lookup"><span data-stu-id="79d0f-155">Script Format For an Assembly</span></span>  
 <span data-ttu-id="79d0f-156">Registrar un ensamblado .NET es bastante sencillo.</span><span class="sxs-lookup"><span data-stu-id="79d0f-156">Registering a .NET assembly is fairly simple.</span></span> <span data-ttu-id="79d0f-157">Un ensamblado .NET se agrega a una base de datos en formato binario con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="79d0f-157">A .NET assembly is added to a database in binary format using the following format:</span></span>  
  
```  
<Create>  
   <ObjectDefinition>  
      <Assembly>  
         <Files>  
            <File>  
               <Name>filename</Name>  
               <Type>filetype</Type>  
               <Data>  
                  <Block>binarydatablock</Block>  
                  <Block>binarydatablock</Block>  
                  ...  
               </Data>  
            </File>  
         </Files>  
         <PermissionSet>PermissionSet</PermissionSet>  
      </Assembly>  
   <ObjectDefinition>  
</Create>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79d0f-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79d0f-158">See Also</span></span>  
 <span data-ttu-id="79d0f-159">[Administración de ensamblados de modelos multidimensionales](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="79d0f-159">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="79d0f-160">Definir procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="79d0f-160">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
