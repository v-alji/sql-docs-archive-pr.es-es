---
title: Utilizar variables en la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], variables
- scripts [Integration Services], variables
- Variables property
- Variable object
- SSIS Script task, variables
- variables [Integration Services], Script task
ms.assetid: 593b5961-4bfa-4ce1-9531-a251c34e89d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2cd8fee5741c3d0e28e52c8712c3896428a05e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752282"
---
# <a name="using-variables-in-the-script-task"></a><span data-ttu-id="97cf8-102">Utilizar variables en la tarea Script</span><span class="sxs-lookup"><span data-stu-id="97cf8-102">Using Variables in the Script Task</span></span>
  <span data-ttu-id="97cf8-103">Las variables permiten que la tarea Script intercambie datos con otros objetos del paquete.</span><span class="sxs-lookup"><span data-stu-id="97cf8-103">Variables make it possible for the Script task to exchange data with other objects in the package.</span></span> <span data-ttu-id="97cf8-104">Para más información, vea [Variables de Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="97cf8-104">For more information, see [Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="97cf8-105">La tarea Script utiliza la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> del objeto `Dts` para leer de y escribir en los objetos <xref:Microsoft.SqlServer.Dts.Runtime.Variable> del paquete.</span><span class="sxs-lookup"><span data-stu-id="97cf8-105">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object to read from and write to <xref:Microsoft.SqlServer.Dts.Runtime.Variable> objects in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97cf8-106">La propiedad <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> de la clase <xref:Microsoft.SqlServer.Dts.Runtime.Variable> es del tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="97cf8-106">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.Variable> class is of type `Object`.</span></span> <span data-ttu-id="97cf8-107">Dado que la tarea Script tiene `Option Strict` habilitado, debe convertir la propiedad <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> al tipo adecuado antes de utilizarla.</span><span class="sxs-lookup"><span data-stu-id="97cf8-107">Because the Script task has `Option Strict` enabled, you must cast the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property to the appropriate type before you can use it.</span></span>  
  
 <span data-ttu-id="97cf8-108">Las variables existentes se agregan a las listas <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> y <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> en el **Editor de la tarea Script** para que estén disponibles en el script personalizado.</span><span class="sxs-lookup"><span data-stu-id="97cf8-108">You add existing variables to the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> and <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> lists in the **Script Task Editor** to make them available to the custom script.</span></span> <span data-ttu-id="97cf8-109">Tenga presente que los nombres de variable distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="97cf8-109">Keep in mind that variable names are case-sensitive.</span></span> <span data-ttu-id="97cf8-110">Dentro del script, tiene acceso a las variables de ambos tipos a través de la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> del objeto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="97cf8-110">Within the script, you access variables of both types through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object.</span></span> <span data-ttu-id="97cf8-111">Utilice la propiedad `Value` para leer de y escribir en las variables individuales.</span><span class="sxs-lookup"><span data-stu-id="97cf8-111">Use the `Value` property to read from and write to individual variables.</span></span> <span data-ttu-id="97cf8-112">La tarea Script administra de forma transparente el bloqueo a medida que el script lee y modifica los valores de las variables.</span><span class="sxs-lookup"><span data-stu-id="97cf8-112">The Script task transparently manages locking as the script reads and modifies the values of variables.</span></span>  
  
 <span data-ttu-id="97cf8-113">Puede utilizar el método <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> de la colección <xref:Microsoft.SqlServer.Dts.Runtime.Variables> que devuelve la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> para comprobar la existencia de una variable antes de utilizarla en el código.</span><span class="sxs-lookup"><span data-stu-id="97cf8-113">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property to check for the existence of a variable before using it in your code.</span></span>  
  
 <span data-ttu-id="97cf8-114">También puede utilizar la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> (Dts.VariableDispenser) para trabajar con variables en la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="97cf8-114">You can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property (Dts.VariableDispenser) to work with variables in the Script task.</span></span> <span data-ttu-id="97cf8-115">Al utilizar <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, debe administrar la semántica de bloqueo y la conversión de tipos de datos para los valores de variables en su propio código.</span><span class="sxs-lookup"><span data-stu-id="97cf8-115">When using the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must handle both the locking semantics and the casting of data types for variable values in your own code.</span></span> <span data-ttu-id="97cf8-116">Puede que necesite utilizar la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> en lugar de la propiedad <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> si desea trabajar con una variable que no está disponible en tiempo de diseño pero que se crea mediante programación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="97cf8-116">You may need to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property instead of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property if you want to work with a variable that is not available at design time but is created programmatically at run time.</span></span>  
  
## <a name="using-the-script-task-within-a-foreach-loop-container"></a><span data-ttu-id="97cf8-117">Utilizar la tarea Script dentro de un contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="97cf8-117">Using the Script Task within a Foreach Loop Container</span></span>  
 <span data-ttu-id="97cf8-118">Cuando una tarea Script se ejecuta repetidamente dentro de un contenedor de bucles Foreach, normalmente el script necesita trabajar con el contenido del elemento actual en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="97cf8-118">When a Script task runs repeatedly within a Foreach Loop container, the script usually needs to work with the contents of the current item in the enumerator.</span></span> <span data-ttu-id="97cf8-119">Por ejemplo, al utilizar un enumerador de archivos Foreach, el script necesita conocer el nombre del archivo actual; al utilizar un enumerador de ADO para Foreach, el script necesita conocer el contenido de las columnas en la fila actual de datos.</span><span class="sxs-lookup"><span data-stu-id="97cf8-119">For example, when using a Foreach File enumerator, the script needs to know the current file name; when using a Foreach ADO enumerator, the script needs to know the contents of the columns in the current row of data.</span></span>  
  
 <span data-ttu-id="97cf8-120">Las variables consiguen que sea posible esta comunicación entre el contenedor de bucles Foreach y la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="97cf8-120">Variables make this communication between the Foreach Loop container and the Script task possible.</span></span> <span data-ttu-id="97cf8-121">En la página **Asignaciones de variables** del **Editor de bucles Para cada uno**, asigne variables a cada elemento de datos que devuelve un único elemento enumerado.</span><span class="sxs-lookup"><span data-stu-id="97cf8-121">On the **Variable Mappings** page of the **Foreach Loop Editor**, assign variables to each item of data that is returned by a single enumerated item.</span></span> <span data-ttu-id="97cf8-122">Por ejemplo, un enumerador de archivos Foreach solamente devuelve un nombre de archivo en Índice 0 y por tanto solamente requiere una asignación de variable, en tanto que un enumerador que devuelve varias columnas de datos en cada fila requiere que asigne una variable diferente a cada columna que desea utilizar en la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="97cf8-122">For example, a Foreach File enumerator returns only a file name at Index 0 and therefore requires only one variable mapping, whereas an enumerator that returns several columns of data in each row requires you to map a different variable to each column that you want to use in the Script task.</span></span>  
  
 <span data-ttu-id="97cf8-123">Después de asignar los elementos enumerados a las variables, debe agregar las variables asignadas a la `ReadOnlyVariables` propiedad en la página **script** del editor de la **tarea script** para que estén disponibles para el script.</span><span class="sxs-lookup"><span data-stu-id="97cf8-123">After you have mapped enumerated items to variables, then you must add the mapped variables to the `ReadOnlyVariables` property on the **Script** page of the **Script Task Editor** to make them available to your script.</span></span> <span data-ttu-id="97cf8-124">Para obtener un ejemplo de una tarea Script dentro de un contenedor de bucles Para cada uno que procesa los archivos de imagen en una carpeta, vea [Trabajar con imágenes con la tarea Script](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="97cf8-124">For an example of a Script task within a Foreach Loop container that processes the image files in a folder, see [Working with Images with the Script Task](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span></span>  
  
## <a name="variables-example"></a><span data-ttu-id="97cf8-125">Ejemplo de variables</span><span class="sxs-lookup"><span data-stu-id="97cf8-125">Variables Example</span></span>  
 <span data-ttu-id="97cf8-126">En el ejemplo siguiente se muestra cómo obtener acceso y utilizar las variables en una tarea Script para determinar la ruta de acceso de flujo de trabajo del paquete.</span><span class="sxs-lookup"><span data-stu-id="97cf8-126">The following example demonstrates how to access and use variables in a Script task to determine the path of package workflow.</span></span> <span data-ttu-id="97cf8-127">En el ejemplo se supone que ha creado variables de entero denominadas `CustomerCount` y `MaxRecordCount` y las ha agregado a la `ReadOnlyVariables` colección en el editor de la **tarea script**.</span><span class="sxs-lookup"><span data-stu-id="97cf8-127">The sample assumes that you have created integer variables named `CustomerCount` and `MaxRecordCount` and added them to the `ReadOnlyVariables` collection in the **Script Task Editor**.</span></span> <span data-ttu-id="97cf8-128">La variable `CustomerCount` contiene el número de registros del cliente que se van a importar.</span><span class="sxs-lookup"><span data-stu-id="97cf8-128">The `CustomerCount` variable contains the number of customer records to be imported.</span></span> <span data-ttu-id="97cf8-129">Si su valor es mayor que el valor de `MaxRecordCount`, la tarea Script informa del error.</span><span class="sxs-lookup"><span data-stu-id="97cf8-129">If its value is greater than the value of `MaxRecordCount`, the Script task reports failure.</span></span> <span data-ttu-id="97cf8-130">Cuando se produce un error porque se ha superado el umbral `MaxRecordCount`, la ruta de acceso de error del flujo de trabajo puede implementar cualquier limpieza necesaria.</span><span class="sxs-lookup"><span data-stu-id="97cf8-130">When a failure occurs because the `MaxRecordCount` threshold has been exceeded, the error path of the workflow can implement any required clean-up.</span></span>  
  
 <span data-ttu-id="97cf8-131">Para compilar correctamente el ejemplo, debe agregar una referencia al ensamblado Microsoft.SqlServer.ScriptTask.</span><span class="sxs-lookup"><span data-stu-id="97cf8-131">To successfully compile the sample, you need to add a reference to the Microsoft.SqlServer.ScriptTask assembly.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim customerCount As Integer  
    Dim maxRecordCount As Integer  
  
    If Dts.Variables.Contains("CustomerCount") = True AndAlso _  
        Dts.Variables.Contains("MaxRecordCount") = True Then  
  
        customerCount = _  
            CType(Dts.Variables("CustomerCount").Value, Integer)  
        maxRecordCount = _  
            CType(Dts.Variables("MaxRecordCount").Value, Integer)  
  
    End If  
  
    If customerCount > maxRecordCount Then  
            Dts.TaskResult = ScriptResults.Failure  
    Else  
            Dts.TaskResult = ScriptResults.Success  
    End If  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
  
public class ScriptMain  
{  
  
    public void Main()  
    {  
        int customerCount;  
        int maxRecordCount;  
  
        if (Dts.Variables.Contains("CustomerCount")==true&&Dts.Variables.Contains("MaxRecordCount")==true)  
  
        {  
            customerCount = (int) Dts.Variables["CustomerCount"].Value;  
            maxRecordCount = (int) Dts.Variables["MaxRecordCount"].Value;  
  
        }  
  
        if (customerCount>maxRecordCount)  
        {  
            Dts.TaskResult = (int)ScriptResults.Failure;  
        }  
        else  
        {  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
    }  
  
}  
  
```  
  
<span data-ttu-id="97cf8-132">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="97cf8-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="97cf8-133">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="97cf8-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="97cf8-134">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="97cf8-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="97cf8-135">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="97cf8-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97cf8-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97cf8-136">See Also</span></span>  
 <span data-ttu-id="97cf8-137">[Variables de Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="97cf8-137">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="97cf8-138">Usar variables en paquetes</span><span class="sxs-lookup"><span data-stu-id="97cf8-138">Use Variables in Packages</span></span>](../../use-variables-in-packages.md)  
  
  
