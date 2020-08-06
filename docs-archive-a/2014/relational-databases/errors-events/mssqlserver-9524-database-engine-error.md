---
title: MSSQLSERVER_9524 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9524 (Database Engine error)
ms.assetid: 12da7931-e124-4466-889c-046f1b7b7bfd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6c46ee0ef0bd1be299614e2cb04a3d6cd99d92e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672032"
---
# <a name="mssqlserver_9524"></a><span data-ttu-id="f5483-102">MSSQLSERVER_9524</span><span class="sxs-lookup"><span data-stu-id="f5483-102">MSSQLSERVER_9524</span></span>
    
## <a name="details"></a><span data-ttu-id="f5483-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f5483-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5483-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="f5483-104">Product Name</span></span>|<span data-ttu-id="f5483-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5483-105">SQL Server</span></span>|  
|<span data-ttu-id="f5483-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f5483-106">Event ID</span></span>|<span data-ttu-id="f5483-107">9254</span><span class="sxs-lookup"><span data-stu-id="f5483-107">9254</span></span>|  
|<span data-ttu-id="f5483-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="f5483-108">Event Source</span></span>|<span data-ttu-id="f5483-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f5483-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f5483-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f5483-110">Component</span></span>|<span data-ttu-id="f5483-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f5483-111">SQLEngine</span></span>|  
|<span data-ttu-id="f5483-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f5483-112">Symbolic Name</span></span>|<span data-ttu-id="f5483-113">XMLERR_INVALID_COLUMNSET_XML</span><span class="sxs-lookup"><span data-stu-id="f5483-113">XMLERR_INVALID_COLUMNSET_XML</span></span>|  
|<span data-ttu-id="f5483-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f5483-114">Message Text</span></span>|<span data-ttu-id="f5483-115">El contenido XML proporcionado no tiene el formato XML requerido para conjuntos de columnas dispersas.</span><span class="sxs-lookup"><span data-stu-id="f5483-115">The XML content provided does not conform to the required XML format for sparse column sets.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f5483-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="f5483-116">Explanation</span></span>  
 <span data-ttu-id="f5483-117">Se ha intentado modificar un conjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="f5483-117">An attempt was made to modify a column set.</span></span> <span data-ttu-id="f5483-118">El contenido XML de un conjunto de columnas debe satisfacer las restricciones de formato correspondientes.</span><span class="sxs-lookup"><span data-stu-id="f5483-118">The XML content of a column set must meet the format restrictions of a column set.</span></span> <span data-ttu-id="f5483-119">El formato general de un conjunto de columnas es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5483-119">The general format of a column set is as follows:</span></span>  
  
 `<column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...`  
  
 <span data-ttu-id="f5483-120">Para obtener más información sobre conjuntos de columnas, vea el tema "Usar conjuntos de columnas" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5483-120">For more information about column sets, see the topic "Using Column Sets" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f5483-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f5483-121">User Action</span></span>  
 <span data-ttu-id="f5483-122">Corrija el formato del contenido XML del conjunto de columnas en la instrucción.</span><span class="sxs-lookup"><span data-stu-id="f5483-122">Correct the format of the XML for the column set in the statement.</span></span>  
  
  
