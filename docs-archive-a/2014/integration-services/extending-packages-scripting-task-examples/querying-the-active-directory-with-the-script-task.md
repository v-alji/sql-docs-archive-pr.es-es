---
title: Consultar Active Directory con la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Active Directory access
- SSIS Script task, Active Directory access
- Script task [Integration Services], examples
- Active Directory [Integration Services]
ms.assetid: a88fefbb-9ea2-4a86-b836-e71315bac68e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 624aa56289b9cab9174882b586a37e5d0de7ca9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663631"
---
# <a name="querying-the-active-directory-with-the-script-task"></a><span data-ttu-id="2bcb2-102">Consultar Active Directory con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="2bcb2-102">Querying the Active Directory with the Script Task</span></span>
  <span data-ttu-id="2bcb2-103">Las aplicaciones de procesamiento de datos empresariales, como los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], a menudo tienen que procesar los datos de forma distinta según la categoría, el puesto u otras características de los empleados almacenados en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-103">Enterprise data processing applications, such as [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, often need to process data differently based on the rank, job title, or other characteristics of employees stored in Active Directory.</span></span> <span data-ttu-id="2bcb2-104">Active Directory es un servicio de directorios de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows que proporciona un almacén centralizado de metadatos, no solamente acerca de los usuarios, sino también acerca de otros recursos de la organización, como los equipos y las impresoras.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-104">Active Directory is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows directory service that provides a centralized store of metadata, not only about users, but also about other organizational assets such as computers and printers.</span></span> <span data-ttu-id="2bcb2-105">El espacio de nombres `System.DirectoryServices` de Microsoft .NET Framework proporciona las clases para trabajar con Active Directory, con el fin de ayudarle a dirigir el flujo de trabajo de procesamiento de datos basándose en la información que almacena.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-105">The `System.DirectoryServices` namespace in the Microsoft .NET Framework provides classes for working with Active Directory, to help you direct data processing workflow based on the information that it stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bcb2-106">Si desea crear una tarea que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de este ejemplo de tarea Script como punto inicial de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="2bcb2-107">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="2bcb2-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="2bcb2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bcb2-108">Description</span></span>  
 <span data-ttu-id="2bcb2-109">En el ejemplo siguiente se recupera el nombre, el puesto y el número de teléfono de un empleado de Active Directory basándose en el valor de la variable `email`, que contiene la dirección de correo electrónico del empleado.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-109">The following example retrieves an employee's name, title, and phone number from Active Directory based on the value of the `email` variable, which contains the e-mail address of the employee.</span></span> <span data-ttu-id="2bcb2-110">Las restricciones de precedencia en el paquete utilizan la información recuperada para determinar, por ejemplo, si se va a enviar un mensaje de correo electrónico de prioridad baja o una página prioritaria, basándose en el puesto del empleado.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-110">Precedence constraints in the package can use the retrieved information to determine, for example, whether to send a low-priority e-mail message or a high-priority page, based on the job title of the employee.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="2bcb2-111">Para configurar este ejemplo de tarea Script</span><span class="sxs-lookup"><span data-stu-id="2bcb2-111">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="2bcb2-112">Cree las tres variable de cadena `email`, `name` y `title`.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-112">Create the three string variables `email`, `name`, and `title`.</span></span> <span data-ttu-id="2bcb2-113">Escriba una dirección de correo electrónico corporativa válida como el valor de la variable `email`.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-113">Enter a valid corporate email address as the value of the `email` variable.</span></span>  
  
2.  <span data-ttu-id="2bcb2-114">En la página **script** del editor de la **tarea script**, agregue la `email` variable a la `ReadOnlyVariables` propiedad.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-114">On the **Script** page of the **Script Task Editor**, add the `email` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="2bcb2-115">Agregue las variables `name` y `title` a la propiedad `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-115">Add the `name` and `title` variables to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="2bcb2-116">En el proyecto de script, agregue una referencia al `System.DirectoryServices` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-116">In the script project, add a reference to the `System.DirectoryServices` namespace.</span></span>  
  
5.  <span data-ttu-id="2bcb2-117">.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-117">.</span></span> <span data-ttu-id="2bcb2-118">En el código, utilice una instrucción `Imports` para importar el espacio de nombres `DirectoryServices`.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-118">In your code, use an `Imports` statement to import the `DirectoryServices` namespace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bcb2-119">Para ejecutar correctamente este script, la empresa debe utilizar Active Directory en la red y almacenar la información de empleado que este ejemplo utiliza.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-119">To run this script successfully, your company must be using Active Directory on its network and storing the employee information that this example uses.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2bcb2-120">Código</span><span class="sxs-lookup"><span data-stu-id="2bcb2-120">Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim directory As DirectoryServices.DirectorySearcher  
    Dim result As DirectoryServices.SearchResult  
    Dim email As String  
  
    email = Dts.Variables("email").Value.ToString  
  
    Try  
        directory = New _  
            DirectoryServices.DirectorySearcher("(mail=" & email & ")")  
        result = directory.FindOne  
        Dts.Variables("name").Value = _  
            result.Properties("displayname").ToString  
        Dts.Variables("title").Value = _  
            result.Properties("title").ToString  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
public void Main()  
{  
    //  
    DirectorySearcher directory;  
    SearchResult result;  
    string email;  
  
    email = (string)Dts.Variables["email"].Value;  
  
    try  
    {  
        directory = new DirectorySearcher("(mail=" + email + ")");  
        result = directory.FindOne();  
        Dts.Variables["name"].Value = result.Properties["displayname"].ToString();  
        Dts.Variables["title"].Value = result.Properties["title"].ToString();  
        Dts.TaskResult = (int)ScriptResults.Success;  
    }  
    catch (Exception ex)  
    {  
        Dts.Events.FireError(0, "Script Task Example", ex.Message + "\n" + ex.StackTrace, String.Empty, 0);  
        Dts.TaskResult = (int)ScriptResults.Failure;  
    }  
  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="2bcb2-121">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="2bcb2-121">External Resources</span></span>  
  
-   <span data-ttu-id="2bcb2-122">Artículo técnico, [Procesar la información de Active Directory en SSIS](https://go.microsoft.com/fwlink/?LinkId=199588), en social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2bcb2-122">Technical article, [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588), on social.technet.microsoft.com</span></span>  
  
<span data-ttu-id="2bcb2-123">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2bcb2-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2bcb2-124">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="2bcb2-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2bcb2-125">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="2bcb2-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2bcb2-126">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="2bcb2-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
