---
title: Crear, modificar y quitar valores predeterminados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- defaults [SMO]
ms.assetid: c30ac3b9-8150-4264-ba4c-c549f44261ab
author: stevestein
ms.author: sstein
ms.openlocfilehash: 747f7ff60122c5265cd68060063946a3e22d0301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749211"
---
# <a name="creating-altering-and-removing-defaults"></a><span data-ttu-id="56cb2-102">Crear, modificar y eliminar valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="56cb2-102">Creating, Altering, and Removing Defaults</span></span>
  <span data-ttu-id="56cb2-103">En los objetos de administración de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SMO), el objeto <xref:Microsoft.SqlServer.Management.Smo.Default> representa la restricción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="56cb2-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), the default constraint is represented by the <xref:Microsoft.SqlServer.Management.Smo.Default> object.</span></span>  
  
 <span data-ttu-id="56cb2-104">La propiedad <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Default> se utiliza para definir el valor que se insertará.</span><span class="sxs-lookup"><span data-stu-id="56cb2-104">The <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Default> object is used to set the value to be inserted.</span></span> <span data-ttu-id="56cb2-105">Puede ser una constante o una instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] que devuelve un valor constante, como GETDATE().</span><span class="sxs-lookup"><span data-stu-id="56cb2-105">This can be a constant or a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement that returns a constant value, such as GETDATE().</span></span> <span data-ttu-id="56cb2-106">La propiedad <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> no puede modificarse mediante el método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="56cb2-106">The <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property cannot be modified by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="56cb2-107">En lugar de ello, debe quitarse el objeto <xref:Microsoft.SqlServer.Management.Smo.Default> y volver a crearse.</span><span class="sxs-lookup"><span data-stu-id="56cb2-107">Instead, the <xref:Microsoft.SqlServer.Management.Smo.Default> object must be dropped and re-created.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56cb2-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56cb2-108">Example</span></span>  
 <span data-ttu-id="56cb2-109">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="56cb2-109">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="56cb2-110">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="56cb2-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-default-in-visual-basic"></a><span data-ttu-id="56cb2-111">Crear, modificar y quitar un valor predeterminado en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56cb2-111">Creating, Altering, and Removing a Default in Visual Basic</span></span>  
 <span data-ttu-id="56cb2-112">En este ejemplo de código se muestra cómo crear un valor predeterminado que está formado por texto simple y otro valor predeterminado que es una instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56cb2-112">This code example shows how to create one default that is simple text, and another default that is a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="56cb2-113">El valor predeterminado debe adjuntarse a la columna mediante el método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> y desasociarse utilizando el método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A>.</span><span class="sxs-lookup"><span data-stu-id="56cb2-113">The default must be attached to the column by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> method and detached by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> method.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaults1](SMO How to#SMO_VBDefaults1)]  -->  
  
## <a name="creating-altering-and-removing-a-default-in-visual-c"></a><span data-ttu-id="56cb2-114">Crear, modificar y quitar un valor predeterminado en Visual C#</span><span class="sxs-lookup"><span data-stu-id="56cb2-114">Creating, Altering, and Removing a Default in Visual C#</span></span>  
 <span data-ttu-id="56cb2-115">En este ejemplo de código se muestra cómo crear un valor predeterminado que está formado por texto simple y otro valor predeterminado que es una instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56cb2-115">This code example shows how to create one default that is simple text, and another default that is a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="56cb2-116">El valor predeterminado debe adjuntarse a la columna mediante el método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> y desasociarse utilizando el método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A>.</span><span class="sxs-lookup"><span data-stu-id="56cb2-116">The default must be attached to the column by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> method and detached by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> method.</span></span>  
  
```csharp
{
          Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database  db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Default object variable by supplying the parent database and the default name   
            //in the constructor.   
            Default def = new Default(db, "Test_Default2");  
  
            //Set the TextHeader and TextBody properties that define the default.   
            def.TextHeader = "CREATE DEFAULT [Test_Default2] AS";  
            def.TextBody = "GetDate()";  
  
            //Create the default on the instance of SQL Server.   
            def.Create();  
  
            //Bind the default to a column in a table in AdventureWorks2012  
            def.BindToColumn("SpecialOffer", "StartDate", "Sales");  
  
            //Unbind the default from the column and remove it from the database.   
            def.UnbindFromColumn("SpecialOffer", "StartDate", "Sales");  
            def.Drop();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-default-in-powershell"></a><span data-ttu-id="56cb2-117">Crear, modificar y quitar un valor predeterminado en PowerShell</span><span class="sxs-lookup"><span data-stu-id="56cb2-117">Creating, Altering, and Removing a Default in PowerShell</span></span>  
 <span data-ttu-id="56cb2-118">En este ejemplo de código se muestra cómo crear un valor predeterminado que está formado por texto simple y otro valor predeterminado que es una instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56cb2-118">This code example shows how to create one default that is simple text, and another default that is a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="56cb2-119">El valor predeterminado debe adjuntarse a la columna mediante el método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> y desasociarse utilizando el método <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A>.</span><span class="sxs-lookup"><span data-stu-id="56cb2-119">The default must be attached to the column by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.BindToColumn%2A> method and detached by using the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.UnbindFromColumn%2A> method.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
#Define a Default object variable by supplying the parent database and the default name in the constructor.  
$def = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Default `  
-argumentlist $db, "Test_Default2"  
  
#Set the TextHeader and TextBody properties that define the default.   
$def.TextHeader = "CREATE DEFAULT [Test_Default2] AS"  
$def.TextBody = "GetDate()"  
  
#Create the default on the instance of SQL Server.   
$def.Create()  
  
#Bind the default to the column.   
$def.BindToColumn("SpecialOffer", "StartDate", "Sales")  
  
#Unbind the default from the column and remove it from the database.   
$def.UnbindFromColumn("SpecialOffer", "StartDate", "Sales")  
$def.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="56cb2-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="56cb2-120">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Default>  
