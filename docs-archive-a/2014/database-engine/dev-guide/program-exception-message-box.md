---
title: Cuadro de mensajes de excepción de programa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- exception message box [SQL Server]
- displaying exception message box
ms.assetid: c771985b-149c-459a-b3cb-7b15fde01150
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9d49bdf8c73f86b2c334018d40510b4ae67c85ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750129"
---
# <a name="program-exception-message-box"></a><span data-ttu-id="0ebc9-102">Programar cuadros de mensajes de excepción</span><span class="sxs-lookup"><span data-stu-id="0ebc9-102">Program Exception Message Box</span></span>
  <span data-ttu-id="0ebc9-103">Puede usar el cuadro de mensajes de excepción en sus aplicaciones para proporcionar un control considerablemente mayor sobre la experiencia de mensajería que el que se proporciona con la clase <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-103">You can use the exception message box in your applications to provide significantly more control over the messaging experience than is provided by the <xref:System.Windows.Forms.MessageBox> class.</span></span> <span data-ttu-id="0ebc9-104">Para obtener más información, vea [programación de cuadros de mensajes de excepción](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span><span class="sxs-lookup"><span data-stu-id="0ebc9-104">For more information, see [Exception Message Box Programming](../../../2014/database-engine/dev-guide/exception-message-box-programming.md).</span></span> <span data-ttu-id="0ebc9-105">Para obtener información sobre la forma de obtener e implementar el archivo .dll del cuadro de mensajes de excepción, vea [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span><span class="sxs-lookup"><span data-stu-id="0ebc9-105">For information about how to obtain and deploy the exception message box .dll, see [Deploying an Exception Message Box Application](../../../2014/database-engine/dev-guide/deploying-an-exception-message-box-application.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="0ebc9-106">Procedimiento</span><span class="sxs-lookup"><span data-stu-id="0ebc9-106">Procedure</span></span>  
  
#### <a name="to-handle-an-exception-by-using-the-exception-message-box"></a><span data-ttu-id="0ebc9-107">Para controlar una excepción mediante el cuadro de mensajes de excepción</span><span class="sxs-lookup"><span data-stu-id="0ebc9-107">To handle an exception by using the exception message box</span></span>  
  
1.  <span data-ttu-id="0ebc9-108">Agregue una referencia al ensamblado Microsoft.ExceptionMessageBox.dll en su proyecto de código administrado.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-108">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="0ebc9-109">Opta Agregue una `using` Directiva (C#) o `Imports` ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .net) para usar el <xref:Microsoft.SqlServer.MessageBox> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-109">(Optional) Add a `using` (C#) or `Imports` ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="0ebc9-110">Cree un bloque try-catch para controlar la excepción anticipada.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-110">Create a try-catch block to handle the anticipated exception.</span></span>  
  
4.  <span data-ttu-id="0ebc9-111">Dentro del bloque `catch`, cree una instancia de la clase <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-111">Within the `catch` block, create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="0ebc9-112">Pase el <xref:System.Exception> objeto controlado por el `try` - `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-112">Pass the <xref:System.Exception> object handled by the `try`-`catch` block.</span></span>  
  
5.  <span data-ttu-id="0ebc9-113">(Opcional) Establezca una o varias de las siguientes propiedades en <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span><span class="sxs-lookup"><span data-stu-id="0ebc9-113">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="0ebc9-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>enumeración que especifica los botones que se van a mostrar en el cuadro de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-114"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="0ebc9-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>enumeración que especifica el botón predeterminado para el cuadro de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-115"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the exception message box.</span></span>  
  
    -   <span data-ttu-id="0ebc9-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>enumeración que se utiliza para controlar otros comportamientos del cuadro de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-116"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="0ebc9-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>enumeración que especifica el símbolo que se va a mostrar en el cuadro de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-117"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
6.  <span data-ttu-id="0ebc9-118">Llame al método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-118">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="0ebc9-119">Pase la ventana primaria a la que pertenece el cuadro de mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-119">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="0ebc9-120">Opta Tenga en cuenta el valor de la <xref:System.Windows.Forms.DialogResult> enumeración devuelta si necesita determinar en qué botón hizo clic el usuario.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-120">(Optional) Note the value of returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-without-an-exception"></a><span data-ttu-id="0ebc9-121">Para mostrar el cuadro de mensajes de excepción sin una excepción</span><span class="sxs-lookup"><span data-stu-id="0ebc9-121">To display the exception message box without an exception</span></span>  
  
1.  <span data-ttu-id="0ebc9-122">Agregue una referencia al ensamblado Microsoft.ExceptionMessageBox.dll en su proyecto de código administrado.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-122">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="0ebc9-123">Opta Agregue una `using` Directiva (C#) o `Imports` (Visual Basic .net) para usar el <xref:Microsoft.SqlServer.MessageBox> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-123">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="0ebc9-124">Cree una instancia de la clase <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-124">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class.</span></span> <span data-ttu-id="0ebc9-125">Pase el texto del mensaje como un valor <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-125">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="0ebc9-126">(Opcional) Establezca una o varias de las siguientes propiedades en <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span><span class="sxs-lookup"><span data-stu-id="0ebc9-126">(Optional) Set one or more of the following properties on <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>:</span></span>  
  
    -   <span data-ttu-id="0ebc9-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons>enumeración que especifica los botones que se van a mostrar en el cuadro de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-127"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons> enumeration that specifies the buttons to display in the exception message box.</span></span>  
  
    -   <span data-ttu-id="0ebc9-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A>: título del cuadro de diálogo del cuadro de mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-128"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Caption%2A> - Dialog box caption of the exception message box.</span></span>  
  
    -   <span data-ttu-id="0ebc9-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton>enumeración que especifica el botón predeterminado del cuadro de diálogo del cuadro de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-129"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.DefaultButton%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDefaultButton> enumeration that specifies the default button for the dialog box of the exception message box.</span></span>  
  
    -   <span data-ttu-id="0ebc9-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions>enumeración que se utiliza para controlar otros comportamientos del cuadro de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-130"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Options%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxOptions> enumeration that you use to control other behaviors of the exception message box.</span></span>  
  
    -   <span data-ttu-id="0ebc9-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol>enumeración que especifica el símbolo que se va a mostrar en el cuadro de mensaje de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-131"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Symbol%2A> - <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxSymbol> enumeration that specifies the symbol to display in the exception message box.</span></span>  
  
5.  <span data-ttu-id="0ebc9-132">Llame al método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-132">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="0ebc9-133">Pase la ventana primaria a la que pertenece el cuadro de mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-133">Pass the parent window to which the exception message box belongs.</span></span>  
  
6.  <span data-ttu-id="0ebc9-134">(Opcional) Tenga en cuenta el valor de la enumeración <xref:System.Windows.Forms.DialogResult> devuelta si necesita determinar en qué botón ha hecho clic el usuario.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-134">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span>  
  
#### <a name="to-display-the-exception-message-box-with-customized-buttons"></a><span data-ttu-id="0ebc9-135">Para mostrar el cuadro de mensajes de excepción con botones personalizados</span><span class="sxs-lookup"><span data-stu-id="0ebc9-135">To display the exception message box with customized buttons</span></span>  
  
1.  <span data-ttu-id="0ebc9-136">Agregue una referencia al ensamblado Microsoft.ExceptionMessageBox.dll en su proyecto de código administrado.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-136">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="0ebc9-137">Opta Agregue una `using` Directiva (C#) o `Imports` (Visual Basic .net) para usar el <xref:Microsoft.SqlServer.MessageBox> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-137">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="0ebc9-138">Cree una instancia de la clase <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> de una de estas dos formas:</span><span class="sxs-lookup"><span data-stu-id="0ebc9-138">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="0ebc9-139">Pase el <xref:System.Exception> objeto controlado por un `try` - `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-139">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="0ebc9-140">Pase el texto del mensaje como un valor <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-140">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="0ebc9-141">Establezca uno de los siguientes valores para <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>:</span><span class="sxs-lookup"><span data-stu-id="0ebc9-141">Set one of the following values for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Buttons%2A>:</span></span>  
  
    -   <span data-ttu-id="0ebc9-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore>: muestra los botones **anular**, **Reintentar**y **omitir** .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-142"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.AbortRetryIgnore> - displays the **Abort**, **Retry**, and **Ignore** buttons.</span></span>  
  
    -   <span data-ttu-id="0ebc9-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom>: muestra los botones personalizados.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-143"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.Custom> - displays custom buttons.</span></span>  
  
    -   <span data-ttu-id="0ebc9-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK>: muestra el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-144"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OK> - displays the **OK** button.</span></span>  
  
    -   <span data-ttu-id="0ebc9-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel>: muestra los botones **Aceptar** y **Cancelar** .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-145"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.OKCancel> - displays the **OK** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="0ebc9-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel>-muestra los botones **Reintentar** y **Cancelar** .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-146"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.RetryCancel> - displays the **Retry** and **Cancel** buttons.</span></span>  
  
    -   <span data-ttu-id="0ebc9-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo>: muestra los botones **sí** y **no** .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-147"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNo> - displays **Yes** and **No** buttons.</span></span>  
  
    -   <span data-ttu-id="0ebc9-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel>: muestra los botones **sí**, **no**y **Cancelar** .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-148"><xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxButtons.YesNoCancel> - displays **Yes**, **No**, and **Cancel** buttons.</span></span>  
  
5.  <span data-ttu-id="0ebc9-149">(Opcional) Si usa botones personalizados, llame a una de las sobrecargas del método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> para especificar el texto para un máximo de cinco botones personalizados.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-149">(Optional) If you use custom buttons, call one of the overloads of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.SetButtonText%2A> method to specify text for up to five custom buttons.</span></span>  
  
6.  <span data-ttu-id="0ebc9-150">Llame al método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-150">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="0ebc9-151">Pase la ventana primaria a la que pertenece el cuadro de mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-151">Pass the parent window to which the exception message box belongs.</span></span>  
  
7.  <span data-ttu-id="0ebc9-152">(Opcional) Tenga en cuenta el valor de la enumeración <xref:System.Windows.Forms.DialogResult> devuelta si necesita determinar en qué botón ha hecho clic el usuario.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-152">(Optional) Note the value of the returned <xref:System.Windows.Forms.DialogResult> enumeration if you need to determine which button the user clicked.</span></span> <span data-ttu-id="0ebc9-153">Si usa botones personalizados, tenga en cuenta el valor de <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> para que la propiedad <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> determine en cuál de los botones personalizados ha hecho clic el usuario.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-153">If you use custom buttons, note the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBoxDialogResult> for the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CustomDialogResult%2A> property to determine which of the custom buttons the user clicked.</span></span>  
  
#### <a name="to-allow-users-to-decide-whether-to-show-the-exception-message-box"></a><span data-ttu-id="0ebc9-154">Para permitir que los usuarios decidan si desean mostrar el cuadro de mensajes de excepción</span><span class="sxs-lookup"><span data-stu-id="0ebc9-154">To allow users to decide whether to show the exception message box</span></span>  
  
1.  <span data-ttu-id="0ebc9-155">Agregue una referencia al ensamblado Microsoft.ExceptionMessageBox.dll en su proyecto de código administrado.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-155">Add a reference in your managed code project to the Microsoft.ExceptionMessageBox.dll assembly.</span></span>  
  
2.  <span data-ttu-id="0ebc9-156">Opta Agregue una `using` Directiva (C#) o `Imports` (Visual Basic .net) para usar el <xref:Microsoft.SqlServer.MessageBox> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-156">(Optional) Add a `using` (C#) or `Imports` (Visual Basic .NET) directive to use the <xref:Microsoft.SqlServer.MessageBox> namespace.</span></span>  
  
3.  <span data-ttu-id="0ebc9-157">Cree una instancia de la clase <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> de una de estas dos formas:</span><span class="sxs-lookup"><span data-stu-id="0ebc9-157">Create an instance of the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in one of two ways:</span></span>  
  
    -   <span data-ttu-id="0ebc9-158">Pase el <xref:System.Exception> objeto controlado por un `try` - `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-158">Pass the <xref:System.Exception> object handled by a `try`-`catch` block.</span></span>  
  
    -   <span data-ttu-id="0ebc9-159">Pase el texto del mensaje como un valor <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-159">Pass the message text as a <xref:System.String> value.</span></span>  
  
4.  <span data-ttu-id="0ebc9-160">Establezca la propiedad <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-160">Set the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.ShowCheckbox%2A> property to `true`.</span></span>  
  
5.  <span data-ttu-id="0ebc9-161">(Opcional) Especifique el texto donde se solicita al usuario que decida si desea que se muestre de nuevo el cuadro de mensajes de excepción para <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-161">(Optional) Specify the text that asks the user to decide whether to show the exception message box again for <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxText%2A>.</span></span> <span data-ttu-id="0ebc9-162">El texto predeterminado es "No volver a mostrar este mensaje".</span><span class="sxs-lookup"><span data-stu-id="0ebc9-162">The default text is "Do not show this message again."</span></span>  
  
6.  <span data-ttu-id="0ebc9-163">Si necesita mantener la decisión del usuario solamente durante la ejecución de la aplicación, establezca el valor de <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> en una variable <xref:System.Boolean> global.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-163">If you need to keep the user's decision only for the duration of the application's execution, set the value of <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.IsCheckboxChecked%2A> to a global <xref:System.Boolean> variable.</span></span> <span data-ttu-id="0ebc9-164">Evalúe este valor antes de crear una instancia del cuadro de mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-164">Evaluate this value before creating an instance of the exception message box.</span></span>  
  
7.  <span data-ttu-id="0ebc9-165">Si necesita almacenar la decisión de un usuario de manera permanente, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ebc9-165">If you need to store a user's decision permanently, do the following:</span></span>  
  
    1.  <span data-ttu-id="0ebc9-166">Llame al método CreateSubKey para abrir una clave del Registro personalizada utilizada por la aplicación y establezca <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> en el objeto RegistryKey devuelto.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-166">Call the CreateSubKey method to open a custom registry key that your application uses, and set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryKey%2A> to the returned RegistryKey object.</span></span>  
  
    2.  <span data-ttu-id="0ebc9-167">Establezca <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> en el nombre del valor del Registro utilizado.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-167">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryValue%2A> to the name of the registry value that is used.</span></span>  
  
    3.  <span data-ttu-id="0ebc9-168">Establezca <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-168">Set <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.CheckboxRegistryMeansDoNotShowDialog%2A> to `true`.</span></span>  
  
    4.  <span data-ttu-id="0ebc9-169">Llame al método <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="0ebc9-169">Call the <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox.Show%2A> method.</span></span> <span data-ttu-id="0ebc9-170">Se evalúa la clave del Registro especificada y solamente se muestra el cuadro de mensajes de excepción si los datos almacenados en la clave del Registro son iguales a 0.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-170">The specified registry key is evaluated, and the exception message box is displayed only if the data stored in the registry key is 0.</span></span> <span data-ttu-id="0ebc9-171">Si se muestra el cuadro de diálogo y el usuario activa la casilla antes de hacer clic en un botón, los datos de la clave del Registro se establecen en 1.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-171">If the dialog box is displayed and the user selects the check box before clicking a button, the data in the registry key is set to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ebc9-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ebc9-172">Example</span></span>  
 <span data-ttu-id="0ebc9-173">En este ejemplo, el cuadro de mensajes de excepción se usa solamente con el botón **Aceptar** para mostrar información de una excepción de la aplicación que incluye la excepción controlada junto con información adicional específica de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-173">This example uses the exception message box with only the **OK** button to display information from an application exception that includes the handled exception along with additional application-specific information.</span></span>  
  
 [!code-csharp[HowTo#emb_showOKbutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showokbutton)]  
  
 [!code-vb[HowTo#emb_vb_showOKbutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showokbutton)]  
  
## <a name="example"></a><span data-ttu-id="0ebc9-174">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ebc9-174">Example</span></span>  
 <span data-ttu-id="0ebc9-175">En este ejemplo se usa el cuadro de mensajes de excepción con los botones **Sí** y **No** entre los que debe elegir el usuario.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-175">This example uses the exception message box with **Yes** and **No** buttons from which the user chooses.</span></span>  
  
 [!code-csharp[HowTo#emb_showYesNobutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showyesnobutton)]  
  
 [!code-vb[HowTo#emb_vb_showYesNobutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showyesnobutton)]  
  
## <a name="example"></a><span data-ttu-id="0ebc9-176">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ebc9-176">Example</span></span>  
 <span data-ttu-id="0ebc9-177">En este ejemplo se usa el cuadro de mensajes de excepción con botones personalizados.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-177">This example uses the exception message box with custom buttons.</span></span>  
  
 [!code-csharp[HowTo#emb_showcustombutton](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_showcustombutton)]  
  
 [!code-vb[HowTo#emb_vb_showcustombutton](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_showcustombutton)]  
  
## <a name="example"></a><span data-ttu-id="0ebc9-178">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ebc9-178">Example</span></span>  
 <span data-ttu-id="0ebc9-179">En este ejemplo se usa la casilla para determinar si debe mostrarse el cuadro de mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-179">This example uses the check box to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_usecheckbox](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_usecheckbox)]  
  
 [!code-vb[HowTo#emb_vb_usecheckbox](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_usecheckbox)]  
  
## <a name="example"></a><span data-ttu-id="0ebc9-180">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ebc9-180">Example</span></span>  
 <span data-ttu-id="0ebc9-181">En este ejemplo se usa la casilla y una clave del Registro para determinar si debe mostrarse el cuadro de mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-181">This example uses the check box and a registry key to determine whether to show the exception message box.</span></span>  
  
 [!code-csharp[HowTo#emb_useregkey](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_useregkey)]  
  
 [!code-vb[HowTo#emb_vb_useregkey](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_useregkey)]  
  
## <a name="example"></a><span data-ttu-id="0ebc9-182">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ebc9-182">Example</span></span>  
 <span data-ttu-id="0ebc9-183">En este ejemplo se usa el cuadro de mensajes de excepción para mostrar información adicional que puede resultar de utilidad para la depuración o solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="0ebc9-183">This example uses the exception message box to show additional information that is helpful when troubleshooting or debugging.</span></span>  
  
 [!code-csharp[HowTo#emb_moreinfo](../../snippets/csharp/SQL15/replication/howto/cs/embform.cs#emb_moreinfo)]  
  
 [!code-vb[HowTo#emb_vb_moreinfo](../../snippets/visualbasic/SQL15/replication/howto/vb/embform.vb#emb_vb_moreinfo)]  
  
  
