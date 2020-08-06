---
title: Conectar tareas mediante programación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- constraints [Integration Services]
ms.assetid: 23668e88-cef4-4009-a9cf-38e607eab7a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5aeeb70ed5741cc7372fdfc63e637fd53d932f91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671638"
---
# <a name="connecting-tasks-programmatically"></a><span data-ttu-id="5b367-102">Conectar tareas mediante programación</span><span class="sxs-lookup"><span data-stu-id="5b367-102">Connecting Tasks Programmatically</span></span>
  <span data-ttu-id="5b367-103">Una restricción de precedencia, representada en el modelo de objetos por la clase <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, establece el orden en que se ejecutan los objetos <xref:Microsoft.SqlServer.Dts.Runtime.Executable> en un paquete.</span><span class="sxs-lookup"><span data-stu-id="5b367-103">A precedence constraint, represented in the object model by the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> class, establishes the order in which <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects run in a package.</span></span> <span data-ttu-id="5b367-104">La restricción de precedencia permite que la ejecución de los contenedores y las tareas de un paquete dependa del resultado de la ejecución de una tarea o un contenedor anterior.</span><span class="sxs-lookup"><span data-stu-id="5b367-104">The precedence constraint allows the execution of the containers and tasks in a package to be dependent on the result of the execution of a previous task or container.</span></span> <span data-ttu-id="5b367-105">Las restricciones de precedencia se establecen entre pares de objetos <xref:Microsoft.SqlServer.Dts.Runtime.Executable> con una llamada al método <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> de la colección <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> en el objeto contenedor.</span><span class="sxs-lookup"><span data-stu-id="5b367-105">Precedence constraints are established between pairs of <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects by calling the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> collection on the container object.</span></span> <span data-ttu-id="5b367-106">Después de crear una restricción entre dos objetos ejecutables, establece la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> para establecer los criterios de ejecución del segundo ejecutable definido en la restricción.</span><span class="sxs-lookup"><span data-stu-id="5b367-106">After you create a constraint between two executable objects, you set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property to establish the criteria for executing the second executable defined in the constraint.</span></span>  
  
 <span data-ttu-id="5b367-107">Puede utilizar una restricción y una expresión en una restricción de precedencia única, según el valor que especifique para la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A>, tal como se describe en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b367-107">You can use both a constraint and an expression in a single precedence constraint, depending on the value that you specify for the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A> property, as described in the following table:</span></span>  
  
|<span data-ttu-id="5b367-108">Valor de la propiedad EvalOp</span><span class="sxs-lookup"><span data-stu-id="5b367-108">Value of the EvalOp property</span></span>|<span data-ttu-id="5b367-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b367-109">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Constraint>|<span data-ttu-id="5b367-110">Especifica que el resultado de ejecución determina si se ejecutan el contenedor o la tarea restringidos.</span><span class="sxs-lookup"><span data-stu-id="5b367-110">Specifies that the execution outcome determines whether the constrained container or task runs.</span></span> <span data-ttu-id="5b367-111">Establezca la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> en el valor deseado de la enumeración <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="5b367-111">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> to the desired value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Expression>|<span data-ttu-id="5b367-112">Especifica que el valor de una expresión determina si se ejecutan el contenedor o la tarea restringidos.</span><span class="sxs-lookup"><span data-stu-id="5b367-112">Specifies that the value of an expression determines whether the constrained container or task runs.</span></span> <span data-ttu-id="5b367-113">Establezca la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span><span class="sxs-lookup"><span data-stu-id="5b367-113">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionAndConstraint>|<span data-ttu-id="5b367-114">Especifica que se debe producir el resultado de la restricción y que se debe evaluar la expresión para que se ejecuten el contenedor o la tarea restringidos.</span><span class="sxs-lookup"><span data-stu-id="5b367-114">Specifies that the constraint outcome must occur and the expression must evaluate for the constrained container or task to run.</span></span> <span data-ttu-id="5b367-115">Establezca las propiedades <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, y establezca su propiedad <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="5b367-115">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `true`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionOrConstraint>|<span data-ttu-id="5b367-116">Especifica que se debe producir el resultado de la restricción o que se debe evaluar la expresión para que se ejecuten el contenedor o la tarea restringidos.</span><span class="sxs-lookup"><span data-stu-id="5b367-116">Specifies that either the constraint outcome must occur, or the expression must evaluate, for the constrained container or task to run.</span></span> <span data-ttu-id="5b367-117">Establezca las propiedades <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> y <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, y establezca su propiedad <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="5b367-117">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `false`.</span></span>|  
  
 <span data-ttu-id="5b367-118">En el ejemplo de código siguiente se muestra cómo agregar dos tareas a un paquete.</span><span class="sxs-lookup"><span data-stu-id="5b367-118">The following code sample demonstrates adding two tasks to a package.</span></span> <span data-ttu-id="5b367-119">Se crea un objeto <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> entre ellas que evita que se ejecute la segunda tarea hasta que finalice la primera.</span><span class="sxs-lookup"><span data-stu-id="5b367-119">A <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> is created between them that prevents the second task from running until the first task finishes.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
  
      // Add a File System task.  
      Executable eFileTask1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost1 = eFileTask1 as TaskHost;  
  
      // Add a second File System task.  
      Executable eFileTask2 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost2 = eFileTask2 as TaskHost;  
  
      // Put a precedence constraint between the tasks.  
      // Set the constraint to specify that the second File System task cannot run  
      // until the first File System task finishes.  
      PrecedenceConstraint pcFileTasks =   
        p.PrecedenceConstraints.Add((Executable)thFileHost1, (Executable)thFileHost2);  
      pcFileTasks.Value = DTSExecResult.Completion;  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task.  
    Dim eFileTask1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost1 As TaskHost = CType(eFileTask1, TaskHost)  
  
    ' Add a second File System task.  
    Dim eFileTask2 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost2 As TaskHost = CType(eFileTask2, TaskHost)  
  
    ' Put a precedence constraint between the tasks.  
    ' Set the constraint to specify that the second File System task cannot run  
    ' until the first File System task finishes.  
    Dim pcFileTasks As PrecedenceConstraint = _  
      p.PrecedenceConstraints.Add(CType(thFileHost1, Executable), CType(thFileHost2, Executable))  
    pcFileTasks.Value = DTSExecResult.Completion  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="5b367-120">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5b367-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5b367-121">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="5b367-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5b367-122">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="5b367-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5b367-123">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="5b367-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b367-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b367-124">See Also</span></span>  
 [<span data-ttu-id="5b367-125">Agregar la tarea de flujo de datos mediante programación</span><span class="sxs-lookup"><span data-stu-id="5b367-125">Adding the Data Flow Task Programmatically</span></span>](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md)  
  
  
