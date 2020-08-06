---
title: Trabajar con archivos de Excel con la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Excel files
- Script task [Integration Services], examples
- Excel [Integration Services]
ms.assetid: b8fa110a-2c9c-4f5a-8fe1-305555640e44
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68a764452de548cd46e74d2a7f2f588a050a21c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673201"
---
# <a name="working-with-excel-files-with-the-script-task"></a><span data-ttu-id="024d1-102">Trabajar con archivos de Excel con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="024d1-102">Working with Excel Files with the Script Task</span></span>
  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="024d1-103">proporciona el administrador de conexiones de Excel, el origen de Excel y el destino de Excel para trabajar con datos almacenados en hojas de cálculo en el formato de archivo de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="024d1-103">provides the Excel connection manager, Excel source, and Excel destination for working with data stored in spreadsheets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel file format.</span></span> <span data-ttu-id="024d1-104">Las técnicas descritas en este tema usan la tarea Script para obtener información acerca de las bases de datos de Excel disponibles (archivos de libro) y tablas (hojas de cálculo y rangos con nombre).</span><span class="sxs-lookup"><span data-stu-id="024d1-104">The techniques described in this topic use the Script task to obtain information about available Excel databases (workbook files) and tables (worksheets and named ranges).</span></span> <span data-ttu-id="024d1-105">Estos ejemplos se pueden modificar con facilidad para trabajar con cualquiera de los demás orígenes de datos basados en archivos que admite el proveedor OLE DB para [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet.</span><span class="sxs-lookup"><span data-stu-id="024d1-105">These samples can easily be modified to work with any of the other file-based data sources supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet OLE DB Provider.</span></span>  
  
 [<span data-ttu-id="024d1-106">Configurar un paquete para probar los ejemplos</span><span class="sxs-lookup"><span data-stu-id="024d1-106">Configuring a Package to Test the Samples</span></span>](#configuring)  
  
 [<span data-ttu-id="024d1-107">Ejemplo 1: comprobar si existe un archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="024d1-107">Example1: Check Whether an Excel File Exists</span></span>](#example1)  
  
 [<span data-ttu-id="024d1-108">Ejemplo 2: comprobar si existe una tabla de Excel</span><span class="sxs-lookup"><span data-stu-id="024d1-108">Example 2: Check Whether an Excel Table Exists</span></span>](#example2)  
  
 [<span data-ttu-id="024d1-109">Ejemplo 3: obtener una lista de archivos de Excel en una carpeta</span><span class="sxs-lookup"><span data-stu-id="024d1-109">Example 3: Get a List of Excel Files in a Folder</span></span>](#example3)  
  
 [<span data-ttu-id="024d1-110">Ejemplo 4: obtener una lista de tablas en un archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="024d1-110">Example 4: Get a List of Tables in an Excel File</span></span>](#example4)  
  
 [<span data-ttu-id="024d1-111">Mostrar los resultados de los ejemplos</span><span class="sxs-lookup"><span data-stu-id="024d1-111">Displaying the Results of the Samples</span></span>](#testing)  
  
> [!NOTE]  
>  <span data-ttu-id="024d1-112">Si desea crear una tarea que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de este ejemplo de tarea Script como punto inicial de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="024d1-112">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="024d1-113">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="024d1-113">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="configuring-a-package-to-test-the-samples"></a><a name="configuring"></a><span data-ttu-id="024d1-114">Configurar un paquete para probar los ejemplos</span><span class="sxs-lookup"><span data-stu-id="024d1-114">Configuring a Package to Test the Samples</span></span>  
 <span data-ttu-id="024d1-115">Puede configurar un paquete único para probar todos los ejemplos de este tema.</span><span class="sxs-lookup"><span data-stu-id="024d1-115">You can configure a single package to test all the samples in this topic.</span></span> <span data-ttu-id="024d1-116">En los ejemplos se usan muchas de las mismas variables de paquete y las mismas clases de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="024d1-116">The samples use many of the same package variables and the same [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes.</span></span>  
  
#### <a name="to-configure-a-package-for-use-with-the-examples-in-this-topic"></a><span data-ttu-id="024d1-117">Para configurar un paquete y utilizarlo con los ejemplos en este tema</span><span class="sxs-lookup"><span data-stu-id="024d1-117">To configure a package for use with the examples in this topic</span></span>  
  
1.  <span data-ttu-id="024d1-118">Cree un nuevo proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] y abra el paquete predeterminado para editar.</span><span class="sxs-lookup"><span data-stu-id="024d1-118">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open the default package for editing.</span></span>  
  
2.  <span data-ttu-id="024d1-119">**Variables**.</span><span class="sxs-lookup"><span data-stu-id="024d1-119">**Variables**.</span></span> <span data-ttu-id="024d1-120">Abra la ventana **Variables** y defina las variables siguientes:</span><span class="sxs-lookup"><span data-stu-id="024d1-120">Open the **Variables** window and define the following variables:</span></span>  
  
    -   <span data-ttu-id="024d1-121">`ExcelFile`, de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="024d1-121">`ExcelFile`, of type `String`.</span></span> <span data-ttu-id="024d1-122">Escriba la ruta de acceso completa y nombre de archivo a un libro de Excel existente.</span><span class="sxs-lookup"><span data-stu-id="024d1-122">Enter the complete path and filename to an existing Excel workbook.</span></span>  
  
    -   <span data-ttu-id="024d1-123">`ExcelTable`, de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="024d1-123">`ExcelTable`, of type `String`.</span></span> <span data-ttu-id="024d1-124">Escriba el nombre de una hoja de cálculo existente o rango con nombre en el libro denominado en el valor de la variable `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="024d1-124">Enter the name of an existing worksheet or named range in the workbook named in the value of the `ExcelFile` variable.</span></span> <span data-ttu-id="024d1-125">Este valor distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="024d1-125">This value is case-sensitive.</span></span>  
  
    -   <span data-ttu-id="024d1-126">`ExcelFileExists`, de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="024d1-126">`ExcelFileExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="024d1-127">`ExcelTableExists`, de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="024d1-127">`ExcelTableExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="024d1-128">`ExcelFolder`, de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="024d1-128">`ExcelFolder`, of type `String`.</span></span> <span data-ttu-id="024d1-129">Escriba la ruta de acceso completa de una carpeta que contiene por lo menos un libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="024d1-129">Enter the complete path of a folder that contains at least one Excel workbook.</span></span>  
  
    -   <span data-ttu-id="024d1-130">`ExcelFiles`, de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="024d1-130">`ExcelFiles`, of type `Object`.</span></span>  
  
    -   <span data-ttu-id="024d1-131">`ExcelTables`, de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="024d1-131">`ExcelTables`, of type `Object`.</span></span>  
  
3.  <span data-ttu-id="024d1-132">**Instrucciones Imports**.</span><span class="sxs-lookup"><span data-stu-id="024d1-132">**Imports statements**.</span></span> <span data-ttu-id="024d1-133">La mayoría de los ejemplos de código le exigen que importe uno o ambos de los espacios de nombres de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] siguientes en la parte superior de su archivo de script:</span><span class="sxs-lookup"><span data-stu-id="024d1-133">Most of the code samples require you to import one or both of the following [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces at the top of your script file:</span></span>  
  
    -   <span data-ttu-id="024d1-134">`System.IO`, para operaciones del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="024d1-134">`System.IO`, for file system operations.</span></span>  
  
    -   <span data-ttu-id="024d1-135">`System.Data.OleDb`, para abrir los archivos de Excel como orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="024d1-135">`System.Data.OleDb`, to open Excel files as data sources.</span></span>  
  
4.  <span data-ttu-id="024d1-136">**Referencias**.</span><span class="sxs-lookup"><span data-stu-id="024d1-136">**References**.</span></span> <span data-ttu-id="024d1-137">Los ejemplos de código que leen información de esquema de los archivos de Excel requieren una referencia adicional en el proyecto de script al espacio de nombres `System.Xml`.</span><span class="sxs-lookup"><span data-stu-id="024d1-137">The code samples that read schema information from Excel files require an additional reference in the script project to the `System.Xml` namespace.</span></span>  
  
5.  <span data-ttu-id="024d1-138">Establezca el lenguaje de scripting predeterminado para el componente de script mediante la opción **Lenguaje de scripting** de la página **General** del cuadro de diálogo **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="024d1-138">Set the default scripting language for the Script component by using the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="024d1-139">Para obtener más información, vea [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="024d1-139">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>  
  
##  <a name="example-1-description-check-whether-an-excel-file-exists"></a><a name="example1"></a> <span data-ttu-id="024d1-140">Descripción de ejemplo 1: comprobar si existe un archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="024d1-140">Example 1 Description: Check Whether an Excel File Exists</span></span>  
 <span data-ttu-id="024d1-141">En este ejemplo se determina si existe el archivo de libro de Excel especificado en la variable `ExcelFile` y, a continuación, se establece el valor booleano de la variable `ExcelFileExists` en el resultado.</span><span class="sxs-lookup"><span data-stu-id="024d1-141">This example determines whether the Excel workbook file specified in the `ExcelFile` variable exists, and then sets the Boolean value of the `ExcelFileExists` variable to the result.</span></span> <span data-ttu-id="024d1-142">Puede usar este valor booleano para la bifurcación en el flujo de trabajo del paquete.</span><span class="sxs-lookup"><span data-stu-id="024d1-142">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="024d1-143">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="024d1-143">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="024d1-144">Agregue una nueva tarea script al paquete y cambie su nombre a `ExcelFileExists` .</span><span class="sxs-lookup"><span data-stu-id="024d1-144">Add a new Script task to the package and change its name to `ExcelFileExists`.</span></span>  
  
2.  <span data-ttu-id="024d1-145">En el **Editor de la tarea Script**, en la pestaña **Script**, haga clic en **ReadOnlyVariables** y escriba el valor de propiedad mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="024d1-145">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="024d1-146">Escriba `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="024d1-146">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="024d1-147">O bien</span><span class="sxs-lookup"><span data-stu-id="024d1-147">-or-</span></span>  
  
    -   <span data-ttu-id="024d1-148">Haga clic en el botón de puntos suspensivos (**...**) situado junto al campo de propiedades y, en el cuadro de diálogo **seleccionar variables** , seleccione la `ExcelFile` variable.</span><span class="sxs-lookup"><span data-stu-id="024d1-148">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFile` variable.</span></span>  
  
3.  <span data-ttu-id="024d1-149">Haga clic en **ReadWriteVariables** y escriba el valor de propiedad mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="024d1-149">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="024d1-150">Escriba `ExcelFileExists`.</span><span class="sxs-lookup"><span data-stu-id="024d1-150">Type `ExcelFileExists`.</span></span>  
  
         <span data-ttu-id="024d1-151">O bien</span><span class="sxs-lookup"><span data-stu-id="024d1-151">-or-</span></span>  
  
    -   <span data-ttu-id="024d1-152">Haga clic en el botón de puntos suspensivos (**...**) situado junto al campo de propiedades y, en el cuadro de diálogo **seleccionar variables** , seleccione la `ExcelFileExists` variable.</span><span class="sxs-lookup"><span data-stu-id="024d1-152">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFileExists` variable.</span></span>  
  
4.  <span data-ttu-id="024d1-153">Haga clic en **Modificar script** para abrir el editor de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-153">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="024d1-154">Agregue una instrucción `Imports` para el espacio de nombres `System.IO` en la parte superior del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-154">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="024d1-155">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="024d1-155">Add the following code.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="024d1-156">Código de ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="024d1-156">Example 1 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    If File.Exists(fileToTest) Then  
      Dts.Variables("ExcelFileExists").Value = True  
    Else  
      Dts.Variables("ExcelFileExists").Value = False  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    string fileToTest;  
  
    fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
    if (File.Exists(fileToTest))  
    {  
      Dts.Variables["ExcelFileExists"].Value = true;  
    }  
    else  
    {  
      Dts.Variables["ExcelFileExists"].Value = false;  
    }  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
##  <a name="example-2-description-check-whether-an-excel-table-exists"></a><a name="example2"></a> <span data-ttu-id="024d1-157">Descripción de ejemplo 2: comprobar si existe una tabla de Excel</span><span class="sxs-lookup"><span data-stu-id="024d1-157">Example 2 Description: Check Whether an Excel Table Exists</span></span>  
 <span data-ttu-id="024d1-158">En este ejemplo se determina si existe la hoja de cálculo de Excel o el rango con nombre especificado en la variable `ExcelTable` en el archivo de libro de Excel especificado en la variable `ExcelFile` y, a continuación, se establece el valor booleano de la variable `ExcelTableExists` en el resultado.</span><span class="sxs-lookup"><span data-stu-id="024d1-158">This example determines whether the Excel worksheet or named range specified in the `ExcelTable` variable exists in the Excel workbook file specified in the `ExcelFile` variable, and then sets the Boolean value of the `ExcelTableExists` variable to the result.</span></span> <span data-ttu-id="024d1-159">Puede usar este valor booleano para la bifurcación en el flujo de trabajo del paquete.</span><span class="sxs-lookup"><span data-stu-id="024d1-159">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="024d1-160">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="024d1-160">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="024d1-161">Agregue una nueva tarea script al paquete y cambie su nombre a `ExcelTableExists` .</span><span class="sxs-lookup"><span data-stu-id="024d1-161">Add a new Script task to the package and change its name to `ExcelTableExists`.</span></span>  
  
2.  <span data-ttu-id="024d1-162">En el **Editor de la tarea Script**, en la pestaña **Script**, haga clic en **ReadOnlyVariables** y escriba el valor de propiedad mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="024d1-162">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="024d1-163">Escriba y sepárelos `ExcelTable` `ExcelFile` con comas`.`</span><span class="sxs-lookup"><span data-stu-id="024d1-163">Type `ExcelTable` and `ExcelFile` separated by commas`.`</span></span>  
  
         <span data-ttu-id="024d1-164">O bien</span><span class="sxs-lookup"><span data-stu-id="024d1-164">-or-</span></span>  
  
    -   <span data-ttu-id="024d1-165">Haga clic en el botón de puntos suspensivos (**...**) situado junto al campo de propiedades y, en el cuadro de diálogo **seleccionar variables** , seleccione las `ExcelTable` `ExcelFile` variables y.</span><span class="sxs-lookup"><span data-stu-id="024d1-165">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTable` and `ExcelFile` variables.</span></span>  
  
3.  <span data-ttu-id="024d1-166">Haga clic en **ReadWriteVariables** y escriba el valor de propiedad mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="024d1-166">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="024d1-167">Escriba `ExcelTableExists`.</span><span class="sxs-lookup"><span data-stu-id="024d1-167">Type `ExcelTableExists`.</span></span>  
  
         <span data-ttu-id="024d1-168">O bien</span><span class="sxs-lookup"><span data-stu-id="024d1-168">-or-</span></span>  
  
    -   <span data-ttu-id="024d1-169">Haga clic en el botón de puntos suspensivos (**...**) situado junto al campo de propiedades y, en el cuadro de diálogo **seleccionar variables** , seleccione la `ExcelTableExists` variable.</span><span class="sxs-lookup"><span data-stu-id="024d1-169">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTableExists` variable.</span></span>  
  
4.  <span data-ttu-id="024d1-170">Haga clic en **Modificar script** para abrir el editor de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-170">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="024d1-171">Agregue una referencia al ensamblado `System.Xml` en el proyecto de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-171">Add a reference to the `System.Xml` assembly in the script project.</span></span>  
  
6.  <span data-ttu-id="024d1-172">Agregue instrucciones `Imports` para los espacios de nombres `System.IO` y `System.Data.OleDb` en la parte superior del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-172">Add `Imports` statements for the `System.IO` and `System.Data.OleDb` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="024d1-173">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="024d1-173">Add the following code.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="024d1-174">Código de ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="024d1-174">Example 2 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
    Dim tableToTest As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim excelTables As DataTable  
    Dim excelTable As DataRow  
    Dim currentTable As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    tableToTest = Dts.Variables("ExcelTable").Value.ToString  
  
    Dts.Variables("ExcelTableExists").Value = False  
    If File.Exists(fileToTest) Then  
      connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & fileToTest & _  
        ";Extended Properties=Excel 8.0"  
      excelConnection = New OleDbConnection(connectionString)  
      excelConnection.Open()  
      excelTables = excelConnection.GetSchema("Tables")  
      For Each excelTable In excelTables.Rows  
        currentTable = excelTable.Item("TABLE_NAME").ToString  
        If currentTable = tableToTest Then  
          Dts.Variables("ExcelTableExists").Value = True  
        End If  
      Next  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
    public void Main()  
        {  
            string fileToTest;  
            string tableToTest;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable excelTables;  
            string currentTable;  
  
            fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
            tableToTest = Dts.Variables["ExcelTable"].Value.ToString();  
  
            Dts.Variables["ExcelTableExists"].Value = false;  
            if (File.Exists(fileToTest))  
            {  
                connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + fileToTest + ";Extended Properties=Excel 8.0";  
                excelConnection = new OleDbConnection(connectionString);  
                excelConnection.Open();  
                excelTables = excelConnection.GetSchema("Tables");  
                foreach (DataRow excelTable in excelTables.Rows)  
                {  
                    currentTable = excelTable["TABLE_NAME"].ToString();  
                    if (currentTable == tableToTest)  
                    {  
                        Dts.Variables["ExcelTableExists"].Value = true;  
                    }  
                }  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
}  
```  
  
##  <a name="example-3-description-get-a-list-of-excel-files-in-a-folder"></a><a name="example3"></a> <span data-ttu-id="024d1-175">Descripción de ejemplo 3: obtener una lista de archivos de Excel en una carpeta</span><span class="sxs-lookup"><span data-stu-id="024d1-175">Example 3 Description: Get a List of Excel Files in a Folder</span></span>  
 <span data-ttu-id="024d1-176">En este ejemplo se llena una matriz con la lista de archivos de Excel ubicados en la carpeta especificada del valor de la variable `ExcelFolder` y, a continuación, se copia la matriz en la variable `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="024d1-176">This example fills an array with the list of Excel files found in the folder specified in the value of the `ExcelFolder` variable, and then copies the array into the `ExcelFiles` variable.</span></span> <span data-ttu-id="024d1-177">Puede usar el enumerador de variable para Foreach para iterar sobre los archivos en la matriz.</span><span class="sxs-lookup"><span data-stu-id="024d1-177">You can use the Foreach from Variable enumerator to iterate over the files in the array.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="024d1-178">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="024d1-178">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="024d1-179">Agregue una nueva tarea Script al paquete y cambie su nombre a **GetExcelFiles**.</span><span class="sxs-lookup"><span data-stu-id="024d1-179">Add a new Script task to the package and change its name to **GetExcelFiles**.</span></span>  
  
2.  <span data-ttu-id="024d1-180">Abra el **Editor de la tarea Script**, en la pestaña **Script**, haga clic en **ReadOnlyVariables** y escriba el valor de propiedad mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="024d1-180">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="024d1-181">Escriba `ExcelFolder`</span><span class="sxs-lookup"><span data-stu-id="024d1-181">Type `ExcelFolder`</span></span>  
  
         <span data-ttu-id="024d1-182">O bien</span><span class="sxs-lookup"><span data-stu-id="024d1-182">-or-</span></span>  
  
    -   <span data-ttu-id="024d1-183">Haga clic en el botón de puntos suspensivos (**...**) situado junto al campo de propiedades y, en el cuadro de diálogo **seleccionar variables** , seleccione la variable ExcelFolder.</span><span class="sxs-lookup"><span data-stu-id="024d1-183">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFolder variable.</span></span>  
  
3.  <span data-ttu-id="024d1-184">Haga clic en **ReadWriteVariables** y escriba el valor de propiedad mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="024d1-184">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="024d1-185">Escriba `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="024d1-185">Type `ExcelFiles`.</span></span>  
  
         <span data-ttu-id="024d1-186">O bien</span><span class="sxs-lookup"><span data-stu-id="024d1-186">-or-</span></span>  
  
    -   <span data-ttu-id="024d1-187">Haga clic en el botón de puntos suspensivos (**...**) situado junto al campo de propiedades y, en el cuadro de diálogo **seleccionar variables** , seleccione la variable ExcelFiles.</span><span class="sxs-lookup"><span data-stu-id="024d1-187">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFiles variable.</span></span>  
  
4.  <span data-ttu-id="024d1-188">Haga clic en **Modificar script** para abrir el editor de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-188">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="024d1-189">Agregue una instrucción `Imports` para el espacio de nombres `System.IO` en la parte superior del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-189">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="024d1-190">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="024d1-190">Add the following code.</span></span>  
  
### <a name="example-3-code"></a><span data-ttu-id="024d1-191">Código de ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="024d1-191">Example 3 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const FILE_PATTERN As String = "*.xls"  
  
    Dim excelFolder As String  
    Dim excelFiles As String()  
  
    excelFolder = Dts.Variables("ExcelFolder").Value.ToString  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN)  
  
    Dts.Variables("ExcelFiles").Value = excelFiles  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    const string FILE_PATTERN = "*.xls";  
  
    string excelFolder;  
    string[] excelFiles;  
  
    excelFolder = Dts.Variables["ExcelFolder"].Value.ToString();  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN);  
  
    Dts.Variables["ExcelFiles"].Value = excelFiles;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="024d1-192">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="024d1-192">Alternate Solution</span></span>  
 <span data-ttu-id="024d1-193">En lugar de usar una tarea Script para recopilar una lista de archivos de Excel en una matriz, puede usar también el enumerador de archivos ForEach para iterar sobre todos los archivos de Excel de una carpeta.</span><span class="sxs-lookup"><span data-stu-id="024d1-193">Instead of using a Script task to gather a list of Excel files into an array, you can also use the ForEach File enumerator to iterate over all the Excel files in a folder.</span></span> <span data-ttu-id="024d1-194">Para obtener más información, consulte [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md) (Crear bucles entre archivos y tablas de Excel usando un contenedor de bucles Para cada uno).</span><span class="sxs-lookup"><span data-stu-id="024d1-194">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="example-4-description-get-a-list-of-tables-in-an-excel-file"></a><a name="example4"></a> <span data-ttu-id="024d1-195">Descripción de ejemplo 4: obtener una lista de tablas en un archivo de Excel</span><span class="sxs-lookup"><span data-stu-id="024d1-195">Example 4 Description: Get a List of Tables in an Excel File</span></span>  
 <span data-ttu-id="024d1-196">En este ejemplo se llena una matriz con la lista de hojas de cálculo y rangos con nombre ubicados en el archivo de libro de Excel especificado por el valor de la variable `ExcelFile` y, a continuación, se copia la matriz en la variable `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="024d1-196">This example fills an array with the list of worksheets and named ranges found in the Excel workbook file specified by the value of the `ExcelFile` variable, and then copies the array into the `ExcelTables` variable.</span></span> <span data-ttu-id="024d1-197">Puede usar el enumerador de variable para Foreach para iterar sobre las tablas en la matriz.</span><span class="sxs-lookup"><span data-stu-id="024d1-197">You can use the Foreach from Variable Enumerator to iterate over the tables in the array.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="024d1-198">La lista de tablas de un libro de Excel incluye tanto hojas (que tienen el sufijo $) como rangos con nombre.</span><span class="sxs-lookup"><span data-stu-id="024d1-198">The list of tables in an Excel workbook includes both worksheets (which have the $ suffix) and named ranges.</span></span> <span data-ttu-id="024d1-199">Si tiene que filtrar la lista para obtener solo las hojas o solo los rangos con nombre, agregue código adicional para este fin.</span><span class="sxs-lookup"><span data-stu-id="024d1-199">If you have to filter the list for only worksheets or only named ranges, you may have to add additional code for this purpose.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="024d1-200">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="024d1-200">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="024d1-201">Agregue una nueva tarea Script al paquete y cambie su nombre a **GetExcelTables**.</span><span class="sxs-lookup"><span data-stu-id="024d1-201">Add a new Script task to the package and change its name to **GetExcelTables**.</span></span>  
  
2.  <span data-ttu-id="024d1-202">Abra el **Editor de la tarea Script**, en la pestaña **Script**, haga clic en **ReadOnlyVariables** y escriba el valor de propiedad mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="024d1-202">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="024d1-203">Escriba `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="024d1-203">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="024d1-204">O bien</span><span class="sxs-lookup"><span data-stu-id="024d1-204">-or-</span></span>  
  
    -   <span data-ttu-id="024d1-205">Haga clic en el botón de puntos suspensivos (**...**) situado junto al campo de propiedades y, en el cuadro de diálogo **seleccionar variables** , seleccione la variable ExcelFile.</span><span class="sxs-lookup"><span data-stu-id="024d1-205">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFile variable.</span></span>  
  
3.  <span data-ttu-id="024d1-206">Haga clic en **ReadWriteVariables** y escriba el valor de propiedad mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="024d1-206">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="024d1-207">Escriba `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="024d1-207">Type `ExcelTables`.</span></span>  
  
         <span data-ttu-id="024d1-208">O bien</span><span class="sxs-lookup"><span data-stu-id="024d1-208">-or-</span></span>  
  
    -   <span data-ttu-id="024d1-209">Haga clic en el botón de puntos suspensivos (**...**) situado junto al campo de propiedades y, en el cuadro de diálogo **seleccionar variables** , seleccione el ExcelTablesvariable.</span><span class="sxs-lookup"><span data-stu-id="024d1-209">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelTablesvariable.</span></span>  
  
4.  <span data-ttu-id="024d1-210">Haga clic en **Modificar script** para abrir el editor de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-210">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="024d1-211">Agregue una referencia al espacio de nombres `System.Xml` en el proyecto de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-211">Add a reference to the `System.Xml` namespace in the script project.</span></span>  
  
6.  <span data-ttu-id="024d1-212">Agregue una instrucción `Imports` para el espacio de nombres `System.Data.OleDb` en la parte superior del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-212">Add an `Imports` statement for the `System.Data.OleDb` namespace at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="024d1-213">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="024d1-213">Add the following code.</span></span>  
  
### <a name="example-4-code"></a><span data-ttu-id="024d1-214">Código de ejemplo 4</span><span class="sxs-lookup"><span data-stu-id="024d1-214">Example 4 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim excelFile As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim tablesInFile As DataTable  
    Dim tableCount As Integer = 0  
    Dim tableInFile As DataRow  
    Dim currentTable As String  
    Dim tableIndex As Integer = 0  
  
    Dim excelTables As String()  
  
    excelFile = Dts.Variables("ExcelFile").Value.ToString  
    connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & excelFile & _  
        ";Extended Properties=Excel 8.0"  
    excelConnection = New OleDbConnection(connectionString)  
    excelConnection.Open()  
    tablesInFile = excelConnection.GetSchema("Tables")  
    tableCount = tablesInFile.Rows.Count  
    ReDim excelTables(tableCount - 1)  
    For Each tableInFile In tablesInFile.Rows  
      currentTable = tableInFile.Item("TABLE_NAME").ToString  
      excelTables(tableIndex) = currentTable  
      tableIndex += 1  
    Next  
  
    Dts.Variables("ExcelTables").Value = excelTables  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            string excelFile;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable tablesInFile;  
            int tableCount = 0;  
            string currentTable;  
            int tableIndex = 0;  
  
            string[] excelTables = new string[5];  
  
            excelFile = Dts.Variables["ExcelFile"].Value.ToString();  
            connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + excelFile + ";Extended Properties=Excel 8.0";  
            excelConnection = new OleDbConnection(connectionString);  
            excelConnection.Open();  
            tablesInFile = excelConnection.GetSchema("Tables");  
            tableCount = tablesInFile.Rows.Count;  
  
            foreach (DataRow tableInFile in tablesInFile.Rows)  
            {  
                currentTable = tableInFile["TABLE_NAME"].ToString();  
                excelTables[tableIndex] = currentTable;  
                tableIndex += 1;  
            }  
  
            Dts.Variables["ExcelTables"].Value = excelTables;  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="024d1-215">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="024d1-215">Alternate Solution</span></span>  
 <span data-ttu-id="024d1-216">En lugar de usar una tarea Script para recopilar una lista de tablas Excel en una matriz, puede usar también el enumerador de conjunto de filas de esquema para Foreach de ADO.NET para iterar sobre todas las tablas (es decir, hojas de cálculo y rangos con nombre) en un archivo de libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="024d1-216">Instead of using a Script task to gather a list of Excel tables into an array, you can also use the ForEach ADO.NET Schema Rowset Enumerator to iterate over all the tables (that is, worksheets and named ranges) in an Excel workbook file.</span></span> <span data-ttu-id="024d1-217">Para obtener más información, consulte [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md) (Crear bucles entre archivos y tablas de Excel usando un contenedor de bucles Para cada uno).</span><span class="sxs-lookup"><span data-stu-id="024d1-217">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="displaying-the-results-of-the-samples"></a><a name="testing"></a><span data-ttu-id="024d1-218">Mostrar los resultados de los ejemplos</span><span class="sxs-lookup"><span data-stu-id="024d1-218">Displaying the Results of the Samples</span></span>  
 <span data-ttu-id="024d1-219">Si ha configurado cada uno de los ejemplos de este tema en el mismo paquete, puede conectar todas las tareas Script a una tarea Script adicional que muestra la salida de todos los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="024d1-219">If you have configured each of the examples in this topic in the same package, you can connect all the Script tasks to an additional Script task that displays the output of all the examples.</span></span>  
  
#### <a name="to-configure-a-script-task-to-display-the-output-of-the-examples-in-this-topic"></a><span data-ttu-id="024d1-220">Para configurar una tarea Script para mostrar la salida de los ejemplos de este tema</span><span class="sxs-lookup"><span data-stu-id="024d1-220">To configure a Script task to display the output of the examples in this topic</span></span>  
  
1.  <span data-ttu-id="024d1-221">Agregue una nueva tarea Script al paquete y cambie su nombre a **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="024d1-221">Add a new Script task to the package and change its name to **DisplayResults**.</span></span>  
  
2.  <span data-ttu-id="024d1-222">Conecte entre sí cada una de las tareas Script de los cuatro ejemplos, de manera que cada tarea se ejecute después de que la tarea anterior se complete correctamente, y conecte la tarea del ejemplo cuatro a la tarea **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="024d1-222">Connect each of the four example Script tasks to one another, so that each task runs after the preceding task completes successfully, and connect the fourth example task to the **DisplayResults** task.</span></span>  
  
3.  <span data-ttu-id="024d1-223">Abra la tarea **DisplayResults** del **Editor de la tarea Script**.</span><span class="sxs-lookup"><span data-stu-id="024d1-223">Open the **DisplayResults** task in the **Script Task Editor**.</span></span>  
  
4.  <span data-ttu-id="024d1-224">En la pestaña **Script**, haga clic en **ReadOnlyVariables** y use uno de los métodos siguientes para agregar las siete variables enumeradas en [Configurar un paquete para probar los ejemplos](#configuring):</span><span class="sxs-lookup"><span data-stu-id="024d1-224">On the **Script** tab, click **ReadOnlyVariables** and use one of the following methods to add all seven variables listed in [Configuring a Package to Test the Samples](#configuring):</span></span>  
  
    -   <span data-ttu-id="024d1-225">Escriba el nombre de cada variable separado por comas.</span><span class="sxs-lookup"><span data-stu-id="024d1-225">Type the name of each variable separated by commas.</span></span>  
  
         <span data-ttu-id="024d1-226">O bien</span><span class="sxs-lookup"><span data-stu-id="024d1-226">-or-</span></span>  
  
    -   <span data-ttu-id="024d1-227">Haga clic en el botón de puntos suspensivos (**...**) situado junto al campo de propiedades y, en el cuadro de diálogo **seleccionar variables** , seleccione las variables.</span><span class="sxs-lookup"><span data-stu-id="024d1-227">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, selecting the variables.</span></span>  
  
5.  <span data-ttu-id="024d1-228">Haga clic en **Modificar script** para abrir el editor de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-228">Click **Edit Script** to open the script editor.</span></span>  
  
6.  <span data-ttu-id="024d1-229">Agregue instrucciones `Imports` para los espacios de nombres `Microsoft.VisualBasic` y `System.Windows.Forms` en la parte superior del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="024d1-229">Add `Imports` statements for the `Microsoft.VisualBasic` and `System.Windows.Forms` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="024d1-230">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="024d1-230">Add the following code.</span></span>  
  
8.  <span data-ttu-id="024d1-231">Ejecute el paquete y examine los resultados que aparecen en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="024d1-231">Run the package and examine the results displayed in a message box.</span></span>  
  
### <a name="code-to-display-the-results"></a><span data-ttu-id="024d1-232">Código para mostrar los resultados</span><span class="sxs-lookup"><span data-stu-id="024d1-232">Code to Display the Results</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const EOL As String = ControlChars.CrLf  
  
    Dim results As String  
    Dim filesInFolder As String()  
    Dim fileInFolder As String  
    Dim tablesInFile As String()  
    Dim tableInFile As String  
  
    results = _  
      "Final values of variables:" & EOL & _  
      "ExcelFile: " & Dts.Variables("ExcelFile").Value.ToString & EOL & _  
      "ExcelFileExists: " & Dts.Variables("ExcelFileExists").Value.ToString & EOL & _  
      "ExcelTable: " & Dts.Variables("ExcelTable").Value.ToString & EOL & _  
      "ExcelTableExists: " & Dts.Variables("ExcelTableExists").Value.ToString & EOL & _  
      "ExcelFolder: " & Dts.Variables("ExcelFolder").Value.ToString & EOL & _  
      EOL  
  
    results &= "Excel files in folder: " & EOL  
    filesInFolder = DirectCast(Dts.Variables("ExcelFiles").Value, String())  
    For Each fileInFolder In filesInFolder  
      results &= " " & fileInFolder & EOL  
    Next  
    results &= EOL  
  
    results &= "Excel tables in file: " & EOL  
    tablesInFile = DirectCast(Dts.Variables("ExcelTables").Value, String())  
    For Each tableInFile In tablesInFile  
      results &= " " & tableInFile & EOL  
    Next  
  
    MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information)  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            const string EOL = "\r";  
  
            string results;  
            string[] filesInFolder;  
            //string fileInFolder;  
            string[] tablesInFile;  
            //string tableInFile;  
  
            results = "Final values of variables:" + EOL + "ExcelFile: " + Dts.Variables["ExcelFile"].Value.ToString() + EOL + "ExcelFileExists: " + Dts.Variables["ExcelFileExists"].Value.ToString() + EOL + "ExcelTable: " + Dts.Variables["ExcelTable"].Value.ToString() + EOL + "ExcelTableExists: " + Dts.Variables["ExcelTableExists"].Value.ToString() + EOL + "ExcelFolder: " + Dts.Variables["ExcelFolder"].Value.ToString() + EOL + EOL;  
  
            results += "Excel files in folder: " + EOL;  
            filesInFolder = (string[])(Dts.Variables["ExcelFiles"].Value);  
            foreach (string fileInFolder in filesInFolder)  
            {  
                results += " " + fileInFolder + EOL;  
            }  
            results += EOL;  
  
            results += "Excel tables in file: " + EOL;  
            tablesInFile = (string[])(Dts.Variables["ExcelTables"].Value);  
            foreach (string tableInFile in tablesInFile)  
            {  
                results += " " + tableInFile + EOL;  
            }  
  
            MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
<span data-ttu-id="024d1-233">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="024d1-233">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="024d1-234">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="024d1-234">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="024d1-235">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="024d1-235">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="024d1-236">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="024d1-236">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="024d1-237">Consulte también</span><span class="sxs-lookup"><span data-stu-id="024d1-237">See Also</span></span>  
 <span data-ttu-id="024d1-238">[Administrador de conexiones con Excel](../connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="024d1-238">[Excel Connection Manager](../connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="024d1-239">Crear bucles entre archivos y tablas de Excel mediante un contenedor de bucles ForEach</span><span class="sxs-lookup"><span data-stu-id="024d1-239">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
  
