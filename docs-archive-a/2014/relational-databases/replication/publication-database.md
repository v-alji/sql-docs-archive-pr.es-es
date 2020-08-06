---
title: Base de datos de publicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.publicationdatabase.f1
ms.assetid: a9fafc9b-9963-4b59-97a0-3472158fa665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 511e5f2e2caa934313ba96fb3dbc4cadddace968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662814"
---
# <a name="publication-database"></a><span data-ttu-id="f9165-102">Base de datos de publicaciones</span><span class="sxs-lookup"><span data-stu-id="f9165-102">Publication Database</span></span>
  <span data-ttu-id="f9165-103">La base de datos de publicaciones es la base de datos del publicador que es el origen de los datos y objetos de base de datos que va a replicar.</span><span class="sxs-lookup"><span data-stu-id="f9165-103">The publication database is the database on the Publisher that is the source of data and database objects to be replicated.</span></span> <span data-ttu-id="f9165-104">Deberá habilitar cada base de datos de publicaciones utilizada en la replicación.</span><span class="sxs-lookup"><span data-stu-id="f9165-104">Each publication database used in replication must be enabled.</span></span> <span data-ttu-id="f9165-105">La base de datos se habilita cuando un miembro del rol fijo del servidor **sysadmin** :</span><span class="sxs-lookup"><span data-stu-id="f9165-105">The database is enabled when a member of the **sysadmin** fixed server role:</span></span>  
  
-   <span data-ttu-id="f9165-106">Crea una publicación en esa base de datos con el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="f9165-106">Creates a publication on that database using the New Publication Wizard.</span></span>  
  
-   <span data-ttu-id="f9165-107">Selecciona la base de datos en el cuadro de diálogo **Propiedades del publicador** .</span><span class="sxs-lookup"><span data-stu-id="f9165-107">Selects the database in the **Publisher Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="f9165-108">Ejecuta **sp_replicationdboption** y establece **True** en la opción **publish** (para publicaciones transaccionales o de instantáneas) o **merge publish**(para publicaciones de combinación).</span><span class="sxs-lookup"><span data-stu-id="f9165-108">Executes **sp_replicationdboption** and sets the option **publish** (for snapshot or transactional publications) or **merge publish** (for merge publications) to **True**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f9165-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="f9165-109">Options</span></span>  
 <span data-ttu-id="f9165-110">**Bases de datos**</span><span class="sxs-lookup"><span data-stu-id="f9165-110">**Databases**</span></span>  
 <span data-ttu-id="f9165-111">Seleccione el nombre de la base de datos que contiene los datos o los objetos de base de datos que desea publicar.</span><span class="sxs-lookup"><span data-stu-id="f9165-111">Select the name of the database that contains the data and database objects that you want to publish.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9165-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9165-112">See Also</span></span>  
 <span data-ttu-id="f9165-113">[Publicar datos y objetos de base de datos](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="f9165-113">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="f9165-114">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="f9165-114">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="f9165-115">[Ver y modificar las propiedades del distribuidor y del publicador](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f9165-115">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="f9165-116">sp_replicationdboption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f9165-116">sp_replicationdboption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql)  
  
  
