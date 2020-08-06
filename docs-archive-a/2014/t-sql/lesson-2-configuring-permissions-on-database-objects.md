---
title: 'Lección 2: Configurar permisos en objetos de base de datos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
helpviewer_keywords:
- database permissions
ms.assetid: f964b66a-ec32-44c2-a185-6a0f173bfa22
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: fcc6ee3ddf9be072b51bd568fd3e72eb6c871785
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749550"
---
# <a name="lesson-2-configuring-permissions-on-database-objects"></a><span data-ttu-id="e9bf4-102">Lección 2: Configuración de permisos en objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="e9bf4-102">Lesson 2: Configuring Permissions on Database Objects</span></span>
  <span data-ttu-id="e9bf4-103">La concesión de acceso de usuario a una base de datos implica tres pasos.</span><span class="sxs-lookup"><span data-stu-id="e9bf4-103">Granting a user access to a database involves three steps.</span></span> <span data-ttu-id="e9bf4-104">Primero, debe crear un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e9bf4-104">First, you create a login.</span></span> <span data-ttu-id="e9bf4-105">El inicio de sesión permite al usuario conectarse a [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9bf4-105">The login lets the user connect to the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="e9bf4-106">Luego, debe configurar el inicio de sesión como un usuario de una base de datos determinada.</span><span class="sxs-lookup"><span data-stu-id="e9bf4-106">Then you configure the login as a user in the specified database.</span></span> <span data-ttu-id="e9bf4-107">Y, por último, debe conceder al usuario permiso a objetos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e9bf4-107">And finally, you grant that user permission to database objects.</span></span> <span data-ttu-id="e9bf4-108">En esta lección se muestran estos tres pasos y cómo crear una vista y un procedimiento almacenado como el objeto.</span><span class="sxs-lookup"><span data-stu-id="e9bf4-108">This lesson shows you these three steps, and shows you how to create a view and a stored procedure as the object.</span></span>  
  
 <span data-ttu-id="e9bf4-109">En esta lección se incluyen los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9bf4-109">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="e9bf4-110">Crear un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="e9bf4-110">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
-   [<span data-ttu-id="e9bf4-111">Conceder acceso a una base de datos</span><span class="sxs-lookup"><span data-stu-id="e9bf4-111">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
-   [<span data-ttu-id="e9bf4-112">Crear vistas y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="e9bf4-112">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
-   [<span data-ttu-id="e9bf4-113">Conceder acceso a un objeto de base de datos</span><span class="sxs-lookup"><span data-stu-id="e9bf4-113">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
-   [<span data-ttu-id="e9bf4-114">Resumen: Configuración de permisos en objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="e9bf4-114">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e9bf4-115">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="e9bf4-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e9bf4-116">Crear un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="e9bf4-116">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
  
