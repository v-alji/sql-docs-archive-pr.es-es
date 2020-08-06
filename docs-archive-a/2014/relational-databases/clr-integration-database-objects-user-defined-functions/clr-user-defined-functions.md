---
title: Funciones CLR definidas por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- building database objects [CLR integration], user-defined functions
- functions [CLR integration]
- common language runtime [SQL Server], user-defined functions
- database objects [CLR integration], user-defined functions
- user-defined functions [CLR integration]
ms.assetid: 6f7491f1-9a46-4146-ae09-056248634de2
author: rothja
ms.author: jroth
ms.openlocfilehash: ba7a4a983ec0cb36ef0fd79df44491f7f23f7648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675444"
---
# <a name="clr-user-defined-functions"></a><span data-ttu-id="1ec0c-102">Funciones definidas por el usuario de CLR</span><span class="sxs-lookup"><span data-stu-id="1ec0c-102">CLR User-Defined Functions</span></span>
  <span data-ttu-id="1ec0c-103">Las funciones definidas por el usuario son rutinas que pueden tomar parámetros, realizar cálculos u otras acciones y devolver un resultado.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-103">User-defined functions are routines that can take parameters, perform calculations or other actions, and return a result.</span></span> <span data-ttu-id="1ec0c-104">A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], las funciones definidas por el usuario se pueden escribir en cualquier lenguaje de programación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, como [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can write user-defined functions in any [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework programming language, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="1ec0c-105">Existen dos tipos de funciones: escalares, que devuelven un valor único, y con valores de tabla, que devuelven un conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-105">There are two types of functions: scalar, which returns a single value, and table-valued, which returns a set of rows.</span></span>  
  
 <span data-ttu-id="1ec0c-106">En la siguiente tabla se muestran los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="1ec0c-107">Funciones escalares de CLR</span><span class="sxs-lookup"><span data-stu-id="1ec0c-107">CLR Scalar-Valued Functions</span></span>](clr-scalar-valued-functions.md)  
 <span data-ttu-id="1ec0c-108">Trata los requisitos de implementación y muestra ejemplos de funciones escalares.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-108">Covers implementation requirements and examples of scalar-valued functions.</span></span>  
  
 [<span data-ttu-id="1ec0c-109">Funciones con valores de tabla en CLR</span><span class="sxs-lookup"><span data-stu-id="1ec0c-109">CLR Table-Valued Functions</span></span>](clr-table-valued-functions.md)  
 <span data-ttu-id="1ec0c-110">Explica cómo implementar y utilizar las funciones con valores de tabla (TVF), así como las diferencias entre las TVF de [!INCLUDE[tsql](../../includes/tsql-md.md)] y de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1ec0c-110">Discusses how to implement and use table-valued functions (TVFs), as well as differences between [!INCLUDE[tsql](../../includes/tsql-md.md)] and common language runtime (CLR) TVFs.</span></span>  
  
 [<span data-ttu-id="1ec0c-111">Agregados definidos por el usuario de CLR</span><span class="sxs-lookup"><span data-stu-id="1ec0c-111">CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates.md)  
 <span data-ttu-id="1ec0c-112">Describe cómo implementar y utilizar los agregados definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1ec0c-112">Describes how to implement and use user-defined aggregates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec0c-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ec0c-113">See Also</span></span>  
 [<span data-ttu-id="1ec0c-114">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="1ec0c-114">User-Defined Functions</span></span>](../user-defined-functions/user-defined-functions.md)  
  
  
