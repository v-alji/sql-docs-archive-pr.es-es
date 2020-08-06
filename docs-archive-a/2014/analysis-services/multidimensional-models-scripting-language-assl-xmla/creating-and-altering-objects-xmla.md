---
title: Crear y modificar objetos (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [XML for Analysis]
- subordinate objects [XML for Analysis]
- XML for Analysis, objects
- modifying objects
- removing objects
- deleting objects
- XMLA, objects
ms.assetid: a2080867-e130-440c-92eb-f768869f34a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2390c0b921368e7e06f0e5563a7eb59769d99c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676231"
---
# <a name="creating-and-altering-objects-xmla"></a><span data-ttu-id="1d4ad-102">Crear y modificar objetos (XMLA)</span><span class="sxs-lookup"><span data-stu-id="1d4ad-102">Creating and Altering Objects (XMLA)</span></span>
  <span data-ttu-id="1d4ad-103">Los objetos principales se pueden crear, modificar y eliminar de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-103">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="1d4ad-104">Entre los objetos principales se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d4ad-104">Major objects include the following objects:</span></span>  
  
-   <span data-ttu-id="1d4ad-105">Servidores</span><span class="sxs-lookup"><span data-stu-id="1d4ad-105">Servers</span></span>  
  
-   <span data-ttu-id="1d4ad-106">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="1d4ad-106">Databases</span></span>  
  
-   <span data-ttu-id="1d4ad-107">Dimensions</span><span class="sxs-lookup"><span data-stu-id="1d4ad-107">Dimensions</span></span>  
  
-   <span data-ttu-id="1d4ad-108">Cubos</span><span class="sxs-lookup"><span data-stu-id="1d4ad-108">Cubes</span></span>  
  
-   <span data-ttu-id="1d4ad-109">Grupos de medida</span><span class="sxs-lookup"><span data-stu-id="1d4ad-109">Measure groups</span></span>  
  
-   <span data-ttu-id="1d4ad-110">Particiones</span><span class="sxs-lookup"><span data-stu-id="1d4ad-110">Partitions</span></span>  
  
-   <span data-ttu-id="1d4ad-111">Perspectivas</span><span class="sxs-lookup"><span data-stu-id="1d4ad-111">Perspectives</span></span>  
  
-   <span data-ttu-id="1d4ad-112">Modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1d4ad-112">Mining models</span></span>  
  
-   <span data-ttu-id="1d4ad-113">Roles</span><span class="sxs-lookup"><span data-stu-id="1d4ad-113">Roles</span></span>  
  
-   <span data-ttu-id="1d4ad-114">Comandos asociados a un servidor o base de datos</span><span class="sxs-lookup"><span data-stu-id="1d4ad-114">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="1d4ad-115">Orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="1d4ad-115">Data sources</span></span>  
  
 <span data-ttu-id="1d4ad-116">Use el comando [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) para crear un objeto principal en una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y el comando [ALTER](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) para modificar un objeto principal existente en una instancia de.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-116">You use the [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) command to create a major object on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], and the [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) command to alter an existing major object on an instance.</span></span> <span data-ttu-id="1d4ad-117">Ambos comandos se ejecutan mediante el método [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="1d4ad-117">Both commands are run using the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="1d4ad-118">Crear objetos</span><span class="sxs-lookup"><span data-stu-id="1d4ad-118">Creating Objects</span></span>  
 <span data-ttu-id="1d4ad-119">Al crear objetos mediante el método `Create`, primero debe identificar el objeto primario que contiene el objeto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-119">When you create objects by using the `Create` method, you must first identify the parent object that contains the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object to be created.</span></span> <span data-ttu-id="1d4ad-120">Para identificar el objeto primario, proporcione una referencia de objeto en la propiedad [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `Create` comando.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-120">You identify the parent object by providing an object reference in the [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Create` command.</span></span> <span data-ttu-id="1d4ad-121">Cada referencia de objeto contiene los identificadores de objeto necesarios para identificar de forma exclusiva el objeto primario para el comando `Create`.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-121">Each object reference contains the object identifiers needed to uniquely identify the parent object for the `Create` command.</span></span> <span data-ttu-id="1d4ad-122">Para obtener más información acerca de las referencias a objetos, vea [definir e identificar objetos &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="1d4ad-122">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="1d4ad-123">Por ejemplo, debe proporcionar una referencia de objeto a un cubo para crear un nuevo grupo de medida para el cubo.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-123">For example, you must provide an object reference to a cube to create a new measure group for the cube.</span></span> <span data-ttu-id="1d4ad-124">La referencia de objeto para el cubo en la propiedad `ParentObject` contiene un identificador de base de datos y un identificador de cubo, ya que es posible que se utilice el mismo identificador de cubo en otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-124">The object reference for the cube in the `ParentObject` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="1d4ad-125">El elemento [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) contiene elementos del lenguaje de scripting de Analysis Services (ASSL) que definen el objeto principal que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-125">The [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) element contains Analysis Services Scripting Language (ASSL) elements that define the major object to be created.</span></span> <span data-ttu-id="1d4ad-126">Para obtener más información sobre ASSL, vea [desarrollar con Analysis Services lenguaje de scripting &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="1d4ad-126">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="1d4ad-127">Si establece el atributo `AllowOverwrite` del comando `Create` en true, puede sobrescribir un objeto principal existente que tenga el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-127">If you set the `AllowOverwrite` attribute of the `Create` command to true, you can overwrite an existing major object that has the specified identifier.</span></span> <span data-ttu-id="1d4ad-128">De lo contrario, si ya existe un objeto principal con el identificador especificado en el objeto primario, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-128">Otherwise, an error occurs if a major object that has the specified identifier already exists in the parent object.</span></span>  
  
 <span data-ttu-id="1d4ad-129">Para obtener más información sobre el `Create` comando, vea [Create Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="1d4ad-129">For more information about the `Create` command, see [Create Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span></span>  
  
### <a name="creating-session-objects"></a><span data-ttu-id="1d4ad-130">Crear objetos de sesión</span><span class="sxs-lookup"><span data-stu-id="1d4ad-130">Creating Session Objects</span></span>  
 <span data-ttu-id="1d4ad-131">Los objetos de sesión son objetos temporales que solo están disponibles para la sesión explícita o implícita utilizada por una aplicación cliente y que se eliminan cuando finaliza la sesión.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-131">Session objects are temporary objects that are available only to the explicit or implicit session used by a client application and are deleted when the session is ended.</span></span> <span data-ttu-id="1d4ad-132">Puede crear objetos de sesión estableciendo el `Scope` atributo del `Create` comando en *Session*.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-132">You can create session objects by setting the `Scope` attribute of the `Create` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d4ad-133">Cuando se usa la configuración de *sesión* , el `ObjectDefinition` elemento solo puede contener elementos ASSL de [dimensión](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [cubo](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)o [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) .</span><span class="sxs-lookup"><span data-stu-id="1d4ad-133">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="altering-objects"></a><span data-ttu-id="1d4ad-134">Modificar objetos</span><span class="sxs-lookup"><span data-stu-id="1d4ad-134">Altering Objects</span></span>  
 <span data-ttu-id="1d4ad-135">Al modificar objetos mediante el `Alter` método, primero debe identificar el objeto que se va a modificar proporcionando una referencia de objeto en la propiedad de [objeto](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `Alter` comando.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-135">When modifying objects by using the `Alter` method, you must first identify the object to be modified by providing an object reference in the [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Alter` command.</span></span> <span data-ttu-id="1d4ad-136">Cada referencia de objeto contiene los identificadores de objeto necesarios para identificar de forma exclusiva el objeto para el comando `Alter`.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-136">Each object reference contains the object identifiers needed to uniquely identify the object for the `Alter` command.</span></span> <span data-ttu-id="1d4ad-137">Para obtener más información acerca de las referencias a objetos, vea [definir e identificar objetos &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="1d4ad-137">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="1d4ad-138">Por ejemplo, debe proporcionar una referencia de objeto a un cubo para modificar la estructura de un cubo.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-138">For example, you must provide an object reference to a cube in order to modify the structure of a cube.</span></span> <span data-ttu-id="1d4ad-139">La referencia de objeto para el cubo en la propiedad `Object` contiene un identificador de base de datos y un identificador de cubo, ya que es posible que se utilice el mismo identificador de cubo en otra base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-139">The object reference for the cube in the `Object` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="1d4ad-140">El elemento `ObjectDefinition` contiene elementos ASSL que definen el objeto principal que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-140">The `ObjectDefinition` element contains ASSL elements that define the major object to be modified.</span></span> <span data-ttu-id="1d4ad-141">Para obtener más información sobre ASSL, vea [desarrollar con Analysis Services lenguaje de scripting &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="1d4ad-141">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="1d4ad-142">Si establece el atributo `AllowCreate` del comando `Alter` en true, puede crear el objeto principal especificado si éste no existe.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-142">If you set the `AllowCreate` attribute of the `Alter` command to true, you can create the specified major object if the object does not exist.</span></span> <span data-ttu-id="1d4ad-143">De lo contrario, si un objeto principal especificado no existe aún, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-143">Otherwise, an error occurs if a specified major object does not already exist.</span></span>  
  
### <a name="using-the-objectexpansion-attribute"></a><span data-ttu-id="1d4ad-144">Utilizar el atributo ObjectExpansion</span><span class="sxs-lookup"><span data-stu-id="1d4ad-144">Using the ObjectExpansion Attribute</span></span>  
 <span data-ttu-id="1d4ad-145">Si solo va a cambiar las propiedades del objeto principal y no está redefiniendo los objetos secundarios contenidos en el objeto principal, puede establecer el `ObjectExpansion` atributo del `Alter` comando en *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-145">If you are changing only the properties of the major object and are not redefining minor objects that are contained by the major object, you can set the `ObjectExpansion` attribute of the `Alter` command to *ObjectProperties*.</span></span> <span data-ttu-id="1d4ad-146">De este modo, la propiedad `ObjectDefinition` solo debe contener los elementos para las propiedades del objeto principal y el comando `Alter` conserva intactos los objetos secundarios asociados al objeto principal.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-146">The `ObjectDefinition` property then only has to contain the elements for the properties of the major object, and the `Alter` command leaves minor objects associated with the major object untouched.</span></span>  
  
 <span data-ttu-id="1d4ad-147">Para volver a definir los objetos secundarios de un objeto principal, debe establecer el `ObjectExpansion` atributo en *ExpandFull* y la definición del objeto debe incluir todos los objetos secundarios contenidos en el objeto principal.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-147">To redefine minor objects for a major object, you must set the `ObjectExpansion` attribute to *ExpandFull* and the object definition must include all minor objects that are contained by the major object.</span></span> <span data-ttu-id="1d4ad-148">Si la propiedad `ObjectDefinition` del comando `Alter` no incluye de forma explícita un objeto secundario contenido en el objeto principal, se elimina el objeto secundario no incluido.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-148">If the `ObjectDefinition` property of the `Alter` command does not explicitly include a minor object that is contained by the major object, the minor object that was not included is deleted.</span></span>  
  
### <a name="altering-session-objects"></a><span data-ttu-id="1d4ad-149">Modificar objetos de sesión</span><span class="sxs-lookup"><span data-stu-id="1d4ad-149">Altering Session Objects</span></span>  
 <span data-ttu-id="1d4ad-150">Para modificar los objetos de sesión creados por el `Create` comando, establezca el `Scope` atributo del `Alter` comando en *Session*.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-150">To modify session objects created by the `Create` command, set the `Scope` attribute of the `Alter` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d4ad-151">Cuando se usa la configuración de *sesión* , el `ObjectDefinition` elemento solo puede contener elementos ASSL de [dimensión](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [cubo](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)o [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) .</span><span class="sxs-lookup"><span data-stu-id="1d4ad-151">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="creating-or-altering-subordinate-objects"></a><span data-ttu-id="1d4ad-152">Crear o modificar objetos subordinados</span><span class="sxs-lookup"><span data-stu-id="1d4ad-152">Creating or Altering Subordinate Objects</span></span>  
 <span data-ttu-id="1d4ad-153">Aunque los comandos `Create` o `Alter` crean o modifican solamente un objeto principal de nivel superior, el objeto principal que se crea o modifica puede contener definiciones para otros objetos principales y secundarios subordinados a éste dentro de la propiedad `ObjectDefinition` envolvente.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-153">Although a `Create` or `Alter` command creates or alters only one topmost major object, the major object being created or modified can contain definitions within the enclosing `ObjectDefinition` property for other major and minor objects that are subordinate to it.</span></span> <span data-ttu-id="1d4ad-154">Por ejemplo, si define un cubo, la base de datos primaria se especifica en `ParentObject` y, dentro de la definición del cubo en `ObjectDefinition`, puede definir grupos de medida para éste; a su vez, dentro de los grupos de medida, puede definir particiones para cada grupo de este tipo.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-154">For example, if you define a cube, you specify the parent database in `ParentObject`, and within the cube definition in `ObjectDefinition` you can define measure groups for the cube, and within the measure groups you can define partitions for each measure group.</span></span> <span data-ttu-id="1d4ad-155">Un objeto secundario solamente se puede definir bajo el objeto principal que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-155">A minor object can be defined only under the major object that contains it.</span></span> <span data-ttu-id="1d4ad-156">Para obtener más información sobre los objetos principales y secundarios, vea [objetos de base de datos &#40;Analysis Services-&#41;de datos multidimensionales ](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="1d4ad-156">For more information about major and minor objects, see [Database Objects &#40;Analysis Services - Multidimensional Data&#41;](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1d4ad-157">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1d4ad-157">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="1d4ad-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d4ad-158">Description</span></span>  
 <span data-ttu-id="1d4ad-159">En el ejemplo siguiente se crea un origen de datos relacional que hace referencia a la base de datos de [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] ejemplo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d4ad-159">The following example creates a relational data source that references the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1d4ad-160">Código</span><span class="sxs-lookup"><span data-stu-id="1d4ad-160">Code</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    </ParentObject>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ImpersonationInfo>  
                <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
            </ImpersonationInfo>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT0S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Create>  
```  
  
### <a name="description"></a><span data-ttu-id="1d4ad-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d4ad-161">Description</span></span>  
 <span data-ttu-id="1d4ad-162">En el ejemplo siguiente se modifica el origen de datos relacional creado en el ejemplo anterior para establecer en 30 segundos el tiempo de espera de consulta para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-162">The following example alters the relational data source created in the previous example to set the query time-out for the data source to 30 seconds.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1d4ad-163">Código</span><span class="sxs-lookup"><span data-stu-id="1d4ad-163">Code</span></span>  
  
```  
<Alter ObjectExpansion="ObjectProperties" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DataSourceID>AdventureWorksDW2012</DataSourceID>  
    </Object>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=fr-dwk-02;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT30S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Alter>  
```  
  
### <a name="comments"></a><span data-ttu-id="1d4ad-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1d4ad-164">Comments</span></span>  
 <span data-ttu-id="1d4ad-165">El `ObjectExpansion` atributo del `Alter` comando se estableció en *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-165">The `ObjectExpansion` attribute of the `Alter` command was set to *ObjectProperties*.</span></span> <span data-ttu-id="1d4ad-166">Esta configuración permite excluir el elemento [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) , un objeto secundario, del origen de datos definido en `ObjectDefinition` .</span><span class="sxs-lookup"><span data-stu-id="1d4ad-166">This setting allows the [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) element, a minor object, to be excluded from the data source defined in `ObjectDefinition`.</span></span> <span data-ttu-id="1d4ad-167">Por lo tanto, la información de suplantación de ese origen de datos permanece activa en la cuenta de servicio, como se especifica en el primer ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1d4ad-167">Therefore, the impersonation information for that data source remains set to the service account, as specified in the first example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d4ad-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d4ad-168">See Also</span></span>  
 <span data-ttu-id="1d4ad-169">[Método Execute &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span><span class="sxs-lookup"><span data-stu-id="1d4ad-169">[Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span></span>  
 <span data-ttu-id="1d4ad-170">[Desarrollo con Analysis Services lenguaje de scripting &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span><span class="sxs-lookup"><span data-stu-id="1d4ad-170">[Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span></span>  
 [<span data-ttu-id="1d4ad-171">Desarrollar con XMLA en Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1d4ad-171">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
