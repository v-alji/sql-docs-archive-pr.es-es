---
title: Detectar un archivo plano vacío con la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- flat files
- Script task [Integration Services], empty flat files
- SSIS Script task, empty flat files
- Script task [Integration Services], examples
ms.assetid: 1b4defb8-886a-483d-8056-d1b91d37bc90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 379b11bd18752ad648fc5f24d11d9ed5bfb63e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673767"
---
# <a name="detecting-an-empty-flat-file-with-the-script-task"></a><span data-ttu-id="ff61f-102">Detectar un archivo plano vacío con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="ff61f-102">Detecting an Empty Flat File with the Script Task</span></span>
  <span data-ttu-id="ff61f-103">El origen de archivo plano no determina si un archivo de este tipo contiene filas de datos antes de intentar procesarlo.</span><span class="sxs-lookup"><span data-stu-id="ff61f-103">The Flat File source does not determine whether a flat file contains rows of data before attempting to process it.</span></span> <span data-ttu-id="ff61f-104">Puede que desee mejorar la eficacia de un paquete (sobre todo un paquete que recorre en iteración numerosos archivos planos) mediante la omisión de archivos que no contienen filas de datos.</span><span class="sxs-lookup"><span data-stu-id="ff61f-104">You may want to improve the efficiency of a package, especially of a package that iterates over numerous flat files, by skipping files that do not contain any rows of data.</span></span> <span data-ttu-id="ff61f-105">La tarea Script puede buscar un archivo plano vacío antes de que el paquete comience a procesar el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="ff61f-105">The Script task can look for an empty flat file before the package begins to process the data flow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff61f-106">Si desea crear una tarea que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de este ejemplo de tarea Script como punto inicial de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="ff61f-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="ff61f-107">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="ff61f-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="ff61f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff61f-108">Description</span></span>  
 <span data-ttu-id="ff61f-109">En el ejemplo siguiente se utilizan métodos del espacio de nombres `System.IO` para probar el archivo plano especificado en un administrador de conexiones de archivos planos a fin de determinar si el archivo está vacío o si solamente contiene filas esperadas que no son de datos, como encabezados de columna o una línea vacía.</span><span class="sxs-lookup"><span data-stu-id="ff61f-109">The following example uses methods from the `System.IO` namespace to test the flat file specified in a Flat File connection manager to determine whether the file is empty, or whether it contains only expected non-data rows such as column headers or an empty line.</span></span> <span data-ttu-id="ff61f-110">En primer lugar, el script comprueba el tamaño del archivo; si el tamaño es de cero bytes, el archivo está vacío.</span><span class="sxs-lookup"><span data-stu-id="ff61f-110">The script checks the size of the file first; if the size is zero bytes, the file is empty.</span></span> <span data-ttu-id="ff61f-111">Si el tamaño de archivo es mayor que cero, el script lee las líneas del archivo hasta que no haya más líneas o hasta que el número de líneas supere el número esperado de filas que no son de datos.</span><span class="sxs-lookup"><span data-stu-id="ff61f-111">If the file size is greater than zero, the script reads lines from the file until there are no more lines, or until the number of lines exceeds the expected number of non-data rows.</span></span> <span data-ttu-id="ff61f-112">Si el número de líneas del archivo es menor o igual que el número esperado de filas que no son de datos, se considera que el archivo está vacío.</span><span class="sxs-lookup"><span data-stu-id="ff61f-112">If the number of lines in the file is less than or equal to the expected number of non-data rows, then the file is considered empty.</span></span> <span data-ttu-id="ff61f-113">El resultado se devuelve como valor booleano en una variable de usuario, cuyo valor puede utilizarse para la bifurcación del flujo de control del paquete.</span><span class="sxs-lookup"><span data-stu-id="ff61f-113">The result is returned as a Boolean value in a user variable, the value of which can be used for branching in the package's control flow.</span></span> <span data-ttu-id="ff61f-114">El `FireInformation` método también muestra el resultado en la ventana de **salida** de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="ff61f-114">The `FireInformation` method also displays the result in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="ff61f-115">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="ff61f-115">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="ff61f-116">Cree y configure un administrador de conexiones de archivos planos denominado `EmptyFlatFileTest` .</span><span class="sxs-lookup"><span data-stu-id="ff61f-116">Create and configure a flat file connection manager named `EmptyFlatFileTest`.</span></span>  
  
2.  <span data-ttu-id="ff61f-117">Cree una variable de entero denominada `FFNonDataRows` y establezca su valor en el número esperado de filas que no son de datos del archivo plano.</span><span class="sxs-lookup"><span data-stu-id="ff61f-117">Create an integer variable named `FFNonDataRows` and set its value to the number of non-data rows expected in the flat file.</span></span>  
  
3.  <span data-ttu-id="ff61f-118">Cree una variable booleana denominada `FFIsEmpty`.</span><span class="sxs-lookup"><span data-stu-id="ff61f-118">Create a Boolean variable named `FFIsEmpty`.</span></span>  
  
4.  <span data-ttu-id="ff61f-119">Agregue la variable `FFNonDataRows` a la propiedad **ReadOnlyVariables** de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="ff61f-119">Add the `FFNonDataRows` variable to the Script task's **ReadOnlyVariables** property.</span></span>  
  
5.  <span data-ttu-id="ff61f-120">Agregue la variable `FFIsEmpty` a la propiedad **ReadWriteVariables** de la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="ff61f-120">Add the `FFIsEmpty` variable to the Script task's **ReadWriteVariables** property.</span></span>  
  
6.  <span data-ttu-id="ff61f-121">Importe el espacio de nombres `System.IO` en su código.</span><span class="sxs-lookup"><span data-stu-id="ff61f-121">In your code, import the `System.IO` namespace.</span></span>  
  
 <span data-ttu-id="ff61f-122">Si recorre en iteración archivos con un enumerador Foreach File, en lugar de utilizar solamente un administrador de conexiones de archivos planos, tendrá que modificar el código de ejemplo siguiente para obtener el nombre de archivo y la ruta de acceso de la variable donde se almacena el valor enumerado y no del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="ff61f-122">If you are iterating over files with a Foreach File enumerator, instead of using a single Flat File connection manager, you will need to modify the sample code below to obtain the file name and path from the variable in which the enumerated value is stored instead of from the connection manager.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ff61f-123">Código</span><span class="sxs-lookup"><span data-stu-id="ff61f-123">Code</span></span>  
  
```vb  
Public Sub Main()  
  
  Dim nonDataRows As Integer = _  
      DirectCast(Dts.Variables("FFNonDataRows").Value, Integer)  
  Dim ffConnection As String = _  
      DirectCast(Dts.Connections("EmptyFlatFileTest").AcquireConnection(Nothing), _  
      String)  
  Dim flatFileInfo As New FileInfo(ffConnection)  
  ' If file size is 0 bytes, flat file does not contain data.  
  Dim fileSize As Long = flatFileInfo.Length  
  If fileSize > 0 Then  
    Dim lineCount As Integer = 0  
    Dim line As String  
    Dim fsFlatFile As New StreamReader(ffConnection)  
    Do Until fsFlatFile.EndOfStream  
      line = fsFlatFile.ReadLine  
      lineCount += 1  
      ' If line count > expected number of non-data rows,  
      '  flat file contains data (default value).  
      If lineCount > nonDataRows Then  
        Exit Do  
      End If  
      ' If line count <= expected number of non-data rows,  
      '  flat file does not contain data.  
      If lineCount <= nonDataRows Then  
        Dts.Variables("FFIsEmpty").Value = True  
      End If  
    Loop  
  Else  
    Dts.Variables("FFIsEmpty").Value = True  
  End If  
  
  Dim fireAgain As Boolean = False  
  Dts.Events.FireInformation(0, "Script Task", _  
      String.Format("{0}: {1}", ffConnection, _  
      Dts.Variables("FFIsEmpty").Value.ToString), _  
      String.Empty, 0, fireAgain)  
  
  Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
public void Main()  
        {  
  
            int nonDataRows = (int)(Dts.Variables["FFNonDataRows"].Value);  
            string ffConnection = (string)(Dts.Connections["EmptyFlatFileTest"].AcquireConnection(null) as String);  
            FileInfo flatFileInfo = new FileInfo(ffConnection);  
            // If file size is 0 bytes, flat file does not contain data.  
            long fileSize = flatFileInfo.Length;  
            if (fileSize > 0)  
            {  
  
                int lineCount = 0;  
                string line;  
                StreamReader fsFlatFile = new StreamReader(ffConnection);  
                while (!(fsFlatFile.EndOfStream))  
                {  
                    Console.WriteLine (fsFlatFile.ReadLine());  
                    lineCount += 1;  
                    // If line count > expected number of non-data rows,  
                    //  flat file contains data (default value).  
                    if (lineCount > nonDataRows)  
                    {  
                        break;  
                    }  
                    // If line count <= expected number of non-data rows,  
                    //  flat file does not contain data.  
                    if (lineCount <= nonDataRows)  
                    {  
                        Dts.Variables["FFIsEmpty"].Value = true;  
                    }  
                }  
            }  
            else  
            {  
                Dts.Variables["FFIsEmpty"].Value = true;  
            }  
  
            bool fireAgain = false;  
            Dts.Events.FireInformation(0, "Script Task", String.Format("{0}: {1}", ffConnection, Dts.Variables["FFIsEmpty"].Value), String.Empty, 0, ref fireAgain);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
```  
  
<span data-ttu-id="ff61f-124">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ff61f-124">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ff61f-125">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="ff61f-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ff61f-126">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="ff61f-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ff61f-127">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="ff61f-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff61f-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff61f-128">See Also</span></span>  
 [<span data-ttu-id="ff61f-129">Ejemplos de tarea Script</span><span class="sxs-lookup"><span data-stu-id="ff61f-129">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)  
  
  
