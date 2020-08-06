---
title: 'Lección 1: Creación y aplicación de una directiva Desactivado de forma predeterminada | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: d31367db-b7db-44c4-8df2-f1240474cf78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a76df1a72b93d09c5c1c199cb0246dbb51c9cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663432"
---
# <a name="lesson-1-create-and-apply-an-off-by-default-policy"></a><span data-ttu-id="4b2ef-102">Lección 1: Creación y aplicación de una directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="4b2ef-102">Lesson 1: Create and Apply an Off By Default Policy</span></span>
  <span data-ttu-id="4b2ef-103">El uso de directivas de administración basada en directivas permite administrar una o varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], uno o varios objetos de instancia, instancias de servidor, una o varias bases de datos o uno o varios objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-103">Using Policy-Based Management policies, you can administer one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], one or more instance objects, server instances, one or more databases, or one or more database objects.</span></span> <span data-ttu-id="4b2ef-104">Como administrador de bases de datos, debe asegurarse de que ciertos servidores no tienen habilitado Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-104">As the database administrator, you want to ensure that certain servers do not have Database Mail enabled.</span></span> <span data-ttu-id="4b2ef-105">En esta lección, creará una condición y una directiva que establezca esa opción de servidor.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-105">In this lesson, you will create a condition and a policy that sets that server option.</span></span> <span data-ttu-id="4b2ef-106">Probará el servidor para ver si cumple con la directiva.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-106">You will test the server to see whether it complies with the policy.</span></span> <span data-ttu-id="4b2ef-107">A continuación, utilizará la directiva para volver a configurar el servidor de modo que cumpla con ella.</span><span class="sxs-lookup"><span data-stu-id="4b2ef-107">Then, you will use the policy to reconfigure the server to bring the server into compliance.</span></span>  
  
 <span data-ttu-id="4b2ef-108">En esta lección se incluyen los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b2ef-108">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="4b2ef-109">Crear la directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="4b2ef-109">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
-   [<span data-ttu-id="4b2ef-110">Configurar un servidor para ejecutar la directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="4b2ef-110">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4b2ef-111">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="4b2ef-111">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4b2ef-112">Crear la directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="4b2ef-112">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="4b2ef-113">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="4b2ef-113">Next Lesson</span></span>  
 [<span data-ttu-id="4b2ef-114">Lección 2: Creación y aplicación de una directiva de normas de denominación</span><span class="sxs-lookup"><span data-stu-id="4b2ef-114">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
