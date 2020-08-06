---
title: Editor de la tarea FTP (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.general.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 28b46fdd-b04a-4f97-a99f-883f5735a6d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0cb4ffe2fa44e76890f6b70912f84dbcaa8f2cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670436"
---
# <a name="ftp-task-editor-general-page"></a><span data-ttu-id="0c03f-102">Editor de la tarea FTP (página General)</span><span class="sxs-lookup"><span data-stu-id="0c03f-102">FTP Task Editor (General Page)</span></span>
  <span data-ttu-id="0c03f-103">Use la página **General** del cuadro de diálogo **Editor de la tarea FTP** para especificar el administrador de conexiones FTP que se conecta al servidor FTP con el que se comunica la tarea.</span><span class="sxs-lookup"><span data-stu-id="0c03f-103">Use the **General** page of the **FTP Task Editor** dialog box to specify the FTP connection manager that connects to the FTP server that the task communicates with.</span></span> <span data-ttu-id="0c03f-104">También puede asignar un nombre a la tarea FTP y describirla.</span><span class="sxs-lookup"><span data-stu-id="0c03f-104">You can also name and describe the FTP task.</span></span>  
  
 <span data-ttu-id="0c03f-105">Para más información sobre esta tarea, vea [Tarea FTP](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="0c03f-105">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0c03f-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="0c03f-106">Options</span></span>  
 <span data-ttu-id="0c03f-107">**FtpConnection**</span><span class="sxs-lookup"><span data-stu-id="0c03f-107">**FtpConnection**</span></span>  
 <span data-ttu-id="0c03f-108">Seleccione un administrador de conexiones FTP existente o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="0c03f-108">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0c03f-109">El administrador de conexiones FTP solo admite la autenticación anónima y la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="0c03f-109">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="0c03f-110">No es compatible con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="0c03f-110">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="0c03f-111">**Temas relacionados**: [Administrador de conexiones FTP](connection-manager/ftp-connection-manager.md), [Editor del administrador de conexiones FTP](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="0c03f-111">**Related Topics**: [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="0c03f-112">**StopOnFailure**</span><span class="sxs-lookup"><span data-stu-id="0c03f-112">**StopOnFailure**</span></span>  
 <span data-ttu-id="0c03f-113">Indica si la tarea FTP termina si se produce un error en una opción FTP.</span><span class="sxs-lookup"><span data-stu-id="0c03f-113">Indicate whether the FTP task terminates if an FTP operation fails.</span></span>  
  
 <span data-ttu-id="0c03f-114">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="0c03f-114">**Name**</span></span>  
 <span data-ttu-id="0c03f-115">Proporcione un nombre único para la tarea FTP.</span><span class="sxs-lookup"><span data-stu-id="0c03f-115">Provide a unique name for the FTP task.</span></span> <span data-ttu-id="0c03f-116">Este nombre se utiliza como etiqueta en el icono de tarea.</span><span class="sxs-lookup"><span data-stu-id="0c03f-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c03f-117">Los nombres de tarea deben ser únicos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="0c03f-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="0c03f-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0c03f-118">**Description**</span></span>  
 <span data-ttu-id="0c03f-119">Escriba una descripción de la tarea FTP.</span><span class="sxs-lookup"><span data-stu-id="0c03f-119">Type a description of the FTP task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c03f-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c03f-120">See Also</span></span>  
 <span data-ttu-id="0c03f-121">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0c03f-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="0c03f-122">[Editor de la tarea FTP &#40;página transferencia de archivos&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span><span class="sxs-lookup"><span data-stu-id="0c03f-122">[FTP Task Editor &#40;File Transfer Page&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span></span>  
 [<span data-ttu-id="0c03f-123">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="0c03f-123">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
