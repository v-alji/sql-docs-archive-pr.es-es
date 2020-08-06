---
title: MSSQLSERVER_102 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 102 (Database Engine error)
ms.assetid: 264dc1a2-c8a0-4c89-b5f6-951baf950299
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 18c330b8d6a534ca11e2ad2c03f89793f8c832e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663009"
---
# <a name="mssqlserver_102"></a><span data-ttu-id="f4809-102">MSSQLSERVER_102</span><span class="sxs-lookup"><span data-stu-id="f4809-102">MSSQLSERVER_102</span></span>
    
## <a name="details"></a><span data-ttu-id="f4809-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f4809-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4809-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="f4809-104">Product Name</span></span>|<span data-ttu-id="f4809-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f4809-105">SQL Server</span></span>|  
|<span data-ttu-id="f4809-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f4809-106">Event ID</span></span>|<span data-ttu-id="f4809-107">102</span><span class="sxs-lookup"><span data-stu-id="f4809-107">102</span></span>|  
|<span data-ttu-id="f4809-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="f4809-108">Event Source</span></span>|<span data-ttu-id="f4809-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f4809-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f4809-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f4809-110">Component</span></span>|<span data-ttu-id="f4809-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f4809-111">SQLEngine</span></span>|  
|<span data-ttu-id="f4809-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f4809-112">Symbolic Name</span></span>|<span data-ttu-id="f4809-113">P_SYNTAXERR2</span><span class="sxs-lookup"><span data-stu-id="f4809-113">P_SYNTAXERR2</span></span>|  
|<span data-ttu-id="f4809-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f4809-114">Message Text</span></span>|<span data-ttu-id="f4809-115">Sintaxis incorrecta cerca de '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="f4809-115">Incorrect syntax near '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f4809-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="f4809-116">Explanation</span></span>  
 <span data-ttu-id="f4809-117">Indica un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="f4809-117">Indicates a syntax error.</span></span> <span data-ttu-id="f4809-118">La información adicional no está disponible porque el error impide que [!INCLUDE[ssDE](../../includes/ssde-md.md)] procese la instrucción.</span><span class="sxs-lookup"><span data-stu-id="f4809-118">Additional information is not available because the error prevents the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from processing the statement.</span></span>  
  
 <span data-ttu-id="f4809-119">Puede deberse a un intento de crear una clave simétrica mediante el cifrado RC4 desusado o RC4_128, cuando no está en el modo de compatibilidad 90 o 100.</span><span class="sxs-lookup"><span data-stu-id="f4809-119">Can be caused by attempting to create a symmetric key using the deprecated RC4 or RC4_128 encryption, when not in 90 or 100 compatibility mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4809-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f4809-120">User Action</span></span>  
 <span data-ttu-id="f4809-121">Busque la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] para los errores de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="f4809-121">Search the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement for syntax errors.</span></span>  
  
 <span data-ttu-id="f4809-122">Si creó una clave simétrica mediante RC4 o RC4_128, seleccione un cifrado más reciente como, por ejemplo, uno de los algoritmos de AES.</span><span class="sxs-lookup"><span data-stu-id="f4809-122">If creating a symmetric key using the RC4 or RC4_128, select a newer encryption such as one of the AES algorithms.</span></span> <span data-ttu-id="f4809-123">(Se recomienda). Si debe usar RC4, emplee ALTER DATABASE SET COMPATIBILITY_LEVEL para establecer el nivel de compatibilidad de la base de datos en 90 o 100.</span><span class="sxs-lookup"><span data-stu-id="f4809-123">(Recommended.) If you must use RC4, use ALTER DATABASE SET COMPATIBILITY_LEVEL to set the database to compatibility level 90 or 100.</span></span> <span data-ttu-id="f4809-124">(No se recomienda).</span><span class="sxs-lookup"><span data-stu-id="f4809-124">(Not recommended.)</span></span>  
  
  
