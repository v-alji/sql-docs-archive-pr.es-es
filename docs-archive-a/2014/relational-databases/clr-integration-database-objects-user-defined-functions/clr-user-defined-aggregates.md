---
title: Agregados definidos por el usuario CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- aggregate functions [CLR integration]
- custom aggregates [CLR integration]
- calculations [CLR integration]
- user-defined functions [CLR integration]
ms.assetid: bad9b7e8-5967-4afa-8dc8-6d840faf9372
author: rothja
ms.author: jroth
ms.openlocfilehash: d1ef5d07fe082d0eeb2c3484d6e99572d8fc80e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673727"
---
# <a name="clr-user-defined-aggregates"></a><span data-ttu-id="e2914-102">Agregados definidos por el usuario de CLR</span><span class="sxs-lookup"><span data-stu-id="e2914-102">CLR User-Defined Aggregates</span></span>
  <span data-ttu-id="e2914-103">Las funciones de agregado realizan un cálculo en un conjunto de valores y devuelven un valor único.</span><span class="sxs-lookup"><span data-stu-id="e2914-103">Aggregate functions perform a calculation on a set of values and return a single value.</span></span> <span data-ttu-id="e2914-104">Tradicionalmente, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] solo ha admitido funciones de agregado integradas, como `SUM` o `MAX` , que operan en un conjunto de valores escalares de entrada y generan un valor de agregado único a partir de ese conjunto.</span><span class="sxs-lookup"><span data-stu-id="e2914-104">Traditionally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has supported only built-in aggregate functions, such as `SUM` or `MAX`, that operate on a set of input scalar values and generate a single aggregate value from that set.</span></span> <span data-ttu-id="e2914-105">La integración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con Common Language Runtime (CLR) de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework permite ahora a los desarrolladores crear funciones de agregado personalizadas en código administrado y hacer que estas funciones estén accesibles para [!INCLUDE[tsql](../../includes/tsql-md.md)] u otro código administrado.</span><span class="sxs-lookup"><span data-stu-id="e2914-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) now allows developers to create custom aggregate functions in managed code, and to make these functions accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span>  
  
 <span data-ttu-id="e2914-106">En la siguiente tabla se muestran los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="e2914-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="e2914-107">Requisitos para agregados definidos por el usuario de CLR</span><span class="sxs-lookup"><span data-stu-id="e2914-107">Requirements for CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates-requirements.md)  
 <span data-ttu-id="e2914-108">Proporciona información general sobre los requisitos para implementar funciones de agregado definidas por el usuario de CLR.</span><span class="sxs-lookup"><span data-stu-id="e2914-108">Provides an overview of the requirements for implementing CLR user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="e2914-109">Invocar funciones de agregado definidas por el usuario de CLR</span><span class="sxs-lookup"><span data-stu-id="e2914-109">Invoking CLR User-Defined Aggregate Functions</span></span>](clr-user-defined-aggregate-invoking-functions.md)  
 <span data-ttu-id="e2914-110">Explica cómo invocar los agregados definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e2914-110">Explains how to invoke user-defined aggregates.</span></span>  
  
  
