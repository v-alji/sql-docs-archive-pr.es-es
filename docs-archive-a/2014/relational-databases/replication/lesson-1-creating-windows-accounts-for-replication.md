---
title: 'Lección 1: Creación de cuentas de Windows para replicación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
- replication [SQL Server], administering
ms.assetid: 65c3816b-47f0-448c-a4a4-ebd3e2a58820
author: rothja
ms.author: jroth
ms.openlocfilehash: 29f1008338b3ba728066ed611108477586a4c899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663332"
---
# <a name="lesson-1-creating-windows-accounts-for-replication"></a><span data-ttu-id="4429a-102">Lección 1: Crear cuentas de Windows para replicación</span><span class="sxs-lookup"><span data-stu-id="4429a-102">Lesson 1: Creating Windows Accounts for Replication</span></span>
  <span data-ttu-id="4429a-103">En esta lección creará cuentas de Windows para ejecutar agentes de replicación.</span><span class="sxs-lookup"><span data-stu-id="4429a-103">In this lesson, you will create Windows accounts to run replication agents.</span></span> <span data-ttu-id="4429a-104">Creará distintas cuentas de Windows en el servidor local para los siguientes agentes:</span><span class="sxs-lookup"><span data-stu-id="4429a-104">You will create a separate Windows account on the local server for the following agents:</span></span>  
  
|<span data-ttu-id="4429a-105">Agente</span><span class="sxs-lookup"><span data-stu-id="4429a-105">Agent</span></span>|<span data-ttu-id="4429a-106">Location</span><span class="sxs-lookup"><span data-stu-id="4429a-106">Location</span></span>|<span data-ttu-id="4429a-107">Nombre de cuenta</span><span class="sxs-lookup"><span data-stu-id="4429a-107">Account name</span></span>|  
|-----------|--------------|------------------|  
|<span data-ttu-id="4429a-108">Agente de instantáneas</span><span class="sxs-lookup"><span data-stu-id="4429a-108">Snapshot Agent</span></span>|<span data-ttu-id="4429a-109">Publisher</span><span class="sxs-lookup"><span data-stu-id="4429a-109">Publisher</span></span>|<span data-ttu-id="4429a-110">\<*machine_name*>\ repl_snapshot</span><span class="sxs-lookup"><span data-stu-id="4429a-110">\<*machine_name*>\repl_snapshot</span></span>|  
|<span data-ttu-id="4429a-111">Agente de registro del LOG</span><span class="sxs-lookup"><span data-stu-id="4429a-111">Log Reader Agent</span></span>|<span data-ttu-id="4429a-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="4429a-112">Publisher</span></span>|<span data-ttu-id="4429a-113">\<*machine_name*>\ repl_logreader</span><span class="sxs-lookup"><span data-stu-id="4429a-113">\<*machine_name*>\repl_logreader</span></span>|  
|<span data-ttu-id="4429a-114">Agente de distribución</span><span class="sxs-lookup"><span data-stu-id="4429a-114">Distribution Agent</span></span>|<span data-ttu-id="4429a-115">Publicador y suscriptor</span><span class="sxs-lookup"><span data-stu-id="4429a-115">Publisher and Subscriber</span></span>|<span data-ttu-id="4429a-116">\<*machine_name*>\ repl_distribution</span><span class="sxs-lookup"><span data-stu-id="4429a-116">\<*machine_name*>\repl_distribution</span></span>|  
|<span data-ttu-id="4429a-117">Agente de mezcla</span><span class="sxs-lookup"><span data-stu-id="4429a-117">Merge Agent</span></span>|<span data-ttu-id="4429a-118">Publicador y suscriptor</span><span class="sxs-lookup"><span data-stu-id="4429a-118">Publisher and Subscriber</span></span>|<span data-ttu-id="4429a-119">\<*machine_name*>\ repl_merge</span><span class="sxs-lookup"><span data-stu-id="4429a-119">\<*machine_name*>\repl_merge</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="4429a-120">En los tutoriales de replicación, el publicador y el distribuidor comparten la misma instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4429a-120">In the replication tutorials, the Publisher and Distributor share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4429a-121">El publicador y el suscriptor pueden compartir la misma instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], aunque no es necesario.</span><span class="sxs-lookup"><span data-stu-id="4429a-121">The Publisher and Subscriber may share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but it is not a requirement.</span></span> <span data-ttu-id="4429a-122">Si el publicador y el suscriptor comparten la misma instancia, no se requieren los pasos que se utilizan para crear las cuentas en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="4429a-122">If the Publisher and Subscriber share the same instance, the steps that are used to create accounts at the Subscriber are not required.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-publisher"></a><span data-ttu-id="4429a-123">Para crear cuentas locales de Windows para agentes de replicación en el publicador</span><span class="sxs-lookup"><span data-stu-id="4429a-123">To create local Windows accounts for replication agents at the Publisher</span></span>  
  
1.  <span data-ttu-id="4429a-124">En el publicador, vaya al Panel de control y abra **Administración de equipos** en **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="4429a-124">At the Publisher, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="4429a-125">En **Herramientas del sistema**, expanda **Usuarios y grupos locales**.</span><span class="sxs-lookup"><span data-stu-id="4429a-125">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="4429a-126">Haga clic con el botón secundario en **usuarios** y después haga clic en **nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="4429a-126">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="4429a-127">Escriba `repl_snapshot` en el cuadro **nombre de usuario** , proporcione la contraseña y otra información relevante y, a continuación, haga clic en **crear** para crear la cuenta de repl_snapshot.</span><span class="sxs-lookup"><span data-stu-id="4429a-127">Enter `repl_snapshot` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_snapshot account.</span></span>  
  
5.  <span data-ttu-id="4429a-128">Repita el paso anterior para crear las cuentas repl_logreader, repl_distribution y repl_merge.</span><span class="sxs-lookup"><span data-stu-id="4429a-128">Repeat the previous step to create the repl_logreader, repl_distribution, and repl_merge accounts.</span></span>  
  
6.  <span data-ttu-id="4429a-129">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4429a-129">Click **Close**.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-subscriber"></a><span data-ttu-id="4429a-130">Para crear cuentas locales de Windows para agentes de replicación en el suscriptor</span><span class="sxs-lookup"><span data-stu-id="4429a-130">To create local Windows accounts for replication agents at the Subscriber</span></span>  
  
1.  <span data-ttu-id="4429a-131">En el suscriptor, vaya al Panel de control y abra **Administración de equipos** en **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="4429a-131">At the Subscriber, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="4429a-132">En **Herramientas del sistema**, expanda **Usuarios y grupos locales**.</span><span class="sxs-lookup"><span data-stu-id="4429a-132">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="4429a-133">Haga clic con el botón secundario en **usuarios** y después haga clic en **nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="4429a-133">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="4429a-134">Escriba `repl_distribution` en el cuadro **nombre de usuario** , proporcione la contraseña y otra información relevante y, a continuación, haga clic en **crear** para crear la cuenta de repl_distribution.</span><span class="sxs-lookup"><span data-stu-id="4429a-134">Enter `repl_distribution` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_distribution account.</span></span>  
  
5.  <span data-ttu-id="4429a-135">Repita el paso anterior para crear la cuenta repl_merge.</span><span class="sxs-lookup"><span data-stu-id="4429a-135">Repeat the previous step to create the repl_merge account.</span></span>  
  
6.  <span data-ttu-id="4429a-136">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4429a-136">Click **Close**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4429a-137">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4429a-137">Next Steps</span></span>  
 <span data-ttu-id="4429a-138">Ha creado correctamente cuentas de Windows para agentes de replicación.</span><span class="sxs-lookup"><span data-stu-id="4429a-138">You have successfully created Windows accounts for replication agents.</span></span> <span data-ttu-id="4429a-139">A continuación, configurará la carpeta de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="4429a-139">Next, you will configure the snapshot folder.</span></span> <span data-ttu-id="4429a-140">Consulte [Lección 2: Preparar la carpeta de instantáneas](lesson-2-preparing-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="4429a-140">See [Lesson 2: Preparing the Snapshot Folder](lesson-2-preparing-the-snapshot-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4429a-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4429a-141">See Also</span></span>  
 [<span data-ttu-id="4429a-142">Información general sobre los agentes de replicación</span><span class="sxs-lookup"><span data-stu-id="4429a-142">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
