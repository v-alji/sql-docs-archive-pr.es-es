---
title: Programación de procedimientos almacenados extendidos de motor de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], programming
- stored procedures [SQL Server], extended
- Database Engine [SQL Server], stored procedures
- macros [SQL Server]
- Extended Stored Procedure API [SQL Server]
ms.assetid: 158a6765-0542-4e84-b5ab-f173d946ef5e
author: rothja
ms.author: jroth
ms.openlocfilehash: fecb8f996ddfcaede83cdb330e9c82bffdce5819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677157"
---
# <a name="database-engine-extended-stored-procedure-programming"></a><span data-ttu-id="98807-102">Programación de procedimientos almacenados extendidos de motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="98807-102">Database Engine Extended Stored Procedure Programming</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="98807-103">En su lugar, utilice la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="98807-103">Use CLR Integration instead.</span></span> <span data-ttu-id="98807-104">Para obtener más información, consulte [Conceptos de programación en el ámbito de la integración de Common Language Runtime &#40;CLR&#41;](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="98807-104">For more information, see [Common Language Runtime &#40;CLR&#41; Integration Programming Concepts](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span></span>  
  
 <span data-ttu-id="98807-105">La [!INCLUDE[msCoName](../includes/msconame-md.md)] API de procedimientos almacenados extendidos proporciona una interfaz de programación de aplicaciones (API) basada en servidor para extender la [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="98807-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Extended Stored Procedure API provides a server-based application programming interface (API) for extending [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="98807-106">La API está compuesta de funciones y macros de C y C++ que se utilizan para crear aplicaciones de las siguientes categorías: procedimientos almacenados extendidos y aplicaciones de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="98807-106">The API consists of C and C++ functions and macros used to build applications in the following categories: extended stored procedures and gateway applications.</span></span>  
  
 <span data-ttu-id="98807-107">Los procedimientos almacenados extendidos permiten crear rutinas externas propias en un lenguaje de programación como C. Estos procedimientos se muestran ante los usuarios como procedimientos almacenados típicos y se ejecutan del mismo modo.</span><span class="sxs-lookup"><span data-stu-id="98807-107">Extended stored procedures allow you to create your own external routines in a programming language such as C. The extended stored procedures appear to users as typical stored procedures and are executed in the same way.</span></span> <span data-ttu-id="98807-108">Es posible pasar parámetros a los procedimientos almacenados extendidos y estos pueden devolver resultados y estados.</span><span class="sxs-lookup"><span data-stu-id="98807-108">Parameters can be passed to extended stored procedures, and they can return results and return status.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98807-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="98807-109">In This Section</span></span>  
 [<span data-ttu-id="98807-110">Programación de procedimientos almacenados extendidos</span><span class="sxs-lookup"><span data-stu-id="98807-110">Programming Extended Stored Procedures</span></span>](extended-stored-procedures-programming/database-engine-extended-stored-procedures-programming.md)  
 <span data-ttu-id="98807-111">Explica cómo crear, administrar y usar procedimientos almacenados extendidos.</span><span class="sxs-lookup"><span data-stu-id="98807-111">Explains how to create, manage, and use extended stored procedures.</span></span>  
  
 [<span data-ttu-id="98807-112">Referencia del programador de procedimientos almacenados extendidos</span><span class="sxs-lookup"><span data-stu-id="98807-112">Extended Stored Procedures Programmer's Reference</span></span>](extended-stored-procedures-reference/database-engine-extended-stored-procedures-reference.md)  
 <span data-ttu-id="98807-113">Contiene temas de referencia relativos a la API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="98807-113">Contains reference topics for the Extended Stored Procedure API.</span></span>  
  
  
