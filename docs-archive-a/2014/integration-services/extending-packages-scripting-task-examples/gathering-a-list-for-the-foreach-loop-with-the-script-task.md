---
title: Recopilar una lista para el bucle Para cada uno con la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], Foreach loops
- Script task [Integration Services], examples
- SSIS Script task, Foreach loops
ms.assetid: 694f0462-d0c5-4191-b64e-821b1bdef055
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 039860da121efaa52115bb515b158ea10373e459
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744774"
---
# <a name="gathering-a-list-for-the-foreach-loop-with-the-script-task"></a><span data-ttu-id="5e53c-102">Recopilar una lista para el bucle Foreach con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="5e53c-102">Gathering a List for the ForEach Loop with the Script Task</span></span>
  <span data-ttu-id="5e53c-103">El enumerador de variable para Foreach enumera los elementos de una lista que le se pasa en una variable y realiza las mismas tareas en cada elemento.</span><span class="sxs-lookup"><span data-stu-id="5e53c-103">The Foreach from Variable Enumerator enumerates over the items in a list that is passed to it in a variable and performs the same tasks on each item.</span></span> <span data-ttu-id="5e53c-104">Puede utilizar código personalizado en una tarea Script para rellenar una lista con este fin.</span><span class="sxs-lookup"><span data-stu-id="5e53c-104">You can use custom code in a Script task to populate a list for this purpose.</span></span> <span data-ttu-id="5e53c-105">Para obtener más información sobre el enumerador, vea [Contenedor de bucles Para cada uno](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="5e53c-105">For more information about the enumerator, see [Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e53c-106">Si desea crear una tarea que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de este ejemplo de tarea Script como punto inicial de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="5e53c-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="5e53c-107">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="5e53c-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="5e53c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e53c-108">Description</span></span>  
 <span data-ttu-id="5e53c-109">En el ejemplo siguiente se utilizan métodos del espacio de nombres `System.IO` para recopilar una lista de libros de Excel del equipo que son posteriores o anteriores a un número de días especificado por el usuario en una variable.</span><span class="sxs-lookup"><span data-stu-id="5e53c-109">The following example uses methods from the `System.IO` namespace to gather a list of Excel workbooks on the computer that are either newer or older than a number of days specified by the user in a variable.</span></span> <span data-ttu-id="5e53c-110">Busca de forma recursiva en los directorios de la unidad C los archivos que tienen la extensión .xls y examina la fecha en la que cada archivo se modificó por última vez para determinar si el archivo pertenece a la lista.</span><span class="sxs-lookup"><span data-stu-id="5e53c-110">It searches directories on Drive C recursively for files that have the .xls extension and examines the date on which each file was last modified to determine whether the file belongs in the list.</span></span> <span data-ttu-id="5e53c-111">Agrega los archivos correspondientes a un objeto `ArrayList` y guarda el objeto `ArrayList` en una variable para el uso posterior en un contenedor de bucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="5e53c-111">It adds qualifying files to an `ArrayList` and saves the `ArrayList` to a variable for later use in a Foreach Loop container.</span></span> <span data-ttu-id="5e53c-112">El contenedor de bucles Foreach se configura para utilizar el enumerador de variable para Foreach.</span><span class="sxs-lookup"><span data-stu-id="5e53c-112">The Foreach Loop container is configured to use the Foreach from Variable enumerator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e53c-113">La variable que utiliza con el enumerador de variable para Foreach debe ser del tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="5e53c-113">The variable that you use with the Foreach from Variable Enumerator must be of type `Object`.</span></span> <span data-ttu-id="5e53c-114">El objeto que incluye en la variable debe implementar una de las interfaces siguientes: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource` o `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span><span class="sxs-lookup"><span data-stu-id="5e53c-114">The object that you place in the variable must implement one of the following interfaces: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource`, or `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span></span> <span data-ttu-id="5e53c-115">Normalmente se utiliza `Array` o `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="5e53c-115">An `Array` or `ArrayList` is commonly used.</span></span> <span data-ttu-id="5e53c-116">`ArrayList` requiere una referencia y una instrucción `Imports` para el espacio de nombres `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="5e53c-116">The `ArrayList` requires a reference and an `Imports` statement for the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="5e53c-117">Puede experimentar con esta tarea utilizando diferentes valores positivos y negativos en la variable de paquete `FileAge`.</span><span class="sxs-lookup"><span data-stu-id="5e53c-117">You can experiment with this task by using different positive and negative values for the `FileAge` package variable.</span></span> <span data-ttu-id="5e53c-118">Por ejemplo, puede escribir 5 para buscar archivos creados en los cinco últimos días o escribir -3 para buscar archivos creados hace más de tres días.</span><span class="sxs-lookup"><span data-stu-id="5e53c-118">For example, you can enter 5 to search for files created in the last five days, or enter -3 to search for files that were created more than three days ago.</span></span> <span data-ttu-id="5e53c-119">Esta tarea puede tardar un minuto o dos en una unidad de disco con un gran número de carpetas donde buscar.</span><span class="sxs-lookup"><span data-stu-id="5e53c-119">This task may take a minute or two on a drive with many folders to search.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="5e53c-120">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="5e53c-120">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="5e53c-121">Cree una variable de paquete denominada `FileAge` del tipo entero y escriba un valor entero positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="5e53c-121">Create a package variable named `FileAge` of type integer and enter a positive or negative integer value.</span></span> <span data-ttu-id="5e53c-122">Cuando el valor es positivo, el código busca archivos posteriores al número especificado de días; cuando es negativo, archivos anteriores al número especificado de días.</span><span class="sxs-lookup"><span data-stu-id="5e53c-122">When the value is positive, the code searches for files newer than the specified number of days; when negative, for files older than the specified number of days.</span></span>  
  
2.  <span data-ttu-id="5e53c-123">Cree una variable de paquete denominada `FileList` de tipo `Object` para recibir la lista de archivos recopilada por la tarea Script para su uso posterior en el enumerador de variable para Foreach.</span><span class="sxs-lookup"><span data-stu-id="5e53c-123">Create a package variable named `FileList` of type `Object` to receive the list of files gathered by the Script task for later use by the Foreach from Variable Enumerator.</span></span>  
  
3.  <span data-ttu-id="5e53c-124">Agregue la variable `FileAge` a la propiedad `ReadOnlyVariables` de la tarea Script y la variable `FileList` a la propiedad `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="5e53c-124">Add the `FileAge` variable to the Script task's `ReadOnlyVariables` property, and add the `FileList` variable to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="5e53c-125">En el código, importe los espacios de nombres `System.Collections` y `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="5e53c-125">In your code, import the `System.Collections` and the `System.IO` namespaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5e53c-126">Código</span><span class="sxs-lookup"><span data-stu-id="5e53c-126">Code</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Math  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Collections  
Imports System.IO  
  
Public Class ScriptMain  
  
  Private Const FILE_AGE As Integer = -50  
  
  Private Const FILE_ROOT As String = "C:\"  
  Private Const FILE_FILTER As String = "*.xls"  
  
  Private isCheckForNewer As Boolean = True  
  Dim fileAgeLimit As Integer  
  Private listForEnumerator As ArrayList  
  
  Public Sub Main()  
  
    fileAgeLimit = DirectCast(Dts.Variables("FileAge").Value, Integer)  
  
    ' If value provided is positive, we want files NEWER THAN n days.  
    '  If negative, we want files OLDER THAN n days.  
    If fileAgeLimit < 0 Then  
      isCheckForNewer = False  
    End If  
    ' Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit)  
  
    listForEnumerator = New ArrayList  
  
    GetFilesInFolder(FILE_ROOT)  
  
    ' Return the list of files to the variable  
    '  for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: " & listForEnumerator.Count.ToString, "Results", Windows.Forms.MessageBoxButtons.OK, Windows.Forms.MessageBoxIcon.Information)  
    Dts.Variables("FileList").Value = listForEnumerator  
  
    Dts.TaskResult = ScriptResults.Success  
  
  End Sub  
  
  Private Sub GetFilesInFolder(ByVal folderPath As String)  
  
    Dim localFiles() As String  
    Dim localFile As String  
    Dim fileChangeDate As Date  
    Dim fileAge As TimeSpan  
    Dim fileAgeInDays As Integer  
    Dim childFolder As String  
  
    Try  
      localFiles = Directory.GetFiles(folderPath, FILE_FILTER)  
      For Each localFile In localFiles  
        fileChangeDate = File.GetLastWriteTime(localFile)  
        fileAge = DateTime.Now.Subtract(fileChangeDate)  
        fileAgeInDays = fileAge.Days  
        CheckAgeOfFile(localFile, fileAgeInDays)  
      Next  
  
      If Directory.GetDirectories(folderPath).Length > 0 Then  
        For Each childFolder In Directory.GetDirectories(folderPath)  
          GetFilesInFolder(childFolder)  
        Next  
      End If  
  
    Catch  
      ' Ignore exceptions on special folders such as System Volume Information.  
    End Try  
  
  End Sub  
  
  Private Sub CheckAgeOfFile(ByVal localFile As String, ByVal fileAgeInDays As Integer)  
  
    If isCheckForNewer Then  
      If fileAgeInDays <= fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    Else  
      If fileAgeInDays > fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    End If  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Math;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Collections;  
using System.IO;  
  
public partial class ScriptMain : Microsoft.SqlServer.Dts.Tasks.ScriptTask.VSTARTScriptObjectModelBase  
    {  
  
        private const int FILE_AGE = -50;  
  
        private const string FILE_ROOT = "C:\\";  
        private const string FILE_FILTER = "*.xls";  
  
        private bool isCheckForNewer = true;  
        int fileAgeLimit;  
        private ArrayList listForEnumerator;  
  
        public void Main()  
  {  
  
    fileAgeLimit = (int)(Dts.Variables["FileAge"].Value);  
  
    // If value provided is positive, we want files NEWER THAN n days.  
    // If negative, we want files OLDER THAN n days.  
    if (fileAgeLimit<0)  
    {  
      isCheckForNewer = false;  
    }  
    // Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit);  
  
    ArrayList listForEnumerator = new ArrayList();  
  
    GetFilesInFolder(FILE_ROOT);  
  
    // Return the list of files to the variable  
    // for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: "+ listForEnumerator.Count, "Results",   
MessageBoxButtons.OK, MessageBoxIcon.Information);  
    Dts.Variables["FileList"].Value = listForEnumerator;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  
  }  
  
        private void GetFilesInFolder(string folderPath)  
        {  
  
            string[] localFiles;  
            DateTime fileChangeDate;  
            TimeSpan fileAge;  
            int fileAgeInDays;  
  
            try  
            {  
                localFiles = Directory.GetFiles(folderPath, FILE_FILTER);  
                foreach (string localFile in localFiles)  
                {  
                    fileChangeDate = File.GetLastWriteTime(localFile);  
                    fileAge = DateTime.Now.Subtract(fileChangeDate);  
                    fileAgeInDays = fileAge.Days;  
                    CheckAgeOfFile(localFile, fileAgeInDays);  
                }  
  
                if (Directory.GetDirectories(folderPath).Length > 0)  
                {  
                    foreach (string childFolder in Directory.GetDirectories(folderPath))  
                    {  
                        GetFilesInFolder(childFolder);  
                    }  
                }  
  
            }  
            catch  
            {  
                // Ignore exceptions on special folders, such as System Volume Information.  
            }  
  
        }  
  
        private void CheckAgeOfFile(string localFile, int fileAgeInDays)  
        {  
  
            if (isCheckForNewer)  
            {  
                if (fileAgeInDays <= fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
            else  
            {  
                if (fileAgeInDays > fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
  
        }  
  
    }  
```  
  
<span data-ttu-id="5e53c-127">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5e53c-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5e53c-128">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="5e53c-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5e53c-129">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="5e53c-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5e53c-130">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="5e53c-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e53c-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e53c-131">See Also</span></span>  
 <span data-ttu-id="5e53c-132">[Contenedor de bucles foreach](../control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="5e53c-132">[Foreach Loop Container](../control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="5e53c-133">Configurar un contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="5e53c-133">Configure a Foreach Loop Container</span></span>](../configure-a-foreach-loop-container.md)  
  
  