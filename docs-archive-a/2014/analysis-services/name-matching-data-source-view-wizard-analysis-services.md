---
title: Coincidencia de nombres (Asistente para vistas del origen de datos) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.namematchingcriteria.f1
ms.assetid: 7f811e02-0fe6-45c9-a7b7-29c61032d96b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50cc46db7f582e0aea1570dadc956336ef8be074
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673338"
---
# <a name="name-matching-data-source-view-wizard-analysis-services"></a><span data-ttu-id="36b4b-102">Coincidencia de nombres (Asistente para vistas del origen de datos) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="36b4b-102">Name Matching (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="36b4b-103">Use la página **Coincidencia de nombres** para seleccionar el criterio que desea utilizar para detectar las posibles relaciones entre las tablas seleccionadas para la vista del origen de datos y las demás tablas del esquema.</span><span class="sxs-lookup"><span data-stu-id="36b4b-103">Use the **Name Matching** page to select the criterion to use for detecting possible relationships between the tables that you select for the data source view and the other tables in the schema.</span></span> <span data-ttu-id="36b4b-104">Si no existen relaciones de claves externas físicas entre las tablas, este criterio le permitirá identificar y agregar las tablas relacionadas a la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="36b4b-104">If no physical foreign key relationships exist between the tables, this criterion helps you identify and add related tables to the data source view.</span></span> <span data-ttu-id="36b4b-105">Las relaciones lógicas identificadas por la coincidencia de nombres también se agregan a la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="36b4b-105">The logical relationships that are identified by name matching are also added to the data source view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36b4b-106">Solo se mostrará esta página si selecciona un origen de datos con varias tablas que no presente relaciones de clave externa con las demás tablas.</span><span class="sxs-lookup"><span data-stu-id="36b4b-106">This page appears only if you select a data source that has multiple tables but no foreign key relationships between any one of the tables.</span></span>  
  
## <a name="options"></a><span data-ttu-id="36b4b-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="36b4b-107">Options</span></span>  
 <span data-ttu-id="36b4b-108">**Crear relaciones lógicas por columnas coincidentes**</span><span class="sxs-lookup"><span data-stu-id="36b4b-108">**Create logical relationships by matching columns**</span></span>  
 <span data-ttu-id="36b4b-109">Seleccione esta opción para usar un criterio de coincidencia de nombres para detectar posibles dependencias y relaciones lógicas entre las tablas seleccionadas que desea incluir en la vista del origen de datos y las demás tablas del esquema.</span><span class="sxs-lookup"><span data-stu-id="36b4b-109">Select to use a name-matching criterion to detect possible logical dependencies and relationships between the tables that you select to include in the data source view and the other tables in the schema.</span></span> <span data-ttu-id="36b4b-110">Si desactiva esta casilla, no se utilizará el criterio de coincidencia de nombres para identificar las relaciones lógicas entre las tablas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="36b4b-110">If you clear this check box, no name-matching criterion is used to identify logical relationships between tables in the data source.</span></span>  
  
 <span data-ttu-id="36b4b-111">**Coincidencias de claves externas**</span><span class="sxs-lookup"><span data-stu-id="36b4b-111">**Foreign key matches**</span></span>  
 <span data-ttu-id="36b4b-112">Seleccione el criterio que desea utilizar para crear relaciones lógicas entre tablas y vistas en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="36b4b-112">Select the criterion to use for creating logical relationships between tables and views in the data source.</span></span> <span data-ttu-id="36b4b-113">Se ignorarán los caracteres que no sean alfanuméricos en las cadenas que desea hacer coincidir.</span><span class="sxs-lookup"><span data-stu-id="36b4b-113">Non-alphanumeric characters are ignored in matching strings.</span></span> <span data-ttu-id="36b4b-114">Por ejemplo, se harán coincidir "Customer ID", "Customer_ID" y "CustomerID".</span><span class="sxs-lookup"><span data-stu-id="36b4b-114">For example, "Customer ID", "Customer_ID", "CustomerID" all match.</span></span> <span data-ttu-id="36b4b-115">Seleccione una de las opciones de la siguiente tabla para crear relaciones conforme a las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="36b4b-115">Select one of the options in the following table to create relationships under the specified conditions.</span></span>  
  
|<span data-ttu-id="36b4b-116">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="36b4b-116">Select</span></span>|<span data-ttu-id="36b4b-117">Para crear</span><span class="sxs-lookup"><span data-stu-id="36b4b-117">To create</span></span>|  
|------------|---------------|  
|<span data-ttu-id="36b4b-118">**Mismo nombre que el de la clave principal**</span><span class="sxs-lookup"><span data-stu-id="36b4b-118">**Same name as primary key**</span></span>|<span data-ttu-id="36b4b-119">Una relación lógica con todas las tablas con un nombre de columna que coincida con el nombre de la columna de clave principal de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="36b4b-119">A logical relationship to any table with a column name that matches the name of the primary key column in a selected table.</span></span>|  
|<span data-ttu-id="36b4b-120">**Mismo nombre que el nombre de tabla de destino**</span><span class="sxs-lookup"><span data-stu-id="36b4b-120">**Same name as destination table name**</span></span>|<span data-ttu-id="36b4b-121">Una relación lógica con todas las tablas con un nombre de columna que coincida con el nombre de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="36b4b-121">A logical relationship to any table with a column name that matches the name of a selected table.</span></span>|  
|<span data-ttu-id="36b4b-122">**Nombre de la tabla de destino + nombre de la clave principal**</span><span class="sxs-lookup"><span data-stu-id="36b4b-122">**Destination table name + primary key name**</span></span>|<span data-ttu-id="36b4b-123">Una relación lógica con todas las tablas en las que el nombre de columna coincide con el nombre de la tabla seleccionada concatenada con el nombre de la columna de clave principal para la tabla seleccionada, por ese orden.</span><span class="sxs-lookup"><span data-stu-id="36b4b-123">A logical relationship to any table in which a column name matches the selected table name concatenated with the name of the primary key column for the selected table, in that order.</span></span> <span data-ttu-id="36b4b-124">Se ignorarán los caracteres que no sean alfanuméricos en la concatenación (por ejemplo, se harán coincidir "Product ID", "Product_ID" y "ProductID").</span><span class="sxs-lookup"><span data-stu-id="36b4b-124">Non-alphanumeric characters within the concatenation are ignored (for example, "Product ID", "Product_ID" and "ProductID" all match).</span></span>|  
  
 <span data-ttu-id="36b4b-125">**Descripción y muestra**</span><span class="sxs-lookup"><span data-stu-id="36b4b-125">**Description and sample**</span></span>  
 <span data-ttu-id="36b4b-126">Vea una descripción y una muestra del criterio seleccionado.</span><span class="sxs-lookup"><span data-stu-id="36b4b-126">View a description and a sample of the selected criterion.</span></span>  
  
  
