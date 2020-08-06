---
title: Seleccionar una columna de clave de tabla anidada (cuadro de diálogo de la vista estructura de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.structure.addnestedtable.f1
helpviewer_keywords:
- Select a Nested Table Key Column dialog box
ms.assetid: f68b89a7-17df-45f8-ba7f-b458cd9b1ec3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dc524f6913b7be15e87869355515397a3e0b65c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675562"
---
# <a name="select-a-nested-table-key-column-dialog-box-mining-structure-view"></a><span data-ttu-id="b354e-102">Seleccione una columna de clave de tabla anidada (cuadro de diálogo de la vista Estructura de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="b354e-102">Select a Nested Table Key Column Dialog Box (Mining Structure View)</span></span>
  <span data-ttu-id="b354e-103">Utilice el cuadro de diálogo **Seleccione una columna de clave de tabla anidada** para designar una columna que actuará como la clave para la nueva tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="b354e-103">Use the **Select a Nested Table Key Column** dialog box to designate a column that will act as the key for the new nested table.</span></span> <span data-ttu-id="b354e-104">Cuando salga del cuadro de diálogo, se agrega una nueva tabla a la estructura de minería de datos que contiene la columna de clave designada.</span><span class="sxs-lookup"><span data-stu-id="b354e-104">When you exit the dialog box, a new table is added to the mining structure that contains the designated key column.</span></span> <span data-ttu-id="b354e-105">Puede agregar columnas adicionales a la tabla anidada haciendo clic con el botón derecho en la estructura y seleccionando **Agregar una columna**.</span><span class="sxs-lookup"><span data-stu-id="b354e-105">You can add additional columns to the nested table by right-clicking the structure and selecting **Add a Column**.</span></span> <span data-ttu-id="b354e-106">El cuadro de diálogo contiene diferentes opciones dependiendo de si está trabajando con un modelo de minería OLAP o un modelo de minería relacional.</span><span class="sxs-lookup"><span data-stu-id="b354e-106">The dialog box contains different options depending on whether you are working with an OLAP mining model or a relational mining model.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b354e-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="b354e-107">Options</span></span>  
 <span data-ttu-id="b354e-108">**Tabla de origen**</span><span class="sxs-lookup"><span data-stu-id="b354e-108">**Source table**</span></span>  
 <span data-ttu-id="b354e-109">La tabla en la que se basa el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="b354e-109">The table on which the mining model is based.</span></span>  
  
 <span data-ttu-id="b354e-110">Solo se utiliza para modelos de minería relacionales.</span><span class="sxs-lookup"><span data-stu-id="b354e-110">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="b354e-111">**Columna de origen**</span><span class="sxs-lookup"><span data-stu-id="b354e-111">**Source column**</span></span>  
 <span data-ttu-id="b354e-112">Lista de todas las columnas disponibles en la tabla de origen que puede emplear como la clave de la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="b354e-112">A list of all the available columns in the source table that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="b354e-113">Solo se utiliza para modelos de minería relacionales.</span><span class="sxs-lookup"><span data-stu-id="b354e-113">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="b354e-114">**Mostrar tipos de columna**</span><span class="sxs-lookup"><span data-stu-id="b354e-114">**Show column types**</span></span>  
 <span data-ttu-id="b354e-115">Una lista de los tipos de datos de columnas disponibles.</span><span class="sxs-lookup"><span data-stu-id="b354e-115">A list of available column data types.</span></span> <span data-ttu-id="b354e-116">Seleccione o deseleccione los tipos de datos para filtrar la lista de columnas en **Columna de origen**.</span><span class="sxs-lookup"><span data-stu-id="b354e-116">Select or clear data types to filter the list of columns in **Source column**.</span></span> <span data-ttu-id="b354e-117">En la lista **Columna de origen** solo se mostrarán las columnas que coinciden con los tipos de datos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="b354e-117">Only columns that match the checked data types will be shown in the **Source column** list.</span></span>  
  
 <span data-ttu-id="b354e-118">Solo se utiliza para modelos de minería relacionales.</span><span class="sxs-lookup"><span data-stu-id="b354e-118">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="b354e-119">**Atributos**</span><span class="sxs-lookup"><span data-stu-id="b354e-119">**Attributes**</span></span>  
 <span data-ttu-id="b354e-120">Lista de atributos que puede utilizar como la clave de la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="b354e-120">A list of attributes that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="b354e-121">Solo se utiliza para modelos de minería de datos OLAP.</span><span class="sxs-lookup"><span data-stu-id="b354e-121">This is only used for OLAP mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b354e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b354e-122">See Also</span></span>  
 [<span data-ttu-id="b354e-123">Vista estructura de minería de datos &#40;diseñador de modelos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="b354e-123">Mining Structure View &#40;Data Mining Model Designer&#41;</span></span>](mining-structure-view-data-mining-model-designer.md)  
  
  
