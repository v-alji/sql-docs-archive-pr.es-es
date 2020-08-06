---
title: Replicación de cambios de esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], schema changes
- schemas [SQL Server replication], replicating changes
ms.assetid: c09007f0-9374-4f60-956b-8a87670cd043
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bec2f363cd8c4f7dea45935568a88722b19323fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673646"
---
# <a name="replicate-schema-changes"></a><span data-ttu-id="acd60-102">Replicar cambios de esquema</span><span class="sxs-lookup"><span data-stu-id="acd60-102">Replicate Schema Changes</span></span>
  <span data-ttu-id="acd60-103">En este tema se describe cómo replicar cambios de esquema en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acd60-103">This topic describes how to replicate schema changes in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="acd60-104">Si realiza los siguientes cambios de esquema en un artículo publicado, se propagan de forma predeterminada a los suscriptores de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="acd60-104">If you make the following schema changes to a published article, they are propagated, by default, to [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers:</span></span>  
  
-   <span data-ttu-id="acd60-105">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="acd60-105">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="acd60-106">ALTER VIEW</span><span class="sxs-lookup"><span data-stu-id="acd60-106">ALTER VIEW</span></span>  
  
-   <span data-ttu-id="acd60-107">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="acd60-107">ALTER PROCEDURE</span></span>  
  
-   <span data-ttu-id="acd60-108">ALTER FUNCTION</span><span class="sxs-lookup"><span data-stu-id="acd60-108">ALTER FUNCTION</span></span>  
  
-   <span data-ttu-id="acd60-109">ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="acd60-109">ALTER TRIGGER</span></span>  
  
 <span data-ttu-id="acd60-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="acd60-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="acd60-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="acd60-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="acd60-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="acd60-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   <span data-ttu-id="acd60-113">**Para replicar cambios de esquema con:**</span><span class="sxs-lookup"><span data-stu-id="acd60-113">**To replicate schema changes, using:**</span></span>  
  
     [<span data-ttu-id="acd60-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="acd60-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="acd60-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="acd60-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="acd60-116">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="acd60-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="acd60-117">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="acd60-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="acd60-118">La instrucción ALTER TABLE … DROP COLUMN siempre se replica en todos los suscriptores cuya suscripción contenga las columnas que se van a quitar, aunque deshabilite la replicación de cambios de esquema.</span><span class="sxs-lookup"><span data-stu-id="acd60-118">The ALTER TABLE ... DROP COLUMN statement is always replicated to all Subscribers whose subscription contains the columns being dropped, even if you disable the replication of schema changes.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="acd60-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="acd60-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="acd60-120">Si no quiere replicar los cambios de esquema para una publicación, deshabilite la replicación de cambios de esquema en el cuadro de diálogo **Propiedades de la publicación: \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="acd60-120">If you do not want to replicate schema changes for a publication, disable the replication of schema changes in the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="acd60-121">Para obtener más información sobre el acceso a este cuadro de diálogo, vea [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="acd60-121">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-disable-replication-of-schema-changes"></a><span data-ttu-id="acd60-122">Para deshabilitar la replicación de los cambios de esquema</span><span class="sxs-lookup"><span data-stu-id="acd60-122">To disable replication of schema changes</span></span>  
  
1.  <span data-ttu-id="acd60-123">En la página **Opciones de suscripción** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** , establezca el valor de la propiedad **Replicar cambios de esquema** en **False**.</span><span class="sxs-lookup"><span data-stu-id="acd60-123">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, set the value of the **Replicate schema changes** property to **False**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="acd60-124">Para propagar únicamente los cambios de esquema específicos, establezca la propiedad en **True** antes de un cambio de esquema y vuelva a establecerla en **False** después de realizar el cambio.</span><span class="sxs-lookup"><span data-stu-id="acd60-124">To propagate only specific schema changes, set the property to **True** before a schema change, and then set it to **False** after the change is made.</span></span> <span data-ttu-id="acd60-125">A la inversa, para propagar la mayoría de los cambios de esquema, excepto un cambio determinado, establezca la propiedad en **False** antes de un cambio de esquema y vuelva a establecerla en **True** después de realizar el cambio.</span><span class="sxs-lookup"><span data-stu-id="acd60-125">Conversely, to propagate most schema changes, but not a given change, set the property to **False** before the schema change, and then set it to **True** after the change is made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="acd60-126">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="acd60-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="acd60-127">Puede utilizar los procedimientos almacenados de replicación para especificar si se replican estos cambios de esquema.</span><span class="sxs-lookup"><span data-stu-id="acd60-127">You can use replication stored procedures to specify whether these schema changes are replicated.</span></span> <span data-ttu-id="acd60-128">El procedimiento almacenado que utiliza depende del tipo de publicación.</span><span class="sxs-lookup"><span data-stu-id="acd60-128">The stored procedure that you use depends on the type of publication.</span></span>  
  
#### <a name="to-create-a-snapshot-or-transactional-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="acd60-129">Para crear una instantánea o una publicación transaccional que no replique cambios de esquema</span><span class="sxs-lookup"><span data-stu-id="acd60-129">To create a snapshot or transactional publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="acd60-130">En la base de datos de publicación del publicador, ejecute [sp_addpublication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql)y especifique un valor de **0** para \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="acd60-130">At the Publisher on the publication database, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="acd60-131">Para obtener más información, vea [Crear una suscripción](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="acd60-131">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-create-a-merge-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="acd60-132">Para crear una publicación de combinación que no replique cambios de esquema</span><span class="sxs-lookup"><span data-stu-id="acd60-132">To create a merge publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="acd60-133">En la base de datos de publicación del publicador, ejecute [sp_addmergepublication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql)y especifique un valor de **0** para \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="acd60-133">At the Publisher on the publication database, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="acd60-134">Para obtener más información, vea [Crear una suscripción](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="acd60-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-snapshot-or-transactional-publication"></a><span data-ttu-id="acd60-135">Para deshabilitar temporalmente la replicación de cambios de esquema para una instantánea o una publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="acd60-135">To temporarily disable replicating schema changes for a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="acd60-136">Para una publicación con replicación de cambios de esquema, ejecute [sp_changepublication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), especificando un valor de **replicate_ddl** para la \*\* \@ propiedad\*\* y un valor de **0** para el \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="acd60-136">For a publication with replication of schema changes, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="acd60-137">Ejecute el comando DDL en el objeto publicado.</span><span class="sxs-lookup"><span data-stu-id="acd60-137">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="acd60-138">Opta Vuelva a habilitar la replicación de los cambios de esquema mediante la ejecución de [sp_changepublication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), especificando un valor de **replicate_ddl** para la \*\* \@ propiedad\*\* y un valor de **1** para el \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="acd60-138">(Optional) Re-enable replicating schema changes by executing [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-merge-publication"></a><span data-ttu-id="acd60-139">Para deshabilitar temporalmente la replicación de cambios de esquema para una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="acd60-139">To temporarily disable replicating schema changes for a merge publication</span></span>  
  
1.  <span data-ttu-id="acd60-140">Para una publicación con replicación de cambios de esquema, ejecute [sp_changemergepublication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), especificando un valor de **replicate_ddl** para la \*\* \@ propiedad\*\* y un valor de **0** para el \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="acd60-140">For a publication with replication of schema changes, execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="acd60-141">Ejecute el comando DDL en el objeto publicado.</span><span class="sxs-lookup"><span data-stu-id="acd60-141">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="acd60-142">Opta Vuelva a habilitar la replicación de los cambios de esquema mediante la ejecución de [sp_changemergepublication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), especificando un valor de **replicate_ddl** para la \*\* \@ propiedad\*\* y un valor de **1** para el \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="acd60-142">(Optional) Re-enable replicating schema changes by executing [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd60-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acd60-143">See Also</span></span>  
 <span data-ttu-id="acd60-144">[Realizar cambios de esquema en bases de datos de publicaciones](make-schema-changes-on-publication-databases.md) </span><span class="sxs-lookup"><span data-stu-id="acd60-144">[Make Schema Changes on Publication Databases](make-schema-changes-on-publication-databases.md) </span></span>  
 [<span data-ttu-id="acd60-145">Realizar cambios de esquema en bases de datos de publicaciones</span><span class="sxs-lookup"><span data-stu-id="acd60-145">Make Schema Changes on Publication Databases</span></span>](make-schema-changes-on-publication-databases.md)  
  
  
