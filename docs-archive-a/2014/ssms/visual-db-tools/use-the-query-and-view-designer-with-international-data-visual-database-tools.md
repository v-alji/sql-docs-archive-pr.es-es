---
title: Usar el diseñador de consultas y vistas con datos internacionales (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Visual Database Tools [SQL Server], international data
- queries [SQL Server], international data
- languages [SQL Server], Query and View Designer
- international considerations [SQL Server], Query and View Designer
- Criteria pane
- View Designer, international data
- Query Designer [SQL Server], international data
- localized information in Query and View Designer [SQL Server]
- global considerations [SQL Server], Query and View Designer
- SQL pane [Visual Database Tools]
- multiple language support [SQL Server], Query and View Designer
ms.assetid: 4b51c56f-f902-4e72-b919-e36127369b63
author: stevestein
ms.author: sstein
ms.openlocfilehash: 905e4c6909c792b019c11ef95662a7ec1a113bb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747376"
---
# <a name="use-the-query-and-view-designer-with-international-data-visual-database-tools"></a><span data-ttu-id="946f4-102">Utilizar el Diseñador de consultas y vistas con datos internacionales (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="946f4-102">Use the Query and View Designer with International Data (Visual Database Tools)</span></span>
  <span data-ttu-id="946f4-103">Puede usar el [Diseñador de consultas y vistas](visual-database-tools.md) con datos en cualquier idioma y en cualquier versión del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="946f4-103">You can use the [Query and View Designer](visual-database-tools.md) with data in any language and in any version of the Windows operating system.</span></span> <span data-ttu-id="946f4-104">Las siguientes instrucciones describen las diferencias que observará y proporcionan información sobre cómo administrar datos en aplicaciones internacionales.</span><span class="sxs-lookup"><span data-stu-id="946f4-104">The following guidelines outline the differences you will notice and provide information about managing data in international applications.</span></span>  
  
## <a name="localized-information-in-the-criteria-and-sql-panes"></a><span data-ttu-id="946f4-105">Información localizada en los paneles Criterios y SQL</span><span class="sxs-lookup"><span data-stu-id="946f4-105">Localized Information in the Criteria and SQL Panes</span></span>  
 <span data-ttu-id="946f4-106">Si se está utilizando el panel Criterios para crear una consulta, los datos podrán especificarse en el formato que corresponda a la Configuración regional de Windows para el equipo.</span><span class="sxs-lookup"><span data-stu-id="946f4-106">If you are using the Criteria pane to create your query, you can enter information in the format that corresponds to the Windows Regional Settings for you computer.</span></span> <span data-ttu-id="946f4-107">Por ejemplo, si está buscando datos, puede especificar los datos en las columnas Criterios mediante el uso de cualquier formato que esté acostumbrado a utilizar, con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="946f4-107">For example, if you are searching for data, you can enter the data in the Criteria columns using whatever format you are accustomed to using, with these exceptions:</span></span>  
  
-   <span data-ttu-id="946f4-108">No se admiten formatos de datos largos.</span><span class="sxs-lookup"><span data-stu-id="946f4-108">Long data formats are not supported.</span></span>  
  
-   <span data-ttu-id="946f4-109">No deben especificarse símbolos de moneda en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="946f4-109">Currency symbols should not be entered in the Criteria pane.</span></span>  
  
-   <span data-ttu-id="946f4-110">Los símbolos de moneda no se mostrarán en el panel Resultados.</span><span class="sxs-lookup"><span data-stu-id="946f4-110">Currency symbols will not display in the Results pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="946f4-111">En el panel Resultados, puede especificar el símbolo de moneda que corresponda a la Configuración regional de Windows del equipo, pero el símbolo desaparecerá y no se mostrará en el panel Resultados.</span><span class="sxs-lookup"><span data-stu-id="946f4-111">In the Results pane, you can actually enter the currency symbol that corresponds to the Windows Regional Settings for your computer, but the symbol will be removed and will not display in the Results pane.</span></span>  
  
-   <span data-ttu-id="946f4-112">Un menos unario aparece siempre en el lado izquierdo (por ejemplo, -1), independientemente de las opciones de Configuración regional.</span><span class="sxs-lookup"><span data-stu-id="946f4-112">Unary minus always appears on the left side (for example, -1) regardless of the Regional Settings options.</span></span>  
  
 <span data-ttu-id="946f4-113">Por el contrario, los datos y palabras clave del panel SQL deberán estar siempre en formato ANSI (EE.UU.).</span><span class="sxs-lookup"><span data-stu-id="946f4-113">In contrast, data and keywords in the SQL pane must always be in ANSI (U.S.) format.</span></span> <span data-ttu-id="946f4-114">Por ejemplo, a medida que el Diseñador de consultas y vistas genera una consulta, inserta la forma ANSI de todas las palabras clave SQL (por ejemplo, SELECT y FROM).</span><span class="sxs-lookup"><span data-stu-id="946f4-114">For example, as the Query and View Designer builds a query, it inserts the ANSI form of all SQL keywords such as SELECT and FROM.</span></span> <span data-ttu-id="946f4-115">Si agrega elementos a la instrucción en el panel SQL, asegúrese de utilizar la forma ANSI estándar para los elementos.</span><span class="sxs-lookup"><span data-stu-id="946f4-115">If you add elements to the statement in the SQL pane, be sure to use the ANSI standard form for the elements.</span></span>  
  
 <span data-ttu-id="946f4-116">Al especificar datos mediante el uso de un formato regional específico en el panel Criterios, el Diseñador de consultas y vistas los traduce automáticamente a formato ANSI en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="946f4-116">When you enter data using local-specific format in the Criteria pane, the Query and View Designer automatically translates it to ANSI format in the SQL pane.</span></span> <span data-ttu-id="946f4-117">Por ejemplo, si la Configuración regional está establecida en Alemán (estándar), puede especificar datos en el panel Criterios en un formato como "31.12.96".</span><span class="sxs-lookup"><span data-stu-id="946f4-117">For example, if your Regional Settings are set to Standard German, you can enter data in the Criteria pane in a format such as "31.12.96."</span></span> <span data-ttu-id="946f4-118">Sin embargo, la fecha aparecerá en el panel SQL en formato de fecha y hora ANSI, como `{ ts '1996-12-31 00:00:00' }.` . Si escribe los datos directamente en el panel SQL, debe hacerlo en formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="946f4-118">However, the date will appear in the SQL pane in ANSI datetime format as `{ ts '1996-12-31 00:00:00' }.` If you enter data directly in the SQL pane, you must enter it in ANSI format.</span></span>  
  
## <a name="sort-order"></a><span data-ttu-id="946f4-119">Criterio de ordenación</span><span class="sxs-lookup"><span data-stu-id="946f4-119">Sort Order</span></span>  
 <span data-ttu-id="946f4-120">El criterio de ordenación de los datos de la consulta viene determinado por la base de datos.</span><span class="sxs-lookup"><span data-stu-id="946f4-120">The sort order of data in your query is determined by the database.</span></span> <span data-ttu-id="946f4-121">Las opciones que establece en el cuadro de diálogo Configuración regional de Windows no afectan al tipo de orden de las consultas.</span><span class="sxs-lookup"><span data-stu-id="946f4-121">Options that you set in the Windows Regional Settings dialog box do not affect sort order for queries.</span></span> <span data-ttu-id="946f4-122">Sin embargo, en una consulta determinada puede solicitar que las filas se devuelvan en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="946f4-122">Within any particular query, however, you can request that rows be returned in a particular order.</span></span>  
  
## <a name="using-double-byte-characters"></a><span data-ttu-id="946f4-123">Utilizar caracteres de doble byte</span><span class="sxs-lookup"><span data-stu-id="946f4-123">Using Double-Byte Characters</span></span>  
 <span data-ttu-id="946f4-124">Puede especificar caracteres DBCS para literales y para nombres de objeto de base de datos tales como alias o nombres de vistas y tablas.</span><span class="sxs-lookup"><span data-stu-id="946f4-124">You can enter DBCS characters for literals and for database object names such as table and view names or aliases.</span></span> <span data-ttu-id="946f4-125">También puede utilizar caracteres DBCS para nombres de parámetros y caracteres marcadores de parámetros.</span><span class="sxs-lookup"><span data-stu-id="946f4-125">You can also use DBCS characters for parameter names and parameter marker characters.</span></span> <span data-ttu-id="946f4-126">Sin embargo, no puede utilizar caracteres DBCS en elementos de lenguaje SQL tales como nombres de funciones o palabras clave SQL.</span><span class="sxs-lookup"><span data-stu-id="946f4-126">However, you cannot use DBCS characters in SQL language elements such as function names or SQL keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="946f4-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="946f4-127">See Also</span></span>  
 [<span data-ttu-id="946f4-128">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="946f4-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
