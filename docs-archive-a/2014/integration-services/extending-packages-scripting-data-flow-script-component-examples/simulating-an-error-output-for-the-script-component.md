---
title: Simular una salida de error para el componente de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], error output
- error outputs [Integration Services], Script component
ms.assetid: f8b6ecff-ac99-4231-a0e7-7ce4ad76bad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bed458ce378eb26cd863811b4974b5f39429e1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744775"
---
# <a name="simulating-an-error-output-for-the-script-component"></a><span data-ttu-id="555ff-102">Simular una salida de error para el componente de script</span><span class="sxs-lookup"><span data-stu-id="555ff-102">Simulating an Error Output for the Script Component</span></span>
  <span data-ttu-id="555ff-103">Aunque no puede configurar directamente una salida como una salida de error en el componente de script para el control automático de filas del error, puede reproducir la funcionalidad de una salida de error integrada mediante la creación de una salida adicional y la utilización de una lógica condicional en su script para dirigir las filas a esta salida cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="555ff-103">Although you cannot directly configure an output as an error output in the Script component for automatic handling of error rows, you can reproduce the functionality of a built-in error output by creating an additional output and using conditional logic in your script to direct rows to this output when appropriate.</span></span> <span data-ttu-id="555ff-104">Puede que desee imitar el comportamiento de una salida de error integrada agregando dos columnas de salida adicionales para recibir el número de error y el identificador de la columna en la que se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="555ff-104">You may want to imitate the behavior of a built-in error output by adding two additional output columns to receive the error number and the ID of the column in which an error occurred.</span></span>  
  
 <span data-ttu-id="555ff-105">Si desea agregar la descripción del error que corresponde a un determinado código de error de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] predefinido, puede usar el método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> de la interfaz <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponible a través de la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> del componente de script.</span><span class="sxs-lookup"><span data-stu-id="555ff-105">If you want to add the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code, you can use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the Script component's <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="555ff-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="555ff-106">Example</span></span>  
 <span data-ttu-id="555ff-107">En el ejemplo se utiliza un componente de script configurado como una transformación con dos salidas sincrónicas.</span><span class="sxs-lookup"><span data-stu-id="555ff-107">The example shown here uses a Script component configured as a transformation that has two synchronous outputs.</span></span> <span data-ttu-id="555ff-108">El propósito del componente de script es filtrar las filas que generan un error de los datos de dirección en la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="555ff-108">The purpose of the Script component is to filter error rows from address data in the AdventureWorks sample database.</span></span> <span data-ttu-id="555ff-109">En este ejemplo ficticio se supone que se está preparando una promoción para clientes norteamericanos y es necesario filtrar las direcciones que no se encuentran en Norteamérica.</span><span class="sxs-lookup"><span data-stu-id="555ff-109">This fictitious example assumes that we are preparing a promotion for North American customers and need to filter out addresses that are not located in North America.</span></span>  
  
#### <a name="to-configure-the-example"></a><span data-ttu-id="555ff-110">Para configurar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="555ff-110">To configure the example</span></span>  
  
1.  <span data-ttu-id="555ff-111">Antes de crear el nuevo componente de script, cree un administrador de conexiones y configure un origen de flujo de datos que seleccione datos de la dirección de la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="555ff-111">Before creating the new Script component, create a connection manager and configure a data flow source that selects address data from the AdventureWorks sample database.</span></span> <span data-ttu-id="555ff-112">En este ejemplo, donde solo se examina la columna CountryRegionName, simplemente puede usar la vista Person.vStateCountryProvinceRegion o puede seleccionar los datos combinando las tablas Person.Address, Person.StateProvincey Person.CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="555ff-112">For this example, which only looks at the CountryRegionName column, you can simply use the Person.vStateCountryProvinceRegion view, or you can select data by joining the Person.Address, Person.StateProvince, and Person.CountryRegion tables.</span></span>  
  
2.  <span data-ttu-id="555ff-113">Agregue un nuevo componente de script a la superficie del diseñador de flujo de datos y configúrelo como una transformación.</span><span class="sxs-lookup"><span data-stu-id="555ff-113">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span> <span data-ttu-id="555ff-114">Abra el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="555ff-114">Open the **Script Transformation Editor**.</span></span>  
  
3.  <span data-ttu-id="555ff-115">En la página **Script**, establezca la propiedad **ScriptLanguage** en el lenguaje de script que quiere usar para programar el script.</span><span class="sxs-lookup"><span data-stu-id="555ff-115">On the **Script** page, set the **ScriptLanguage** property to the script language that you want to use to code the script.</span></span>  
  
4.  <span data-ttu-id="555ff-116">Haga clic en **Editar script** para abrir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="555ff-116">Click **Edit Script** to open [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
5.  <span data-ttu-id="555ff-117">En el método `Input0_ProcessInputRow`, escriba o pegue el código de ejemplo que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="555ff-117">In the `Input0_ProcessInputRow` method, type or paste the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="555ff-118">Cierre VSTA.</span><span class="sxs-lookup"><span data-stu-id="555ff-118">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="555ff-119">En la página **Columnas de entrada**, seleccione las columnas que quiere procesar en la transformación Script.</span><span class="sxs-lookup"><span data-stu-id="555ff-119">On the **Input Columns** page, select the columns that you want to process in the Script transformation.</span></span> <span data-ttu-id="555ff-120">En este ejemplo se utiliza únicamente la columna CountryRegionName.</span><span class="sxs-lookup"><span data-stu-id="555ff-120">This example uses only the CountryRegionName column.</span></span> <span data-ttu-id="555ff-121">Las columnas de entrada disponibles que no se seleccionen pasarán simplemente al flujo de datos sin cambios.</span><span class="sxs-lookup"><span data-stu-id="555ff-121">Available input columns that you leave unselected will simply be passed through unchanged in the data flow.</span></span>  
  
8.  <span data-ttu-id="555ff-122">En la página **entradas y salidas** , agregue una nueva y segunda salida, y establezca su `SynchronousInputID` valor en el identificador de la entrada, que también es el valor de la `SynchronousInputID` propiedad de la salida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="555ff-122">On the **Inputs and Outputs** page, add a new, second output, and set its `SynchronousInputID` value to the ID of the input, which is also the value of the `SynchronousInputID` property of the default output.</span></span> <span data-ttu-id="555ff-123">Establezca la propiedad `ExclusionGroup` de ambas salidas en el mismo valor distinto de cero (por ejemplo, 1) para indicar que cada fila se dirigirá únicamente a una de las dos salidas.</span><span class="sxs-lookup"><span data-stu-id="555ff-123">Set the `ExclusionGroup` property of both outputs to the same non-zero value (for example, 1) to indicate that each row will be directed to only one of the two outputs.</span></span> <span data-ttu-id="555ff-124">Asigne un nombre distintivo a la nueva salida de error, como "MyErrorOutput".</span><span class="sxs-lookup"><span data-stu-id="555ff-124">Give the new error output a distinctive name, such as "MyErrorOutput."</span></span>  
  
9. <span data-ttu-id="555ff-125">Agregue las columnas de salida adicionales a la nueva salida de error para capturar la información de error deseada que puede incluir el código de error, el identificador de la columna en la que se produjo el error y, posiblemente, la descripción del error.</span><span class="sxs-lookup"><span data-stu-id="555ff-125">Add additional output columns to the new error output to capture the desired error information, which may include the error code, the ID of the column in which the error occurred, and possibly the error description.</span></span> <span data-ttu-id="555ff-126">En este ejemplo se crean las nuevas columnas, ErrorColumn y ErrorMessage.</span><span class="sxs-lookup"><span data-stu-id="555ff-126">This example creates the new columns, ErrorColumn and ErrorMessage.</span></span> <span data-ttu-id="555ff-127">Si está detectando los errores de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] predefinidos en su propia implementación, asegúrese de agregar una columna ErrorCode para el número de error.</span><span class="sxs-lookup"><span data-stu-id="555ff-127">If you are catching predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] errors in your own implementation, make sure to add an ErrorCode column for the error number.</span></span>  
  
10. <span data-ttu-id="555ff-128">Observe el valor del identificador de la columna o columnas de entrada que el componente de script comprobará para las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="555ff-128">Note the ID value of the input column or columns that the Script component will check for error conditions.</span></span> <span data-ttu-id="555ff-129">En este ejemplo se usa este identificador de columna para rellenar el valor ErrorColumn.</span><span class="sxs-lookup"><span data-stu-id="555ff-129">This example uses this column identifier to populate the ErrorColumn value.</span></span>  
  
11. <span data-ttu-id="555ff-130">Cierre el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="555ff-130">Close the **Script Transformation Editor.**</span></span>  
  
12. <span data-ttu-id="555ff-131">Adjunte las salidas del componente de script a destinos convenientes.</span><span class="sxs-lookup"><span data-stu-id="555ff-131">Attach the outputs of the Script component to suitable destinations.</span></span> <span data-ttu-id="555ff-132">Para pruebas ad hoc, la manera más fácil de configurar es mediante destinos de archivo plano.</span><span class="sxs-lookup"><span data-stu-id="555ff-132">Flat file destinations are the easiest to configure for ad hoc testing.</span></span>  
  
13. <span data-ttu-id="555ff-133">Ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="555ff-133">Run the package.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  If Row.CountryRegionName <> "Canada" _  
      And Row.CountryRegionName <> "United States" Then  
  
    Row.ErrorColumn = 68 ' ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America."  
    Row.DirectRowToMyErrorOutput()  
  
  Else  
  
    Row.DirectRowToOutput0()  
  
  End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
{  
  
  if (Row.CountryRegionName!="Canada"&&Row.CountryRegionName!="United States")  
  
  {  
    Row.ErrorColumn = 68; // ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America.";  
    Row.DirectRowToMyErrorOutput();  
  
  }  
  else  
  {  
  
    Row.DirectRowToOutput0();  
  
  }  
  
}  
```  
  
<span data-ttu-id="555ff-134">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="555ff-134">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="555ff-135">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="555ff-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="555ff-136">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="555ff-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="555ff-137">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="555ff-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="555ff-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="555ff-138">See Also</span></span>  
 <span data-ttu-id="555ff-139">[Control de errores en los datos](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="555ff-139">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="555ff-140">[Usar salidas de error en un componente de flujo de datos](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="555ff-140">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="555ff-141">Crear una transformación sincrónica con el componente de script</span><span class="sxs-lookup"><span data-stu-id="555ff-141">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
