---
title: Trabajar con objetos de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- database objects [SMO]
- objects [SMO]
ms.assetid: 702fd63d-8734-4a02-872e-aecfb037c787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 14dd0c0175a23f809fc925c5104ac15ac408805b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749217"
---
# <a name="working-with-database-objects"></a><span data-ttu-id="cd7ae-102">Trabajar con objetos de bases de datos</span><span class="sxs-lookup"><span data-stu-id="cd7ae-102">Working with Database Objects</span></span>
  <span data-ttu-id="cd7ae-103">Éstas son las fases de la creación de objetos SMO:</span><span class="sxs-lookup"><span data-stu-id="cd7ae-103">The stages of SMO object creation are as follows:</span></span>  
  
1.  <span data-ttu-id="cd7ae-104">Crear una instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-104">Create an instance of the object.</span></span>  
  
2.  <span data-ttu-id="cd7ae-105">Establecer las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-105">Set the object properties.</span></span>  
  
3.  <span data-ttu-id="cd7ae-106">Crear instancias de objetos secundarios.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-106">Create instances of the child objects.</span></span>  
  
4.  <span data-ttu-id="cd7ae-107">Establecer las propiedades de los objetos secundarios.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-107">Set the child object properties.</span></span>  
  
5.  <span data-ttu-id="cd7ae-108">Crear el objeto.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-108">Create the object.</span></span>  
  
 <span data-ttu-id="cd7ae-109">Cuando se crean instancias de objetos SMO en una aplicación SMO, no existen en la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hasta que se emite el método `Create`.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-109">When instances of SMO objects are created in an SMO application, they do not exist on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] until the `Create` method is issued.</span></span> <span data-ttu-id="cd7ae-110">Sin embargo, no es necesario emitir un método `Create` para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-110">However, it is not necessary to issue a `Create` method for every individual object.</span></span> <span data-ttu-id="cd7ae-111">Si un objeto tiene un conjunto de objetos secundarios, solo hace falta el objeto primario para ejecutar el método `Create`.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-111">If an object has a set of child objects, only the parent object is required to run the `Create` method.</span></span> <span data-ttu-id="cd7ae-112">Por ejemplo, la definición de una tabla requiere que contenga al menos una columna para existir.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-112">For example, the definition of a table requires that it contains at least one column to exist.</span></span> <span data-ttu-id="cd7ae-113">Asimismo, una columna no puede existir aislada sin una tabla.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-113">Also, a column cannot exist in isolation without a table.</span></span> <span data-ttu-id="cd7ae-114">Hay una relación de codependencia entre la tabla y sus columnas.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-114">There is a codependent relationship between the table and its columns.</span></span>  
  
 <span data-ttu-id="cd7ae-115">El método <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> le permite hacer cambios en un objeto.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-115">The <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> method lets you make changes to an object.</span></span> <span data-ttu-id="cd7ae-116">Si se realizan varios cambios en un objeto, como agregar objetos secundarios a una de las colecciones del objeto o cambiar un valor de propiedad, se agrupan por lotes y se ejecutan como uno solo.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-116">Several changes to an object, such as adding child objects to one of the object's collections or changing a property value, are batched together and run as one.</span></span> <span data-ttu-id="cd7ae-117">El método `Alter` reduce el tráfico de red y mejora el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-117">The `Alter` method reduces network traffic and improves overall performance.</span></span>  
  
 <span data-ttu-id="cd7ae-118">La instrucción `Drop` se utiliza para quitar un objeto y todos los objetos secundarios codependientes que hicieron falta para crear el objeto inicialmente.</span><span class="sxs-lookup"><span data-stu-id="cd7ae-118">The `Drop` statement is used to remove an object and all its codependent child objects that were required to create the object initially.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7ae-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd7ae-119">See Also</span></span>  
 [<span data-ttu-id="cd7ae-120">Modelo de objetos SMO</span><span class="sxs-lookup"><span data-stu-id="cd7ae-120">SMO Object Model</span></span>](../smo-object-model.md)  
  
  
