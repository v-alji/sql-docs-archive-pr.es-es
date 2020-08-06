---
title: Establecer el nivel de compatibilidad para publicaciones de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], replication
- backward compatibility [SQL Server], replication
- publications [SQL Server replication], backward compatibility
ms.assetid: db47ac73-948b-4d77-b272-bb3565135ea5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04ad80b0c99e7282ff2acfa459a08665efbdee1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677545"
---
# <a name="set-the-compatibility-level-for-merge-publications"></a><span data-ttu-id="c0b6c-102">Establecer el nivel de compatibilidad para publicaciones de mezcla</span><span class="sxs-lookup"><span data-stu-id="c0b6c-102">Set the Compatibility Level for Merge Publications</span></span>
  <span data-ttu-id="c0b6c-103">En este tema se describe cómo establecer el nivel de compatibilidad para las publicaciones de mezcla en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0b6c-103">This topic describes how to set the compatibility level for merge publications in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c0b6c-104">La replicación de mezcla emplea el nivel de compatibilidad de la publicación para determinar qué características pueden usar las publicaciones de una base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-104">Merge replication uses the publication compatibility level to determine which features can be used by publications in a given database.</span></span>  
  
 <span data-ttu-id="c0b6c-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c0b6c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c0b6c-106">**Para establecer el nivel de compatibilidad para publicaciones de mezcla con:**</span><span class="sxs-lookup"><span data-stu-id="c0b6c-106">**To set the compatibility level for merge publications, using:**</span></span>  
  
     [<span data-ttu-id="c0b6c-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0b6c-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c0b6c-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0b6c-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c0b6c-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c0b6c-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c0b6c-110">Establezca el nivel de compatibilidad en la página **Tipos de suscriptor** del Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-110">Set the compatibility level on the **Subscriber Types** page of the New Publication Wizard.</span></span> <span data-ttu-id="c0b6c-111">Para obtener más información acerca de cómo obtener acceso a este asistente, vea [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c0b6c-111">For more information on accessing this wizard, see [Create a Publication](create-a-publication.md).</span></span> <span data-ttu-id="c0b6c-112">Después de crear una publicación de instantáneas, el nivel de compatibilidad se puede aumentar pero no se puede reducir.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-112">After a publication snapshot is created, the compatibility level can be increased but cannot be decreased.</span></span> <span data-ttu-id="c0b6c-113">Aumente el nivel de compatibilidad en la página **General** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="c0b6c-113">Increase the compatibility level on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="c0b6c-114">Para obtener más información sobre el acceso a este cuadro de diálogo, vea [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c0b6c-114">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="c0b6c-115">Si aumenta el nivel de compatibilidad, las suscripciones existentes en los servidores que se ejecuten con versiones anteriores al nivel de compatibilidad no se podrán sincronizar.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-115">If you increase the publication compatibility level, any existing subscriptions at servers running versions prior to the compatibility level will no longer be able to synchronize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0b6c-116">Debido a que el nivel de compatibilidad tiene implicaciones en otras propiedades de la publicación y en cuanto a qué propiedades del artículo son válidas, no cambie el nivel de compatibilidad ni otras propiedades en el mismo uso del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-116">Because the compatibility level has implications for other publication properties and for which article properties are valid, do not change the compatibility level and other properties in the same use of the dialog box.</span></span> <span data-ttu-id="c0b6c-117">La instantánea de la publicación se volverá a generar después de cambiar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-117">The snapshot for the publication should be regenerated after the property is changed.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level"></a><span data-ttu-id="c0b6c-118">Para establecer el nivel de compatibilidad de la publicación</span><span class="sxs-lookup"><span data-stu-id="c0b6c-118">To set the publication compatibility level</span></span>  
  
-   <span data-ttu-id="c0b6c-119">En la página **Tipos de suscriptor** del Asistente para nueva publicación, seleccione los tipos de suscriptores que admitirá la publicación.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-119">On the **Subscriber Types** page of the New Publication Wizard, select the types of Subscribers that the publication should support.</span></span>  
  
#### <a name="to-increase-the-publication-compatibility-level"></a><span data-ttu-id="c0b6c-120">Para aumentar el nivel de compatibilidad de la publicación</span><span class="sxs-lookup"><span data-stu-id="c0b6c-120">To increase the publication compatibility level</span></span>  
  
-   <span data-ttu-id="c0b6c-121">En la página **General** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** , seleccione el valor para **Nivel de compatibilidad**.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-121">On the **General** page of the **Publication Properties - \<Publication>** dialog box, select for **Compatibility level**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c0b6c-122">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0b6c-122">Using Transact-SQL</span></span>  
 <span data-ttu-id="c0b6c-123">El nivel de compatibilidad para una publicación de combinación se puede establecer mediante programación cuando una publicación se crea o bien, se puede modificar mediante programación en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-123">The compatibility level for a merge publication can either be set programmatically when a publication is created or modified programmatically at a later time.</span></span> <span data-ttu-id="c0b6c-124">Puede usar procedimientos almacenados de replicación para establecer o cambiar esta propiedad de publicación.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-124">You can use replication stored procedures to set or change this publication property.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level-for-a-merge-publication"></a><span data-ttu-id="c0b6c-125">Para establecer el nivel de compatibilidad de la publicación para una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="c0b6c-125">To set the publication compatibility level for a merge publication</span></span>  
  
1.  <span data-ttu-id="c0b6c-126">En el publicador, ejecute [sp_addmergepublication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), especificando un valor para **@publication_compatibility_level** para que la publicación sea compatible con versiones anteriores de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0b6c-126">At the Publisher, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value for **@publication_compatibility_level** to make the publication compatible with older versions of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c0b6c-127">Para obtener más información, vea [Crear una suscripción](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c0b6c-127">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="c0b6c-128">Para cambiar el nivel de compatibilidad de la publicación de una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="c0b6c-128">To change the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="c0b6c-129">Ejecute [sp_changemergepublication &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), especificando **publication_compatibility_level** para **@property** y el nivel de compatibilidad de la publicación adecuado para **@value** .</span><span class="sxs-lookup"><span data-stu-id="c0b6c-129">Execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying **publication_compatibility_level** for **@property** and the appropriate publication compatibility level for **@value**.</span></span>  
  
#### <a name="to-determine-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="c0b6c-130">Para determinar el nivel de compatibilidad de la publicación de una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="c0b6c-130">To determine the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="c0b6c-131">Ejecute [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql) especificando la publicación deseada.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-131">Execute [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying the desired publication.</span></span>  
  
2.  <span data-ttu-id="c0b6c-132">Busque el nivel de compatibilidad de la publicación en la columna **de backward_comp_level** en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-132">Locate the publication compatibility level in the **backward_comp_level** column in the result set.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="c0b6c-133">Ejemplos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c0b6c-133">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="c0b6c-134">Este ejemplo crea una publicación de combinación y establece el nivel de compatibilidad de la publicación.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-134">This example creates a merge publication and sets the publication compatibility level.</span></span>  
  
```  
-- To avoid storing the login and password in the script file, the values   
-- are passed into SQLCMD as scripting variables. For information about   
-- how to use scripting variables on the command line and in SQL Server  
-- Management Studio, see the "Executing Replication Scripts" section in  
-- the topic "Programming Replication Using System Stored Procedures".  
  
--Add a new merge publication.  
DECLARE @publicationDB AS sysname;  
DECLARE @publication AS sysname;  
DECLARE @login AS sysname;  
DECLARE @password AS sysname;  
SET @publicationDB = N'AdventureWorks2012';   
SET @publication = N'AdvWorksSalesOrdersMerge'   
SET @login = $(Login);  
SET @password = $(Password);  
  
-- Create a new merge publication.   
USE [AdventureWorks2012]  
EXEC sp_addmergepublication   
@publication = @publication,   
-- Set the compatibility level to SQL Server 2014.  
@publication_compatibility_level = '120RTM';   
  
-- Create the snapshot job for the publication.  
EXEC sp_addpublication_snapshot   
@publication = @publication,  
@job_login = @login,  
@job_password = @password;  
GO  
```  
  
 <span data-ttu-id="c0b6c-135">Este ejemplo cambia el nivel de compatibilidad de la publicación para la publicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-135">This example changes the publication compatibility level for the merge publication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c0b6c-136">Cambiar el nivel de compatibilidad de la publicación podría no permitirse si la publicación usa alguna característica que requiera un nivel de compatibilidad determinado.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-136">Changing the publication compatibility level might not be allowed if the publication uses any features that require a particular compatibility level.</span></span> <span data-ttu-id="c0b6c-137">Para obtener más información, vea [Compatibilidad con versiones anteriores de replicación](../replication-backward-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="c0b6c-137">For more information, see [Replication Backward Compatibility](../replication-backward-compatibility.md).</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
  
-- Change the publication compatibility level to   
-- SQL Server 2012.  
EXEC sp_changemergepublication   
@publication = @publication,   
@property = N'publication_compatibility_level',   
@value = N'110RTM';  
GO  
  
```  
  
 <span data-ttu-id="c0b6c-138">Este ejemplo devuelve el nivel de compatibilidad de la publicación actual para la publicación de combinación.</span><span class="sxs-lookup"><span data-stu-id="c0b6c-138">This example returns the current publication compatibility level for the merge publication.</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
EXEC sp_helpmergepublication   
@publication = @publication;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0b6c-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0b6c-139">See Also</span></span>  
 <span data-ttu-id="c0b6c-140">[Create a Publication](create-a-publication.md) (Creación de una publicación)</span><span class="sxs-lookup"><span data-stu-id="c0b6c-140">[Create a Publication](create-a-publication.md)</span></span>  
  
  
