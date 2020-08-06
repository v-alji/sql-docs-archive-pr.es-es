---
title: 'Paso 3: Agregar redirección de flujo de errores | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5683a45d-9e73-4cd5-83ca-fae8b26b488c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ceaea310cba05a940f310c01b52d5f912a53bea8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672171"
---
# <a name="step-3-adding-error-flow-redirection"></a><span data-ttu-id="e23fe-102">Paso 3: Adición de redirección de flujo de errores</span><span class="sxs-lookup"><span data-stu-id="e23fe-102">Step 3: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="e23fe-103">Como se ha mostrado en la tarea anterior, la transformación Lookup Currency Key no puede generar una coincidencia cuando la transformación intenta procesar el archivo plano de ejemplo dañado que ha generado un error.</span><span class="sxs-lookup"><span data-stu-id="e23fe-103">As demonstrated in the previous task, the Lookup Currency Key transformation cannot generate a match when the transformation tries to process the corrupted sample flat file, which produced an error.</span></span> <span data-ttu-id="e23fe-104">Puesto que la transformación utiliza la configuración de salida de error predeterminada, cualquier error da lugar a un error de la transformación.</span><span class="sxs-lookup"><span data-stu-id="e23fe-104">Because the transformation uses the default settings for error output, any error causes the transformation to fail.</span></span> <span data-ttu-id="e23fe-105">Cuando se produce un error en la transformación, también se produce un error en el resto del paquete.</span><span class="sxs-lookup"><span data-stu-id="e23fe-105">When the transformation fails, the rest of the package also fails.</span></span>  
  
 <span data-ttu-id="e23fe-106">En lugar de permitir que se produzca un error en la transformación, puede configurar el componente de modo que la fila que genera el error se redirija a otra ruta de procesamiento mediante la salida de error.</span><span class="sxs-lookup"><span data-stu-id="e23fe-106">Instead of permitting the transformation to fail, you can configure the component to redirect the failed row to another processing path by using the error output.</span></span> <span data-ttu-id="e23fe-107">El uso de una ruta de procesamiento independiente permite hacer varias cosas.</span><span class="sxs-lookup"><span data-stu-id="e23fe-107">Use of a separate error processing path lets you do a number of things.</span></span> <span data-ttu-id="e23fe-108">Por ejemplo, puede intentar eliminar los datos y luego volver a procesar la fila con error.</span><span class="sxs-lookup"><span data-stu-id="e23fe-108">For instance, you might try to clean the data and then reprocess the failed row.</span></span> <span data-ttu-id="e23fe-109">O bien, puede guardar la fila con error junto con otra información adicional sobre el error para comprobarla y procesarla de nuevo más adelante.</span><span class="sxs-lookup"><span data-stu-id="e23fe-109">Or, you might save the failed row along with additional error information for later verification and reprocessing.</span></span>  
  
 <span data-ttu-id="e23fe-110">En esta tarea configurará la transformación Lookup Currency Key para redirigir cualquier fila con errores a la salida de errores.</span><span class="sxs-lookup"><span data-stu-id="e23fe-110">In this task, you will configure the Lookup Currency Key transformation to redirect any rows that fail to the error output.</span></span> <span data-ttu-id="e23fe-111">En la rama de errores del flujo de datos, estas filas se escribirán en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e23fe-111">In the error branch of the data flow, these rows will be written to a file.</span></span>  
  
 <span data-ttu-id="e23fe-112">De forma predeterminada, las dos columnas adicionales en una [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] salida de error, **ErrorCode** y **ErrorColumn**, solo contienen códigos numéricos que representan un número de error y el identificador de la columna en la que se produjo el error.</span><span class="sxs-lookup"><span data-stu-id="e23fe-112">By default the two extra columns in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error output, **ErrorCode** and **ErrorColumn**, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="e23fe-113">Estos valores numéricos pueden tener un uso limitado sin la correspondiente descripción del error.</span><span class="sxs-lookup"><span data-stu-id="e23fe-113">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="e23fe-114">Para mejorar la utilidad de la salida de errores, antes de que el paquete escriba las filas con errores en el archivo, se utilizará un componente de script para obtener acceso a la API de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y obtener una descripción del error.</span><span class="sxs-lookup"><span data-stu-id="e23fe-114">To enhance the usefulness of the error output, before the package writes the failed rows to the file, you will use a Script component to access the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] API and get a description of the error.</span></span>  
  
### <a name="to-configure-an-error-output"></a><span data-ttu-id="e23fe-115">Para configurar una salida de error</span><span class="sxs-lookup"><span data-stu-id="e23fe-115">To configure an error output</span></span>  
  
1.  <span data-ttu-id="e23fe-116">En el **cuadro de herramientas de SSIS**, expanda **común**y, a continuación, arrastre **componente de script** a la superficie de diseño de la pestaña **flujo de datos** . Coloque el **script** a la derecha de la transformación **lookup Currency Key** .</span><span class="sxs-lookup"><span data-stu-id="e23fe-116">In the **SSIS Toolbox**, expand **Common**, and then drag **Script Component** onto the design surface of the **Data Flow** tab. Place **Script** to the right of the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="e23fe-117">En el cuadro de diálogo **Seleccionar el tipo de componente de script** , haga clic en **Transformación**y luego en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e23fe-117">In the **Select Script Component Type** dialog box, click **Transformation**, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="e23fe-118">Haga clic en la transformación **Lookup Currency Key** y luego arrastre la flecha roja hasta la transformación **Script** que acaba de agregar para conectar los dos componentes.</span><span class="sxs-lookup"><span data-stu-id="e23fe-118">Click the **Lookup Currency Key** transformation and then drag the red arrow onto the newly added **Script** transformation to connect the two components.</span></span>  
  
     <span data-ttu-id="e23fe-119">La flecha roja representa la salida de errores de la transformación **Lookup Currency Key** .</span><span class="sxs-lookup"><span data-stu-id="e23fe-119">The red arrow represents the error output of the **Lookup Currency Key** transformation.</span></span> <span data-ttu-id="e23fe-120">Utilizando la flecha roja para conectar la transformación con el componente de script, puede redirigir cualquier error de procesamiento a dicho componente, que, a continuación, lo procesará y enviará al destino.</span><span class="sxs-lookup"><span data-stu-id="e23fe-120">By using the red arrow to connect the transformation to the Script component, you can redirect any processing errors to the Script component, which then processes the errors and sends them to the destination.</span></span>  
  
4.  <span data-ttu-id="e23fe-121">En el cuadro de diálogo **Configurar la salida de errores** , en la columna **Error** , seleccione **Redirigir fila**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e23fe-121">In the **Configure Error Output** dialog box, in the **Error** column, select **Redirect row**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="e23fe-122">En la superficie de diseño **Flujo de datos** , haga clic en **Componente de script** en el **Componente de script**recién agregado y cambie el nombre por **Get Error Description**.</span><span class="sxs-lookup"><span data-stu-id="e23fe-122">On the **Data Flow** design surface, click **Script Component** in the newly added **ScriptComponent**, and change the name to **Get Error Description**.</span></span>  
  
6.  <span data-ttu-id="e23fe-123">Haga doble clic en la transformación **Get Error Description** .</span><span class="sxs-lookup"><span data-stu-id="e23fe-123">Double-click the **Get Error Description** transformation.</span></span>  
  
7.  <span data-ttu-id="e23fe-124">En el cuadro de diálogo **Editor de transformación Script** , en la página **Columnas de entrada** , seleccione la columna **ErrorCode** .</span><span class="sxs-lookup"><span data-stu-id="e23fe-124">In the **Script Transformation Editor** dialog box, on the **Input Columns** page, select the **ErrorCode** column.</span></span>  
  
8.  <span data-ttu-id="e23fe-125">En la página **Entradas y salidas** , expanda **Salida 0**, haga clic en **Columnas de salida**y, a continuación, en **Agregar columna**.</span><span class="sxs-lookup"><span data-stu-id="e23fe-125">On the **Inputs and Outputs** page, expand **Output 0**, click **Output Columns**, and then click **Add Column**.</span></span>  
  
9. <span data-ttu-id="e23fe-126">En la `Name` propiedad, escriba **ErrorDescription** y establezca la `DataType` propiedad en **cadena Unicode [DT_WSTR]**.</span><span class="sxs-lookup"><span data-stu-id="e23fe-126">In the `Name` property, type **ErrorDescription** and set the `DataType` property to **Unicode string [DT_WSTR]**.</span></span>  
  
10. <span data-ttu-id="e23fe-127">En la página **script** , compruebe que la `LocaleID` propiedad está establecida en **Inglés (Estados Unidos.**</span><span class="sxs-lookup"><span data-stu-id="e23fe-127">On the **Script** page, verify that the `LocaleID` property is set to **English (United States.**</span></span>  
  
11. <span data-ttu-id="e23fe-128">Haga clic en **Editar script** para abrir [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="e23fe-128">Click **Edit Script** to open [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="e23fe-129">En el método `Input0_ProcessInputRow`, escriba o pegue el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e23fe-129">In the `Input0_ProcessInputRow` method, type or paste the following code.</span></span>  
  
     <span data-ttu-id="e23fe-130">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="e23fe-130">[Visual Basic]</span></span>  
  
    ```  
    Row.ErrorDescription =   
      Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
    ```  
  
     <span data-ttu-id="e23fe-131">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="e23fe-131">[Visual C#]</span></span>  
  
    ```  
    Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
    ```  
  
     <span data-ttu-id="e23fe-132">La subrutina completada será como el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e23fe-132">The completed subroutine will look like the following code.</span></span>  
  
     <span data-ttu-id="e23fe-133">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="e23fe-133">[Visual Basic]</span></span>  
  
    ```  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
      Row.ErrorDescription =   
        Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
    ```  
  
     <span data-ttu-id="e23fe-134">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="e23fe-134">[Visual C#]</span></span>  
  
    ```  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
        {  
  
            Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
        }  
    ```  
  
12. <span data-ttu-id="e23fe-135">En el menú **Compilar** , haga clic en **Compilar solución** para compilar el script y guardar los cambios y, a continuación, cierre VSTA.</span><span class="sxs-lookup"><span data-stu-id="e23fe-135">On the **Build** menu, click **Build Solution** to build the script and save your changes, and then close VSTA.</span></span>  
  
13. <span data-ttu-id="e23fe-136">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Editor de transformación Script** .</span><span class="sxs-lookup"><span data-stu-id="e23fe-136">Click **OK** to close the **Script Transformation Editor** dialog box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e23fe-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e23fe-137">Next Steps</span></span>  
 <span data-ttu-id="e23fe-138">[Paso 4: agregar un destino de archivo plano] (lesson-4-4-adding-a-flat-file-destination.md</span><span class="sxs-lookup"><span data-stu-id="e23fe-138">[Step 4: Adding a Flat File Destination](lesson-4-4-adding-a-flat-file-destination.md</span></span>  
  
  
