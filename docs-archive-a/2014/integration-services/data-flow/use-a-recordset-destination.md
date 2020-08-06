---
title: Usar un destino de conjunto de registros | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Recordset destination
ms.assetid: a7b143dc-8008-404f-83b0-b45ffbca6029
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34d1d5a7aa76876a9d8718b691b1d24a8835e2e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676069"
---
# <a name="use-a-recordset-destination"></a><span data-ttu-id="42589-102">Usar un destino de conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="42589-102">Use a Recordset Destination</span></span>
  <span data-ttu-id="42589-103">El destino de conjunto de registros no guarda los datos en un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="42589-103">The Recordset destination does not save data to an external data source.</span></span> <span data-ttu-id="42589-104">En su lugar, guarda los datos en memoria, en un conjunto de registros que se almacena en una variable de paquete [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] del tipo de datos `Object`.</span><span class="sxs-lookup"><span data-stu-id="42589-104">Instead, the Recordset destination saves data in memory in a recordset that is stored in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package variable of the `Object` data type.</span></span> <span data-ttu-id="42589-105">Una vez que el destino de conjunto de registros guarda los datos, normalmente se utiliza un contenedor de bucles Foreach con el enumerador de ADO para Foreach para procesar una fila del conjunto de registros cada vez.</span><span class="sxs-lookup"><span data-stu-id="42589-105">After the Recordset destination saves the data, you typically use a Foreach Loop container with the Foreach ADO enumerator to process one row of the recordset at a time.</span></span> <span data-ttu-id="42589-106">El enumerador de ADO para Foreach guarda el valor de cada columna de la fila actual en una variable de paquete independiente.</span><span class="sxs-lookup"><span data-stu-id="42589-106">The Foreach ADO enumerator saves the value from each column of the current row into a separate package variable.</span></span> <span data-ttu-id="42589-107">A continuación, las tareas que se configuran en el contenedor de bucles Foreach leen esos valores de las variables y realizan alguna acción con ellos.</span><span class="sxs-lookup"><span data-stu-id="42589-107">Then, the tasks that you configure inside the Foreach Loop container read those values from the variables and perform some action with them.</span></span>  
  
 <span data-ttu-id="42589-108">Puede utilizar el destino de conjunto de registros en muchos escenarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="42589-108">You can use the Recordset destination in many different scenarios.</span></span> <span data-ttu-id="42589-109">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="42589-109">Here are some examples:</span></span>  
  
-   <span data-ttu-id="42589-110">Puede usar una tarea Enviar correo y el lenguaje de expresiones [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para enviar un mensaje de correo personalizado por cada fila del conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="42589-110">You can use a Send Mail task and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language to send a customized e-mail message for each row in the recordset.</span></span>  
  
-   <span data-ttu-id="42589-111">Puede utilizar un componente de script configurado como origen en una tarea Flujo de datos para leer los valores de las columnas del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="42589-111">You can use a Script component configured as a source, inside a Data Flow task, to read the column values into the columns of the data flow.</span></span> <span data-ttu-id="42589-112">A continuación, puede utilizar transformaciones y destinos para transformar y guardar cada fila.</span><span class="sxs-lookup"><span data-stu-id="42589-112">Then, you can use transformations and destinations to transform and save the row.</span></span> <span data-ttu-id="42589-113">En este ejemplo, la tarea Flujo de datos se ejecuta una vez por cada fila.</span><span class="sxs-lookup"><span data-stu-id="42589-113">In this example, the Data Flow task runs once for each row.</span></span>  
  
 <span data-ttu-id="42589-114">En las secciones siguientes se describe en primer lugar el proceso general de uso del destino de conjunto de registros y, a continuación, se muestra un ejemplo concreto acerca de cómo se utiliza el destino.</span><span class="sxs-lookup"><span data-stu-id="42589-114">The following sections first describe the general process of using the Recordset destination and then show a specific example of how to use the destination.</span></span>  
  
## <a name="general-steps-to-using-a-recordset-destination"></a><span data-ttu-id="42589-115">Pasos generales para utilizar un destino de conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="42589-115">General Steps to Using a Recordset Destination</span></span>  
 <span data-ttu-id="42589-116">El procedimiento siguiente resume los pasos que son necesarios para guardar los datos en un destino de conjunto de registros y utilizar, a continuación, el contenedor de bucles Foreach para procesar cada fila.</span><span class="sxs-lookup"><span data-stu-id="42589-116">The following procedure summarizes the steps that are required to save data to a Recordset destination, and then use the Foreach Loop container to process each row.</span></span>  
  
#### <a name="to-save-data-to-a-recordset-destination-and-process-each-row-by-using-the-foreach-loop-container"></a><span data-ttu-id="42589-117">Para guardar los datos en un destino de conjunto de registros y procesar cada fila utilizando el contenedor de bucles Foreach</span><span class="sxs-lookup"><span data-stu-id="42589-117">To save data to a Recordset destination and process each row by using the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="42589-118">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cree o abra un paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42589-118">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="42589-119">Cree una variable que contendrá el conjunto de registros guardados en la memoria por el destino de conjunto de registros y establezca el tipo de la variable en `Object`.</span><span class="sxs-lookup"><span data-stu-id="42589-119">Create a variable that will contain the recordset saved into memory by the Recordset destination, and set the variable's type to `Object`.</span></span>  
  
3.  <span data-ttu-id="42589-120">Cree variables adicionales de los tipos adecuados para que contengan los valores de cada columna del conjunto de registros que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="42589-120">Create additional variables of the appropriate types to contain the values of each column in the recordset that you want to use.</span></span>  
  
4.  <span data-ttu-id="42589-121">Agregue y configure el administrador de conexiones requerido por el origen de datos que pretende utilizar en su flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="42589-121">Add and configure the connection manager required by the data source that you plan to use in your data flow.</span></span>  
  
5.  <span data-ttu-id="42589-122">Agregue una tarea Flujo de datos al paquete y en la pestaña Flujo de datos del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , configure los orígenes y las transformaciones que se van a utilizar para cargar y transformar los datos.</span><span class="sxs-lookup"><span data-stu-id="42589-122">Add a Data Flow task to the package, and on the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, configure sources and transformations to load and transform the data.</span></span>  
  
6.  <span data-ttu-id="42589-123">Agregue un destino de conjunto de registros al flujo de datos y asócielo con las transformaciones.</span><span class="sxs-lookup"><span data-stu-id="42589-123">Add a Recordset destination to the data flow and connect it to the transformations.</span></span> <span data-ttu-id="42589-124">En la propiedad `VariableName` del destino de conjunto de registros, escriba el nombre de la variable que creó para el conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="42589-124">For the `VariableName` property of the Recordset destination, enter the name of the variable that you created to hold the recordset.</span></span>  
  
7.  <span data-ttu-id="42589-125">En la pestaña Flujo de control del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , agregue un contenedor de bucles Foreach y conecte este contenedor después de la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="42589-125">On the Control Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container and connect this container after the Data Flow task.</span></span> <span data-ttu-id="42589-126">A continuación, abra el **Editor de bucles Foreach** para configurar el contenedor con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="42589-126">Then, open the **Foreach Loop Editor** to configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="42589-127">En la página **Colección** , seleccione el enumerador ADO para Foreach.</span><span class="sxs-lookup"><span data-stu-id="42589-127">On the **Collection** page, select the Foreach ADO Enumerator.</span></span> <span data-ttu-id="42589-128">A continuación, en **Variable de origen de objeto ADO**, seleccione la variable que contiene el conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="42589-128">Then, for **ADO object source variable**, select the variable that contains the recordset.</span></span>  
  
    2.  <span data-ttu-id="42589-129">En la página **Asignaciones de variables** , asigne el índice de base cero de cada columna que quiera usar a la variable adecuada.</span><span class="sxs-lookup"><span data-stu-id="42589-129">On the **Variable Mappings** page, map the zero-based index of each column that you want to use to the appropriate variable.</span></span>  
  
         <span data-ttu-id="42589-130">En cada iteración del bucle, el enumerador rellena estas variables con los valores de columna de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="42589-130">On each iteration of the loop, the enumerator populates these variables with the column values from the current row.</span></span>  
  
8.  <span data-ttu-id="42589-131">Dentro del contenedor de bucles Foreach, agregue y configure las tareas que va a utilizar para procesar una fila del conjunto cada vez al leer los valores de las variables.</span><span class="sxs-lookup"><span data-stu-id="42589-131">Inside the Foreach Loop container, add and configure tasks to process one row of the recordset at a time by reading the values from the variables.</span></span>  
  
## <a name="example-of-using-the-recordset-destination"></a><span data-ttu-id="42589-132">Ejemplo de uso del destino de conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="42589-132">Example of Using the Recordset Destination</span></span>  
 <span data-ttu-id="42589-133">En el ejemplo siguiente, la tarea Flujo de datos carga información sobre los empleados de [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] de la tabla Sales.SalesPerson en un destino de conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="42589-133">In the following example, the Data Flow task loads information about [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] employees from the Sales.SalesPerson table into a Recordset destination.</span></span> <span data-ttu-id="42589-134">A continuación, un contenedor de bucles Foreach lee una fila de datos cada vez y llama a la tarea Enviar correo.</span><span class="sxs-lookup"><span data-stu-id="42589-134">Then, a Foreach Loop container reads one row of data at a time, and calls a Send Mail task.</span></span> <span data-ttu-id="42589-135">La tarea Enviar correo utiliza expresiones para enviar un mensaje de correo electrónico personalizado a cada vendedor sobre el importe de su paga extraordinaria.</span><span class="sxs-lookup"><span data-stu-id="42589-135">The Send Mail task uses expressions to send a customized e-mail message to each salesperson about the amount of his or her bonus.</span></span>  
  
#### <a name="to-create-the-project-and-configure-the-variables"></a><span data-ttu-id="42589-136">Para crear el proyecto y configurar las variables</span><span class="sxs-lookup"><span data-stu-id="42589-136">To create the project and configure the variables</span></span>  
  
1.  <span data-ttu-id="42589-137">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cree un nuevo proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42589-137">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="42589-138">En el menú **SSIS** , seleccione **Variables**.</span><span class="sxs-lookup"><span data-stu-id="42589-138">On the **SSIS** menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="42589-139">En la ventana **Variables** , cree las variables que contendrán el conjunto de registros y los valores de columna de la fila actual:</span><span class="sxs-lookup"><span data-stu-id="42589-139">In the **Variables** window, create the variables that will hold the recordset and the column values from the current row:</span></span>  
  
    1.  <span data-ttu-id="42589-140">Cree una variable con nombre `BonusRecordset` y establezca su tipo en `Object`.</span><span class="sxs-lookup"><span data-stu-id="42589-140">Create a variable named, `BonusRecordset`, and set its type to `Object`.</span></span>  
  
         <span data-ttu-id="42589-141">La variable `BonusRecordset` contiene el conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="42589-141">The `BonusRecordset` variable holds the recordset.</span></span>  
  
    2.  <span data-ttu-id="42589-142">Cree una variable con nombre `EmailAddress` y establezca su tipo en `String`.</span><span class="sxs-lookup"><span data-stu-id="42589-142">Create a variable named, `EmailAddress`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="42589-143">La variable `EmailAddress` contiene la dirección de correo electrónico del vendedor.</span><span class="sxs-lookup"><span data-stu-id="42589-143">The `EmailAddress` variable holds the salesperson's e-mail address.</span></span>  
  
    3.  <span data-ttu-id="42589-144">Cree una variable con nombre `FirstName` y establezca su tipo en `String`.</span><span class="sxs-lookup"><span data-stu-id="42589-144">Create a variable named, `FirstName`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="42589-145">La variable `FirstName` contiene el nombre del vendedor.</span><span class="sxs-lookup"><span data-stu-id="42589-145">The `FirstName` variable holds the salesperson's first name.</span></span>  
  
    4.  <span data-ttu-id="42589-146">Cree una variable con nombre `Bonus` y establezca su tipo en `Double`.</span><span class="sxs-lookup"><span data-stu-id="42589-146">Create a variable named, `Bonus`, and set its type to `Double`.</span></span>  
  
         <span data-ttu-id="42589-147">La variable `Bonus` contiene el importe de la bonificación del vendedor.</span><span class="sxs-lookup"><span data-stu-id="42589-147">The `Bonus` variable holds the amount of the salesperson's bonus.</span></span>  
  
#### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="42589-148">Para configurar los administradores de conexión</span><span class="sxs-lookup"><span data-stu-id="42589-148">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="42589-149">En el área de Administradores de conexiones del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , agregue y configure un nuevo administrador de conexiones OLE DB que se conecte a la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42589-149">In the Connection Managers area of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add and configure a new OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>  
  
     <span data-ttu-id="42589-150">El origen de OLE DB de la tarea Flujo de datos utilizará este administrador de conexiones para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="42589-150">The OLE DB source in the Data Flow task will use this connection manager to retrieve data.</span></span>  
  
2.  <span data-ttu-id="42589-151">En el área de Administradores de conexiones, agregue y configure un nuevo administrador de conexiones SMTP que se conecte a un servidor SMTP disponible.</span><span class="sxs-lookup"><span data-stu-id="42589-151">In the Connection Managers area, add and configure a new SMTP connection manager that connects to an available SMTP server.</span></span>  
  
     <span data-ttu-id="42589-152">La tarea Enviar correo incluida en el contenedor de bucles Foreach utilizará este administrador de conexiones para enviar correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="42589-152">The Send Mail task inside the Foreach Loop container will use this connection manager to send emails.</span></span>  
  
#### <a name="to-configure-the-data-flow-and-the-recordset-destination"></a><span data-ttu-id="42589-153">Para configurar el flujo de datos y el destino de conjunto de registros</span><span class="sxs-lookup"><span data-stu-id="42589-153">To configure the data flow and the Recordset Destination</span></span>  
  
1.  <span data-ttu-id="42589-154">En la pestaña **Flujo de control** del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , agregue una tarea Flujo de datos a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="42589-154">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Data Flow task to the design surface.</span></span>  
  
2.  <span data-ttu-id="42589-155">En la pestaña **Flujo de datos** pestaña, añadir un origen de OLE DB a la tarea de flujo de datos, y luego abrir el **Editor de origen de OLE DB.**</span><span class="sxs-lookup"><span data-stu-id="42589-155">On the **Data Flow** tab, add an OLE DB source to the Data Flow task, and then open the **OLE DB Source Editor.**</span></span>  
  
3.  <span data-ttu-id="42589-156">En la página **Administrador de conexiones** del editor, configure el origen con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="42589-156">On the **Connection Manager** page of the editor, configure the source with the following settings:</span></span>  
  
    1.  <span data-ttu-id="42589-157">En **Administrador de conexiones OLE DB**, seleccione el administrador de conexiones OLE DB que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="42589-157">For **OLE DB connection manager**, select the OLE DB connection manager that you previously created.</span></span>  
  
    2.  <span data-ttu-id="42589-158">En **Modo de acceso a datos**, seleccione **Comando SQL**.</span><span class="sxs-lookup"><span data-stu-id="42589-158">For **Data access mode**, select **SQL command**.</span></span>  
  
    3.  <span data-ttu-id="42589-159">En **Texto de comando SQL**, escriba la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="42589-159">For **SQL command text**, enter the following query:</span></span>  
  
        ```  
        SELECT     Person.Contact.EmailAddress, Person.Contact.FirstName, CONVERT(float, Sales.SalesPerson.Bonus) AS Bonus  
        FROM         Sales.SalesPerson INNER JOIN  
                              Person.Contact ON Sales.SalesPerson.SalesPersonID = Person.Contact.ContactID  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="42589-160">Tiene que convertir el valor `currency` de la columna Bonus en un valor `float` antes de poder cargar ese valor en una variable de paquete cuyo tipo sea `Double`.</span><span class="sxs-lookup"><span data-stu-id="42589-160">You have to convert the `currency` value in the Bonus column to a `float` before you can load that value into a package variable whose type is `Double`.</span></span>  
  
4.  <span data-ttu-id="42589-161">En la pestaña **Flujo de datos** , agregue un destino de conjunto de registros y conecte el destino después del origen de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="42589-161">On the **Data Flow** tab, add a Recordset destination, and connect the destination after the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="42589-162">Abra el **Editor de destino de conjunto de registros**y configure el destino con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="42589-162">Open the **Recordset Destination Editor**, and configure the destination with the following settings:</span></span>  
  
    1.  <span data-ttu-id="42589-163">En la pestaña **propiedades de componente** , en `VariableName` propiedad, `User::BonusRecordset` Seleccione.</span><span class="sxs-lookup"><span data-stu-id="42589-163">On the **Component Properties** tab, for `VariableName` property, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="42589-164">En la pestaña **Columnas de entrada** , seleccione las tres columnas disponibles.</span><span class="sxs-lookup"><span data-stu-id="42589-164">On the **Input Columns** tab, select all three of the available columns.</span></span>  
  
#### <a name="to-configure-the-foreach-loop-container-and-run-the-package"></a><span data-ttu-id="42589-165">Para configurar el contenedor de bucles Foreach y ejecutar el paquete</span><span class="sxs-lookup"><span data-stu-id="42589-165">To configure the Foreach Loop container and run the package</span></span>  
  
1.  <span data-ttu-id="42589-166">En la pestaña **Flujo de control** del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , agregue un contenedor de bucles Foreach y conecte el contenedor después de la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="42589-166">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container, and connect the container after the Data Flow task.</span></span>  
  
2.  <span data-ttu-id="42589-167">Abra el **Editor de bucles Foreach**y configure el contenedor con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="42589-167">Open the **Foreach Loop Editor**, and configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="42589-168">En la página **colección** , en **enumerador**, seleccione **enumerador de ADO para foreach**y, en variable de origen de **objeto ADO**, seleccione `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="42589-168">On the **Collection** page, for **Enumerator**, select **Foreach ADO Enumerator**, and for **ADO object source variable**, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="42589-169">En la página **asignaciones de variables** , asigne `User::EmailAddress` al índice 0, `User::FirstName` al índice 1 y `User::Bonus` al índice 2.</span><span class="sxs-lookup"><span data-stu-id="42589-169">On the **Variable Mappings** page, map `User::EmailAddress` to index 0, `User::FirstName` to index 1, and `User::Bonus` to index 2.</span></span>  
  
3.  <span data-ttu-id="42589-170">En la pestaña **Flujo de control** , en el contenedor de bucles Foreach, agregue una tarea Enviar correo.</span><span class="sxs-lookup"><span data-stu-id="42589-170">On the **Control Flow** tab, inside the Foreach Loop container, add a Send Mail task.</span></span>  
  
4.  <span data-ttu-id="42589-171">Abra el **Editor de la tarea Enviar correo**, y a continuación, en la página **Correo** , configure la tarea con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="42589-171">Open the **Send Mail Task Editor**, and then on the **Mail** page, configure the task with the following settings:</span></span>  
  
    1.  <span data-ttu-id="42589-172">En **SmtpConnection**, seleccione el administrador de conexiones SMTP que se configuró previamente.</span><span class="sxs-lookup"><span data-stu-id="42589-172">For **SmtpConnection**, select the SMTP connection manager that was configured previously.</span></span>  
  
    2.  <span data-ttu-id="42589-173">En **De**, escriba una dirección de correo electrónico adecuada.</span><span class="sxs-lookup"><span data-stu-id="42589-173">For **From**, enter an appropriate e-mail address.</span></span>  
  
         <span data-ttu-id="42589-174">Si utiliza su propia dirección de correo electrónico, podrá comprobar que el paquete se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="42589-174">If you use your own e-mail address, you will be able to confirm that the package runs successfully.</span></span> <span data-ttu-id="42589-175">Recibirá las confirmaciones de los mensajes que no se pudieron entregar enviados por la tarea Enviar correo a los vendedores ficticios de [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42589-175">You will receive undeliverable receipts for the messages sent by the Send Mail task to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
    3.  <span data-ttu-id="42589-176">En **Para**, escriba una dirección de correo electrónico predeterminada.</span><span class="sxs-lookup"><span data-stu-id="42589-176">For **To**, enter a default e-mail address.</span></span>  
  
         <span data-ttu-id="42589-177">Este valor no se utilizará, pero se reemplazará en tiempo de ejecución por la dirección de correo electrónico de cada vendedor.</span><span class="sxs-lookup"><span data-stu-id="42589-177">This value will not be used, but will be replaced at run time by the e-mail address of each salesperson.</span></span>  
  
    4.  <span data-ttu-id="42589-178">En **Asunto**, escriba "Paga extraordinaria anual".</span><span class="sxs-lookup"><span data-stu-id="42589-178">For **Subject**, enter "Your annual bonus".</span></span>  
  
    5.  <span data-ttu-id="42589-179">En **MessageSourceType**, seleccione **Entrada directa**.</span><span class="sxs-lookup"><span data-stu-id="42589-179">For **MessageSourceType**, select **Direct Input**.</span></span>  
  
5.  <span data-ttu-id="42589-180">En la página **Expresiones** del **Editor de la tarea Enviar correo**, haga clic en el botón de puntos suspensivos ( **…** ) para abrir el **Editor de expresiones de propiedad**.</span><span class="sxs-lookup"><span data-stu-id="42589-180">On the **Expressions** page of the **Send Mail Task Editor**, click the ellipsis button (**...**) to open the **Property Expressions Editor**.</span></span>  
  
6.  <span data-ttu-id="42589-181">En el **Editor de expresiones de propiedad**, escriba la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="42589-181">In the **Property Expressions Editor**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="42589-182">En **ToLine**, agregue la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="42589-182">For **ToLine**, add the following expression:</span></span>  
  
        ```  
        @[User::EmailAddress]  
        ```  
  
    2.  <span data-ttu-id="42589-183">En la propiedad **MessageSource** , agregue la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="42589-183">For the **MessageSource** property, add the following expression:</span></span>  
  
        ```  
        "Dear " +  @[User::FirstName] + ": The amount of your bonus for this year is $" +  (DT_WSTR, 12) @[User::Bonus] + ". Thank you!"  
        ```  
  
7.  <span data-ttu-id="42589-184">Ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="42589-184">Run the package.</span></span>  
  
     <span data-ttu-id="42589-185">Si especificó un servidor SMTP válido y proporcionó su propia dirección de correo electrónico, recibirá las confirmaciones de los mensajes que no se pueden entregar que la tarea Enviar correo enviará a los vendedores ficticios de [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42589-185">If you have specified a valid SMTP server and provided your own e-mail address, you will receive undeliverable receipts for the messages that the Send Mail task sends to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
  
