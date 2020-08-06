---
title: Creación de una nueva cuenta de Correo electrónico de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], accounts
- accounts [Database Mail]
ms.assetid: c07abbc6-fc6a-470b-8fa3-532f2e06b16a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec7d1c9147998b5a19cc0e6af13220bd64e165fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671096"
---
# <a name="create-a-database-mail-account"></a><span data-ttu-id="62ebd-102">Crear una nueva cuenta de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="62ebd-102">Create a Database Mail Account</span></span>
  <span data-ttu-id="62ebd-103">Use el **Asistente para configuración de Correo electrónico de base de datos** o [!INCLUDE[tsql](../../includes/tsql-md.md)] para crear una cuenta de Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="62ebd-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create a Database Mail account.</span></span>  
  
-   <span data-ttu-id="62ebd-104">**Antes de empezar:**  [Requisitos previos](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="62ebd-104">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
-   <span data-ttu-id="62ebd-105">**Para crear una cuenta de Correo electrónico de base de datos, mediante:**  [Asistente para configuración de Correo electrónico de base de datos](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="62ebd-105">**To Create a Database Mail Account, using:**  [Database Mail Configuration Wizard](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="62ebd-106">**Seguimiento:**  [pasos siguientes para configurar el Correo electrónico de base de datos](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="62ebd-106">**Follow Up:**  [Next Steps to Configure the Database Mail](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="62ebd-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="62ebd-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="62ebd-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="62ebd-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="62ebd-109">Determine el nombre y el número de puerto del servidor de Protocolo simple de transferencia de correo (SMTP) que usa para enviar correo electrónico. Si el SMTP precisa autenticación, determine el nombre de usuario y la contraseña para el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="62ebd-109">Determine the server name and port number for the Simple Mail Transfer Protocol (SMTP) server you use to send e-mail.If the SMTP server requires authentication, determine the user name and password for the SMTP server.</span></span>  
  
-   <span data-ttu-id="62ebd-110">Opcionalmente, también puede especificar el tipo de servidor y el número de puerto del servidor.</span><span class="sxs-lookup"><span data-stu-id="62ebd-110">Optionally, you may also specify the type of the server and the port number for the server.</span></span> <span data-ttu-id="62ebd-111">El tipo de servidor siempre es 'SMTP' para el correo saliente.</span><span class="sxs-lookup"><span data-stu-id="62ebd-111">The server type is always 'SMTP' for outgoing mail.</span></span> <span data-ttu-id="62ebd-112">La mayoría de los servidores SMTP usan el puerto 25, es decir, el puerto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="62ebd-112">Most SMTP servers use port 25, the default.</span></span>  
  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="62ebd-113">Usar el asistente para configuración del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="62ebd-113">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="62ebd-114">**Para crear una cuenta de Correo electrónico de base de datos mediante un asistente**</span><span class="sxs-lookup"><span data-stu-id="62ebd-114">**To create a Database Mail account using a Wizard**</span></span>  
  
-   <span data-ttu-id="62ebd-115">En el explorador de objetos, conecte a la instancia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la que quiera configurar el Correo electrónico de base de datos y expanda el árbol del servidor.</span><span class="sxs-lookup"><span data-stu-id="62ebd-115">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="62ebd-116">Expanda el nodo **Administración** .</span><span class="sxs-lookup"><span data-stu-id="62ebd-116">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="62ebd-117">Haga doble clic en el Correo electrónico de base de datos para abrir el asistente de configuración del Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="62ebd-117">Double Click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="62ebd-118">En la página de **Seleccionar tarea de configuración** , seleccione **Administrar cuentas y perfiles de Correo electrónico de base de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="62ebd-118">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles**, and click **Next**.</span></span>  
  
-   <span data-ttu-id="62ebd-119">En la página de **Administrar perfiles y cuentas** , seleccione **Crear una nueva cuenta** y haga clic **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="62ebd-119">On the **Manage Profiles and Accounts** page, select **Create a new account** and click **Next**.</span></span>  
  
-   <span data-ttu-id="62ebd-120">En la página de **Nueva cuenta** , especifique el nombre de cuenta, la descripción, la información del servidor de correo, y el tipo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="62ebd-120">On the **New Account** page, specify the account name, description, mail server information, and authentication type.</span></span> <span data-ttu-id="62ebd-121">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="62ebd-121">Click **Next**</span></span>  
  
-   <span data-ttu-id="62ebd-122">En la página de **Finalización del asistente** , revise las acciones que realizará y haga clic en **Finalizar** para completar crear la nueva cuenta.</span><span class="sxs-lookup"><span data-stu-id="62ebd-122">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new account.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="62ebd-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="62ebd-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="62ebd-124">**Para crear una cuenta de Correo electrónico de base de datos mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="62ebd-124">**To Create a Database Mail account using Transact-SQL**</span></span>  
  
 <span data-ttu-id="62ebd-125">Ejecute el procedimiento almacenado **msdb.dbo.sysmail_add_account_sp** para crear la cuenta, especificando:</span><span class="sxs-lookup"><span data-stu-id="62ebd-125">Execute the stored procedure **msdb.dbo.sysmail_add_account_sp** to create the account and specify the following information:</span></span>  
  
-   <span data-ttu-id="62ebd-126">El nombre de la cuenta que va a crear.</span><span class="sxs-lookup"><span data-stu-id="62ebd-126">The name of the account to create.</span></span>  
  
-   <span data-ttu-id="62ebd-127">Una descripción opcional de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="62ebd-127">An optional description of the account.</span></span>  
  
-   <span data-ttu-id="62ebd-128">La dirección de correo electrónico que se muestra en los mensajes de correo electrónico salientes.</span><span class="sxs-lookup"><span data-stu-id="62ebd-128">The e-mail address to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="62ebd-129">El nombre para mostrar que se muestra en los mensajes de correo electrónico salientes.</span><span class="sxs-lookup"><span data-stu-id="62ebd-129">The display name to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="62ebd-130">El nombre de servidor del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="62ebd-130">The server name of the SMTP server.</span></span>  
  
-   <span data-ttu-id="62ebd-131">El nombre de usuario que se utiliza para iniciar sesión en el servidor SMTP, si el servidor SMTP requiere autenticación.</span><span class="sxs-lookup"><span data-stu-id="62ebd-131">The user name to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
-   <span data-ttu-id="62ebd-132">La contraseña que se usa para iniciar sesión en el servidor SMTP, si el servidor SMTP requiere autenticación.</span><span class="sxs-lookup"><span data-stu-id="62ebd-132">The password to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
 <span data-ttu-id="62ebd-133">En el ejemplo siguiente se crea una nueva cuenta de Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="62ebd-133">The following example creates a new Database Mail account.</span></span>  
  
```  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
```  
  
##  <a name="follow-up-next-steps-to-configuring-the-database-mail"></a><a name="FollowUp"></a> <span data-ttu-id="62ebd-134">Seguimiento: pasos siguientes para configurar el Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="62ebd-134">Follow Up: Next Steps to Configuring the Database Mail</span></span>  
  
-   [<span data-ttu-id="62ebd-135">Crear un perfil de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="62ebd-135">Create a Database Mail Profile</span></span>](create-a-database-mail-profile.md)  
  
  
