---
title: Crear un proveedor de registro personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom log providers [Integration Services], creating
ms.assetid: fc20af96-9eb8-4195-8d3f-8a4d7c753f24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1efb736aece2cc8d118c81326989559f0d17a60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746328"
---
# <a name="creating-a-custom-log-provider"></a><span data-ttu-id="8867b-102">Crear un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="8867b-102">Creating a Custom Log Provider</span></span>
  <span data-ttu-id="8867b-103">El entorno en tiempo de ejecución de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] incluye amplias funciones de registro.</span><span class="sxs-lookup"><span data-stu-id="8867b-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time environment has extensive logging capabilities.</span></span> <span data-ttu-id="8867b-104">Un registro permite capturar eventos que se generan durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="8867b-104">A log lets you capture events that occur during package execution.</span></span> [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="8867b-105">incluye varios proveedores de registro que permiten crear registros y almacenarlos en diversos formatos como XML, texto, base de datos o en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="8867b-105">includes a variety of log providers that enable logs to be created and stored in multiple formats, such as XML, text, database, or in the Windows event log.</span></span> <span data-ttu-id="8867b-106">Si uno de estos proveedores o formatos de salida no se ajusta sus necesidades, puede crear un proveedor de registro personalizado.</span><span class="sxs-lookup"><span data-stu-id="8867b-106">If one of these providers or output formats does not fit your needs, you can create a custom log provider.</span></span>

 <span data-ttu-id="8867b-107">Los pasos necesarios para crear un proveedor de registro personalizado son similares a los pasos para crear cualquier otro objeto personalizado para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8867b-107">The steps involved in creating a custom log provider are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>

-   <span data-ttu-id="8867b-108">Cree una clase nueva que herede de la clase base.</span><span class="sxs-lookup"><span data-stu-id="8867b-108">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="8867b-109">Para un proveedor de registro, la clase base es <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>.</span><span class="sxs-lookup"><span data-stu-id="8867b-109">For a log provider, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>.</span></span>

-   <span data-ttu-id="8867b-110">Aplique el atributo que identifica el tipo de objeto para la clase.</span><span class="sxs-lookup"><span data-stu-id="8867b-110">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="8867b-111">Para un proveedor de registro, el atributo es <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8867b-111">For a log provider, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>.</span></span>

-   <span data-ttu-id="8867b-112">Invalide la implementación de los métodos y las propiedades de la clase base.</span><span class="sxs-lookup"><span data-stu-id="8867b-112">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="8867b-113">Para un proveedor de registro, estos incluyen la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, los métodos <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="8867b-113">For a log provider, these include the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> methods.</span></span>

-   <span data-ttu-id="8867b-114">Las interfaces de usuario personalizadas para los proveedores de registro personalizados no están implementadas en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8867b-114">Custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

## <a name="getting-started-with-a-custom-log-provider"></a><span data-ttu-id="8867b-115">Introducción a un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="8867b-115">Getting Started with a Custom Log Provider</span></span>

### <a name="creating-projects-and-classes"></a><span data-ttu-id="8867b-116">Crear proyectos y clases</span><span class="sxs-lookup"><span data-stu-id="8867b-116">Creating Projects and Classes</span></span>
 <span data-ttu-id="8867b-117">Dado que todos los proveedores de registro administrados se derivan de la clase base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, el primer paso para crear un proveedor de registro personalizado consiste en crear un proyecto de bibliotecas de clases en el lenguaje de programación administrado que prefiera y, a continuación, crear una clase que herede de la clase base.</span><span class="sxs-lookup"><span data-stu-id="8867b-117">Because all managed log providers derive from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, the first step when you create a custom log provider is to create a class library project in your preferred managed programming language, and then create a class that inherits from the base class.</span></span> <span data-ttu-id="8867b-118">En esta clase derivada se invalidarán los métodos y las propiedades de la clase base para implementar la funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="8867b-118">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>

 <span data-ttu-id="8867b-119">Configure el proyecto para firmar el ensamblado que se generará con un archivo de claves del nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="8867b-119">Configure the project to sign the assembly that will be generated with a strong name key file.</span></span>

> [!NOTE]
>  <span data-ttu-id="8867b-120">Muchos proveedores de registro de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] tienen una interfaz de usuario personalizada que implementa <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> y reemplaza el cuadro de texto **Configuración** en el cuadro de diálogo **Configurar registros de SSIS** por una lista desplegable filtrada de administradores de conexiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="8867b-120">Many [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] log providers have a custom user interface that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> and replaces the **Configuration** text box in the **Configure SSIS Logs** dialog box with a filtered dropdown list of available connection managers.</span></span> <span data-ttu-id="8867b-121">Sin embargo, las interfaces de usuario personalizadas para los proveedores de registro personalizados no se implementan en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8867b-121">However custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

### <a name="applying-the-dtslogprovider-attribute"></a><span data-ttu-id="8867b-122">Aplicar el atributo DtsLogProvider</span><span class="sxs-lookup"><span data-stu-id="8867b-122">Applying the DtsLogProvider Attribute</span></span>
 <span data-ttu-id="8867b-123">Aplique el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> a la clase que ha creado para identificarlo como un proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="8867b-123">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to the class that you have created to identify it as a log provider.</span></span> <span data-ttu-id="8867b-124">Este atributo proporciona información en tiempo de diseño, como el nombre y la descripción del proveedor de registro.</span><span class="sxs-lookup"><span data-stu-id="8867b-124">This attribute provides design-time information such as the name and description of the log provider.</span></span> <span data-ttu-id="8867b-125">Las `DisplayName` `Description` propiedades y del atributo corresponden al **nombre** y `Description` las columnas que se muestran en el editor **configurar registros de SSIS** , que se muestra al configurar el registro para un paquete en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8867b-125">The `DisplayName` and `Description` properties of the attribute correspond to the **Name** and `Description` columns displayed in the **Configure SSIS Logs** editor, which is displayed when configuring logging for a package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="8867b-126">La propiedad <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.LogProviderType%2A> del atributo no se usa.</span><span class="sxs-lookup"><span data-stu-id="8867b-126">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.LogProviderType%2A> property of the attribute is not used.</span></span> <span data-ttu-id="8867b-127">Sin embargo, debe especificar un valor para la propiedad o el proveedor de registro personalizado no aparecerá en la lista de proveedores de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="8867b-127">However, you must enter a value for it, or the custom log provider will not appear in the list of available log providers.</span></span>

> [!NOTE]
>  <span data-ttu-id="8867b-128">Desde que las interfaces de usuario personalizadas para los proveedores de registro personalizados no se implementa en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], especificar un valor para la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.UITypeName%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="8867b-128">Since custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], specifying a value for the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> has no effect.</span></span>

```vb
<DtsLogProvider(DisplayName:="MyLogProvider", Description:="A simple log provider.", LogProviderType:="Custom")> _
Public Class MyLogProvider
     Inherits LogProviderBase
    ' TODO: Override the base class methods.
End Class
```

```csharp
[DtsLogProvider(DisplayName="MyLogProvider", Description="A simple log provider.", LogProviderType="Custom")]
public class MyLogProvider : LogProviderBase
{
    // TODO: Override the base class methods.
}
```

## <a name="building-deploying-and-debugging-a-custom-log-provider"></a><span data-ttu-id="8867b-129">Generar, implementar y depurar un proveedor de registro personalizado</span><span class="sxs-lookup"><span data-stu-id="8867b-129">Building, Deploying, and Debugging a Custom Log Provider</span></span>
 <span data-ttu-id="8867b-130">Los pasos para generar, implementar y depurar un proveedor de registro personalizado en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] son muy similares a los pasos requeridos para otros tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="8867b-130">The steps for building, deploying, and debugging a custom log provider in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are very similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="8867b-131">Para obtener más información, consulte [Generar, implementar y depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="8867b-131">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>

<span data-ttu-id="8867b-132">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8867b-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8867b-133">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="8867b-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8867b-134">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="8867b-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8867b-135">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="8867b-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="8867b-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8867b-136">See Also</span></span>
 <span data-ttu-id="8867b-137">[Codificar un proveedor de registro personalizado](coding-a-custom-log-provider.md) [desarrollar una interfaz de usuario para un proveedor de registro personalizado](developing-a-user-interface-for-a-custom-log-provider.md)</span><span class="sxs-lookup"><span data-stu-id="8867b-137">[Coding a Custom Log Provider](coding-a-custom-log-provider.md) [Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md)</span></span>


