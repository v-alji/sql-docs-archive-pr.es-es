---
title: 'Tutorial: evaluar las prácticas recomendadas mediante la administración basada en directivas | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- best practices analyzer
- Policy-Based Management, best practices policies
- Best Practices [Database Engine]
- Policy-Based Management, evaluating policies
- BPA
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: c7867f9b-7acc-4fae-bde1-63808c403ebc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 42e6b505c71abecce7b56b5cb2544b4e9f4e8f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746627"
---
# <a name="tutorial-evaluating-best-practices-by-using-policy-based-management"></a><span data-ttu-id="4cc13-102">Tutorial: Evaluación de los procedimientos recomendados mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="4cc13-102">Tutorial: Evaluating Best Practices by Using Policy-Based Management</span></span>
  <span data-ttu-id="4cc13-103">Este es el tutorial Evaluar las prácticas recomendadas usando administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="4cc13-103">Welcome to the Evaluating Best Practices by Using Policy-Based Management tutorial.</span></span> <span data-ttu-id="4cc13-104">Este tutorial está destinado a usuarios que están familiarizados con [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], pero que no conocen la administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="4cc13-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but new to Policy-Based Management.</span></span> <span data-ttu-id="4cc13-105">La administración basada en directivas es un sistema para definir directivas que se pueden usar para aplicar normas de administración de sitios.</span><span class="sxs-lookup"><span data-stu-id="4cc13-105">Policy-Based Management is a system for defining policies that can be used enforce site administration standards.</span></span> <span data-ttu-id="4cc13-106">Incluye una serie de directivas de prácticas recomendadas que puede usar para analizar una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y determinar si esa instancia cumple las indicaciones y recomendaciones de las prácticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="4cc13-106">Policy-Based Management includes a set of best practices policies that you can use to analyze an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to determine whether the instance meets best practices guidelines and recommendations.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="4cc13-107">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="4cc13-107">What You Will Learn</span></span>  
 <span data-ttu-id="4cc13-108">En este tutorial, obtendrá información sobre cómo evaluar las directivas de las prácticas recomendadas para [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] a petición (o "ad hoc") o de forma programada.</span><span class="sxs-lookup"><span data-stu-id="4cc13-108">In this tutorial, you will learn how to evaluate best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on an on-demand (or "ad hoc") basis, or on a scheduled basis.</span></span>  
  
 <span data-ttu-id="4cc13-109">El tutorial está compuesto por dos lecciones:</span><span class="sxs-lookup"><span data-stu-id="4cc13-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="4cc13-110">Lección 1: Evaluación de los procedimientos a petición</span><span class="sxs-lookup"><span data-stu-id="4cc13-110">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
 <span data-ttu-id="4cc13-111">En esta lección, realiza una evaluación a petición de las directivas con una o más instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc13-111">In this lesson, you perform an on-demand evaluation of the policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="4cc13-112">Lección 2: Evaluación de las directivas de procedimientos recomendados de forma programada</span><span class="sxs-lookup"><span data-stu-id="4cc13-112">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>](../../2014/tutorials/lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis.md)  
 <span data-ttu-id="4cc13-113">En esta lección, configura las directivas de prácticas recomendadas para ejecutarse de forma programada.</span><span class="sxs-lookup"><span data-stu-id="4cc13-113">In this lesson, you configure best practices policies to run on a scheduled basis.</span></span> <span data-ttu-id="4cc13-114">La lección muestra cómo configurar las directivas programadas en una instancia única y cómo implementar las directivas programadas a partir de una ubicación central en varias instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc13-114">The lesson shows how to configure scheduled policies on a single instance, and how to deploy scheduled policies from a central location to multiple instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cc13-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4cc13-115">Requirements</span></span>  
 <span data-ttu-id="4cc13-116">En esta lección se requieren conocimientos básicos de bases de datos y de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc13-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4cc13-117">Para usar este tutorial, el servidor debe tener instalado [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc13-117">To use this tutorial, the server must have [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="4cc13-118">Iniciar el tutorial</span><span class="sxs-lookup"><span data-stu-id="4cc13-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="4cc13-119">Lección 1: Evaluación de los procedimientos a petición</span><span class="sxs-lookup"><span data-stu-id="4cc13-119">Lesson 1: Evaluate Best Practices on an On-Demand Basis</span></span>](../../2014/tutorials/lesson-1-evaluate-best-practices-on-an-on-demand-basis.md)  
  
## <a name="see-also"></a><span data-ttu-id="4cc13-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4cc13-120">See Also</span></span>  
 [<span data-ttu-id="4cc13-121">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="4cc13-121">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
