---
title: Especificar una consulta SQL o MDX (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.specsqlmdxquery.f1
ms.assetid: e4128221-3b46-48be-b0f1-d82477ce6782
author: minewiskan
ms.author: owend
ms.openlocfilehash: bce5e92aaed7a62311e989d6963e4fa5764028ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748280"
---
# <a name="specify-a-sql-or-mdx-query-ssas"></a><span data-ttu-id="2f1ab-102">Especificar una consulta SQL o MDX (SSAS)</span><span class="sxs-lookup"><span data-stu-id="2f1ab-102">Specify a SQL or MDX Query (SSAS)</span></span>
  <span data-ttu-id="2f1ab-103">Esta página del **Asistente para la importación de tablas** le permite importar datos usando una consulta SQL o MDX.</span><span class="sxs-lookup"><span data-stu-id="2f1ab-103">This page of the **Table Import Wizard** enables you to import data by using a SQL or MDX query.</span></span> <span data-ttu-id="2f1ab-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="2f1ab-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="2f1ab-105">La consulta puede tratar los datos que se importan.</span><span class="sxs-lookup"><span data-stu-id="2f1ab-105">The query can manipulate the data that is imported.</span></span> <span data-ttu-id="2f1ab-106">Por ejemplo, podría combinar los datos de tablas diferentes o seleccionar únicamente las filas que cumplan ciertos criterios.</span><span class="sxs-lookup"><span data-stu-id="2f1ab-106">For example, you could join data from different tables or select only rows that meet certain criteria.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2f1ab-107">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="2f1ab-107">UI element list</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2f1ab-108">Término</span><span class="sxs-lookup"><span data-stu-id="2f1ab-108">Term</span></span>|<span data-ttu-id="2f1ab-109">Definición</span><span class="sxs-lookup"><span data-stu-id="2f1ab-109">Definition</span></span>|  
|<span data-ttu-id="2f1ab-110">**Nombre descriptivo de la consulta**</span><span class="sxs-lookup"><span data-stu-id="2f1ab-110">**Friendly Query Name**</span></span>|<span data-ttu-id="2f1ab-111">Escriba un nombre único para la consulta.</span><span class="sxs-lookup"><span data-stu-id="2f1ab-111">Type a unique name for the query.</span></span> <span data-ttu-id="2f1ab-112">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2f1ab-112">This is a required field.</span></span>|  
|<span data-ttu-id="2f1ab-113">**Instrucción SQL**</span><span class="sxs-lookup"><span data-stu-id="2f1ab-113">**SQL Statement**</span></span>|<span data-ttu-id="2f1ab-114">Escriba o pegue una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="2f1ab-114">Type or paste a SQL statement.</span></span>|  
|<span data-ttu-id="2f1ab-115">**Validación**</span><span class="sxs-lookup"><span data-stu-id="2f1ab-115">**Validate**</span></span>|<span data-ttu-id="2f1ab-116">Determine si la instrucción SQL es válida.</span><span class="sxs-lookup"><span data-stu-id="2f1ab-116">Determine if the SQL statement is valid.</span></span>|  
|<span data-ttu-id="2f1ab-117">**Diseño**</span><span class="sxs-lookup"><span data-stu-id="2f1ab-117">**Design**</span></span>|<span data-ttu-id="2f1ab-118">Diseñe una instrucción SQL utilizando el cuadro de diálogo de diseñador de consultas.</span><span class="sxs-lookup"><span data-stu-id="2f1ab-118">Design a SQL statement by using the query designer dialog box.</span></span> <span data-ttu-id="2f1ab-119">Para más información, vea [Diseñador de consultas relacionales &#40;SSAS&#41;](relational-query-designer-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="2f1ab-119">For more information, see [Relational Query Designer &#40;SSAS&#41;](relational-query-designer-ssas.md).</span></span>|  
  
  
