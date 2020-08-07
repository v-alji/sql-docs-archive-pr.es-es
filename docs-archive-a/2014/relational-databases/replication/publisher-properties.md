---
title: Propiedades del publicador de Replicación de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.distpubproperties.f1
- sql12.rep.configdistwizard.pubproperties.general.f1
- sql12.rep.configdistwizard.pubproperties.pubdb.f1
- sql12.rep.configdistwizard.pubproperties.subscribers.f1
ms.assetid: 98df1aea-0406-40bf-a917-4bd80464125c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e14f82e855cc29f83859d85dfdaaf85a1bda37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746244"
---
# <a name="sql-server-replication-publisher-properties"></a><span data-ttu-id="14e5a-102">Propiedades del publicador de Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="14e5a-102">SQL Server Replication Publisher Properties</span></span>
  <span data-ttu-id="14e5a-103">Esta sección contiene información sobre las propiedades del publicador disponibles en el distribuidor y en el publicador.</span><span class="sxs-lookup"><span data-stu-id="14e5a-103">This section contains information on Publisher properties available at the Distributor and the Publisher.</span></span> 

## <a name="general"></a><span data-ttu-id="14e5a-104">General</span><span class="sxs-lookup"><span data-stu-id="14e5a-104">General</span></span>  
  <span data-ttu-id="14e5a-105"> La página **General** del cuadro de diálogo **Propiedades del publicador** muestra información de solo lectura sobre el distribuidor y la base de datos de distribución que usa el publicador.</span><span class="sxs-lookup"><span data-stu-id="14e5a-105">The **General** page of the **Publisher Properties** dialog box displays read-only information on the Distributor and distribution database that the Publisher uses.</span></span> <span data-ttu-id="14e5a-106">Para cambiar el distribuidor o la base de datos de distribución de un publicador:</span><span class="sxs-lookup"><span data-stu-id="14e5a-106">To change the Distributor or distribution database for a Publisher:</span></span>  
  
1.  <span data-ttu-id="14e5a-107">Deshabilite la publicación en el publicador.</span><span class="sxs-lookup"><span data-stu-id="14e5a-107">Disable publishing on the Publisher.</span></span> <span data-ttu-id="14e5a-108">Para obtener más información, vea [Deshabilitar la publicación y distribución](disable-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="14e5a-108">For more information, see [Disable Publishing and Distribution](disable-publishing-and-distribution.md).</span></span>    
2.  <span data-ttu-id="14e5a-109">Vuelva a configurar la publicación y la distribución.</span><span class="sxs-lookup"><span data-stu-id="14e5a-109">Reconfigure publishing and distribution.</span></span> <span data-ttu-id="14e5a-110">Para obtener más información, consulte [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="14e5a-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  

## <a name="distributor"></a><span data-ttu-id="14e5a-111">Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="14e5a-111">Distributor</span></span>
  <span data-ttu-id="14e5a-112"> El cuadro de diálogo **Propiedades del publicador** le permitirá ver y modificar las propiedades asociadas con la relación entre el publicador y el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="14e5a-112">The **Publisher Properties** dialog box allows you to view and modify properties associated with the relationship between the Publisher and its Distributor.</span></span>  
  
### <a name="options"></a><span data-ttu-id="14e5a-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="14e5a-113">Options</span></span>  
 <span data-ttu-id="14e5a-114">**Conexión del agente al publicador**</span><span class="sxs-lookup"><span data-stu-id="14e5a-114">**Agent Connection to the Publisher**</span></span>  
 <span data-ttu-id="14e5a-115">Especifique el contexto en el que los siguientes agentes establecerán conexiones del distribuidor al publicador:</span><span class="sxs-lookup"><span data-stu-id="14e5a-115">Specify the context under which the following agents make connections from the Distributor to the Publisher:</span></span>  
  
-   <span data-ttu-id="14e5a-116">Agente de lectura de cola para publicaciones transaccionales que permiten suscripciones de actualización en cola</span><span class="sxs-lookup"><span data-stu-id="14e5a-116">The Queue Reader Agent for transactional publications that allow queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="14e5a-117">Agente de instantáneas y Agente de registro del LOG para publicaciones de Oracle</span><span class="sxs-lookup"><span data-stu-id="14e5a-117">The Snapshot Agent and Log Reader Agent for Oracle publications.</span></span>  
  
 <span data-ttu-id="14e5a-118">Seleccione **Suplantar cuenta de proceso del agente** para establecer conexiones al publicador a través del contexto de la cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con la que se ejecutan los agentes o especifique **Autenticación de SQL Server**y escriba un valor para **Inicio de sesión** y **Contraseña**.</span><span class="sxs-lookup"><span data-stu-id="14e5a-118">Select **Impersonate agent process account** to make connections to the Publisher using the context of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which these agents run, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> <span data-ttu-id="14e5a-119">Se recomienda seleccionar **Suplantar cuenta de proceso del agente**.</span><span class="sxs-lookup"><span data-stu-id="14e5a-119">It is recommended that you select **Impersonate agent process account**.</span></span> <span data-ttu-id="14e5a-120">Para obtener más información, vea [Modelo de seguridad del agente de replicación](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="14e5a-120">For more information on agent security, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
 <span data-ttu-id="14e5a-121">Las cuentas de Windows con las que se ejecutan los agentes se especifican en el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="14e5a-121">The Windows accounts under which these agents run are specified in the New Publication Wizard.</span></span> <span data-ttu-id="14e5a-122">Podrá cambiar las cuentas:</span><span class="sxs-lookup"><span data-stu-id="14e5a-122">These accounts can be changed:</span></span>  
  
-   <span data-ttu-id="14e5a-123">En el cuadro de diálogo **Propiedades del distribuidor** del Agente de lectura de cola.</span><span class="sxs-lookup"><span data-stu-id="14e5a-123">In the **Distributor Properties** dialog box for the Queue Reader Agent.</span></span>  
  
-   <span data-ttu-id="14e5a-124">En el cuadro de diálogo **Propiedades de la publicación** del Agente de instantáneas y del Agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="14e5a-124">In the **Publication Properties** dialog box for the Snapshot Agent and Log Reader Agent.</span></span>  
  
 <span data-ttu-id="14e5a-125">**Varios**</span><span class="sxs-lookup"><span data-stu-id="14e5a-125">**Miscellaneous**</span></span>  
 <span data-ttu-id="14e5a-126">Las propiedades **Tipo de publicador** y **Nombre de base de datos de distribución** son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="14e5a-126">The properties **Publisher Type** and **Distribution Database Name** are read-only.</span></span> <span data-ttu-id="14e5a-127">Es posible cambiar la propiedad **Carpeta de instantáneas predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="14e5a-127">The property **Default Snapshot Folder** can be changed.</span></span> <span data-ttu-id="14e5a-128">Para obtener más información sobre la carpeta de instantáneas, vea [Proteger la carpeta de instantáneas](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="14e5a-128">For more information about the snapshot folder, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  

## <a name="publication-databases"></a><span data-ttu-id="14e5a-129">Bases de datos de publicación</span><span class="sxs-lookup"><span data-stu-id="14e5a-129">Publication Databases</span></span>
  <span data-ttu-id="14e5a-130">La página **Bases de datos de publicaciones** del cuadro de diálogo **Propiedades del publicador** permite a un usuario que tenga el rol fijo de servidor **sysadmin** habilitar bases de datos para replicación.</span><span class="sxs-lookup"><span data-stu-id="14e5a-130">The **Publication Databases** page of the **Publisher Properties** dialog box allows a user in the **sysadmin** fixed server role to enable databases for replication.</span></span> <span data-ttu-id="14e5a-131">Al habilitar una base de datos, ésta no se publica, sino que permite que cualquier usuario del rol fijo de base de datos **db_owner** para esa base de datos cree una o varias publicaciones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14e5a-131">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications on the database.</span></span>  
  
### <a name="options"></a><span data-ttu-id="14e5a-132">Opciones</span><span class="sxs-lookup"><span data-stu-id="14e5a-132">Options</span></span>  
 <span data-ttu-id="14e5a-133">**Transaccional**</span><span class="sxs-lookup"><span data-stu-id="14e5a-133">**Transactional**</span></span>  
 <span data-ttu-id="14e5a-134">Active esta casilla para permitir que los usuarios que tengan el rol fijo de base de datos **db_owner** creen publicaciones de instantáneas o publicaciones transaccionales en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14e5a-134">Select this check box to allow users in the **db_owner** fixed database role to create snapshot publications or transactional publications in the database.</span></span> 
  
 <span data-ttu-id="14e5a-135">**Combinar**</span><span class="sxs-lookup"><span data-stu-id="14e5a-135">**Merge**</span></span>  
 <span data-ttu-id="14e5a-136">Active esta casilla para permitir que los usuarios que tengan el rol fijo de base de datos **db_owner** creen publicaciones de combinación en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="14e5a-136">Select this check box to allow users in the **db_owner** fixed database role to create merge publications in the database.</span></span>  

## <a name="subscribers"></a><span data-ttu-id="14e5a-137">Suscriptores</span><span class="sxs-lookup"><span data-stu-id="14e5a-137">Subscribers</span></span>

  <span data-ttu-id="14e5a-138">La página **Suscriptores** del cuadro de diálogo **Propiedades del publicador** se utiliza para que los publicadores ejecuten versiones de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14e5a-138">The **Subscribers** page of the **Publisher Properties** dialog box is used for Publishers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="14e5a-139">Esta página permite habilitar a los suscriptores para que reciban datos de publicaciones de este Publicador.</span><span class="sxs-lookup"><span data-stu-id="14e5a-139">The page allows you to enable Subscribers to receive data from publications on this Publisher.</span></span> <span data-ttu-id="14e5a-140">Al habilitar un suscriptor para que reciba de desde este Publicador no se crean suscripciones para publicaciones de este publicador.</span><span class="sxs-lookup"><span data-stu-id="14e5a-140">Enabling a Subscriber to receive data from this Publisher does not create subscriptions to publications on this Publisher.</span></span> <span data-ttu-id="14e5a-141">Para crear una suscripción, debe utilizar el Asistente para nueva suscripción.</span><span class="sxs-lookup"><span data-stu-id="14e5a-141">To create a subscription, you must use the New Subscription Wizard.</span></span>  
  
### <a name="options"></a><span data-ttu-id="14e5a-142">Opciones</span><span class="sxs-lookup"><span data-stu-id="14e5a-142">Options</span></span>  
 <span data-ttu-id="14e5a-143">**Suscriptores**</span><span class="sxs-lookup"><span data-stu-id="14e5a-143">**Subscribers**</span></span>  
 <span data-ttu-id="14e5a-144">La cuadrícula de propiedades de **Suscriptores** muestra los suscriptores que están habilitados para recibir datos de las publicaciones de este publicador.</span><span class="sxs-lookup"><span data-stu-id="14e5a-144">The **Subscribers** property grid shows Subscribers that are enabled to receive data from publications on this Publisher.</span></span> <span data-ttu-id="14e5a-145">Haga clic en el botón de propiedades (**...**) que se encuentra junto a un suscriptor para ver y establecer propiedades adicionales.</span><span class="sxs-lookup"><span data-stu-id="14e5a-145">Click the properties button (**...**) next to a Subscriber to view and set additional properties.</span></span>  
  
 <span data-ttu-id="14e5a-146">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="14e5a-146">**Add**</span></span>  
 <span data-ttu-id="14e5a-147">Haga clic en **Agregar** para agregar un suscriptor, y luego haga clic en **Agregar suscriptor de SQL Server** o en **Agregar suscriptor que no sea de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="14e5a-147">Click **Add** to add a Subscriber, and then click **Add SQL Server Subscriber** or **Add Non-SQL Server Subscriber**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="14e5a-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14e5a-148">See Also</span></span>  
 [<span data-ttu-id="14e5a-149">Ver y modificar las propiedades del distribuidor y del publicador</span><span class="sxs-lookup"><span data-stu-id="14e5a-149">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
  
