---
title: Crear, modificar y quitar reglas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- rules [SMO]
ms.assetid: 16981459-524e-4b39-a899-4370eaf763cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7742a9cb718bdde4f268d5226c45eba475f44ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675251"
---
# <a name="creating-altering-and-removing-rules"></a><span data-ttu-id="b878b-102">Crear, modificar y quitar reglas</span><span class="sxs-lookup"><span data-stu-id="b878b-102">Creating, Altering, and Removing Rules</span></span>
  <span data-ttu-id="b878b-103">En SMO, el objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> representa las reglas.</span><span class="sxs-lookup"><span data-stu-id="b878b-103">In SMO, rules are represented by the <xref:Microsoft.SqlServer.Management.Smo.Rule> object.</span></span> <span data-ttu-id="b878b-104">La propiedad <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A>, que es una cadena de texto que contiene una expresión de condición que utiliza operadores o predicados, como IN, LIKE o BETWEEN, define la regla.</span><span class="sxs-lookup"><span data-stu-id="b878b-104">The rule is defined by the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property, which is a text string that contains a condition expression that uses operators or predicates, such as IN, LIKE, or BETWEEN.</span></span> <span data-ttu-id="b878b-105">Una regla no puede hacer referencia a columnas u otros objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b878b-105">A rule cannot reference columns or other database objects.</span></span> <span data-ttu-id="b878b-106">Se pueden incluir funciones integradas que no hagan referencia a objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b878b-106">Built-in functions that do not reference database objects can be included.</span></span>  
  
 <span data-ttu-id="b878b-107">La definición en la propiedad <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> debe contener una variable que haga referencia al valor de datos escrito.</span><span class="sxs-lookup"><span data-stu-id="b878b-107">The definition in the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property must contain a variable that refers to the data value entered.</span></span> <span data-ttu-id="b878b-108">Se puede utilizar cualquier nombre o símbolo para representar el valor cuando se crea la regla, pero el primer carácter debe ser el \@ símbolo.</span><span class="sxs-lookup"><span data-stu-id="b878b-108">Any name or symbol can be used to represent the value when creating the rule, but the first character must be the \@ symbol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b878b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b878b-109">Example</span></span>  
 <span data-ttu-id="b878b-110">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b878b-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="b878b-111">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="b878b-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-basic"></a><span data-ttu-id="b878b-112">Crear, modificar y quitar una regla en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b878b-112">Creating, Altering, and Removing a Rule in Visual Basic</span></span>  
 <span data-ttu-id="b878b-113">En este ejemplo de código se muestra cómo crear una regla, cómo adjuntarla a una columna, cómo modificar las propiedades del objeto <xref:Microsoft.SqlServer.Management.Smo.Rule>, cómo desasociar la regla de la columna y, por último, cómo quitarla.</span><span class="sxs-lookup"><span data-stu-id="b878b-113">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="b878b-114">La instrucción `Dim` para el objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> se especifica con la ruta completa del ensamblado para evitar la ambigüedad con un objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> en el ensamblado System.Data.</span><span class="sxs-lookup"><span data-stu-id="b878b-114">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBRules1](SMO How to#SMO_VBRules1)]  -->  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-c"></a><span data-ttu-id="b878b-115">Crear, modificar y quitar una regla en Visual C#</span><span class="sxs-lookup"><span data-stu-id="b878b-115">Creating, Altering, and Removing a Rule in Visual C#</span></span>  
 <span data-ttu-id="b878b-116">En este ejemplo de código se muestra cómo crear una regla, cómo adjuntarla a una columna, cómo modificar las propiedades del objeto <xref:Microsoft.SqlServer.Management.Smo.Rule>, cómo desasociar la regla de la columna y, por último, cómo quitarla.</span><span class="sxs-lookup"><span data-stu-id="b878b-116">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="b878b-117">La instrucción `Dim` para el objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> se especifica con la ruta completa del ensamblado para evitar la ambigüedad con un objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> en el ensamblado System.Data.</span><span class="sxs-lookup"><span data-stu-id="b878b-117">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Rule object variable by supplying the parent database, name and schema in the constructor.   
            //Note that the full namespace must be given for the Rule type to differentiate it from other Rule types.   
            Microsoft.SqlServer.Management.Smo.Rule ru;  
            ru = new Rule(db, "TestRule", "Production");  
            //Set the TextHeader and TextBody properties to define the rule.   
            ru.TextHeader = "CREATE RULE [Production].[TestRule] AS";  
            ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())";  
            //Create the rule on the instance of SQL Server.   
            ru.Create();  
            //Bind the rule to a column in the Product table by supplying the table, schema, and   
            //column as arguments in the BindToColumn method.   
            ru.BindToColumn("Product", "SellEndDate", "Production");  
            //Unbind from the column before removing the rule from the database.   
            ru.UnbindFromColumn("Product", "SellEndDate", "Production");  
            ru.Drop();  
  
        }  
```  
  
## <a name="creating-altering-and-removing-a-rule-in-powershell"></a><span data-ttu-id="b878b-118">Crear, modificar y quitar una regla en PowerShell</span><span class="sxs-lookup"><span data-stu-id="b878b-118">Creating, Altering, and Removing a Rule in PowerShell</span></span>  
 <span data-ttu-id="b878b-119">En este ejemplo de código se muestra cómo crear una regla, cómo adjuntarla a una columna, cómo modificar las propiedades del objeto <xref:Microsoft.SqlServer.Management.Smo.Rule>, cómo desasociar la regla de la columna y, por último, cómo quitarla.</span><span class="sxs-lookup"><span data-stu-id="b878b-119">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="b878b-120">La instrucción `Dim` para el objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> se especifica con la ruta completa del ensamblado para evitar la ambigüedad con un objeto <xref:Microsoft.SqlServer.Management.Smo.Rule> en el ensamblado System.Data.</span><span class="sxs-lookup"><span data-stu-id="b878b-120">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a Rule object variable by supplying the parent database, name and schema in the constructor.
$ru = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Rule -argumentlist $db, "TestRule", "Production"  
  
#Set the TextHeader and TextBody properties to define the rule.
$ru.TextHeader = "CREATE RULE [Production].[TestRule] AS"  
$ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())"  
  
#Create the rule on the instance of SQL Server.
$ru.Create()  
  
# Bind the rule to a column in the Product table by supplying the table, schema, and column as arguments in the BindToColumn method.
$ru.BindToColumn("Product", "SellEndDate", "Production")  
  
#Unbind from the column before removing the rule from the database.
$ru.UnbindFromColumn("Product", "SellEndDate", "Production")  
$ru.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="b878b-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b878b-121">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Rule>  
