---
title: Programación de cuadros de mensajes de excepción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- ExceptionMessageBox class, about ExceptionMessageBox class
- exception message box [SQL Server], about exception message box
- exception message box [SQL Server]
- interfaces [SQL Server]
- exceptions [SQL Server]
- messages [SQL Server], exception message box
ms.assetid: 0b1ba514-6959-4e69-bfd2-3cf3c1ac4b9c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2425169f838199ce24b4331dd57c74b480adf62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751434"
---
# <a name="exception-message-box-programming"></a><span data-ttu-id="a90e1-102">Programación de cuadros de mensajes de excepción</span><span class="sxs-lookup"><span data-stu-id="a90e1-102">Exception Message Box Programming</span></span>
  <span data-ttu-id="a90e1-103">El cuadro de mensaje de excepción es una interfaz de programación que se instala con [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] los componentes gráficos y los usa.</span><span class="sxs-lookup"><span data-stu-id="a90e1-103">The exception message box is a programmatic interface that is installed with and used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] graphical components.</span></span> <span data-ttu-id="a90e1-104">El cuadro de mensaje de excepción es un ensamblado administrado compatible que puede usar en sus aplicaciones para proporcionar un control considerablemente mayor sobre la experiencia de mensajería y ofrecer a sus usuarios la opción de guardar el contenido del mensaje de error para hacer referencia al mismo posteriormente y obtener la ayuda sobre los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a90e1-104">The exception message box is a supported managed assembly that you can use in your applications to provide significantly more control over the messaging experience and to give your users the options to save error message content for later reference and to get help on messages.</span></span> <span data-ttu-id="a90e1-105">Dado que todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalan el cuadro de mensaje de excepción, salvo [!INCLUDE[ssEW](../../includes/ssew-md.md)], puede usarlo sin ninguna configuración adicional en cualquier equipo en el que se hayan instalado los componentes de cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a90e1-105">Because the exception message box is installed by all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssEW](../../includes/ssew-md.md)], you can use it with no additional configuration on any computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client components have been installed.</span></span>  
  
 <span data-ttu-id="a90e1-106">La clase <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> del espacio de nombres <xref:Microsoft.SqlServer.MessageBox> incluye toda la funcionalidad de la clase <xref:System.Windows.Forms.MessageBox> y más.</span><span class="sxs-lookup"><span data-stu-id="a90e1-106">The <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in the <xref:Microsoft.SqlServer.MessageBox> namespace has all the functionality of the <xref:System.Windows.Forms.MessageBox> class and more.</span></span> <span data-ttu-id="a90e1-107">La clase <xref:System.Windows.Forms.MessageBox>, que resulta perfecta para cualquier tarea para la que pueda usarse <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>, está diseñada para administrar con elegancia excepciones de código administrado.</span><span class="sxs-lookup"><span data-stu-id="a90e1-107">Ideal for any tasks for which <xref:System.Windows.Forms.MessageBox> may be used, <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> is designed to elegantly handle managed code exceptions.</span></span> <span data-ttu-id="a90e1-108">El cuadro de mensaje de excepción le permite hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a90e1-108">The exception message box allows you to do the following:</span></span>  
  
-   <span data-ttu-id="a90e1-109">Proporcionar texto hasta para cinco botones personalizados.</span><span class="sxs-lookup"><span data-stu-id="a90e1-109">Provide customized button text for up to five buttons.</span></span> <span data-ttu-id="a90e1-110">Los botones y el cuadro de diálogo cambian de tamaño automáticamente para las distintas longitudes de texto.</span><span class="sxs-lookup"><span data-stu-id="a90e1-110">Buttons and the dialog box resize automatically for different text lengths.</span></span>  
  
-   <span data-ttu-id="a90e1-111">Permitir que los usuarios copien fácilmente en el Portapapeles el título del mensaje, el texto, el texto del botón y los vínculos de ayuda (si existen) o que envíen esta información en un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a90e1-111">Allow users to easily copy the message title, text, button text, and help links (if any) to the Clipboard or send this information in an e-mail message.</span></span>  
  
-   <span data-ttu-id="a90e1-112">Muestra todas las excepciones y los errores subyacentes en un árbol de relaciones jerárquicas cuando los usuarios hacen clic en **información adicional**.</span><span class="sxs-lookup"><span data-stu-id="a90e1-112">Display all underlying exceptions and errors in a hierarchical relationship tree when users click **Additional Information**.</span></span>  
  
-   <span data-ttu-id="a90e1-113">Permitir que los usuarios decidan si debe mostrarse el mensaje cuando vuelva a producirse la misma excepción.</span><span class="sxs-lookup"><span data-stu-id="a90e1-113">Allow users to decide whether to display the message when the same exception occurs again.</span></span>  
  
-   <span data-ttu-id="a90e1-114">Obtener acceso a un sistema de ayuda en pantalla utilizando un vínculo de ayuda asociado con la excepción.</span><span class="sxs-lookup"><span data-stu-id="a90e1-114">Access an online help system by using a help link associated with the exception.</span></span>  
  
 <span data-ttu-id="a90e1-115">Para obtener más información, vea [cuadro de mensaje de excepción de programa](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span><span class="sxs-lookup"><span data-stu-id="a90e1-115">For more information, see [Program Exception Message Box](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span></span>  
  
  
