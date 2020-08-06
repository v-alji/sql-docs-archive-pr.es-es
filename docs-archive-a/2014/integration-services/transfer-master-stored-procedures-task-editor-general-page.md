---
title: Editor de la tarea transferir procedimientos almacenados principales (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.general.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: fa1abd4c-e2be-427f-be53-860e49c97227
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a25a5c9c6ed3802e21ac522e94163ce5fb9e8c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747100"
---
# <a name="transfer-master-stored-procedures-task-editor-general-page"></a><span data-ttu-id="33d03-102">Editor de la tarea Transferir procedimientos almacenados principales (Página General)</span><span class="sxs-lookup"><span data-stu-id="33d03-102">Transfer Master Stored Procedures Task Editor (General Page)</span></span>
  <span data-ttu-id="33d03-103">Use la página **General** del cuadro de diálogo **Editor de la tarea Transferir procedimientos almacenados principales** para asignar un nombre a la tarea de transferencia de procedimientos almacenados master y describirla.</span><span class="sxs-lookup"><span data-stu-id="33d03-103">Use the **General** page of the **Transfer Master Stored Procedures Task Editor** dialog box to name and describe the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="33d03-104">Para obtener más información acerca de esta tarea, vea [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="33d03-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33d03-105">Esta tarea transfiere solo los procedimientos almacenados definidos por el usuario que pertenecen a **dbo** desde una base de datos **master** del servidor de origen a una base de datos **master** del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="33d03-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="33d03-106">A los usuarios se les debe conceder el permiso CREATE PROCEDURE en la base de datos **maestra** del servidor de destino o deben ser miembros del rol fijo del servidor **sysadmin** del servidor de destino para crear procedimientos almacenados en dicho servidor.</span><span class="sxs-lookup"><span data-stu-id="33d03-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="33d03-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="33d03-107">Options</span></span>  
 <span data-ttu-id="33d03-108">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="33d03-108">**Name**</span></span>  
 <span data-ttu-id="33d03-109">Escriba un nombre único para la tarea de transferencia de procedimientos almacenados principales.</span><span class="sxs-lookup"><span data-stu-id="33d03-109">Type a unique name for the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="33d03-110">Este nombre se utiliza como etiqueta en el icono de tarea.</span><span class="sxs-lookup"><span data-stu-id="33d03-110">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33d03-111">Los nombres de tarea deben ser únicos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="33d03-111">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="33d03-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="33d03-112">**Description**</span></span>  
 <span data-ttu-id="33d03-113">Escriba una descripción de la tarea de transferencia de procedimientos almacenados principales.</span><span class="sxs-lookup"><span data-stu-id="33d03-113">Type a description of the Transfer Master Stored Procedures task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d03-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33d03-114">See Also</span></span>  
 <span data-ttu-id="33d03-115">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="33d03-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="33d03-116">[Tareas de Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="33d03-116">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="33d03-117">[Editor de la tarea transferir procedimientos almacenados principales &#40;página procedimientos almacenados&#41;](../../2014/integration-services/transfer-master-stored-procedures-task-editor-stored-procedures-page.md) </span><span class="sxs-lookup"><span data-stu-id="33d03-117">[Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;](../../2014/integration-services/transfer-master-stored-procedures-task-editor-stored-procedures-page.md) </span></span>  
 [<span data-ttu-id="33d03-118">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="33d03-118">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
