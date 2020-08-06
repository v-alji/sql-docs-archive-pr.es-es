---
title: 'Tutorial: Administrar servidores mediante administración basada en directivas | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: 7de96e7b-9fb8-4cc8-8d85-61345d68a1e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b707a5ecd362c6b3b54e853f89d79e25a9e1428
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670989"
---
# <a name="tutorial-administering-servers-by-using-policy-based-management"></a><span data-ttu-id="7da90-102">Tutorial: Administración de servidores mediante la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="7da90-102">Tutorial: Administering Servers by Using Policy-Based Management</span></span>
  <span data-ttu-id="7da90-103">Éste es el tutorial Administrar servidores mediante administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="7da90-103">Welcome to the Administering Servers by Using Policy-Based Management Policies tutorial.</span></span> <span data-ttu-id="7da90-104">Este tutorial está destinado a los usuarios que conocen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pero que no tienen experiencia con la administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="7da90-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but new to the Policy-Based Management.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="7da90-105">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="7da90-105">What You Will Learn</span></span>  
 <span data-ttu-id="7da90-106">En este tutorial se crea una directiva para administrar el servidor y una directiva que se aplica a una única base de datos.</span><span class="sxs-lookup"><span data-stu-id="7da90-106">This tutorial creates a policy to administer your server and a policy that applies to a single database.</span></span> <span data-ttu-id="7da90-107">Se ejecuta una directiva a petición para probar el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7da90-107">One policy is run on demand to test for compliance.</span></span> <span data-ttu-id="7da90-108">La otra directiva exige el cumplimiento en el futuro.</span><span class="sxs-lookup"><span data-stu-id="7da90-108">The other policy enforces future compliance.</span></span>  
  
 <span data-ttu-id="7da90-109">El tutorial está compuesto por dos lecciones:</span><span class="sxs-lookup"><span data-stu-id="7da90-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="7da90-110">Lección 1: Creación y aplicación de una directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="7da90-110">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
 <span data-ttu-id="7da90-111">En esta lección se crea una directiva que especifica que Correo electrónico de base de datos no está habilitado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="7da90-111">This lesson creates a policy that specifies that Database Mail is not enabled on the server.</span></span> <span data-ttu-id="7da90-112">A continuación, se comprueba si el servidor cumple la directiva y se configura el servidor deshabilitando Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="7da90-112">Then, it checks to see whether your server complies with the policy, and configures the server by disabling Database Mail.</span></span>  
  
 [<span data-ttu-id="7da90-113">Lección 2: Creación y aplicación de una directiva de normas de denominación</span><span class="sxs-lookup"><span data-stu-id="7da90-113">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
 <span data-ttu-id="7da90-114">En esta lección se crea una directiva que define y exige una denominación estándar para las tablas.</span><span class="sxs-lookup"><span data-stu-id="7da90-114">This lesson creates a policy that defines and enforces a naming standard for tables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7da90-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7da90-115">Requirements</span></span>  
 <span data-ttu-id="7da90-116">En esta lección se requieren conocimientos básicos de bases de datos y de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7da90-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="7da90-117">Para utilizar este tutorial, el sistema debe tener instalado [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7da90-117">To use this tutorial, your system must have [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="7da90-118">Iniciar el tutorial</span><span class="sxs-lookup"><span data-stu-id="7da90-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="7da90-119">Lección 1: Creación y aplicación de una directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="7da90-119">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="7da90-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7da90-120">See Also</span></span>  
 [<span data-ttu-id="7da90-121">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="7da90-121">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
