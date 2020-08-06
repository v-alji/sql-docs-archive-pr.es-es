---
title: Analizar formatos de archivo de texto no estándar con el componente de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- text file reading [Integration Services]
- Script component [Integration Services], non-standard text file formats
- transformations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: 1fda034d-09e4-4647-9a9f-e8d508c2cc8f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a0ca1a0d10bdad40d39a366864a07d2b0a61d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744776"
---
# <a name="parsing-non-standard-text-file-formats-with-the-script-component"></a><span data-ttu-id="33617-102">Analizar formatos de archivo de texto no estándar con el componente de script</span><span class="sxs-lookup"><span data-stu-id="33617-102">Parsing Non-Standard Text File Formats with the Script Component</span></span>
  <span data-ttu-id="33617-103">Cuando los datos de origen están organizados en un formato no estándar, puede resultar más cómodo consolidar toda la lógica de análisis en un único script que encadenar varias transformaciones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="33617-103">When your source data is arranged in a non-standard format, you may find it more convenient to consolidate all your parsing logic in a single script than to chain together multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] transformations to achieve the same result.</span></span>  
  
 [<span data-ttu-id="33617-104">Ejemplo 1: Analizar registros delimitados por fila</span><span class="sxs-lookup"><span data-stu-id="33617-104">Example 1: Parsing Row-Delimited Records</span></span>](#example1)  
  
 [<span data-ttu-id="33617-105">Ejemplo 2: Dividir registros primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="33617-105">Example 2: Splitting Parent and Child Records</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="33617-106">Si desea crear un componente que pueda reutilizar más fácilmente en varias tareas de flujo de datos y varios paquetes, puede utilizar el código de este ejemplo de componente de script como punto de inicio para el componente de flujo de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="33617-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="33617-107">Para obtener más información, vea [Desarrollar un componente de flujo de datos personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="33617-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
##  <a name="example-1-parsing-row-delimited-records"></a><a name="example1"></a> <span data-ttu-id="33617-108">Ejemplo 1: Analizar registros delimitados por fila</span><span class="sxs-lookup"><span data-stu-id="33617-108">Example 1: Parsing Row-Delimited Records</span></span>  
 <span data-ttu-id="33617-109">En este ejemplo se muestra cómo tomar un archivo de texto en el que cada columna de datos aparece en una línea independiente y analizarlo en una tabla de destino utilizando el componente de script.</span><span class="sxs-lookup"><span data-stu-id="33617-109">This example shows how to take a text file in which each column of data appears on a separate line and parse it into a destination table by using the Script component.</span></span>  
  
 <span data-ttu-id="33617-110">Para obtener más información sobre cómo configurar el componente de script para su uso como una transformación en el flujo de datos, vea [crear una transformación sincrónica con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)y [crear una transformación asincrónica con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="33617-110">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="33617-111">Para configurar este ejemplo de componente de script</span><span class="sxs-lookup"><span data-stu-id="33617-111">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="33617-112">Cree y guarde un archivo de texto denominado **rowdelimiteddata.txt** que contenga los siguientes datos de origen:</span><span class="sxs-lookup"><span data-stu-id="33617-112">Create and save a text file named **rowdelimiteddata.txt** that contains the following source data:</span></span>  
  
    ```  
    FirstName: Nancy  
    LastName: Davolio  
    Title: Sales Representative  
    City: Seattle  
    StateProvince: WA  
  
    FirstName: Andrew  
    LastName: Fuller  
    Title: Vice President, Sales  
    City: Tacoma  
    StateProvince: WA  
  
    FirstName: Steven  
    LastName: Buchanan  
    Title: Sales Manager  
    City: London  
    StateProvince:  
  
    ```  
  
2.  <span data-ttu-id="33617-113">Abra [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33617-113">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="33617-114">Seleccione una base de datos de destino y abra una nueva ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="33617-114">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="33617-115">En la ventana de consulta, ejecute el siguiente script para crear la tabla de destino:</span><span class="sxs-lookup"><span data-stu-id="33617-115">In the query window, execute the following script to create the destination table:</span></span>  
  
    ```  
    create table RowDelimitedData  
    (  
    FirstName varchar(32),  
    LastName varchar(32),  
    Title varchar(32),  
    City varchar(32),  
    StateProvince varchar(32)  
    )  
  
    ```  
  
4.  <span data-ttu-id="33617-116">Abra [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] y cree un nuevo paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] denominado ParseRowDelim.dtsx.</span><span class="sxs-lookup"><span data-stu-id="33617-116">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named ParseRowDelim.dtsx.</span></span>  
  
5.  <span data-ttu-id="33617-117">Agregue un administrador de conexiones de archivos planos al paquete, denomínelo RowDelimitedData y configúrelo para conectarse al archivo rowdelimiteddata.txt que creó en un paso anterior.</span><span class="sxs-lookup"><span data-stu-id="33617-117">Add a Flat File connection manager to the package, name it RowDelimitedData, and configure it to connect to the rowdelimiteddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="33617-118">Agregue un administrador de conexiones OLE DB al paquete y configúrelo para conectarse a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y a la base de datos donde creó la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="33617-118">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination table.</span></span>  
  
7.  <span data-ttu-id="33617-119">Agregue una tarea de flujo de datos al paquete y haga clic en la pestaña **Flujo de datos** del Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="33617-119">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="33617-120">Agregue un origen de archivo plano al flujo de datos y configúrelo para utilizar el administrador de conexiones RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="33617-120">Add a Flat File Source to the data flow and configure it to use the RowDelimitedData connection manager.</span></span> <span data-ttu-id="33617-121">En la página **Columnas** del **Editor de origen de archivos planos**, seleccione la única columna externa disponible.</span><span class="sxs-lookup"><span data-stu-id="33617-121">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="33617-122">Agregue un componente de script al flujo de datos y configúrelo como una transformación.</span><span class="sxs-lookup"><span data-stu-id="33617-122">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="33617-123">Conecte la salida del origen de archivo plano al componente de script.</span><span class="sxs-lookup"><span data-stu-id="33617-123">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="33617-124">Haga doble clic en el componente de script para mostrar el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="33617-124">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="33617-125">En la página **Columnas de entrada** del **Editor de transformación Script**, seleccione la única columna de entrada disponible.</span><span class="sxs-lookup"><span data-stu-id="33617-125">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="33617-126">En la página **entradas y salidas** del **Editor de script de transformación**, seleccione salida 0 y establezca su `SynchronousInputID` en ninguno.</span><span class="sxs-lookup"><span data-stu-id="33617-126">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0 and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="33617-127">Cree 5 columnas de salida, todas del tipo cadena [DT_STR] con una longitud de 32:</span><span class="sxs-lookup"><span data-stu-id="33617-127">Create 5 output columns, all of type string [DT_STR] with a length of 32:</span></span>  
  
    -   <span data-ttu-id="33617-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="33617-128">FirstName</span></span>  
  
    -   <span data-ttu-id="33617-129">Apellidos</span><span class="sxs-lookup"><span data-stu-id="33617-129">LastName</span></span>  
  
    -   <span data-ttu-id="33617-130">Título</span><span class="sxs-lookup"><span data-stu-id="33617-130">Title</span></span>  
  
    -   <span data-ttu-id="33617-131">City</span><span class="sxs-lookup"><span data-stu-id="33617-131">City</span></span>  
  
    -   <span data-ttu-id="33617-132">StateProvince</span><span class="sxs-lookup"><span data-stu-id="33617-132">StateProvince</span></span>  
  
13. <span data-ttu-id="33617-133">En la página **script** del **Editor de script de transformación**, haga clic en **Editar script** y escriba el código que se muestra en la `ScriptMain` clase del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="33617-133">On the **Script** page of the **Script Transformation Editor**, click **Edit Script** and enter the code shown in the `ScriptMain` class of the example.</span></span> <span data-ttu-id="33617-134">Cierre el entorno de desarrollo de script y el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="33617-134">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
14. <span data-ttu-id="33617-135">Agregue un destino de SQL Server al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="33617-135">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="33617-136">Configúrelo para utilizar el administrador de conexiones OLE DB y la tabla RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="33617-136">Configure it to use the OLE DB connection manager and the RowDelimitedData table.</span></span> <span data-ttu-id="33617-137">Conecte la salida del componente de script a este destino.</span><span class="sxs-lookup"><span data-stu-id="33617-137">Connect the output of the Script Component to this destination.</span></span>  
  
15. <span data-ttu-id="33617-138">Ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="33617-138">Run the package.</span></span> <span data-ttu-id="33617-139">Después de que el paquete haya finalizado, examine los registros en la tabla de destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33617-139">After the package has finished, examine the records in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination table.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Dim columnName As String  
    Dim columnValue As String  
  
    ' Check for an empty row.  
    If Row.Column0.Trim.Length > 0 Then  
        columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"))  
        ' Check for an empty value after the colon.  
        If Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd.Length > 1 Then  
            ' Extract the column value from after the colon and space.  
            columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2)  
            Select Case columnName  
                Case "FirstName"  
                    ' The FirstName value indicates a new record.  
                    Me.Output0Buffer.AddRow()  
                    Me.Output0Buffer.FirstName = columnValue  
                Case "LastName"  
                    Me.Output0Buffer.LastName = columnValue  
                Case "Title"  
                    Me.Output0Buffer.Title = columnValue  
                Case "City"  
                    Me.Output0Buffer.City = columnValue  
                Case "StateProvince"  
                    Me.Output0Buffer.StateProvince = columnValue  
            End Select  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
        string columnName;  
        string columnValue;  
  
        // Check for an empty row.  
        if (Row.Column0.Trim().Length > 0)  
        {  
            columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"));  
            // Check for an empty value after the colon.  
            if (Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd().Length > 1)  
            // Extract the column value from after the colon and space.  
            {  
                columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2);  
                switch (columnName)  
                {  
                    case "FirstName":  
                        // The FirstName value indicates a new record.  
                        this.Output0Buffer.AddRow();  
                        this.Output0Buffer.FirstName = columnValue;  
                        break;  
                    case "LastName":  
                        this.Output0Buffer.LastName = columnValue;  
                        break;  
                    case "Title":  
                        this.Output0Buffer.Title = columnValue;  
                        break;  
                    case "City":  
                        this.Output0Buffer.City = columnValue;  
                        break;  
                    case "StateProvince":  
                        this.Output0Buffer.StateProvince = columnValue;  
                        break;  
                }  
            }  
        }  
  
    }  
```  
  
##  <a name="example-2-splitting-parent-and-child-records"></a><a name="example2"></a> <span data-ttu-id="33617-140">Ejemplo 2: Dividir registros primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="33617-140">Example 2: Splitting Parent and Child Records</span></span>  
 <span data-ttu-id="33617-141">Este ejemplo muestra cómo tomar un archivo de texto, en el que una fila de separación precede a una fila de registro primario a la que siguen un número indefinido de filas de registro secundario, y cómo analizarlo en tablas de destino primarias y secundarias correctamente normalizadas mediante el componente de script.</span><span class="sxs-lookup"><span data-stu-id="33617-141">This example shows how to take a text file, in which a separator row precedes a parent record row that is followed by an indefinite number of child record rows, and parse it into properly normalized parent and child destination tables by using the Script component.</span></span> <span data-ttu-id="33617-142">Este sencillo ejemplo se puede adaptar fácilmente a archivos de origen que utilizan más de una fila o columna para cada registro primario y secundario, siempre que exista una forma de identificar el principio y el final de cada registro.</span><span class="sxs-lookup"><span data-stu-id="33617-142">This simple example could easily be adapted for source files that use more than one row or column for each parent and child record, as long as there is some way to identify the beginning and end of each record.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="33617-143">El único fin de este ejemplo es usarlo para realizar una demostración.</span><span class="sxs-lookup"><span data-stu-id="33617-143">This sample is intended for demonstration purposes only.</span></span> <span data-ttu-id="33617-144">Si ejecuta más de una vez el ejemplo, se insertan valores de clave duplicados en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="33617-144">If you run the sample more than once, it inserts duplicate key values into the destination table.</span></span>  
  
 <span data-ttu-id="33617-145">Para obtener más información sobre cómo configurar el componente de script para su uso como una transformación en el flujo de datos, vea [crear una transformación sincrónica con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)y [crear una transformación asincrónica con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="33617-145">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="33617-146">Para configurar este ejemplo de componente de script</span><span class="sxs-lookup"><span data-stu-id="33617-146">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="33617-147">Cree y guarde un archivo de texto denominado **prentchilddata.txt** que contenga los siguientes datos de origen:</span><span class="sxs-lookup"><span data-stu-id="33617-147">Create and save a text file named **parentchilddata.txt** that contains the following source data:</span></span>  
  
    ```  
    **********  
    PARENT 1 DATA  
    child 1 data  
    child 2 data  
    child 3 data  
    child 4 data  
    **********  
    PARENT 2 DATA  
    child 5 data  
    child 6 data  
    child 7 data  
    child 8 data  
    **********  
  
    ```  
  
2.  <span data-ttu-id="33617-148">Abra [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33617-148">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="33617-149">Seleccione una base de datos de destino y abra una nueva ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="33617-149">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="33617-150">En la ventana de consulta, ejecute el siguiente script para crear las tablas de destino:</span><span class="sxs-lookup"><span data-stu-id="33617-150">In the query window, execute the following script to create the destination tables:</span></span>  
  
    ```  
    CREATE TABLE [dbo].[Parents]([ParentID] [int] NOT NULL,  
    [ParentRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Parents] PRIMARY KEY CLUSTERED   
    ([ParentID] ASC))  
    GO  
    CREATE TABLE [dbo].[Children]([ChildID] [int] NOT NULL,  
    [ParentID] [int] NOT NULL,  
    [ChildRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Children] PRIMARY KEY CLUSTERED   
    ([ChildID] ASC))  
    GO  
    ALTER TABLE [dbo].[Children] ADD CONSTRAINT [FK_Children_Parents] FOREIGN KEY([ParentID])  
    REFERENCES [dbo].[Parents] ([ParentID])  
  
    ```  
  
4.  <span data-ttu-id="33617-151">Abra [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] y cree un nuevo paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] denominado SplitParentChild.dtsx.</span><span class="sxs-lookup"><span data-stu-id="33617-151">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named SplitParentChild.dtsx.</span></span>  
  
5.  <span data-ttu-id="33617-152">Agregue un administrador de conexiones de archivos planos al paquete, denomínelo ParentChildData y configúrelo para conectarse al archivo parentchilddata.txt que creó en un paso anterior.</span><span class="sxs-lookup"><span data-stu-id="33617-152">Add a Flat File connection manager to the package, name it ParentChildData, and configure it to connect to the parentchilddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="33617-153">Agregue un administrador de conexiones OLE DB al paquete y configúrelo para conectarse a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y a la base de datos donde creó las tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="33617-153">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination tables.</span></span>  
  
7.  <span data-ttu-id="33617-154">Agregue una tarea de flujo de datos al paquete y haga clic en la pestaña **Flujo de datos** del Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="33617-154">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="33617-155">Agregue un origen de archivo plano al flujo de datos y configúrelo para utilizar el administrador de conexiones ParentChildData.</span><span class="sxs-lookup"><span data-stu-id="33617-155">Add a Flat File Source to the data flow and configure it to use the ParentChildData connection manager.</span></span> <span data-ttu-id="33617-156">En la página **Columnas** del **Editor de origen de archivos planos**, seleccione la única columna externa disponible.</span><span class="sxs-lookup"><span data-stu-id="33617-156">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="33617-157">Agregue un componente de script al flujo de datos y configúrelo como una transformación.</span><span class="sxs-lookup"><span data-stu-id="33617-157">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="33617-158">Conecte la salida del origen de archivo plano al componente de script.</span><span class="sxs-lookup"><span data-stu-id="33617-158">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="33617-159">Haga doble clic en el componente de script para mostrar el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="33617-159">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="33617-160">En la página **Columnas de entrada** del **Editor de transformación Script**, seleccione la única columna de entrada disponible.</span><span class="sxs-lookup"><span data-stu-id="33617-160">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="33617-161">En la página **entradas y salidas** del **Editor de script de transformación**, seleccione salida 0, cambie su nombre a ParentRecords y establezca su `SynchronousInputID` en ninguno.</span><span class="sxs-lookup"><span data-stu-id="33617-161">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0, rename it to ParentRecords, and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="33617-162">Cree 2 columnas de salida:</span><span class="sxs-lookup"><span data-stu-id="33617-162">Create 2 output columns:</span></span>  
  
    -   <span data-ttu-id="33617-163">ParentID (la clave principal), de tipo entero de cuatro bytes con signo [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="33617-163">ParentID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="33617-164">ParentRecord, de tipo cadena [DT_STR] con una longitud de 32.</span><span class="sxs-lookup"><span data-stu-id="33617-164">ParentRecord, of type string [DT_STR] with a length of 32.</span></span>  
  
13. <span data-ttu-id="33617-165">Cree una segunda salida y denomínela ChildRecords.</span><span class="sxs-lookup"><span data-stu-id="33617-165">Create a second output and name it ChildRecords.</span></span> <span data-ttu-id="33617-166">El valor `SynchronousInputID` de la nueva salida ya está establecido en Ninguno.</span><span class="sxs-lookup"><span data-stu-id="33617-166">The `SynchronousInputID` of the new output is already set to None.</span></span> <span data-ttu-id="33617-167">Cree 3 columnas de salida:</span><span class="sxs-lookup"><span data-stu-id="33617-167">Create 3 output columns:</span></span>  
  
    -   <span data-ttu-id="33617-168">ChildID (la clave principal), de tipo entero de cuatro bytes con signo [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="33617-168">ChildID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="33617-169">ParentID (la clave externa), también de tipo entero de cuatro bytes con signo [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="33617-169">ParentID (the foreign key), also of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="33617-170">ChildRecord, de tipo cadena [DT_STR] con una longitud de 50.</span><span class="sxs-lookup"><span data-stu-id="33617-170">ChildRecord, of type string [DT_STR] with a length of 50</span></span>  
  
14. <span data-ttu-id="33617-171">En la página **Script** del **Editor de transformación Script**, haga clic en **Editar script**.</span><span class="sxs-lookup"><span data-stu-id="33617-171">On the **Script** page of the **Script Transformation Editor**, click **Edit Script**.</span></span> <span data-ttu-id="33617-172">En la clase `ScriptMain`, escriba el código mostrado en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="33617-172">In the `ScriptMain` class, enter the code shown in the example.</span></span> <span data-ttu-id="33617-173">Cierre el entorno de desarrollo de script y el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="33617-173">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
15. <span data-ttu-id="33617-174">Agregue un destino de SQL Server al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="33617-174">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="33617-175">Conecte la salida ParentRecords del componente de script a este destino. Configúrela para utilizar el administrador de conexiones OLE DB y la tabla Parents.</span><span class="sxs-lookup"><span data-stu-id="33617-175">Connect the ParentRecords output of the Script Component to this destination.Configure it to use the OLE DB connection manager and the Parents table.</span></span>  
  
16. <span data-ttu-id="33617-176">Agregue otro destino de SQL Server al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="33617-176">Add another SQL Server Destination to the data flow.</span></span> <span data-ttu-id="33617-177">Conecte la salida ChildRecords del componente de script a este destino.</span><span class="sxs-lookup"><span data-stu-id="33617-177">Connect the ChildRecords output of the Script Component to this destination.</span></span> <span data-ttu-id="33617-178">Configúrela para utilizar el administrador de conexiones OLE DB y la tabla Children.</span><span class="sxs-lookup"><span data-stu-id="33617-178">Configure it to use the OLE DB connection manager and the Children table.</span></span>  
  
17. <span data-ttu-id="33617-179">Ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="33617-179">Run the package.</span></span> <span data-ttu-id="33617-180">Después de que el paquete haya finalizado, examine los registros primarios y secundarios en las dos tablas de destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33617-180">After the package has finished, examine the parent and child records in the two [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination tables.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Static nextRowIsParent As Boolean = False  
    Static parentCounter As Integer = 0  
    Static childCounter As Integer = 0  
  
    ' If current row starts with separator characters,  
    '  then following row contains new parent record.  
    If Row.Column0.StartsWith("***") Then  
        nextRowIsParent = True  
    Else  
        If nextRowIsParent Then  
            ' Current row contains parent record.  
            parentCounter += 1  
            Me.ParentRecordsBuffer.AddRow()  
            Me.ParentRecordsBuffer.ParentID = parentCounter  
            Me.ParentRecordsBuffer.ParentRecord = Row.Column0  
            nextRowIsParent = False  
        Else  
            ' Current row contains child record.  
            childCounter += 1  
            Me.ChildRecordsBuffer.AddRow()  
            Me.ChildRecordsBuffer.ChildID = childCounter  
            Me.ChildRecordsBuffer.ParentID = parentCounter  
            Me.ChildRecordsBuffer.ChildRecord = Row.Column0  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
    int static_Input0_ProcessInputRow_childCounter = 0;  
    int static_Input0_ProcessInputRow_parentCounter = 0;  
    bool static_Input0_ProcessInputRow_nextRowIsParent = false;  
  
        // If current row starts with separator characters,   
        // then following row contains new parent record.   
        if (Row.Column0.StartsWith("***"))  
        {  
            static_Input0_ProcessInputRow_nextRowIsParent = true;  
        }  
        else  
        {  
            if (static_Input0_ProcessInputRow_nextRowIsParent)  
            {  
                // Current row contains parent record.   
                static_Input0_ProcessInputRow_parentCounter += 1;  
                this.ParentRecordsBuffer.AddRow();  
                this.ParentRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ParentRecordsBuffer.ParentRecord = Row.Column0;  
                static_Input0_ProcessInputRow_nextRowIsParent = false;  
            }  
            else  
            {  
                // Current row contains child record.   
                static_Input0_ProcessInputRow_childCounter += 1;  
                this.ChildRecordsBuffer.AddRow();  
                this.ChildRecordsBuffer.ChildID = static_Input0_ProcessInputRow_childCounter;  
                this.ChildRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ChildRecordsBuffer.ChildRecord = Row.Column0;  
            }  
        }  
  
    }  
```  
  
<span data-ttu-id="33617-181">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="33617-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="33617-182">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="33617-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="33617-183">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="33617-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="33617-184">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="33617-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33617-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33617-185">See Also</span></span>  
 [<span data-ttu-id="33617-186">Crear una transformación sincrónica con el componente de script</span><span class="sxs-lookup"><span data-stu-id="33617-186">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)  
 [<span data-ttu-id="33617-187">Crear una transformación asincrónica con el componente de script</span><span class="sxs-lookup"><span data-stu-id="33617-187">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
  
  
