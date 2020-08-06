---
title: Buscar impresoras instaladas con la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- System.Drawing.Printing namespace
- printers [Integration Services]
- SSIS Script task, printers
- locating printers
- Printing namespace
- Script task [Integration Services], examples
- finding printers [SQL Server]
- Script task [Integration Services], printers
ms.assetid: 50a55014-e2c3-4ecd-84e1-3e877c55a260
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc4bc06879a55d4d07afca1011cc479dd7e7903a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748199"
---
# <a name="finding-installed-printers-with-the-script-task"></a><span data-ttu-id="9b133-102">Buscar impresoras instaladas con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="9b133-102">Finding Installed Printers with the Script Task</span></span>
  <span data-ttu-id="9b133-103">Los datos que se transforman con los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tienen a menudo un informe impreso como último destino.</span><span class="sxs-lookup"><span data-stu-id="9b133-103">The data that is transformed by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages often has a printed report as its final destination.</span></span> <span data-ttu-id="9b133-104">El `System.Drawing.Printing` espacio de nombres de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] proporciona clases para trabajar con impresoras.</span><span class="sxs-lookup"><span data-stu-id="9b133-104">The `System.Drawing.Printing` namespace in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for working with printers.</span></span>

> [!NOTE]
>  <span data-ttu-id="9b133-105">Si desea crear una tarea que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de este ejemplo de tarea Script como punto inicial de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="9b133-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="9b133-106">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="9b133-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="9b133-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b133-107">Description</span></span>
 <span data-ttu-id="9b133-108">En el ejemplo siguiente se buscan impresoras instaladas en el servidor que admiten el tamaño de papel legal (que se utiliza en Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="9b133-108">The following example locates printers installed on the server that support legal size paper (as used in the United States).</span></span> <span data-ttu-id="9b133-109">El código para comprobar los tamaños de papel compatibles está encapsulado en una función privada.</span><span class="sxs-lookup"><span data-stu-id="9b133-109">The code to check supported paper sizes is encapsulated in a private function.</span></span> <span data-ttu-id="9b133-110">Para permitir realizar el seguimiento del progreso del script a medida que se comprueban los valores de cada impresora, el script utiliza el método <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> para provocar un mensaje informativo para las impresoras con papel de tamaño legal y una advertencia para las impresoras sin papel de tamaño legal.</span><span class="sxs-lookup"><span data-stu-id="9b133-110">To enable you to track the progress of the script as it checks the settings for each printer, the script uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to raise an informational message for printers with legal size paper, and to raise a warning for printers without legal size paper.</span></span> <span data-ttu-id="9b133-111">Estos mensajes aparecen en la ventana **Salida** del IDE de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) al ejecutar el paquete en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="9b133-111">These messages appear in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE when you run the package in the designer.</span></span>

#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="9b133-112">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="9b133-112">To configure this Script Task example</span></span>

1.  <span data-ttu-id="9b133-113">Cree la variable denominada `PrinterList` con el tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="9b133-113">Create the variable named `PrinterList` with type `Object`.</span></span>

2.  <span data-ttu-id="9b133-114">En la página **Script** del **Editor de la tarea Script**, agregue esta variable a la propiedad ReadWriteVariables.</span><span class="sxs-lookup"><span data-stu-id="9b133-114">On the **Script** page of the **Script Task Editor**, add this variable to the ReadWriteVariables property.</span></span>

3.  <span data-ttu-id="9b133-115">Agregue una referencia al espacio de nombres **System.Drawing** en el proyecto de script.</span><span class="sxs-lookup"><span data-stu-id="9b133-115">In the script project, add a reference to the **System.Drawing** namespace.</span></span>

4.  <span data-ttu-id="9b133-116">En el código, use las `Imports` instrucciones para importar los espacios de nombres **System. Collections** y `System.Drawing.Printing` .</span><span class="sxs-lookup"><span data-stu-id="9b133-116">In your code, use `Imports` statements to import the **System.Collections** and the `System.Drawing.Printing` namespaces.</span></span>

### <a name="code"></a><span data-ttu-id="9b133-117">Código</span><span class="sxs-lookup"><span data-stu-id="9b133-117">Code</span></span>

```vb
Public Sub Main()

    Dim printerName As String
    Dim currentPrinter As New PrinterSettings
    Dim size As PaperSize

    Dim printerList As New ArrayList
    For Each printerName In PrinterSettings.InstalledPrinters
        currentPrinter.PrinterName = printerName
        If PrinterHasLegalPaper(currentPrinter) Then
            printerList.Add(printerName)
            Dts.Events.FireInformation(0, "Example", _
                "Printer " & printerName & " has legal paper.", _
                String.Empty, 0, False)
        Else
            Dts.Events.FireWarning(0, "Example", _
                "Printer " & printerName & " DOES NOT have legal paper.", _
                String.Empty, 0)
        End If
    Next

    Dts.Variables("PrinterList").Value = printerList

    Dts.TaskResult = ScriptResults.Success

End Sub

Private Function PrinterHasLegalPaper( _
    ByVal thisPrinter As PrinterSettings) As Boolean

    Dim size As PaperSize
    Dim hasLegal As Boolean = False

    For Each size In thisPrinter.PaperSizes
        If size.Kind = PaperKind.Legal Then
            hasLegal = True
        End If
    Next

    Return hasLegal

End Function
```

```csharp
public void Main()
        {

            PrinterSettings currentPrinter = new PrinterSettings();
            PaperSize size;
            Boolean Flag = false;

            ArrayList printerList = new ArrayList();
            foreach (string printerName in PrinterSettings.InstalledPrinters)
            {
                currentPrinter.PrinterName = printerName;
                if (PrinterHasLegalPaper(currentPrinter))
                {
                    printerList.Add(printerName);
                    Dts.Events.FireInformation(0, "Example", "Printer " + printerName + " has legal paper.", String.Empty, 0, ref Flag);
                }
                else
                {
                    Dts.Events.FireWarning(0, "Example", "Printer " + printerName + " DOES NOT have legal paper.", String.Empty, 0);
                }
            }

            Dts.Variables["PrinterList"].Value = printerList;

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private bool PrinterHasLegalPaper(PrinterSettings thisPrinter)
        {

            bool hasLegal = false;

            foreach (PaperSize size in thisPrinter.PaperSizes)
            {
                if (size.Kind == PaperKind.Legal)
                {
                    hasLegal = true;
                }
            }

            return hasLegal;

        }
```

<span data-ttu-id="9b133-118">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9b133-118">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9b133-119">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="9b133-119">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9b133-120">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="9b133-120">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9b133-121">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="9b133-121">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b133-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b133-122">See Also</span></span>
 [<span data-ttu-id="9b133-123">Ejemplos de tarea Script</span><span class="sxs-lookup"><span data-stu-id="9b133-123">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)


