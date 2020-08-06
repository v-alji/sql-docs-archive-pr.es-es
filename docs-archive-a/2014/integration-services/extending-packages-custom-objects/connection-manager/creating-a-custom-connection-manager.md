---
title: Crear un administrador de conexiones personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], creating
ms.assetid: e83f8e02-ace4-42e0-b979-2f6be1460985
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857efebbe311e5510e15cae9e78a2b424559ded7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751313"
---
# <a name="creating-a-custom-connection-manager"></a><span data-ttu-id="05886-102">Crear un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="05886-102">Creating a Custom Connection Manager</span></span>
  <span data-ttu-id="05886-103">Los pasos que debe seguir para crear un administrador de conexiones personalizado son similares a los pasos necesarios para crear cualquier otro objeto personalizado para [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="05886-103">The steps that you must follow to create a custom connection manager are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="05886-104">Cree una clase nueva que herede de la clase base.</span><span class="sxs-lookup"><span data-stu-id="05886-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="05886-105">Para un administrador de conexiones, la clase base es <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="05886-105">For a connection manager, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span></span>  
  
-   <span data-ttu-id="05886-106">Aplique el atributo que identifica el tipo de objeto para la clase.</span><span class="sxs-lookup"><span data-stu-id="05886-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="05886-107">Para un administrador de conexiones, el atributo es <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="05886-107">For a connection manager, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span></span>  
  
-   <span data-ttu-id="05886-108">Invalide la implementación de los métodos y las propiedades de la clase base.</span><span class="sxs-lookup"><span data-stu-id="05886-108">Override the implementation of the methods and properties of the base class.</span></span> <span data-ttu-id="05886-109">Para un administrador de conexiones, estos incluyen la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> y los métodos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="05886-109">For a connection manager, these include the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods.</span></span>  
  
-   <span data-ttu-id="05886-110">Si lo desea, desarrolle una interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="05886-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="05886-111">Para un administrador de conexiones, esto requiere una clase que implemente la interfaz <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>.</span><span class="sxs-lookup"><span data-stu-id="05886-111">For a connection manager, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05886-112">Muchas de las tareas, orígenes y destinos que se han incluido en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] se usan únicamente con tipos específicos de administradores de conexiones integrados.</span><span class="sxs-lookup"><span data-stu-id="05886-112">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="05886-113">Por consiguiente, estos ejemplos no se pueden probar con las tareas y componentes integrados.</span><span class="sxs-lookup"><span data-stu-id="05886-113">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="getting-started-with-a-custom-connection-manager"></a><span data-ttu-id="05886-114">Introducción a un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="05886-114">Getting Started with a Custom Connection Manager</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="05886-115">Crear proyectos y clases</span><span class="sxs-lookup"><span data-stu-id="05886-115">Creating Projects and Classes</span></span>  
 <span data-ttu-id="05886-116">Dado que todos los administradores de conexiones administrados se derivan de la clase base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, el primer paso para crear un administrador de conexiones personalizado consiste en crear un proyecto de bibliotecas de clases en el lenguaje de programación administrado que prefiera y, a continuación, crear una clase que herede de la clase base.</span><span class="sxs-lookup"><span data-stu-id="05886-116">Because all managed connection managers derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, the first step when you create a custom connection manager is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="05886-117">En esta clase derivada se invalidarán los métodos y las propiedades de la clase base para implementar la funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="05886-117">In this derived class, you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="05886-118">En la misma solución, cree un segundo proyecto de bibliotecas de clases para la interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="05886-118">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="05886-119">Se recomienda usar un ensamblado independiente para la interfaz de usuario a fin de facilitar la implementación, ya que le permite actualizar y volver a implementar la tarea o su interfaz de usuario de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="05886-119">A separate assembly for the user interface is recommended for ease of deployment because it lets you update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="05886-120">Configure ambos proyectos para firmar los ensamblados que se generarán en tiempo de compilación mediante un archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="05886-120">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsconnection-attribute"></a><span data-ttu-id="05886-121">Aplicar el atributo DtsConnection</span><span class="sxs-lookup"><span data-stu-id="05886-121">Applying the DtsConnection Attribute</span></span>  
 <span data-ttu-id="05886-122">Aplique el atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> a la clase que ha creado para identificarlo como un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="05886-122">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class that you have created to identify it as a connection manager.</span></span> <span data-ttu-id="05886-123">Este atributo proporciona información en tiempo de diseño, como el nombre, la descripción y el tipo de conexión del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="05886-123">This attribute provides design-time information such as the name, description, and connection type of the connection manager.</span></span> <span data-ttu-id="05886-124">Las <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> `Description` propiedades y se corresponden con el **tipo** y `Description` las columnas que se muestran en el cuadro de diálogo **Agregar administrador de conexiones SSIS** , que se muestra al configurar las conexiones para un paquete en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="05886-124">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> and `Description` properties correspond to the **Type** and `Description` columns displayed in the **Add SSIS Connection Manager** dialog box, which is displayed when configuring connections for a package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="05886-125">Use la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> para vincular el administrador de conexiones a su interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="05886-125">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> property to link the connection manager to its custom user interface.</span></span> <span data-ttu-id="05886-126">Para obtener el token de clave pública necesario para esta propiedad, puede usar **sn.exe -t** con el fin de mostrar el token de clave pública del archivo de pares de claves (.snk) que quiere usar para firmar el ensamblado de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="05886-126">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
<DtsConnection(ConnectionType:="SQLVB", _  
  DisplayName:="SqlConnectionManager (VB)", _  
  Description:="Connection manager for Sql Server", _  
  UITypeName:="SqlConnMgrUIVB.SqlConnMgrUIVB,SqlConnMgrUIVB,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")> _  
Public Class SqlConnMgrVB  
  Inherits ConnectionManagerBase  
  . . .  
End Class  
```  
  
```csharp  
[DtsConnection(ConnectionType = "SQLCS",  
  DisplayName = "SqlConnectionManager (CS)",  
  Description = "Connection manager for Sql Server",  
  UITypeName = "SqlConnMgrUICS.SqlConnMgrUICS,SqlConnMgrUICS,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")]  
public class SqlConnMgrCS :  
ConnectionManagerBase  
{  
  . . .  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-connection-manager"></a><span data-ttu-id="05886-127">Generar, implementar y depurar un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="05886-127">Building, Deploying, and Debugging a Custom Connection Manager</span></span>  
 <span data-ttu-id="05886-128">Los pasos para generar, implementar y depurar un administrador de conexiones personalizado en [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] son similares a los pasos necesarios en otros tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="05886-128">The steps for building, deploying, and debugging a custom connection manager in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps for other types of custom objects.</span></span> <span data-ttu-id="05886-129">Para obtener más información, consulte [Generar, implementar y depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="05886-129">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="05886-130">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="05886-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="05886-131">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="05886-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="05886-132">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="05886-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="05886-133">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="05886-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05886-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05886-134">See Also</span></span>  
 <span data-ttu-id="05886-135">[Codificar un administrador de conexiones personalizado](coding-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="05886-135">[Coding a Custom Connection Manager](coding-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="05886-136">Desarrollar una interfaz de usuario para un administrador de conexiones personalizado</span><span class="sxs-lookup"><span data-stu-id="05886-136">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
