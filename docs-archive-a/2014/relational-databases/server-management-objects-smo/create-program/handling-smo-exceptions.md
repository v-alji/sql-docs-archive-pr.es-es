---
title: Control de excepciones de SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SMO [SQL Server], exceptions
- exceptions [SMO]
- SQL Server Management Objects, exceptions
- inner exceptions [SMO]
ms.assetid: 4c725ff2-6588-44ca-b86a-87979e164153
author: stevestein
ms.author: sstein
ms.openlocfilehash: f4ae9e475a019c9bf874ee3f8365f3f3ac8e19d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676978"
---
# <a name="handling-smo-exceptions"></a><span data-ttu-id="ccec5-102">Controlar excepciones SMO</span><span class="sxs-lookup"><span data-stu-id="ccec5-102">Handling SMO Exceptions</span></span>
  <span data-ttu-id="ccec5-103">En código administrado, se producen excepciones cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="ccec5-103">In managed code, exceptions are thrown when an error occurs.</span></span> <span data-ttu-id="ccec5-104">Los métodos y propiedades SMO no notifican el fin correcto o incorrecto en el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ccec5-104">SMO methods and properties do not report success or failure in the return value.</span></span> <span data-ttu-id="ccec5-105">En su lugar, las excepciones se pueden detectar y controlar mediante un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ccec5-105">Instead, exceptions can be caught and handled by an exception handler.</span></span>  
  
 <span data-ttu-id="ccec5-106">En SMO existen diferentes clases de excepción.</span><span class="sxs-lookup"><span data-stu-id="ccec5-106">Different exception classes exist in the SMO.</span></span> <span data-ttu-id="ccec5-107">Se puede extraer información sobre la excepción de las propiedades de excepción como la propiedad `Message`, que proporciona un mensaje de texto sobre la excepción.</span><span class="sxs-lookup"><span data-stu-id="ccec5-107">Information about the exception can be extracted from the exception properties such as the `Message` property that gives a text message about the exception.</span></span>  
  
 <span data-ttu-id="ccec5-108">Las instrucciones de control de excepciones son específicas del lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="ccec5-108">The exception handling statements are specific to the programming language.</span></span> <span data-ttu-id="ccec5-109">Por ejemplo, en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic es la instrucción `Catch`.</span><span class="sxs-lookup"><span data-stu-id="ccec5-109">For example, in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic it is the `Catch` statement.</span></span>  
  
## <a name="inner-exceptions"></a><span data-ttu-id="ccec5-110">Excepciones internas</span><span class="sxs-lookup"><span data-stu-id="ccec5-110">Inner Exceptions</span></span>  
 <span data-ttu-id="ccec5-111">Las excepciones pueden ser o generales o específicas.</span><span class="sxs-lookup"><span data-stu-id="ccec5-111">Exceptions can either be general or specific.</span></span> <span data-ttu-id="ccec5-112">Las excepciones generales contienen un conjunto de excepciones específicas.</span><span class="sxs-lookup"><span data-stu-id="ccec5-112">General exceptions contain a set of specific exceptions.</span></span> <span data-ttu-id="ccec5-113">Se pueden utilizar varias instrucciones `Catch` para controlar los errores anticipados y permitir que los errores restantes pasen explícitamente a código general de control de errores.</span><span class="sxs-lookup"><span data-stu-id="ccec5-113">Several `Catch` statements can be used to handle anticipated errors and let remaining errors fall through to general exception handling code.</span></span> <span data-ttu-id="ccec5-114">Las excepciones se producen a menudo en una secuencia en cascada.</span><span class="sxs-lookup"><span data-stu-id="ccec5-114">Exceptions often occur in a cascading sequence.</span></span> <span data-ttu-id="ccec5-115">Con frecuencia, una excepción SQL puede provocar una excepción SMO.</span><span class="sxs-lookup"><span data-stu-id="ccec5-115">Frequently, an SMO exception might have been caused by an SQL exception.</span></span> <span data-ttu-id="ccec5-116">La manera de detectar si es esto lo que ha sucedido consiste en utilizar la propiedad `InnerException` de forma consecutiva para determinar la excepción original que produjo la excepción final de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="ccec5-116">The way to detect this is to use the `InnerException` property successively to determine the original exception that caused the final, top-level exception.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccec5-117">La `SQLException` excepción se declara en el espacio de nombres **System. Data. SqlClient** .</span><span class="sxs-lookup"><span data-stu-id="ccec5-117">The `SQLException` exception is declared in the **System.Data.SqlClient** namespace.</span></span>  
  
 <span data-ttu-id="ccec5-118">![Diagrama que muestra los niveles de los que una excepción](../../../database-engine/dev-guide/media/exception-flow.gif "Diagrama que muestra los niveles de los que una excepción")</span><span class="sxs-lookup"><span data-stu-id="ccec5-118">![A diagram that shows the levels from which an excp](../../../database-engine/dev-guide/media/exception-flow.gif "A diagram that shows the levels from which an excp")</span></span>  
  
 <span data-ttu-id="ccec5-119">El diagrama muestra el flujo de excepciones a través de los niveles de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ccec5-119">The diagram shows the flow of exceptions through the layers of the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccec5-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccec5-120">Example</span></span>  
 <span data-ttu-id="ccec5-121">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="ccec5-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="ccec5-122">Para obtener más información, vea [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="ccec5-122">For more information, see [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) or [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="catching-an-exception-in-visual-basic"></a><span data-ttu-id="ccec5-123">Detectar una excepción en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ccec5-123">Catching an Exception in Visual Basic</span></span>  
 <span data-ttu-id="ccec5-124">En este ejemplo de código se muestra cómo usar la instrucción `Try...Catch...Finally` de [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] para detectar una excepción SMO.</span><span class="sxs-lookup"><span data-stu-id="ccec5-124">This code example shows how to use the `Try...Catch...Finally`[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] statement to catch a SMO exception.</span></span> <span data-ttu-id="ccec5-125">Todas las excepciones SMO tienen el tipo SmoException y se enumeran en la referencia SMO.</span><span class="sxs-lookup"><span data-stu-id="ccec5-125">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="ccec5-126">La secuencia de excepciones internas se muestra para indicar la raíz del error.</span><span class="sxs-lookup"><span data-stu-id="ccec5-126">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="ccec5-127">Para obtener más información, vea la documentación de [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="ccec5-127">For more information, see the [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET documentation.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBExceptions1](SMO How to#SMO_VBExceptions1)]  -->  
  
## <a name="catching-an-exception-in-visual-c"></a><span data-ttu-id="ccec5-128">Detectar una excepción en Visual C#</span><span class="sxs-lookup"><span data-stu-id="ccec5-128">Catching an Exception in Visual C#</span></span>  
 <span data-ttu-id="ccec5-129">En este ejemplo de código se muestra cómo usar la instrucción `Try...Catch...Finally` de Visual C# para detectar una excepción SMO.</span><span class="sxs-lookup"><span data-stu-id="ccec5-129">This code example shows how to use the `Try...Catch...Finally` Visual C# statement to catch a SMO exception.</span></span> <span data-ttu-id="ccec5-130">Todas las excepciones SMO tienen el tipo SmoException y se enumeran en la referencia SMO.</span><span class="sxs-lookup"><span data-stu-id="ccec5-130">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="ccec5-131">La secuencia de excepciones internas se muestra para indicar la raíz del error.</span><span class="sxs-lookup"><span data-stu-id="ccec5-131">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="ccec5-132">Para obtener más información, vea la documentación de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="ccec5-132">For more information, see the Visual C# documentation.</span></span>  
  
```  
{   
//This sample requires the Microsoft.SqlServer.Management.Smo.Agent namespace to be included.   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define an Operator object variable by supplying the parent SQL Agent and the name arguments in the constructor.   
//Note that the Operator type requires [] parenthesis to differentiate it from a Visual Basic key word.   
op = new Operator(srv.JobServer, "Test_Operator");   
op.Create();   
//Start exception handling.   
try {   
    //Create the operator again to cause an SMO exception.   
    OperatorCategory opx;   
    opx = new OperatorCategory(srv.JobServer, "Test_Operator");   
    opx.Create();   
}   
//Catch the SMO exception   
catch (SmoException smoex) {   
    Console.WriteLine("This is an SMO Exception");   
   //Display the SMO exception message.   
   Console.WriteLine(smoex.Message);   
   //Display the sequence of non-SMO exceptions that caused the SMO exception.   
   Exception ex;   
   ex = smoex.InnerException;   
   while (!object.ReferenceEquals(ex.InnerException, (null))) {   
      Console.WriteLine(ex.InnerException.Message);   
      ex = ex.InnerException;   
    }   
    }   
   //Catch other non-SMO exceptions.   
   catch (Exception ex) {   
      Console.WriteLine("This is not an SMO exception.");   
}   
}  
```  
  
  
