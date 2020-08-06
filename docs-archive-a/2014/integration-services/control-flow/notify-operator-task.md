---
title: Tarea Notificar al operador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.notifyoperatortask.f1
helpviewer_keywords:
- Notify Operator task
- notifications [Integration Services]
- SQL Server Agent [Integration Services]
ms.assetid: 6c816c68-c6d6-44e4-bb34-c8e060a958a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed5158a4ec5cfe8374fedbb2afbca1294b58f05e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750065"
---
# <a name="notify-operator-task"></a><span data-ttu-id="7d609-102">Notificar al operador, tarea</span><span class="sxs-lookup"><span data-stu-id="7d609-102">Notify Operator Task</span></span>
  <span data-ttu-id="7d609-103">La tarea Notificar al operador envía mensajes de notificación a los operadores del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d609-103">The Notify Operator task sends notification messages to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operators.</span></span> <span data-ttu-id="7d609-104">Un operador del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es un alias para una persona o grupo que puede recibir notificaciones electrónicas.</span><span class="sxs-lookup"><span data-stu-id="7d609-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator is an alias for a person or group that can receive electronic notifications.</span></span> <span data-ttu-id="7d609-105">Para obtener más información sobre operadores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea [Operadores](../../ssms/agent//operators.md).</span><span class="sxs-lookup"><span data-stu-id="7d609-105">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operators, see [Operators](../../ssms/agent//operators.md).</span></span>  
  
 <span data-ttu-id="7d609-106">Si usa la tarea Notificar al operador, un paquete puede notificar a uno o más operadores a través de correo electrónico, buscapersonas o **net send**.</span><span class="sxs-lookup"><span data-stu-id="7d609-106">By using the Notify Operator task, a package can notify one or more operators via e-mail, pager, or **net send**.</span></span> <span data-ttu-id="7d609-107">Es posible notificar a cada operador por distintos métodos.</span><span class="sxs-lookup"><span data-stu-id="7d609-107">Each operator can be notified by different methods.</span></span> <span data-ttu-id="7d609-108">Por ejemplo, se notifica al Operador A por correo electrónico y mediante buscapersonas, y al Operador B mediante buscapersonas y **net send**.</span><span class="sxs-lookup"><span data-stu-id="7d609-108">For example, OperatorA is notified by e-mail and pager, and OperatorB is notified by pager and **net send**.</span></span> <span data-ttu-id="7d609-109">Los operadores que reciben notificaciones de la tarea deben ser miembros de la colección **OperatorNotify** en la tarea Notificar al operador.</span><span class="sxs-lookup"><span data-stu-id="7d609-109">The operators who receive notifications from the task must be members of the **OperatorNotify** collection on the Notify Operator task.</span></span>  
  
 <span data-ttu-id="7d609-110">La tarea Notificar al operador es la única tarea de mantenimiento de la base de datos que no encapsula una instrucción Transact-SQL o un comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="7d609-110">The Notify Operator task is the only database maintenance task that does not encapsulate a Transact-SQL statement or a DBCC command.</span></span>  
  
## <a name="configuration-of-the-notify-operator-task"></a><span data-ttu-id="7d609-111">Configuración de la tarea Notificar al operador</span><span class="sxs-lookup"><span data-stu-id="7d609-111">Configuration of the Notify Operator Task</span></span>  
 <span data-ttu-id="7d609-112">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d609-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="7d609-113">Esta tarea se encuentra en la sección **Tareas del plan de mantenimiento** del **Cuadro de herramientas** , en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d609-113">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7d609-114">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d609-114">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7d609-115">Tarea Notificar al operador &#40;Plan de mantenimiento&#41;</span><span class="sxs-lookup"><span data-stu-id="7d609-115">Notify Operator Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/notify-operator-task-maintenance-plan.md)  
  
 <span data-ttu-id="7d609-116">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="7d609-116">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="7d609-117">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="7d609-117">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
