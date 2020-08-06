---
title: Reglas para especificar valores de búsqueda (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- time [SQL Server], searches
- date searches
- dates [SQL Server], searches
- embedding apostrophes [SQL Server]
- logical value searches [SQL Server]
- case-sensitive search matches
- search criteria [SQL Server], rules
- text value searches [SQL Server]
- numeric value searches [SQL Server]
ms.assetid: 3c8134b7-83f4-41b4-99c8-e3949a685ff5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 907bcac93863bc5660993e910b37e25e25a129b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663264"
---
# <a name="rules-for-entering-search-values-visual-database-tools"></a><span data-ttu-id="b0875-102">Reglas para especificar valores de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b0875-102">Rules for Entering Search Values (Visual Database Tools)</span></span>
  <span data-ttu-id="b0875-103">En este tema se tratan las convenciones que se deben utilizar para especificar los siguientes tipos de valores literales en una condición de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="b0875-103">This topic discusses the conventions you must use when entering the following types of literal values for a search condition:</span></span>  
  
-   <span data-ttu-id="b0875-104">Valores de texto</span><span class="sxs-lookup"><span data-stu-id="b0875-104">Text values</span></span>  
  
-   <span data-ttu-id="b0875-105">Valores numéricos</span><span class="sxs-lookup"><span data-stu-id="b0875-105">Numeric values</span></span>  
  
-   <span data-ttu-id="b0875-106">Fechas</span><span class="sxs-lookup"><span data-stu-id="b0875-106">Dates</span></span>  
  
-   <span data-ttu-id="b0875-107">Valores lógicos</span><span class="sxs-lookup"><span data-stu-id="b0875-107">Logical values</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0875-108">La información de este tema se deriva de las reglas para SQL 92 estándar.</span><span class="sxs-lookup"><span data-stu-id="b0875-108">The information in this topic is derived from the rules for standard SQL-92.</span></span> <span data-ttu-id="b0875-109">Sin embargo, cada base de datos puede implementar SQL a su forma.</span><span class="sxs-lookup"><span data-stu-id="b0875-109">However, each database can implement SQL in its own way.</span></span> <span data-ttu-id="b0875-110">Por tanto, estas instrucciones podrían no ser válidas en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="b0875-110">Therefore, the guidelines provided here might not apply in every case.</span></span> <span data-ttu-id="b0875-111">Si tiene dudas sobre cómo se escriben valores de búsqueda en una base de datos específica, consulte la documentación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b0875-111">If you have questions about how to enter search values for a particular database, refer to the documentation for the database that you are using.</span></span>  
  
## <a name="searching-on-text-values"></a><span data-ttu-id="b0875-112">Buscar valores de texto</span><span class="sxs-lookup"><span data-stu-id="b0875-112">Searching on Text Values</span></span>  
 <span data-ttu-id="b0875-113">Las siguientes directrices se aplican al escribir valores de texto en las condiciones de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="b0875-113">The following guidelines apply when you enter text values in search conditions:</span></span>  
  
-   <span data-ttu-id="b0875-114">**Comillas** Escriba los valores de texto entre comillas sencillas, como en el siguiente ejemplo de apellido:</span><span class="sxs-lookup"><span data-stu-id="b0875-114">**Quotation marks** Enclose text values in single quotation marks, as in this example for a last name:</span></span>  
  
    ```  
    'Smith'  
    ```  
  
     <span data-ttu-id="b0875-115">Cuando escriba una condición de búsqueda en el [panel Criterios](visual-database-tools.md), solo tiene que escribir el valor del texto; el Diseñador de consultas y vistas agregará automáticamente las comillas sencillas.</span><span class="sxs-lookup"><span data-stu-id="b0875-115">If you are entering a search condition in the [Criteria Pane](visual-database-tools.md), you can simply type the text value and the Query and View Designer will automatically put single quotation marks around it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b0875-116">En algunas bases de datos, los términos entre comillas sencillas se interpretan como valores literales, mientras que los términos entre comillas dobles se interpretan como objetos de base de datos, como las referencias a tablas o columnas.</span><span class="sxs-lookup"><span data-stu-id="b0875-116">In some databases, terms in single quotation marks are interpreted as literal values, whereas terms in double quotation marks are interpreted as database objects such as column or table references.</span></span> <span data-ttu-id="b0875-117">Por tanto, aunque el Diseñador de consultas y vistas puede aceptar términos entre comillas dobles, se podrían interpretar de una forma distinta de la esperada.</span><span class="sxs-lookup"><span data-stu-id="b0875-117">Therefore, even though the Query and View Designer can accept terms in double quotation marks, it might interpret them differently than you expect.</span></span>  
  
-   <span data-ttu-id="b0875-118">**Apóstrofos incrustados** Si los datos que busca contienen una comilla sencilla (un apóstrofo), puede escribir dos comillas sencillas para indicar que lo que desea indicar con la comilla sencilla es un valor literal y no un delimitador.</span><span class="sxs-lookup"><span data-stu-id="b0875-118">**Embedding apostrophes** If the data you are searching for contains a single quotation mark (an apostrophe), you can enter two single quotation marks to indicate that you mean the single quotation mark as a literal value and not a delimiter.</span></span> <span data-ttu-id="b0875-119">Por ejemplo, la siguiente condición busca el valor "Swann's Way":</span><span class="sxs-lookup"><span data-stu-id="b0875-119">For example, the following condition searches for the value "Swann's Way:"</span></span>  
  
    ```  
    ='Swann''s Way'  
    ```  
  
-   <span data-ttu-id="b0875-120">**Límites de longitud** No exceda la longitud máxima de la instrucción SQL en la base de datos al escribir cadenas largas.</span><span class="sxs-lookup"><span data-stu-id="b0875-120">**Length limits** Do not exceed the maximum length of the SQL statement for your database when entering long strings.</span></span>  
  
-   <span data-ttu-id="b0875-121">**Distinción entre mayúsculas y minúsculas** Debe tener en cuenta las reglas de distinción de mayúsculas y minúsculas de la base de datos que esté usando.</span><span class="sxs-lookup"><span data-stu-id="b0875-121">**Case sensitivity** Follow the case sensitivity rules for the database you are using.</span></span> <span data-ttu-id="b0875-122">Esta base de datos determinará si las búsquedas de texto distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b0875-122">The database you are using determines whether text searches are case sensitive.</span></span> <span data-ttu-id="b0875-123">Por ejemplo, algunas bases de datos interpretan que el operador "=" implica una coincidencia de mayúsculas y minúsculas, pero otras permiten coincidencias de cualquier combinación de caracteres en mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b0875-123">For example, some databases interpret the operator "=" to mean an exact case-sensitive match, but others will allow matches on any combination of uppercase and lowercase characters.</span></span>  
  
     <span data-ttu-id="b0875-124">Si no está seguro de que la base de datos distinga mayúsculas de minúsculas en las búsquedas, puede utilizar las funciones UPPER o LOWER en la condición de búsqueda para convertir las mayúsculas y minúsculas de los datos de búsqueda, como se indica en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0875-124">If you are unsure about whether the database uses a case-sensitive search, you can use the UPPER or LOWER functions in the search condition to convert the case of the search data, as illustrated in the following example:</span></span>  
  
    ```  
    WHERE UPPER(lname) = 'SMITH'  
    ```  
  
## <a name="searching-on-numeric-values"></a><span data-ttu-id="b0875-125">Buscar valores numéricos</span><span class="sxs-lookup"><span data-stu-id="b0875-125">Searching on Numeric Values</span></span>  
 <span data-ttu-id="b0875-126">Las siguientes directrices se aplican al escribir valores numéricos en las condiciones de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="b0875-126">The following guidelines apply when you enter numeric values in search conditions:</span></span>  
  
-   <span data-ttu-id="b0875-127">**Comillas** No debe escribir números entre comillas.</span><span class="sxs-lookup"><span data-stu-id="b0875-127">**Quotation marks** Do not enclose numbers in quotation marks.</span></span>  
  
-   <span data-ttu-id="b0875-128">**Caracteres no numéricos** No incluya caracteres no numéricos, salvo el separador decimal (el definido en el cuadro de diálogo **Configuración regional** del Panel de control de Windows) y el signo negativo (-).</span><span class="sxs-lookup"><span data-stu-id="b0875-128">**Non-numeric characters** Do not include non-numeric characters except the decimal separator (as defined in the **Regional Settings** dialog box of Windows Control Panel) and negative sign (-).</span></span> <span data-ttu-id="b0875-129">No incluya símbolos de agrupación de dígitos (como el punto entre los millares) ni símbolos de moneda.</span><span class="sxs-lookup"><span data-stu-id="b0875-129">Do not include digit grouping symbols (such as a comma between thousands) or currency symbols.</span></span>  
  
-   <span data-ttu-id="b0875-130">**Separadores decimales** Si escribe números enteros, puede incluir un separador decimal, independientemente de si el valor que busca es un número entero o real.</span><span class="sxs-lookup"><span data-stu-id="b0875-130">**Decimal marks** If you are entering whole numbers, you can include a decimal mark, whether the value you are searching for is an integer or a real number.</span></span>  
  
-   <span data-ttu-id="b0875-131">**Notación científica** Puede utilizar la notación científica para escribir números muy grandes o muy pequeños, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0875-131">**Scientific notation** You can enter very large or very small numbers using scientific notation, as in this example:</span></span>  
  
    ```  
    > 1.23456e-9  
    ```  
  
## <a name="searching-on-dates"></a><span data-ttu-id="b0875-132">Buscar fechas</span><span class="sxs-lookup"><span data-stu-id="b0875-132">Searching on Dates</span></span>  
 <span data-ttu-id="b0875-133">El formato empleado para escribir fechas dependerá de la base de datos utilizada y del panel del Diseñador de consultas y vistas en el que escriba la fecha.</span><span class="sxs-lookup"><span data-stu-id="b0875-133">The format you use to enter dates depends on the database you are using and in what pane of the Query and View Designer you are entering the date.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b0875-134">Si no sabe qué formato utiliza el origen de datos, escriba una fecha en la columna Filtro del panel Criterios en cualquier formato.</span><span class="sxs-lookup"><span data-stu-id="b0875-134">If you don't know which format your data source uses, type a date into the filter column of the Criteria pane in any format familiar to you.</span></span> <span data-ttu-id="b0875-135">El diseñador convertirá la mayoría de estas entradas al formato adecuado.</span><span class="sxs-lookup"><span data-stu-id="b0875-135">The designer will convert most of such entries into the appropriate format.</span></span>  
  
 <span data-ttu-id="b0875-136">El Diseñador de consultas y vistas permite trabajar con los siguientes formatos de fecha:</span><span class="sxs-lookup"><span data-stu-id="b0875-136">The Query and View Designer can work with the following date formats:</span></span>  
  
-   <span data-ttu-id="b0875-137">**Específico de la configuración regional** Formato especificado para las fechas en el cuadro de diálogo **Propiedades de la Configuración regional de Windows** .</span><span class="sxs-lookup"><span data-stu-id="b0875-137">**Locale-specific** The format specified for dates in the **Windows Regional Settings Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="b0875-138">**Específico de la base de datos** Cualquier formato válido para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b0875-138">**Database-specific** Any format understood by the database.</span></span>  
  
-   <span data-ttu-id="b0875-139">**Fecha ANSI estándar** Formato que utiliza llaves, el marcador 'd' para designar la fecha y una cadena de fecha, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0875-139">**ANSI standard date** A format that uses braces, the marker 'd' to designate the date, and a date string, as in the following example:</span></span>  
  
    ```  
    { d '1990-12-31' }  
    ```  
  
-   <span data-ttu-id="b0875-140">**Fecha y hora ANSI estándar** Similar a la fecha ANSI estándar, pero utiliza 'ts' en lugar de 'd' y agrega horas, minutos y segundos a la fecha (con un reloj de 24 horas), como en el siguiente ejemplo del 31 de diciembre de 1990:</span><span class="sxs-lookup"><span data-stu-id="b0875-140">**ANSI standard datetime** Similar to ANSI-standard date, but uses 'ts' instead of 'd' and adds hours, minutes, and seconds to the date (using a 24-hour clock), as in this example for December 31, 1990:</span></span>  
  
    ```  
    { ts '1990-12-31 00:00:00' }  
    ```  
  
     <span data-ttu-id="b0875-141">En general, las bases de datos que representan las fechas mediante un tipo de datos de fecha real utilizan el formato de fecha estándar ANSI.</span><span class="sxs-lookup"><span data-stu-id="b0875-141">In general, the ANSI standard date format is used with databases that represent dates using a true date data type.</span></span> <span data-ttu-id="b0875-142">En cambio, las bases de datos que admiten un tipo de datos datetime utilizan el formato de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="b0875-142">In contrast, the datetime format is used with databases that support a datetime data type.</span></span>  
  
 <span data-ttu-id="b0875-143">En la tabla siguiente se resumen los formatos de fecha que se pueden utilizar en los distintos paneles del Diseñador de consultas y vistas.</span><span class="sxs-lookup"><span data-stu-id="b0875-143">The following table summarizes the date format that you can use in different panes of the Query and View Designer.</span></span>  
  
|<span data-ttu-id="b0875-144">**Panel**</span><span class="sxs-lookup"><span data-stu-id="b0875-144">**Pane**</span></span>|<span data-ttu-id="b0875-145">**Formato de fecha**</span><span class="sxs-lookup"><span data-stu-id="b0875-145">**Date format**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="b0875-146">Criterios</span><span class="sxs-lookup"><span data-stu-id="b0875-146">Criteria</span></span>|<span data-ttu-id="b0875-147">Específico de la configuración regional Específico de la base de datos Estándar ANSI</span><span class="sxs-lookup"><span data-stu-id="b0875-147">Locale-specific Database-specific ANSI standard</span></span><br /><br /> <span data-ttu-id="b0875-148">Las fechas escritas en el [panel Criterios](visual-database-tools.md) se convierten a un formato compatible con la base de datos en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="b0875-148">Dates entered in the [Criteria Pane](visual-database-tools.md) are converted to a database-compatible format in the SQL pane.</span></span>|  
|<span data-ttu-id="b0875-149">SQL</span><span class="sxs-lookup"><span data-stu-id="b0875-149">SQL</span></span>|<span data-ttu-id="b0875-150">Específico de la base de datos Estándar ANSI</span><span class="sxs-lookup"><span data-stu-id="b0875-150">Database-specific ANSI standard</span></span>|  
|<span data-ttu-id="b0875-151">Results</span><span class="sxs-lookup"><span data-stu-id="b0875-151">Results</span></span>|<span data-ttu-id="b0875-152">Específico de la configuración regional</span><span class="sxs-lookup"><span data-stu-id="b0875-152">Locale-specific</span></span>|  
  
## <a name="searching-on-logical-values"></a><span data-ttu-id="b0875-153">Buscar valores lógicos</span><span class="sxs-lookup"><span data-stu-id="b0875-153">Searching on Logical Values</span></span>  
 <span data-ttu-id="b0875-154">El formato de los datos lógicos varía de una base de datos a otra.</span><span class="sxs-lookup"><span data-stu-id="b0875-154">The format of logical data varies from database to database.</span></span> <span data-ttu-id="b0875-155">Los valores False suelen almacenarse como cero (0).</span><span class="sxs-lookup"><span data-stu-id="b0875-155">Very frequently, a value of False is stored as zero (0).</span></span> <span data-ttu-id="b0875-156">Un valor True se suele almacenar como 1 y, de vez en cuando, como -1.</span><span class="sxs-lookup"><span data-stu-id="b0875-156">A value of True is most frequently stored as 1 and occasionally as -1.</span></span> <span data-ttu-id="b0875-157">Las siguientes directrices se aplican al escribir valores lógicos en las condiciones de búsqueda:</span><span class="sxs-lookup"><span data-stu-id="b0875-157">The following guidelines apply when you enter logical values in search conditions:</span></span>  
  
-   <span data-ttu-id="b0875-158">Para buscar un valor False, utilice un cero, como se indica en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0875-158">To search for a value of False, use a zero, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 0  
    ```  
  
-   <span data-ttu-id="b0875-159">Si no está seguro del formato que debe utilizar al buscar un valor True, pruebe a utilizar 1, como se indica en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0875-159">If you are not sure what format to use when searching for a True value, try using 1, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 1  
    ```  
  
-   <span data-ttu-id="b0875-160">Como alternativa, puede ampliar el ámbito de la búsqueda a cualquier valor distinto de cero, como se indica en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0875-160">Alternatively, you can broaden the scope of the search by searching for any non-zero value, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract <> 0  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b0875-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0875-161">See Also</span></span>  
 [<span data-ttu-id="b0875-162">Especificar criterios de búsqueda (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="b0875-162">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
