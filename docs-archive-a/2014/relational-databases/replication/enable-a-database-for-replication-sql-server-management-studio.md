---
title: Habilitar una base de datos para replicación (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server replication]
ms.assetid: 8092faa3-9cff-4f81-926c-6a0070d1ce2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 307d52e24187e35c1c30f609facd13bfad569216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663374"
---
# <a name="enable-a-database-for-replication-sql-server-management-studio"></a><span data-ttu-id="23496-102">Habilitar una base de datos para replicación (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="23496-102">Enable a Database for Replication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="23496-103">Una base de datos se habilita de forma implícita para replicación cuando un miembro del rol fijo de servidor **sysadmin** crea una publicación con el Asistente para nueva publicación.</span><span class="sxs-lookup"><span data-stu-id="23496-103">A database is implicitly enabled for replication when a member of the **sysadmin** fixed server role creates a publication with the New Publication Wizard.</span></span> <span data-ttu-id="23496-104">Un miembro del rol fijo de servidor **sysadmin** también puede habilitar una base de datos para replicación de forma explícita, de manera que un miembro del rol fijo de base de datos **db_owner** pueda crear una o varias publicaciones en esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="23496-104">A member of the **sysadmin** fixed server role can also enable a database for replication explicitly, so that a member of the **db_owner** fixed database role can create one or more publications in that database.</span></span> <span data-ttu-id="23496-105">Para habilitar una base de datos de forma explícita, use la página **Bases de datos de publicación** del cuadro de diálogo **Propiedades del publicador: \<Publisher>** .</span><span class="sxs-lookup"><span data-stu-id="23496-105">To enable a database explicitly, use the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box.</span></span> <span data-ttu-id="23496-106">Para obtener más información sobre el acceso a este cuadro de diálogo, vea [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="23496-106">For more information about accessing this dialog box, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
### <a name="to-enable-a-database-for-replication"></a><span data-ttu-id="23496-107">Para habilitar una base de datos para replicación</span><span class="sxs-lookup"><span data-stu-id="23496-107">To enable a database for replication</span></span>  
  
1.  <span data-ttu-id="23496-108">En la página **Bases de datos de publicación** del cuadro de diálogo **Propiedades del publicador: \<Publisher>** , active las casillas **Transaccional** o **Mezclar** para cada una de las bases de datos que quiera replicar.</span><span class="sxs-lookup"><span data-stu-id="23496-108">On the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box, select the **Transactional** and/or **Merge** check box for each database you want to replicate.</span></span> <span data-ttu-id="23496-109">Active la casilla **Transaccional** para habilitar la base de datos para replicación de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="23496-109">Select **Transactional** to enable the database for snapshot replication.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
