---
title: Editor de la tarea transferir mensajes de error (página mensajes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.errormessages.F1
helpviewer_keywords:
- Transfer Error Messages Task Editor
ms.assetid: cb2226a0-3037-4fdf-966f-81eabc0da9cf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0d626f01e05a30777810b26880da5aedc3e7ad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678248"
---
# <a name="transfer-error-messages-task-editor-messages-page"></a><span data-ttu-id="07a2a-102">Editor de la tarea Transferir mensajes de error (página Mensajes)</span><span class="sxs-lookup"><span data-stu-id="07a2a-102">Transfer Error Messages Task Editor (Messages Page)</span></span>
  <span data-ttu-id="07a2a-103">Use la página **Mensajes** del cuadro de diálogo **Editor de la tarea Transferir mensajes de error** para especificar propiedades para copiar uno o varios mensajes de error definidos por el usuario de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] de una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a otra.</span><span class="sxs-lookup"><span data-stu-id="07a2a-103">Use the **Messages** page of the **Transfer Error Messages Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] user-defined error messages from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="07a2a-104">Para obtener más información acerca de esta tarea, vea [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span><span class="sxs-lookup"><span data-stu-id="07a2a-104">For more information about this task, see [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="07a2a-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="07a2a-105">Options</span></span>  
 <span data-ttu-id="07a2a-106">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="07a2a-106">**SourceConnection**</span></span>  
 <span data-ttu-id="07a2a-107">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="07a2a-107">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="07a2a-108">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="07a2a-108">**DestinationConnection**</span></span>  
 <span data-ttu-id="07a2a-109">Seleccione un administrador de conexiones SMO de la lista o haga clic en **\<New connection...>** para crear una nueva conexión al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="07a2a-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="07a2a-110">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="07a2a-110">**IfObjectExists**</span></span>  
 <span data-ttu-id="07a2a-111">Seleccione si la tarea debe sobrescribir mensajes de error definidos por el usuario existentes, omitir mensajes existentes o generar un error si existen ya mensajes de error con el mismo nombre en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="07a2a-111">Select whether the task should overwrite existing user-defined error messages, skip existing messages, or fail if error messages of the same name already exist on the destination server.</span></span>  
  
 <span data-ttu-id="07a2a-112">**TransferAllErrorMessages**</span><span class="sxs-lookup"><span data-stu-id="07a2a-112">**TransferAllErrorMessages**</span></span>  
 <span data-ttu-id="07a2a-113">Seleccione si la tarea debe copiar todos los mensajes definidos por el usuario o solo los especificados del servidor de origen al de destino.</span><span class="sxs-lookup"><span data-stu-id="07a2a-113">Select whether the task should copy all or only the specified user-defined messages from the source server to the destination server.</span></span>  
  
 <span data-ttu-id="07a2a-114">Esta propiedad presenta las opciones indicadas en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="07a2a-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="07a2a-115">Value</span><span class="sxs-lookup"><span data-stu-id="07a2a-115">Value</span></span>|<span data-ttu-id="07a2a-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="07a2a-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="07a2a-117">**True**</span><span class="sxs-lookup"><span data-stu-id="07a2a-117">**True**</span></span>|<span data-ttu-id="07a2a-118">Copiar todos los mensajes definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="07a2a-118">Copy all user-defined messages.</span></span>|  
|<span data-ttu-id="07a2a-119">**False**</span><span class="sxs-lookup"><span data-stu-id="07a2a-119">**False**</span></span>|<span data-ttu-id="07a2a-120">Copiar solo los mensajes definidos por el usuario especificados.</span><span class="sxs-lookup"><span data-stu-id="07a2a-120">Copy only the specified user-defined messages.</span></span>|  
  
 <span data-ttu-id="07a2a-121">**ErrorMessagesList**</span><span class="sxs-lookup"><span data-stu-id="07a2a-121">**ErrorMessagesList**</span></span>  
 <span data-ttu-id="07a2a-122">Haga clic en el botón Examinar **(…)** para seleccionar los mensajes de error que quiera copiar.</span><span class="sxs-lookup"><span data-stu-id="07a2a-122">Click the browse button **(...)** to select the error messages to copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07a2a-123">Para poder seleccionar los mensajes de error que se van a copiar, debe especificar el parámetro **SourceConnection** .</span><span class="sxs-lookup"><span data-stu-id="07a2a-123">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
 <span data-ttu-id="07a2a-124">**ErrorMessageLanguagesList**</span><span class="sxs-lookup"><span data-stu-id="07a2a-124">**ErrorMessageLanguagesList**</span></span>  
 <span data-ttu-id="07a2a-125">Haga clic en el botón Examinar **(…)** para seleccionar los idiomas para los que se van a copiar mensajes de error definidos por el usuario al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="07a2a-125">Click the browse button **(...)** to select the languages for which to copy user-defined error messages to the destination server.</span></span> <span data-ttu-id="07a2a-126">Debe existir una versión en us_english (página de códigos 1033) del mensaje en el servidor de destino para poder transferir versiones en otros idiomas del mensaje a ese servidor.</span><span class="sxs-lookup"><span data-stu-id="07a2a-126">A us_english (code page 1033) version of the message must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07a2a-127">Para poder seleccionar los mensajes de error que se van a copiar, debe especificar el parámetro **SourceConnection** .</span><span class="sxs-lookup"><span data-stu-id="07a2a-127">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a2a-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07a2a-128">See Also</span></span>  
 <span data-ttu-id="07a2a-129">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="07a2a-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="07a2a-130">[Tareas de Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="07a2a-130">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="07a2a-131">[Editor de la tarea transferir mensajes de error &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="07a2a-131">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="07a2a-132">[Administrador de conexiones SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="07a2a-132">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="07a2a-133">[Editor de la tarea transferir mensajes de error &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="07a2a-133">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="07a2a-134">Administrador de conexiones SMO</span><span class="sxs-lookup"><span data-stu-id="07a2a-134">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
