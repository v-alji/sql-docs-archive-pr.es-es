---
title: Usar DiffGrams para modificar datos en SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- data deletions [SQLXML]
- updating data [SQLXML]
- DiffGrams [SQLXML]
- modifying data [SQLXML]
- .NET Framework [SQLXML], DiffGrams
- XML [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- data modifications [SQLXML]
- record insertion [SQLXML]
- SQLXML, DiffGrams
- deleting data
- record updates [SQLXML]
- record deletions [SQLXML]
ms.assetid: 48b8a8f9-f3af-404f-8c84-f4c3703364d9
author: rothja
ms.author: jroth
ms.openlocfilehash: cc2e24304679a7648f18148eb45f33b9bf719a9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673582"
---
# <a name="using-diffgrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="414e2-102">Usar DiffGrams para modificar datos en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="414e2-102">Using DiffGrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="414e2-103">El formato DiffGram se introduce en el componente **DataSet** del [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="414e2-103">The DiffGram format is introduced in the **DataSet** component of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="414e2-104">En .NET Framework, puede crear DiffGrams y utilizarlos para modificar datos en tablas de una base de datos de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="414e2-104">Within the .NET Framework, you can create DiffGrams and use them to modify data in tables in a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="414e2-105">En esta sección se proporciona una introducción breve a los DiffGrams y ejemplos de cómo utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="414e2-105">This section provides a brief introduction to DiffGrams and examples of how to use them.</span></span> <span data-ttu-id="414e2-106">Se supone que está familiarizado con los DiffGrams en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="414e2-106">It is assumed that you are familiar with DiffGrams in the .NET Framework.</span></span> <span data-ttu-id="414e2-107">En esta documentación, el enfoque principal recae en los problemas de DiffGram específicos de SQLXML.</span><span class="sxs-lookup"><span data-stu-id="414e2-107">In this documentation, the primary focus is on DiffGram issues that are specific to SQLXML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="414e2-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="414e2-108">In This Section</span></span>  
 [<span data-ttu-id="414e2-109">Introducción a los DiffGrams en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="414e2-109">Introduction to DiffGrams in SQLXML 4.0</span></span>](introduction-to-diffgrams-in-sqlxml-4-0.md)  
 <span data-ttu-id="414e2-110">Proporciona información básica sobre los Diffgrams.</span><span class="sxs-lookup"><span data-stu-id="414e2-110">Provides basic information about Diffgrams.</span></span>  
  
 [<span data-ttu-id="414e2-111">Ejemplos de DiffGram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="414e2-111">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
 <span data-ttu-id="414e2-112">Proporciona ejemplos del uso de Diffgrams.</span><span class="sxs-lookup"><span data-stu-id="414e2-112">Provides examples of using Diffgrams.</span></span>  
  
 [<span data-ttu-id="414e2-113">Ejecutar un DiffGram mediante ADO &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="414e2-113">Executing a DiffGram by Using ADO &#40;SQLXML 4.0&#41;</span></span>](executing-a-diffgram-by-using-ado-sqlxml-4-0.md)  
 <span data-ttu-id="414e2-114">Proporciona un ejemplo de ejecución de un Diffgram con Objetos de datos ActiveX (ADO).</span><span class="sxs-lookup"><span data-stu-id="414e2-114">Provides an example of executing a Diffgram with ActiveX Data Objects (ADO).</span></span>  
  
 [<span data-ttu-id="414e2-115">Ejecutar un DiffGram utilizando clases administradas de SQLXML</span><span class="sxs-lookup"><span data-stu-id="414e2-115">Executing a DiffGram by Using SQLXML Managed Classes</span></span>](../net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="414e2-116">Proporciona un ejemplo de ejecución de un Diffgram con clases administradas de SQLXML.</span><span class="sxs-lookup"><span data-stu-id="414e2-116">Provides an example of executing a Diffgram with SQLXML Managed Classes.</span></span>  
  
  
