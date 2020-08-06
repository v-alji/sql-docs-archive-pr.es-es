---
title: Inicio de sesión para suscripciones actualizables | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptionslogin.f1
ms.assetid: 301ea227-0455-40ba-9009-d38f8676b325
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a5cc9190c77f506b13ba8b5fba0e32d5a925570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749225"
---
# <a name="login-for-updatable-subscriptions"></a><span data-ttu-id="cd415-102">Inicio de sesión para suscripciones actualizables</span><span class="sxs-lookup"><span data-stu-id="cd415-102">Login for Updatable Subscriptions</span></span>
  <span data-ttu-id="cd415-103">Si ha seleccionado **Replicar** en la página **Suscripciones actualizables** de este asistente, debe especificar una cuenta en el suscriptor bajo la que se realizan las conexiones al publicador para las suscripciones de actualización inmediata.</span><span class="sxs-lookup"><span data-stu-id="cd415-103">If you selected **Replicate** on the **Updatable Subscriptions** page of this wizard, you must specify an account at the Subscriber under which connections to the Publisher are made for immediate updating subscriptions.</span></span> <span data-ttu-id="cd415-104">Las conexiones las utilizan los desencadenadores que se activan en el suscriptor y propagan los cambios al publicador.</span><span class="sxs-lookup"><span data-stu-id="cd415-104">Connections are used by the triggers that fire at the Subscriber and propagate changes to the Publisher.</span></span> <span data-ttu-id="cd415-105">Esta cuenta es necesaria aunque se haya seleccionado **Poner en cola cambios y confirmar cuando sea posible** en la página **Suscripciones actualizables** , porque, de forma predeterminada, el Asistente para nueva suscripción configura la actualización en cola con la capacidad para cambiar a actualización inmediata si es necesario.</span><span class="sxs-lookup"><span data-stu-id="cd415-105">This account is required even if you selected **Queue changes and commit when possible** on the **Updatable Subscriptions** page, because by default the New Subscription Wizard configures queued updating with the ability to switch to immediate updating if required.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd415-106">La cuenta especificada para la conexión solo debe tener permiso para insertar, actualizar y eliminar datos en las vistas que crea la replicación en la base de datos de publicaciones; no debe tener ningún permiso adicional.</span><span class="sxs-lookup"><span data-stu-id="cd415-106">The account specified for the connection should only be granted permission to insert, update, and delete data on the views that replication creates in the publication database; it should not be given any additional permissions.</span></span> <span data-ttu-id="cd415-107">Conceda permisos para las vistas de la base de datos de publicación designadas con el formato **syncobj_** _\<HexadecimalNumber>_ a la cuenta que ha configurado en cada suscriptor.</span><span class="sxs-lookup"><span data-stu-id="cd415-107">Grant permissions on views in the publication database that are named in the form **syncobj_**_\<HexadecimalNumber>_ to the account you configured at each Subscriber.</span></span>  
  
 <span data-ttu-id="cd415-108">Hay tres opciones disponibles para el tipo de conexión:</span><span class="sxs-lookup"><span data-stu-id="cd415-108">There are three options available for the type of connection:</span></span>  
  
-   <span data-ttu-id="cd415-109">Un servidor vinculado o un servidor remoto previamente definido.</span><span class="sxs-lookup"><span data-stu-id="cd415-109">A linked server or remote server that you have already defined.</span></span>  
  
-   <span data-ttu-id="cd415-110">Un servidor vinculado que crea la replicación; la conexión se establece con las credenciales especificadas en este asistente.</span><span class="sxs-lookup"><span data-stu-id="cd415-110">A linked server that replication creates; the connection is made with the credentials you specify in this wizard.</span></span>  
  
-   <span data-ttu-id="cd415-111">Un servidor vinculado que crea la replicación; la conexión se establece con las credenciales del usuario que realiza el cambio en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="cd415-111">A linked server that replication creates; the connection is made with the credentials of the user making the change at the Subscriber.</span></span>  
  
 <span data-ttu-id="cd415-112">Las dos primeras opciones se pueden especificar en este asistente.</span><span class="sxs-lookup"><span data-stu-id="cd415-112">The first two options can be specified in this wizard.</span></span> <span data-ttu-id="cd415-113">La última opción solo se puede especificar mediante [sp_link_publication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); Especifique un valor de **1** para el parámetro **@security_mode** .</span><span class="sxs-lookup"><span data-stu-id="cd415-113">The last option can only be specified using [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); specify a value of **1** for the parameter **@security_mode**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd415-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="cd415-114">Options</span></span>  
 <span data-ttu-id="cd415-115">**Crear un servidor vinculado que se conecte mediante el siguiente inicio de sesión para la Autenticación de SQL Server:**</span><span class="sxs-lookup"><span data-stu-id="cd415-115">**Create a linked server that connects using the following SQL Server Authentication login:**</span></span>  
 <span data-ttu-id="cd415-116">La replicación crea un servidor vinculado utilizando las credenciales especificadas en los campos **Inicio de sesión** y **Contraseña** .</span><span class="sxs-lookup"><span data-stu-id="cd415-116">Replication creates a linked server using the credentials specified in the **Login** and **Password** fields.</span></span>  
  
 <span data-ttu-id="cd415-117">**Inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="cd415-117">**Login**</span></span>  
 <span data-ttu-id="cd415-118">Escriba un inicio de sesión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que solo tenga los permisos descritos en este tema.</span><span class="sxs-lookup"><span data-stu-id="cd415-118">Enter a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that has only the permissions described in this topic.</span></span>  
  
 <span data-ttu-id="cd415-119">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="cd415-119">**Password**</span></span>  
 <span data-ttu-id="cd415-120">Escriba una contraseña segura para el inicio de sesión especificado en **Inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="cd415-120">Enter a strong password for the login specified in **Login**.</span></span>  
  
 <span data-ttu-id="cd415-121">**Confirmar contraseña**</span><span class="sxs-lookup"><span data-stu-id="cd415-121">**Confirm Password**</span></span>  
 <span data-ttu-id="cd415-122">Vuelva a escribir la contraseña para confirmar que se ha escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="cd415-122">Re-enter the password to confirm that it was entered correctly.</span></span>  
  
 <span data-ttu-id="cd415-123">**Utilizar un servidor vinculado o un servidor remoto que ya está definido.**</span><span class="sxs-lookup"><span data-stu-id="cd415-123">**Use a linked server or remote server that you have already defined.**</span></span>  
 <span data-ttu-id="cd415-124">Esta opción requiere un servidor vinculado o un servidor remoto que ya se ha definido.</span><span class="sxs-lookup"><span data-stu-id="cd415-124">This option requires a linked server or remote server that you have already defined.</span></span> <span data-ttu-id="cd415-125">Para obtener más información, vea [Servidores vinculados &#40;motor de base de datos&#41;](../linked-servers/linked-servers-database-engine.md) y [Servidores remotos](../../database-engine/configure-windows/remote-servers.md).</span><span class="sxs-lookup"><span data-stu-id="cd415-125">For more information, see [Linked Servers &#40;Database Engine&#41;](../linked-servers/linked-servers-database-engine.md) and [Remote Servers](../../database-engine/configure-windows/remote-servers.md).</span></span> <span data-ttu-id="cd415-126">Asegúrese de que el inicio de sesión utilizado para el servidor vinculado o el servidor remoto tiene una contraseña segura y solo tiene los permisos descritos en este tema.</span><span class="sxs-lookup"><span data-stu-id="cd415-126">Ensure that the login used for the linked server or remote server has a strong password and has only the permissions described in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd415-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd415-127">See Also</span></span>  
 <span data-ttu-id="cd415-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span><span class="sxs-lookup"><span data-stu-id="cd415-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span></span>  
 <span data-ttu-id="cd415-129">[View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md)  (Ver y modificar la configuración de seguridad de la replicación)</span><span class="sxs-lookup"><span data-stu-id="cd415-129">[View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md) </span></span>  
 <span data-ttu-id="cd415-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="cd415-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span></span>  
 [<span data-ttu-id="cd415-131">Suscribirse a publicaciones</span><span class="sxs-lookup"><span data-stu-id="cd415-131">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
