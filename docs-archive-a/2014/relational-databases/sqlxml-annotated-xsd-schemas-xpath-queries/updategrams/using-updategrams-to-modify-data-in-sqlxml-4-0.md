---
title: Usar diagramas para modificar datos en SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- data insertions [SQLXML]
- data deletions [SQLXML]
- updating data [SQLXML]
- modifying data [SQLXML]
- OPENXML function
- updategrams [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- modifying databases
- data modifications [SQLXML]
- deleting data
- inserting data
ms.assetid: b8b3b892-cb73-41d0-b945-bce148d81d9b
author: rothja
ms.author: jroth
ms.openlocfilehash: a4a2397668ed08df91377cc35dea22fd52788580
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674726"
---
# <a name="using-updategrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="ee687-102">Utilizar los diagramas de actualización para modificar datos en SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="ee687-102">Using Updategrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="ee687-103">Puede modificar (insertar, actualizar o eliminar) una base de datos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] desde un documento XML existente mediante una diagrama o la función OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee687-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="ee687-104">En esta sección se proporciona información sobre los diagramas de actualización y ejemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="ee687-104">This section provides information about updategrams and examples of their usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee687-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ee687-105">In This Section</span></span>  
 [<span data-ttu-id="ee687-106">Introducción a diagramas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-106">Introduction to Updategrams &#40;SQLXML 4.0&#41;</span></span>](introduction-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-107">Proporciona información básica y ejemplos de diagramas de actualización.</span><span class="sxs-lookup"><span data-stu-id="ee687-107">Provides basic information and examples of updategrams.</span></span>  
  
 [<span data-ttu-id="ee687-108">Especificar un esquema de asignación anotado en un diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-108">Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;</span></span>](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-109">Explica y proporciona ejemplos de esquemas de asignación anotados en los diagramas de actualización.</span><span class="sxs-lookup"><span data-stu-id="ee687-109">Explains and provides examples of annotated mapping schemas in updategrams.</span></span>  
  
 [<span data-ttu-id="ee687-110">Control de valores NULL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-110">NULL Handling &#40;SQLXML 4.0&#41;</span></span>](null-handling-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-111">Describe cómo especificar NULL para los valores de elemento y atributo.</span><span class="sxs-lookup"><span data-stu-id="ee687-111">Describes how to specify NULL for element and attribute values.</span></span>  
  
 [<span data-ttu-id="ee687-112">Insertar datos mediante XML diagramas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-112">Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](inserting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-113">Describe y proporciona ejemplos de uso de los diagramas de actualización para insertar los datos.</span><span class="sxs-lookup"><span data-stu-id="ee687-113">Describes and provides examples of using updategrams to insert data.</span></span>  
  
 [<span data-ttu-id="ee687-114">Eliminar datos mediante XML diagramas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-114">Deleting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](deleting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-115">Describe y proporciona ejemplos de uso de los diagramas de actualización para eliminar los datos.</span><span class="sxs-lookup"><span data-stu-id="ee687-115">Describes and provides examples of using updategrams to delete data.</span></span>  
  
 [<span data-ttu-id="ee687-116">Actualizar datos mediante XML diagramas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-116">Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](updating-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-117">Describe y proporciona ejemplos de uso de los diagramas de actualización para modificar los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="ee687-117">Describes and provides examples of using updategrams to modify existing data.</span></span>  
  
 [<span data-ttu-id="ee687-118">Pasar parámetros a diagramas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-118">Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;</span></span>](passing-parameters-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-119">Describe y proporciona ejemplos de paso de parámetros a los diagramas de actualización.</span><span class="sxs-lookup"><span data-stu-id="ee687-119">Describes and provides examples of passing parameters to updategrams.</span></span>  
  
 [<span data-ttu-id="ee687-120">Controlar los problemas de simultaneidad de bases de datos en diagramas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-120">Handling Database Concurrency Issues in Updategrams &#40;SQLXML 4.0&#41;</span></span>](handling-database-concurrency-issues-in-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-121">Describe los distintos niveles de protección posibles para administrar los problemas de simultaneidad en los diagramas de actualización y proporciona los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ee687-121">Describes the various levels of protection possible for handling concurrency issues in updategrams, and provides examples.</span></span>  
  
 [<span data-ttu-id="ee687-122">Aplicaciones de ejemplo de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-122">Updategram Sample Applications &#40;SQLXML 4.0&#41;</span></span>](../../../database-engine/dev-guide/updategram-sample-applications-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-123">Proporciona aplicaciones de ejemplo que usan los diagramas de actualización.</span><span class="sxs-lookup"><span data-stu-id="ee687-123">Provides sample applications that use updategrams.</span></span>  
  
 [<span data-ttu-id="ee687-124">Instrucciones y limitaciones de XML diagramas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ee687-124">Guidelines and Limitations of XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="ee687-125">Enumera algunas cosas que hay que recordar a la hora de trabajar con los diagramas de actualización.</span><span class="sxs-lookup"><span data-stu-id="ee687-125">Lists some things to remember when working with updategrams.</span></span>  
  
  
