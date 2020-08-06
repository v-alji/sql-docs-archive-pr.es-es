---
title: Crear un destino ODBC con el componente de script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], destination components
- ODBC destination [Integration Services]
- destinations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: d198c866-78f4-4a50-ae15-333160645815
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10adff11a7e1db24d9a244c3e83949a010b606c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674214"
---
# <a name="creating-an-odbc-destination-with-the-script-component"></a><span data-ttu-id="6ae9e-102">Crear un destino ODBC con el componente de script</span><span class="sxs-lookup"><span data-stu-id="6ae9e-102">Creating an ODBC Destination with the Script Component</span></span>
  <span data-ttu-id="6ae9e-103">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], normalmente se guardan los datos en un destino ODBC mediante un destino [!INCLUDE[vstecado](../../includes/vstecado-md.md)] y el proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para ODBC.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you typically save data to an ODBC destination by using an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for ODBC.</span></span> <span data-ttu-id="6ae9e-104">Sin embargo, también se puede crear un destino ODBC ad hoc para utilizar en un paquete único.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-104">However, you can also create an ad hoc ODBC destination for use in a single package.</span></span> <span data-ttu-id="6ae9e-105">Para crear este destino ODBC ad hoc, use el componente de script como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-105">To create this ad hoc ODBC destination, you use the Script component as shown in the following example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ae9e-106">Si desea crear un componente que pueda reutilizar más fácilmente en varias tareas de flujo de datos y varios paquetes, puede utilizar el código de este ejemplo de componente de script como punto de inicio para el componente de flujo de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="6ae9e-107">Para obtener más información, vea [Desarrollar un componente de flujo de datos personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6ae9e-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ae9e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ae9e-108">Example</span></span>  
 <span data-ttu-id="6ae9e-109">En el ejemplo siguiente se muestra cómo crear un componente de destino que usa un administrador de conexiones ODBC existente para guardar los datos del flujo de datos en una tabla de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ae9e-109">The following example demonstrates how to create a destination component that uses an existing ODBC connection manager to save data from the data flow into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="6ae9e-110">Este ejemplo es una versión modificada del destino [!INCLUDE[vstecado](../../includes/vstecado-md.md)] personalizado que se mostró en el tema [Crear un destino con el componente de script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="6ae9e-110">This example is a modified version of the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination that was demonstrated in the topic, [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="6ae9e-111">Sin embargo, en este ejemplo, el destino [!INCLUDE[vstecado](../../includes/vstecado-md.md)] personalizado se ha modificado para que funcione con un administrador de conexiones ODBC y guarde los datos a un destino de ODBC.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-111">However, in this example, the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination has been modified to work with an ODBC connection manager and save data to an ODBC destination.</span></span> <span data-ttu-id="6ae9e-112">Estas modificaciones también incluyen los cambios siguientes:</span><span class="sxs-lookup"><span data-stu-id="6ae9e-112">These modifications also include the following changes:</span></span>  
  
-   <span data-ttu-id="6ae9e-113">No puede llamar al método `AcquireConnection` del administrador de conexiones ODBC desde el código administrado, porque devuelve un objeto nativo.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-113">You cannot call the `AcquireConnection` method of the ODBC connection manager from managed code, because it returns a native object.</span></span> <span data-ttu-id="6ae9e-114">Por consiguiente, este ejemplo usa la cadena de conexión del administrador de conexiones para conectar directamente al origen de datos mediante el proveedor de datos de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para ODBC administrado.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-114">Therefore, this sample uses the connection string of the connection manager to connect to the data source directly by using the managed ODBC [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider.</span></span>  
  
-   <span data-ttu-id="6ae9e-115">`OdbcCommand` espera los parámetros posicionales.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-115">The `OdbcCommand` expects positional parameters.</span></span> <span data-ttu-id="6ae9e-116">Los signos de interrogación (?) en el texto del comando indican las posiciones de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-116">The positions of the parameters are indicated by the question marks (?) in the text of the command.</span></span> <span data-ttu-id="6ae9e-117">(En cambio, `SqlCommand` espera parámetros con nombre.)</span><span class="sxs-lookup"><span data-stu-id="6ae9e-117">(In contrast, a `SqlCommand` expects named parameters.)</span></span>  
  
 <span data-ttu-id="6ae9e-118">En este ejemplo se usa la tabla **Person.Address** en la base de datos de ejemplo **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-118">This example uses the **Person.Address** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="6ae9e-119">En el ejemplo se pasan las columnas primera y cuarta, las columnas **int \* AddressID**\* y **nvarchar (30) City** , de esta tabla a través del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-119">The example passes the first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, of this table through the data flow.</span></span> <span data-ttu-id="6ae9e-120">Estos mismos datos se usan en los ejemplos de origen, transformación y destino en el tema [Desarrollar tipos específicos de los componentes de script](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="6ae9e-120">This same data is used in the source, transformation, and destination samples in the topic, [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="6ae9e-121">Para configurar este ejemplo de componente de script</span><span class="sxs-lookup"><span data-stu-id="6ae9e-121">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="6ae9e-122">Cree un administrador de conexiones ODBC que se conecte a la base de datos **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-122">Create an ODBC connection manager that connects to the **AdventureWorks** database.</span></span>  
  
2.  <span data-ttu-id="6ae9e-123">Cree una tabla de destino ejecutando el siguiente comando Transact-SQL en la base de datos **AdventureWorks**:</span><span class="sxs-lookup"><span data-stu-id="6ae9e-123">Create a destination table by running the following Transact-SQL command in the **AdventureWorks** database:</span></span>  
  
    ```  
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,  
        [City] [nvarchar](30) NOT NULL)  
    ```  
  
3.  <span data-ttu-id="6ae9e-124">Agregue un nuevo componente de script a la superficie del diseñador de flujo de datos y configúrelo como destino.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-124">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>  
  
4.  <span data-ttu-id="6ae9e-125">Conecte la salida de un origen o transformación de nivel superior al componente de destino en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ae9e-125">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="6ae9e-126">(Puede conectar directamente un origen a un destino sin ninguna transformación). Para asegurarse de que este ejemplo funciona, la salida del componente ascendente debe incluir por lo menos las columnas **AddressID** y **City** de la tabla **Person.Address** de la base de datos de ejemplo **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-126">(You can connect a source directly to a destination without any transformations.) To ensure that this sample works, the output of the upstream component must include at least the **AddressID** and **City** columns from the **Person.Address** table of the **AdventureWorks** sample database.</span></span>  
  
5.  <span data-ttu-id="6ae9e-127">Abra el **Editor de transformación Script**.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-127">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="6ae9e-128">En la página **Columnas de entrada**, seleccione las columnas **AddressID** y **City**.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-128">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>  
  
6.  <span data-ttu-id="6ae9e-129">En la página **Entradas y salidas**, cambie el nombre de la entrada por un nombre más descriptivo, como **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-129">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>  
  
7.  <span data-ttu-id="6ae9e-130">En la página **Administradores de conexiones**, agregue o cree el administrador de conexiones ODBC con un nombre descriptivo, como **MyODBCConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-130">On the **Connection Managers** page, add or create the ODBC connection manager with a descriptive name such as **MyODBCConnectionManager**.</span></span>  
  
8.  <span data-ttu-id="6ae9e-131">En la página **script** , haga clic en **Editar script**y, a continuación, escriba el script que se muestra a continuación en la `ScriptMain` clase.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-131">On the **Script** page, click **Edit Script**, and then enter the script shown below in the `ScriptMain` class.</span></span>  
  
9. <span data-ttu-id="6ae9e-132">Cierre el entorno de desarrollo de script y el **Editor de transformación Script** y, a continuación, ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-132">Close the script development environment, close the **Script Transformation Editor**, and then run the sample.</span></span>  
  
    ```vb  
    Imports System.Data.Odbc  
    ...  
    Public Class ScriptMain  
        Inherits UserComponent  
  
        Dim odbcConn As OdbcConnection  
        Dim odbcCmd As OdbcCommand  
        Dim odbcParam As OdbcParameter  
  
        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)  
  
            Dim connectionString As String  
            connectionString = Me.Connections.MyODBCConnectionManager.ConnectionString  
            odbcConn = New OdbcConnection(connectionString)  
            odbcConn.Open()  
  
        End Sub  
  
        Public Overrides Sub PreExecute()  
  
            odbcCmd = New OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " & _  
                "VALUES(?, ?)", odbcConn)  
            odbcParam = New OdbcParameter("@addressid", OdbcType.Int)  
            odbcCmd.Parameters.Add(odbcParam)  
            odbcParam = New OdbcParameter("@city", OdbcType.NVarChar, 30)  
            odbcCmd.Parameters.Add(odbcParam)  
  
        End Sub  
  
        Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)  
  
            With odbcCmd  
                .Parameters("@addressid").Value = Row.AddressID  
                .Parameters("@city").Value = Row.City  
                .ExecuteNonQuery()  
            End With  
  
        End Sub  
  
        Public Overrides Sub ReleaseConnections()  
  
            odbcConn.Close()  
  
        End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System.Data.Odbc;  
    ...  
    public class ScriptMain :  
        UserComponent  
    {  
        OdbcConnection odbcConn;  
        OdbcCommand odbcCmd;  
        OdbcParameter odbcParam;  
  
        public override void AcquireConnections(object Transaction)  
        {  
  
            string connectionString;  
            connectionString = this.Connections.MyODBCConnectionManager.ConnectionString;  
            odbcConn = new OdbcConnection(connectionString);  
            odbcConn.Open();  
  
        }  
  
        public override void PreExecute()  
        {  
  
            odbcCmd = new OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " +  
                "VALUES(?, ?)", odbcConn);  
            odbcParam = new OdbcParameter("@addressid", OdbcType.Int);  
            odbcCmd.Parameters.Add(odbcParam);  
            odbcParam = new OdbcParameter("@city", OdbcType.NVarChar, 30);  
            odbcCmd.Parameters.Add(odbcParam);  
  
        }  
  
        public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)  
        {  
  
            {  
                odbcCmd.Parameters["@addressid"].Value = Row.AddressID;  
                odbcCmd.Parameters["@city"].Value = Row.City;  
                odbcCmd.ExecuteNonQuery();  
            }  
  
        }  
  
        public override void ReleaseConnections()  
        {  
  
            odbcConn.Close();  
  
        }  
    }  
    ```  
  
<span data-ttu-id="6ae9e-133">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6ae9e-133">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6ae9e-134">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="6ae9e-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6ae9e-135">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="6ae9e-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6ae9e-136">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="6ae9e-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae9e-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ae9e-137">See Also</span></span>  
 [<span data-ttu-id="6ae9e-138">Creating a Destination with the Script Component (Crear un destino con el componente de script)</span><span class="sxs-lookup"><span data-stu-id="6ae9e-138">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
  
  
