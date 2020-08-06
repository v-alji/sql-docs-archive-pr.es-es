---
title: Administración de inicios de sesión en la lista de acceso a la publicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server replication], publication access list
- publications [SQL Server replication], publication access lists
- publication access list (PAL)
- PAL (publication access list)
- logins [SQL Server replication], managing
ms.assetid: fceb216b-0b18-4e3b-8ae0-13e35920dcbc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b96e6f46403cf3a482f00a3f5155527177920967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670916"
---
# <a name="manage-logins-in-the-publication-access-list"></a><span data-ttu-id="8cf8c-102">Administrar inicios de sesión en la lista de acceso a la publicación</span><span class="sxs-lookup"><span data-stu-id="8cf8c-102">Manage Logins in the Publication Access List</span></span>
  <span data-ttu-id="8cf8c-103">En este tema se describe cómo administrar inicios de sesión en la lista de acceso a la publicación (PAL) en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8cf8c-103">This topic describes how to manage logins in the Publication Access List in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8cf8c-104">La lista de acceso a la publicación (PAL) controla el acceso a una publicación.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-104">Access to a publication is controlled by the publication access list (PAL).</span></span> <span data-ttu-id="8cf8c-105">Se pueden agregar y quitar inicios de sesión y grupos de la PAL.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-105">Logins and groups can be added and removed from the PAL.</span></span>  
  
 <span data-ttu-id="8cf8c-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="8cf8c-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8cf8c-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="8cf8c-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8cf8c-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8cf8c-108">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="8cf8c-109">**Para administrar inicios de sesión en la lista de acceso a la publicación con:**</span><span class="sxs-lookup"><span data-stu-id="8cf8c-109">**To manage logins in the Publication Access List, using:**</span></span>  
  
     [<span data-ttu-id="8cf8c-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8cf8c-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8cf8c-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8cf8c-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8cf8c-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8cf8c-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="8cf8c-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8cf8c-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="8cf8c-114">Debe asociar el inicio de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a un usuario de la base de datos de publicaciones antes de agregar el inicio de sesión a la PAL.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-114">You must associate the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login with a database user in the publication database before you add the login to the PAL.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8cf8c-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8cf8c-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8cf8c-116">Use la lista de acceso a la publicación (PAL) de la página **Lista de acceso a la publicación** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** para administrar los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-116">You use the publication access list (PAL) on the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box to manage logins.</span></span> <span data-ttu-id="8cf8c-117">Para obtener más información sobre cómo acceder a este cuadro de diálogo, vea [Ver y modificar propiedades de publicación](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8cf8c-117">For more information about how to access this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-manage-logins-in-the-pal"></a><span data-ttu-id="8cf8c-118">Para administrar inicios de sesión en la lista de acceso de la publicación</span><span class="sxs-lookup"><span data-stu-id="8cf8c-118">To manage logins in the PAL</span></span>  
  
1.  <span data-ttu-id="8cf8c-119">En la página **Lista de acceso a la publicación** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** , use los botones **Agregar**, **Quitar** y **Quitar todo** para agregar y quitar inicios de sesión y grupos de la PAL.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-119">On the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box, use the **Add**, **Remove**, and **Remove All** buttons to add and remove logins and groups from the PAL.</span></span> <span data-ttu-id="8cf8c-120">No quite **distributor_admin** de la PAL.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-120">Do not remove **distributor_admin** from the PAL.</span></span> <span data-ttu-id="8cf8c-121">La replicación utiliza esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-121">This account is used by replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8cf8c-122">Si se utiliza un distribuidor remoto, las cuentas de la lista de acceso de la publicación deben estar disponibles tanto en el publicador como en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-122">If a remote Distributor is used, accounts in the PAL must be available at both the Publisher and the Distributor.</span></span> <span data-ttu-id="8cf8c-123">La cuenta debe ser una cuenta de dominio o una cuenta local que esté definida en ambos servidores.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-123">The account must be either a domain account or a local account that is defined at both servers.</span></span> <span data-ttu-id="8cf8c-124">Las contraseñas asociadas a ambos inicios de sesión deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-124">The passwords that are associated with both logins must be the same.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8cf8c-125">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8cf8c-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-groups-and-logins-that-belong-to-the-pal"></a><span data-ttu-id="8cf8c-126">Para ver los grupos y los inicios de sesión que pertenecen a la PAL</span><span class="sxs-lookup"><span data-stu-id="8cf8c-126">To view groups and logins that belong to the PAL</span></span>  
  
1.  <span data-ttu-id="8cf8c-127">En el publicador de la base de datos de publicaciones, ejecute [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8cf8c-127">At the Publisher on the publication database, execute [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span></span> <span data-ttu-id="8cf8c-128">En \*\* \@ publicación\*\*, especifique el nombre de la publicación.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-128">For **\@publication**, specify the publication name.</span></span> <span data-ttu-id="8cf8c-129">Esto muestra información acerca de los grupos y los inicios de sesión en la PAL.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-129">This displays information about the groups and logins in the PAL.</span></span>  
  
#### <a name="to-add-groups-and-logins-to-the-pal"></a><span data-ttu-id="8cf8c-130">Para agregar grupos e inicios de sesión a la PAL</span><span class="sxs-lookup"><span data-stu-id="8cf8c-130">To add groups and logins to the PAL</span></span>  
  
1.  <span data-ttu-id="8cf8c-131">En el publicador de la base de datos de publicación, ejecute [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8cf8c-131">At the Publisher on the publication database, execute [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span></span> <span data-ttu-id="8cf8c-132">En \*\* \@ publicación**, especifique el nombre de la publicación; y para \*\* \@ Inicio de sesión**, especifique el nombre del inicio de sesión o del grupo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-132">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being added.</span></span>  
  
#### <a name="to-remove-groups-and-logins-from-the-pal"></a><span data-ttu-id="8cf8c-133">Para quitar grupos e inicios de sesión de la PAL</span><span class="sxs-lookup"><span data-stu-id="8cf8c-133">To remove groups and logins from the PAL</span></span>  
  
1.  <span data-ttu-id="8cf8c-134">En el publicador de la base de datos de publicación, ejecute [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8cf8c-134">At the Publisher on the publication database, execute [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span></span> <span data-ttu-id="8cf8c-135">En \*\* \@ publicación**, especifique el nombre de la publicación; y para \*\* \@ Inicio de sesión**, especifique el nombre del inicio de sesión o del grupo que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="8cf8c-135">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf8c-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8cf8c-136">See Also</span></span>  
 <span data-ttu-id="8cf8c-137">[Modelo de seguridad del Agente de replicación](replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="8cf8c-137">[Replication Agent Security Model](replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="8cf8c-138">[Proteger una topología de replicación](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="8cf8c-138">[Secure a Replication Topology](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="8cf8c-139">Proteger al publicador</span><span class="sxs-lookup"><span data-stu-id="8cf8c-139">Secure the Publisher</span></span>](secure-the-publisher.md)  
  
  
