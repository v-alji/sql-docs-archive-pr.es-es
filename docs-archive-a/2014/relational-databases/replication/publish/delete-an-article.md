---
title: Eliminación de una artículo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- articles [SQL Server replication], dropping
- sp_droparticle
- sp_dropmergearticle
- deleting articles
- removing articles
- dropping articles
ms.assetid: 185b58fc-38c0-4abe-822e-6ec20066c863
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 082f90d33c2b8dedfae34dcada9b3935bed134ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669609"
---
# <a name="delete-an-article"></a><span data-ttu-id="e1c28-102">Eliminar un artículo</span><span class="sxs-lookup"><span data-stu-id="e1c28-102">Delete an Article</span></span>
  <span data-ttu-id="e1c28-103">En este tema se describe cómo eliminar un artículo en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[tsql](../../../includes/tsql-md.md)] o Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="e1c28-103">This topic describes how to delete an article in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] or Replication Management Objects (RMO).</span></span> <span data-ttu-id="e1c28-104">Para obtener información sobre las condiciones en que se pueden quitar artículos, y si la eliminación de un artículo requiere una nueva instantánea o la reinicialización de las suscripciones, vea [Agregar y quitar artículos de publicaciones existentes](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="e1c28-104">For information about the conditions under which articles can be dropped and whether dropping an article requires a new snapshot or the reinitialization of subscriptions, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e1c28-105">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1c28-105">Using Transact-SQL</span></span>  
 <span data-ttu-id="e1c28-106">Los artículos pueden eliminarse mediante programación con procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="e1c28-106">Articles can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="e1c28-107">Los procedimientos almacenados que se usen dependerán del tipo de publicación a la que pertenece el artículo.</span><span class="sxs-lookup"><span data-stu-id="e1c28-107">The stored procedures that you use depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-from-a-snapshot-or-transactional-publication"></a><span data-ttu-id="e1c28-108">Para eliminar un artículo de una publicación de instantáneas o transaccional</span><span class="sxs-lookup"><span data-stu-id="e1c28-108">To delete an article from a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="e1c28-109">Ejecute [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) para eliminar un artículo, especificado por **\@article**, de una publicación, especificada por **\@publication**.</span><span class="sxs-lookup"><span data-stu-id="e1c28-109">Execute [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="e1c28-110">Especifique un valor de **1** para \*\* \@ force_invalidate_snapshot\*\*.</span><span class="sxs-lookup"><span data-stu-id="e1c28-110">Specify a value of **1** for **\@force_invalidate_snapshot**.</span></span>  
  
2.  <span data-ttu-id="e1c28-111">(Opcional) Para quitar completamente el objeto publicado de la base de datos, ejecute el comando `DROP <objectname>` en el publicador de la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="e1c28-111">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
#### <a name="to-delete-an-article-from-a-merge-publication"></a><span data-ttu-id="e1c28-112">Para eliminar un artículo de una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="e1c28-112">To delete an article from a merge publication</span></span>  
  
1.  <span data-ttu-id="e1c28-113">Ejecute [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) para eliminar un artículo, especificado por **\@article**, de una publicación, especificada por **\@publication**.</span><span class="sxs-lookup"><span data-stu-id="e1c28-113">Execute [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="e1c28-114">Si es necesario, especifique un valor de **1** para \*\* \@ force_invalidate_snapshot\*\* y un valor de **1** para \*\* \@ force_reinit_subscription\*\*.</span><span class="sxs-lookup"><span data-stu-id="e1c28-114">If necessary, specify a value of **1** for **\@force_invalidate_snapshot** and a value of **1** for **\@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="e1c28-115">(Opcional) Para quitar completamente el objeto publicado de la base de datos, ejecute el comando `DROP <objectname>` en el publicador de la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="e1c28-115">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="e1c28-116">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1c28-116">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="e1c28-117">En el siguiente ejemplo se elimina un artículo de una publicación transaccional</span><span class="sxs-lookup"><span data-stu-id="e1c28-117">The following example deletes an article from a transactional publication.</span></span> <span data-ttu-id="e1c28-118">Dado que este cambio invalida la instantánea existente, se especifica un valor de **1** para el parámetro \*\* \@ force_invalidate_snapshot\*\* .</span><span class="sxs-lookup"><span data-stu-id="e1c28-118">Because this change invalidates the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_droparticle](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droparticle)]  
  
 <span data-ttu-id="e1c28-119">El ejemplo siguiente elimina dos artículos de una publicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="e1c28-119">The following example deletes two articles from a merge publication.</span></span> <span data-ttu-id="e1c28-120">Dado que estos cambios invalidan la instantánea existente, se especifica un valor de **1** para el parámetro \*\* \@ force_invalidate_snapshot\*\* .</span><span class="sxs-lookup"><span data-stu-id="e1c28-120">Because these changes invalidate the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergearticle)]
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergearticles.sql#sp_dropmergearticle)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="e1c28-121">Uso de Replication Management Objects (RMO)</span><span class="sxs-lookup"><span data-stu-id="e1c28-121">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="e1c28-122">Puede eliminar artículos mediante programación utilizando Replication Management Objects (RMO).</span><span class="sxs-lookup"><span data-stu-id="e1c28-122">You can delete articles programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="e1c28-123">Las clases RMO que usa para eliminar un artículo dependen del tipo de publicación al que pertenece el artículo.</span><span class="sxs-lookup"><span data-stu-id="e1c28-123">The RMO classes you use to delete an article depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="e1c28-124">Para eliminar un artículo que pertenece a una publicación transaccional o de instantáneas</span><span class="sxs-lookup"><span data-stu-id="e1c28-124">To delete an article that belongs to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="e1c28-125">Cree una conexión al publicador mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="e1c28-125">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="e1c28-126">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.TransArticle>.</span><span class="sxs-lookup"><span data-stu-id="e1c28-126">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransArticle> class.</span></span>  
  
3.  <span data-ttu-id="e1c28-127">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>y <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="e1c28-127">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="e1c28-128">Establezca la conexión del paso 1 para la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="e1c28-128">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="e1c28-129">Compruebe la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para asegurarse de que el artículo existe.</span><span class="sxs-lookup"><span data-stu-id="e1c28-129">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="e1c28-130">Si el valor de esta propiedad es `false`, se definieron incorrectamente las propiedades de artículo en el paso 3, o bien el artículo no existe.</span><span class="sxs-lookup"><span data-stu-id="e1c28-130">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="e1c28-131">Llame al método <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="e1c28-131">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="e1c28-132">Cierre todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="e1c28-132">Close all connections.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-merge-publication"></a><span data-ttu-id="e1c28-133">Para eliminar un artículo que pertenece a una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="e1c28-133">To delete an article that belongs to a merge publication</span></span>  
  
1.  <span data-ttu-id="e1c28-134">Cree una conexión al publicador mediante la clase <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="e1c28-134">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="e1c28-135">Cree una instancia de la clase <xref:Microsoft.SqlServer.Replication.MergeArticle>.</span><span class="sxs-lookup"><span data-stu-id="e1c28-135">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeArticle> class.</span></span>  
  
3.  <span data-ttu-id="e1c28-136">Establezca las propiedades <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>y <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="e1c28-136">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="e1c28-137">Establezca la conexión del paso 1 para la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="e1c28-137">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="e1c28-138">Compruebe la propiedad <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> para asegurarse de que el artículo existe.</span><span class="sxs-lookup"><span data-stu-id="e1c28-138">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="e1c28-139">Si el valor de esta propiedad es `false`, se definieron incorrectamente las propiedades de artículo en el paso 3, o bien el artículo no existe.</span><span class="sxs-lookup"><span data-stu-id="e1c28-139">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="e1c28-140">Llame al método <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="e1c28-140">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="e1c28-141">Cierre todas las conexiones.</span><span class="sxs-lookup"><span data-stu-id="e1c28-141">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c28-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1c28-142">See Also</span></span>  
 <span data-ttu-id="e1c28-143">[Agregar y quitar artículos de publicaciones existentes](add-articles-to-and-drop-articles-from-existing-publications.md) </span><span class="sxs-lookup"><span data-stu-id="e1c28-143">[Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md) </span></span>  
 [<span data-ttu-id="e1c28-144">Conceptos de procedimientos almacenados del sistema de replicación</span><span class="sxs-lookup"><span data-stu-id="e1c28-144">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
