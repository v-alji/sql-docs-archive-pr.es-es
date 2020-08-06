---
title: Conceder acceso a una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database access
ms.assetid: 686edfe2-3650-48a6-a2da-9d46fa211ad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45b6d6c8dcd9c04d18489807271802aafee785b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676774"
---
# <a name="granting-access-to-a-database"></a><span data-ttu-id="7a9d2-102">Conceder acceso a una base de datos</span><span class="sxs-lookup"><span data-stu-id="7a9d2-102">Granting Access to a Database</span></span>
  <span data-ttu-id="7a9d2-103">Mary ahora tiene acceso a esta instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], pero no tiene permiso para tener acceso a las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="7a9d2-103">Mary now has access to this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but does not have permission to access the databases.</span></span> <span data-ttu-id="7a9d2-104">Incluso no tiene acceso a su propia base de datos **TestData** hasta que la autorice como usuario de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a9d2-104">She does not even have access to her default database **TestData** until you authorize her as a database user.</span></span>  
  
 <span data-ttu-id="7a9d2-105">Para conceder acceso a Mary, cambie a la base de datos **TestData** y, a continuación, use la instrucción CREATE USER para asignar su inicio de sesión a un usuario denominado Mary.</span><span class="sxs-lookup"><span data-stu-id="7a9d2-105">To grant Mary access, switch to the **TestData** database, and then use the CREATE USER statement to map her login to a user named Mary.</span></span>  
  
### <a name="to-create-a-user-in-a-database"></a><span data-ttu-id="7a9d2-106">Para crear un usuario en una base de datos</span><span class="sxs-lookup"><span data-stu-id="7a9d2-106">To create a user in a database</span></span>  
  
1.  <span data-ttu-id="7a9d2-107">Escriba y ejecute las siguientes instrucciones (reemplace `computer_name` con el nombre de su equipo) para conceder acceso a `Mary` a la base de datos `TestData` .</span><span class="sxs-lookup"><span data-stu-id="7a9d2-107">Type and execute the following statements (replacing `computer_name` with the name of your computer) to grant `Mary` access to the `TestData` database.</span></span>  
  
    ```  
    USE [TestData];  
    GO  
  
    CREATE USER [Mary] FOR LOGIN [computer_name\Mary];  
    GO  
  
    ```  
  
     <span data-ttu-id="7a9d2-108">Ahora, Mary tiene acceso a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y a la base de datos `TestData` .</span><span class="sxs-lookup"><span data-stu-id="7a9d2-108">Now, Mary has access to both [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and the `TestData` database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7a9d2-109">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="7a9d2-109">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7a9d2-110">Crear vistas y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="7a9d2-110">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
  
